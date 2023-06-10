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

#### Acknowledgements

<style>
    .image-wrapper{
        display: inline-block;
        text-align: center;
    }
</style>

<div class="image-wrapper">
        <img width="200" src="https://images.squarespace-cdn.com/content/v1/57a45f33c534a5832b558f0f/1511267602299-O2HBB5C9AF0TM8WDFNK1/mikael_lund_500x500.png?format=750w">
        <figcaption><font size="5">Mikael Lund</font></figcaption>
</div>
<div class="image-wrapper">
        <img width="200" src="https://janheyda.files.wordpress.com/2014/02/heyda-photo.jpg">
        <figcaption><font size="5">Jan Heyda</font></figcaption>
</div>
<div class="image-wrapper"> 
        <img width="200" src="https://pubs.rsc.org/image/article/2017/CP/c7cp02132a/c7cp02132a-p2_hi-res.gif">
        <figcaption><font size="5">Nobuyuki Matubayasi</font></figcaption>
</div>

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
<font size="3"> [Hervø-Hansen et al. Phys. Chem. Chem. Phys. 2022](https://doi.org/10.1039/D1CP04129K) </font>

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
<font size="3"> [Hervø-Hansen et al. Phys. Chem. Chem. Phys. 2022](https://doi.org/10.1039/D1CP04129K) </font>

---

<section>
  <h4>Interaction-component analysis</h4>
  \[\begin{aligned}
  \mu^{\mathrm{ex}} = &amp; \int_{-\infty}^{\epsilon_{\mathrm{max}}} \varepsilon \rho_1(\varepsilon) \  \mathrm{d}\varepsilon + \int_{-\infty}^{\epsilon_{\mathrm{max}}} \mathcal{F}(\rho_0, \rho_1;\varepsilon) \  \mathrm{d}\varepsilon \\
  &amp; +\int_{\epsilon_{\mathrm{max}}}^{\infty} \mathcal{F}(\rho_0, \rho_1;\varepsilon) \  \mathrm{d}\varepsilon
  \end{aligned} \]
</section>

---

#### Interaction-component analysis: The interaction component

{{< figure src="InteractionComponent.png" >}}
<font size="3"> [Hervø-Hansen et al. Phys. Chem. Chem. Phys. 2022](https://doi.org/10.1039/D1CP04129K) </font>

---

#### Cation contribution: Binding

{{< figure src="CationBinding.png" >}}
<font size="3"> [Hervø-Hansen et al. Phys. Chem. Chem. Phys. 2022](https://doi.org/10.1039/D1CP04129K) </font>

---

#### Interaction-component analysis: The excluded-volume component

{{< figure src="ExcludedVolumeComponent.png" >}}
<font size="3"> [Hervø-Hansen et al. Phys. Chem. Chem. Phys. 2022](https://doi.org/10.1039/D1CP04129K) </font>

---

#### Interaction-component analysis: The excluded-volume ion component

{{< figure src="ExcludedVolumeIonComponent.png" >}}
<font size="3"> [Hervø-Hansen et al. Phys. Chem. Chem. Phys. 2022](https://doi.org/10.1039/D1CP04129K) </font>

---

#### Interaction-component analysis: The excluded-volume water component

{{< figure src="ExcludedVolumeWaterComponent.png" >}}
<font size="3"> [Hervø-Hansen et al. Phys. Chem. Chem. Phys. 2022](https://doi.org/10.1039/D1CP04129K) </font>

---

#### Conclusions
1. Free-energy calculations reveal can be highly different in their perturbation mechanism.
2. Effects not found at full coupling between the solute and solvent correlates with the Setschenow coefficient.


