---
title: Voltage of a Battery
numbering:
  enumerator: 4.3.%s
---

A battery is thermodynamically similar to a fuel cell with closed chambers. In a fuel cell, the chambers contain water and oxygen/hydrogen gases, whereas in a Li‑ion battery these gases are replaced with lithium. (Lithium does not easily exist as a gas at ambient temperature and pressure; instead it is stored as a solid or by intercalation into host compounds such as $\text{CoO}_2$, $\text{FePO}_4$, or graphite.)

In the fuel cell the mobile ion is $\text{O}^{2-}$ (which, along with an electron and $\text{O}_2$, forms $\text{H}_2\text{O}$). In a Li‑ion battery the mobile ion is $\text{Li}^+$, which reacts with an electron and a metal oxide (e.g. $\text{CoO}_2$) to form $\text{LiCoO}_2$. This battery chemistry is now standard for portable electronics.

```{figure} ../images/batteries/schematic.png
:label: fig:battery_schematic
:align: center
:width: 500px

Schematic of a Li-ion battery under discharge.
```

[](#fig:battery_schematic) schematically shows a Li‑ion battery with different host materials on the two sides (implying different chemical potentials for $\text{Li}$). Let’s calculate the battery voltage using the same approach as in Module 2. In equilibrium, the two half‑reactions (as well as the mobile $\text{Li}^+$ ion) must be balanced:

$$
\text{Li}^+_{\text{N}} + e^-_{\text{N}} \; \rightleftharpoons \; \text{Li}
$$

$$
\text{LiCoO}_2 - \text{CoO}_2  \rightleftharpoons \;  \text{Li}^+_{\text{P}} + e^-_{\text{P}}
$$

$$
\text{Li}^+_{\text{N}} \; \rightleftharpoons \; \text{Li}^+_{\text{P}}
$$

Since electrons cannot equilibrate between the two electrodes without shorting the battery, the net reaction is

$$
\bigl( e^-_{\text{N}} - e^-_{\text{P}} \bigr) \; \longleftrightarrow \; \text{Li} - \left( \text{LiCoO}_2 - \text{CoO}_2 \right)
$$

Applying the equilibrium condition (similar to [Equation %s](#eq:fuel_cell_eq_electron_diff)) gives:

$$
\mu_{e^-_{\text{N}}} - \mu_{e^-_{\text{P}}} = \Bigl( \mu_{\text{Li}} - \mu_{\text{LiCoO}_2-\text{CoO}_2} \Bigr)
$$

Here, $\mu_{\text{Li}}$ is the chemical potential of $\text{Li}$ in metallic form and $\mu_{\text{LiCoO}_2-\text{CoO}_2}$ is the chemical potential of $\text{Li}$ when inserted in the host. For simplicity, we denote the $\text{Li}$ in $\text{LiCoO}_2$ as “Li” and write $\mu_{\text{“Li”}} = \mu_{\text{LiCoO}_2-\text{CoO}_2}$.

Recall that the battery voltage is given by the difference in chemical potential between the negative and positive electrodes:

$$
V = \frac{1}{\mathscr{F}} \Bigl( \mu_{e^-_{\text{N}}} - \mu_{e^-_{\text{P}}} \Bigr)
= \frac{1}{\mathscr{F}} \Bigl( \mu_{\text{Li}} - \mu_{\text{“Li”}} \Bigr)
$$

A positive voltage implies that the chemical potential of $\text{Li}$ is higher in the negative electrode (metallic $\text{Li}$) than in the positive electrode (where $\text{Li}$ reacts with $\text{CoO}_2$ to form $\text{LiCoO}_2$). To discharge a battery, $\text{Li}$ moves from a region of higher potential (negative electrode) to one of lower potential (positive electrode), producing electrical work.
