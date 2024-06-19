---
title: The 17th Mini-Symposium on Liquids 2024

event: The 17th Mini-Symposium on Liquids 2024
event_url: https://kenkoga.wixsite.com/liquid 

location: Kyushu University
address:
  street: 744 Motooka
  city: Fukuoka
  region: Nishi Ward
  postcode: '819-0395'
  country: Japan

summary: 'Presenting the poster: Advancing Chemical Potential Calculations of Large Polymers: *Introducing the Effect of Conformational Change*'
abstract: >-
    Soft matter systems, such as polymers and globular proteins, undergo structural alterations when subjected to thermal, mechanical, or chemical stress.
    Under native conditions, proteins typically form compact, folded structures, but these can unfold and extend under stress.
    Understanding the thermodynamics of these transformations requires knowledge of the excess chemical potential, $\Delta \mu^{\mathrm{ex}}$.
    Masutani and Matsubayasi developed a methodology for calculating changes in the excess chemical potential due to alterations in the liquid composition of various molecular states.
    However, this method is a linear approximation and does not account for structural transitions induced by changes in solvent composition, which appears as higher-order terms and can be important when the solvent composition is changed much.
    In this work, we present a computational approach to determine the change in the excess chemical potential of a flexible solute molecule when the composition of a mixed-solvent system varies isothermally.
    One of the key results in the formulation of our new methdology is the derivation of the following exact inequality:
    $$
    \int P_B(\psi) \Delta\nu^{\mathrm{solv}}(\psi) \mathrm{d}\psi \le \Delta \mu^{\mathrm{ex}} \le \int P_A(\psi)\Delta \nu^{\mathrm{solv}}(\psi) \mathrm{d}\psi
    $$
    Here, $P_A(\psi) and $P_B(\psi)$ represent the probabilities of observing configuration $\psi$ of the solute in solvent conditions $A$ and $B$, respectively.
    $\Delta\nu^{\mathrm{solv}}(\psi)$ denotes the change in solvation free energy of the solute in a given configuration $\psi$ from solvent condition $A$ to $B$.
    This inequality establishes upper and lower bounds for the change in solvation free energy, depending on the solvent conditions under which the structural ensemble was generated.
    Our second key result is the formulation of an approach parallel to the Bennett Acceptance Ratio (BAR) method to obtain $\Delta \mu^{\mathrm{ex}}$ from the statistics of $\Delta \nu^{\mathrm{solv}}(\psi)$.
    The configurations of the solute in solvent conditions $A$ and $B$ can be prepared using any method that generates Boltzmann-distributed samples, with our choice being molecular dynamics (MD) simulations.
    Similarly, the change in solvation free energy of a given structure ($\Delta\nu^{\mathrm{solv}}(\psi)$) can be obtained using methods such as RISM-type integral-equation theories, implicit-solvent models, or the method of energy representation, the latter being utilized in this work.
    To test and apply our newly developed methdology, we invesgated the change in solvation of a PEG-36-mer in neat water, urea, and NaCl solutions.

# Talk start and end times.
#   End time can optionally be hidden by prefixing the line with `#`.
date: '2024-06-06T09:30:00Z'
date_end: '2024-06-07T13:00:00Z'
all_day: false

# Schedule page publish date (NOT talk date).
publishDate: '2024-05-14'

authors: []
tags: []

# Is this a featured talk? (true/false)
featured: True

image:
  caption: 'Image credit: [**Unsplash**](https://unsplash.com/photos/bzdhc5b3Bxs)'
  focal_point: Right

url_code: ''
url_pdf: ''
url_slides: ''
url_video: ''

# Markdown Slides (optional).
#   Associate this talk with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects = []:
---

