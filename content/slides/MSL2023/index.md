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
#### Hofmeister series

{{% fragment %}} Monovalent anion series: F⁻ > Cl⁻ > I⁻ {{% /fragment %}}

{{% fragment %}} Monovalent cation series: Na⁺ > K⁺ > Cs⁺ {{% /fragment %}}

---

{{< slide background-image="Franz_hofmeister.jpg" >}}
#### Hofmeister series

Nomenclature:

{{% fragment %}} *Salting-in*: Increased solubility in aqueous phase, ΔG<sub>sol</sub>decreases, kₛ decreases. {{% /fragment %}}

{{% fragment %}} *Salting-out*: Decreasing solubility in aqueous phase, ΔG<sub>sol</sub> increases, kₛ increases. {{% /fragment %}}

---

#### Thermodynamic framework for solvation thermodynamics



---

## Controls

- Next: `Right Arrow` or `Space`
- Previous: `Left Arrow`
- Start: `Home`
- Finish: `End`
- Overview: `Esc`
- Speaker notes: `S`
- Fullscreen: `F`
- Zoom: `Alt + Click`
- [PDF Export](https://revealjs.com/pdf-export/)

---

## Code Highlighting

Inline code: `variable`

Code block:

```python
porridge = "blueberry"
if porridge == "blueberry":
    print("Eating...")
```

---

## Math

In-line math: $x + y = z$

Block math:

$$
f\left( x \right) = \;\frac{{2\left( {x + 4} \right)\left( {x - 4} \right)}}{{\left( {x + 4} \right)\left( {x + 1} \right)}}
$$

---

## Fragments

Make content appear incrementally

```
{{%/* fragment */%}} One {{%/* /fragment */%}}
{{%/* fragment */%}} **Two** {{%/* /fragment */%}}
{{%/* fragment */%}} Three {{%/* /fragment */%}}
```

Press `Space` to play!

{{% fragment %}} One {{% /fragment %}}
{{% fragment %}} **Two** {{% /fragment %}}
{{% fragment %}} Three {{% /fragment %}}

---

A fragment can accept two optional parameters:

- `class`: use a custom style (requires definition in custom CSS)
- `weight`: sets the order in which a fragment appears

---

## Speaker Notes

Add speaker notes to your presentation

```markdown
{{%/* speaker_note */%}}

- Only the speaker can read these notes
- Press `S` key to view
  {{%/* /speaker_note */%}}
```

Press the `S` key to view the speaker notes!

{{< speaker_note >}}

- Only the speaker can read these notes
- Press `S` key to view
  {{< /speaker_note >}}

---

## Themes

- black: Black background, white text, blue links (default)
- white: White background, black text, blue links
- league: Gray background, white text, blue links
- beige: Beige background, dark text, brown links
- sky: Blue background, thin dark text, blue links

---

- night: Black background, thick white text, orange links
- serif: Cappuccino background, gray text, brown links
- simple: White background, black text, blue links
- solarized: Cream-colored background, dark green text, blue links

---

{{< slide background-image="/media/boards.jpg" >}}

## Custom Slide

Customize the slide style and background

```markdown
{{</* slide background-image="/media/boards.jpg" */>}}
{{</* slide background-color="#0000FF" */>}}
{{</* slide class="my-style" */>}}
```

---

## Custom CSS Example

Let's make headers navy colored.

Create `assets/css/reveal_custom.css` with:

```css
.reveal section h1,
.reveal section h2,
.reveal section h3 {
  color: navy;
}
```

---

# Questions?

[Ask](https://github.com/wowchemy/wowchemy-hugo-modules/discussions)

[Documentation](https://wowchemy.com/docs/managing-content/#create-slides)
