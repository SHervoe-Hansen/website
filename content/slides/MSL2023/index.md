---
title: Anion-Cation Contrast in Solute Solvation
summary: Talk given at MSL2023
authors: [admin]
tags: [Presentation]
categories: []
date: '2020-06-11T09:00:00Z'
slides:
  # Choose a theme from https://github.com/hakimel/reveal.js#theming
  theme: black
  # Choose a code highlighting style (if highlighting enabled in `params.toml`)
  #   Light style: github. Dark style: dracula (default).
  highlight_style: dracula
---

{{< slide background-image="glowing_water.jpg" >}}
# <span style="color:silver">Anion-Cation Contrast in Solute Solvation</span>
<span style="color:silver">Stefan Hervø-Hansen | June 11, 2023 | MSL2023</span>

---

#### Drug and materials discovery is a complex, expensive, and time-consuming

{{< figure src="drug_expense.jpg" >}} 
<font size="3"> [Scannell et al. Nat Rev Drug Discov. 2012](https://doi.org/10.1038/nrd3681) </font>

---

#### Solvation free energies to understand underlying physics of liquid structure

{{< figure src="charge_asymmetry.png" >}}
<font size="3"> [Mobley et al. J Phys Chem B. 2008](https://doi.org/10.1021/jp709958f) </font>

---

{{< slide background-image="Franz_hofmeister.jpg" >}}

---

#### Hofmeister series

{{% fragment %}} Monovalent anion series: F⁻ > Cl⁻ > I⁻ {{% /fragment %}}
<br><br>
{{% fragment %}} Monovalent cation series: Na⁺ > K⁺ > Cs⁺ {{% /fragment %}}

---

#### Nomenclature:

{{% fragment %}} *Salting-in*: Increased solubility in aqueous phase, ΔG<sub>sol</sub> decreases, kₛ decreases. {{% /fragment %}}
<br><br>
{{% fragment %}} *Salting-out*: Decreasing solubility in aqueous phase, ΔG<sub>sol</sub> increases, kₛ increases. {{% /fragment %}}

---

#### Thermodynamic framework for solvation thermodynamics
<font size="5">
$$
\beta \mu^{\mathrm{ex}} = \mu_{\mathrm{r}} + \langle \Delta U_{\mathrm{a}} \rangle_{\lambda=1} + RT \ln \left\langle e^{\beta \left( \langle U_{\mathrm{a}} \rangle - U_{\mathrm{a}} \right)} \right\rangle_{\lambda=1}
$$

{{% fragment %}}
Energy-Representation Theory of Solvation allows a straightforward route into such an energetic decomposition:
$$
\Delta G_{\mathrm{sol}} = \sum_{\mathrm{species},\ i} \Delta G_{\mathrm{sol}, i}
$$
$$
\Delta G_{\mathrm{sol},i}=\int \rho(\epsilon) \epsilon \ \mathrm{d}\epsilon - \int \mathcal{F}(\epsilon) \ \mathrm{d}\epsilon
$$
</font>
{{% /fragment %}}

<font size="3"> [Widom, J Chem Phys. 1963](https://doi.org/10.1063/1.1734110); [van der Vegt & Nayar, J Phys Chem B. 2017](https://doi.org/10.1021/acs.jpcb.7b06453); [Matubayasi, BCSJ. 2019](https://doi.org/10.1246/bcsj.20190246) </font>

---

#### Setschenow coefficients
<font size="5">
$$
\ln\left(\frac{S(c_s)}{S(0)}\right) = -k_s c_s = -\frac{\Delta \Delta G_{\mathrm{sol}}}{RT}
$$
$$
\Delta \Delta G_{\mathrm{sol}}=\Delta G_{\mathrm{sol}}(c_s)-\Delta G_{\mathrm{sol}}(0)
$$
</font>

{{< figure src="SetschenowTotal.png" >}}

---

#### Anion-cation contrast
<font size="5">
$$
\Delta G_{\mathrm{sol}} = \cancel{\Delta G_{\mathrm{self}}} + \Delta G_{\mathrm{anion}} + \Delta G_{\mathrm{cation}} + \Delta G_{\mathrm{water}}
$$
$$
k_s = \frac{1}{RT} \left( \frac{\partial \Delta G_{\mathrm{anion}}}{\partial c_{s}} + \frac{\partial \Delta G_{\mathrm{cation}}}{\partial c_{s}} + \frac{\partial \Delta G_{\mathrm{water}}}{\partial c_{s}} \right)
$$
</font>

{{< figure src="SetschenowSpecies.png" >}}

---

#### Interaction-component analysis


---

#### Interaction-component analysis: The interaction component

{{< figure src="InteractionComponent.png" >}}

---

#### Cation contribution: Binding

{{< figure src="CationBinding.png" >}}

---

#### Interaction-component analysis: The excluded-volume component

{{< figure src="ExcludedVolumeComponent.png" >}}

---

#### Interaction-component analysis: The excluded-volume ion component

{{< figure src="ExcludedVolumeIonComponent.png" >}}

---

#### Interaction-component analysis: The excluded-volume water component

{{< figure src="ExcludedVolumeWaterComponent.png" >}}

---

#### The chaotropic & kosmotropic properties of salt

Visit my poster and let us disscuss:
1. Do the properties exist?
2. Are the properties important?
3. By which methods are they measurable

---

# Questions?

[Ask](https://github.com/wowchemy/wowchemy-hugo-modules/discussions)

[Documentation](https://wowchemy.com/docs/managing-content/#create-slides)
