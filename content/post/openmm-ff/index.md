---
title: OpenMM Tricks and Guides
subtitle: Easy development of OpenMM formatted force fields.

# Summary for listings and search engines
summary: Easy development of OpenMM formatted force fields and conversion of AMBER & Gromacs formats to openMM. 

# Link this post with a project
projects: []

# Date published
date: '2020-07-12'

# Date updated
lastmod: '2022-07-12'

# Is this an unpublished draft?
draft: false

# Show this page in the Featured widget?
featured: true

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.
#image:
#  caption: 'Image credit: [**Reedsy**](https://reedsy.com)'
#  focal_point: ''
#  placement: 2
#  preview_only: false

authors:
  - admin

tags:
  - OpenMM
  - Molecular dynamics
  - Tips and tricks

categories:

---

## The OpenMM Force Field Format
OpenMM uses the Extensible Markup Language (XML) format to store force field parameters. One of the primary advantages is this offers an easy-to-read and edit force field format. As with all of OpenMM, the construction of force fields files is documented well in the [OpenMM User Guide](http://docs.openmm.org/latest/userguide/), however having myself now tried to write force fields for simple molecules like thiocyanate anion and polyethylene glycol of arbitrary length, I have to come to realize there are some tips and tricks to aid in the construction and validation of the force field.

## Include all Fourier terms within a single PeriodicTorsionForce
A dihedral angle is an angle between two intersecting planes. Within chemistry, it is the angle between two sets of three atoms having two atoms in common. Thus this energy is supposed to approximate the effect of bond order (like the restricted rotation around a double bond) and capture steric and electronic effects. A common way to express the difference in energy upon rotation of a dihedral angle is via a Fourier series. We can write the dihedral energy, $E(\omega)$ as
$$
E(\omega) = \sum_{n} \left(1+\cos\left(n \omega - \omega_0\right)\right).
$$
Here $\omega$ is the dihedral angle formed by the four particles in question, $\omega_0$ is the phase offset, $n$ is the periodicity, and $k$ is the force constant. Note in the equation that the Fourier series is a _sum_ of terms, and this way of thinking may help a lot when writing the dihedral energy terms in the OpenMM force field files.

In OpenMM, the tag that controls the addition of dihedral energy terms is _PeriodicTorsionForce_ as described in the [User Guide](http://docs.openmm.org/latest/userguide/application/05_creating_ffs.html#periodictorsionforce). However, one thing that was not clear to me was the rules allowed when writing the dihedral angle energy which had more than one term. In specific, my first attempt when creating a PEG force field was
```xml
<PeriodicTorsionForce>
  <Proper type1="peg-CE" type2="peg-CE" type3="peg-OE" type4="peg-CF"
          periodicity1="1" phase1="0" k1="2.38545"/>
  <Proper type1="peg-CE" type2="peg-CE" type3="peg-OE" type4="peg-CF"
          periodicity1="2" phase1="0" k1="1.21365"/>
  <Proper type1="peg-CE" type2="peg-CE" type3="peg-OE" type4="peg-CF"
          periodicity1="3" phase1="0" k3="1.79955"/>
</PeriodicTorsionForce>
```
In the above implementation, I thought it would be allowed to write the individual terms of the Fourier series using individual "Proper" tags. This approach turned out to be wrong. Only one of the three terms was read upon creating the system for the four atom types. If one reads the User Guide a bit closer, it states one can add multiple terms by the inclusion of multiple _periodicity_, _phase_, and _k_ with an increasing integer following the keyword. Thus the correct implementation of the dihedral energy term is
```xml
<PeriodicTorsionForce>
  <Proper type1="peg-CE" type2="peg-CE" type3="peg-OE" type4="peg-CF"
  	  periodicity1="1" phase1="0" k1="2.38545"
	  periodicity2="2" phase2="0" k2="1.21365"
	  periodicity3="3" phase3="0" k3="1.79955"/>
</PeriodicTorsionForce>
```

## Nonbonded Exceptions: Easy to Include and Equally Easy to Forget
While I praised OpenMM's User Guide for being well documented, it does come short in explaining how to construct nonbonded exceptions between species. To create exceptions one introduces the tag "NBFixPair" which alters the default entries in the Lennard-Jones table. An example of a force field using "NBFixPair" is outlined below
```xml
<ForceField>
  <LennardJonesForce lj14scale="0.5">
    <!--ammonium sulfate types-->
    <Atom type="ammonium-N" sigma="3.25000e-01" epsilon="7.11280e-01"/>
    <Atom type="ammonium-H" sigma="1.06908e-01" epsilon="6.56888e-02"/>
    <Atom type="sulfate-S" sigma="3.56359e-01" epsilon="1.04600e+00"/>
    <Atom type="sulfate-O" sigma="2.95992e-01" epsilon="8.78640e-01"/>
    <!--exceptions-->
    <NBFixPair type1="sulfate-O" type2="ammonium-N" sigma="3.50860e-1" epsilon="7.90543e-1"/>
    <NBFixPair type1="sulfate-O" type2="ammonium-H" sigma="2.27638e-1" epsilon="2.40243e-1"/>
  </LennardJonesForce>
</ForceField>
```
In this force field, the Lennard-Jones interactions between the atoms of ammonium and sulfate with the atoms of water are determined from the sigma and epsilon entries within the Atom section being a single atom property. Meanwhile, the interactions between the oxygen of sulfate and the atoms of ammonium are customized to a specific value for sigma and epsilon.

While this is a super easy way to include nonbonded exceptions, there is one major drawback. OpenMM version 7.7.0 only allows "NBFixPair" to be used in the section having the tag "LennardJonesForce" and not in the section with the tag "NonbondedForce". So what does one do when you have a system that possesses electrostatic interactions, Lennard-Jones interactions, and Lennard-Jones exceptions? One option is to include the two sections "NonbondedForce" and "LennardJonesForce", in which epsilon have been set to null in "NonbondedForce" and within "LennardJonesForce" all epsilon and sigma are written for the individual atoms alongside with the nonbonded exceptions as shown above. Be aware this approach does cause OpenMM to hang if one additionally plans on including long-range correction and utilizing multiple GPUs. This bug has been [addressed and fixed with the next release of OpenMM](https://github.com/openmm/openmm/pull/3668).

## Converting AMBER or Gromacs Files with Manual Tweaking Can Go a Long Way
If one does not have to start from scratch but already has a force field for some molecular species in either an AMBER or Gromacs format, it is possible to convert it to XML format. One can use the [ParmEd](https://github.com/ParmEd/ParmEd) python package, which provides easy solutions for converting between various force field formats. Let us say we have an Amber topology and a PDB file which have, for example, been prepared using Ambertools's _tleap_ one may convert the topology into OpenMM's force field format using the following code
```python
struc = pmd.load_file('Topology.top', xyz='Structure.pdb')
amber_pset = pmd.amber.parameters.ParameterSet.from_structure(struc)
omm_pset = pmd.openmm.parameters.OpenMMParameterSet.from_parameterset(amber_pset)
omm_pset.residues.update(pmd.modeller.ResidueTemplateContainer.from_structure(struc).to_library())
omm_pset.write("forcefield.xml")
```
A similar approach can be done for Gromacs file formats.

## Validating Your Custom OpenMM Force Field
Congratulations. You have now most likely constructed your own force field, but it does not yield the same energy for your XML formatted force field on a single configuration compared to if you used Amber or Gromacs formatted topology files. The reason as to why can be many, for example, there can be missing bonded interactions, parameters are not being read correctly, wrong input, and so on. In order to easily debug the terms of the Hamiltonian in OpenMM, we may utilize the function `XmlSerializer.serialize()` which provides an easy-to-read output of all the various terms which constitute the Hamiltonian. A minimal example can be found below
```python
from openmm import unit as u
from openmm import app
import openmm as mm

pdb = app.PDBFile('PEG_2.pdb')
forcefield = app.ForceField('peg.xml')
integrator = mm.LangevinMiddleIntegrator(298.15*u.kelvin, 1.0/u.picoseconds, 4.0*u.femtoseconds)
platform = mm.Platform.getPlatformByName('CPU')
system = forcefield.createSystem(pdb.topology, nonbondedMethod=app.PME, ewaldErrorTolerance=0.00001,
                                  nonbondedCutoff=0.01*u.nanometers,
                                 hydrogenMass=1.25*u.dalton, constraints=app.HBonds, rigidWater=True)
sim = app.Simulation(pdb.topology, system, integrator, platform)
sim.context.setPositions(pdb.positions)
force = sim.system.getForce(0)
print(mm.XmlSerializer.serialize(force))
```
The code would yield the following output
```
<?xml version="1.0" ?>
<Force forceGroup="0" name="HarmonicBondForce" type="HarmonicBondForce" usesPeriodic="0" version="2">
	<Bonds>
		<Bond d=".1415" k="267776" p1="0" p2="1"/>
		<Bond d=".1415" k="267776" p1="1" p2="2"/>
		<Bond d=".153" k="259408" p1="2" p2="8"/>
		<Bond d=".1415" k="267776" p1="8" p2="9"/>
		<Bond d=".1415" k="267776" p1="9" p2="10"/>
	</Bonds>
</Force>
```
From this example, we can see that with our forcefield implementation we have constructed harmonic bonds between all non-hydrogen atoms in a polyethylene glycol dimer. The addition of `constraints=app.HBonds` in `forcefield.createSystem()` causes the bonds involving hydrogen to disappear as expected.
