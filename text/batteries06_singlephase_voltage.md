---
title: 4.6 Voltage of a Single-Phase Battery Electrode
numbering:
  enumerator: 4.6.%s
---

Using the expressions for the chemical potentials in the negative ([Equation %s](#eq:mu_li_metal)) and positive ([Equation %s](#eq:mu_li_lattice_gas)) electrodes, we substitute them into [Equation %s](#eq:voltage_from_mu) for the voltage:


$$
V = \frac{1}{\mathscr{F}} \left(\mu_{\text{Li}} - \mu_{\text{“Li”}}\right)
= \frac{1}{\mathscr{F}} \left[ \mu^0_{\text{Li metal}} - \mu^0_{\text{“Li”}} - RT \ln \frac{X}{1-X} \right]
$$

```{figure} ../images/batteries/singlephase_gibbs_mu_voltage.png
:label: fig:singlephase_voltage
:align: center
:width: 500px

Example single-phase electrode voltage predicted by a lattice-gas model. The logarithmic term from configurational entropy causes the voltage to diverge as $X \to 0$.
```


An example voltage plot is shown in [](#fig:singlephase_voltage). Note that because of the logarithmic term (due to configurational entropy), the voltage diverges (tends to infinity) as $X \to 0$. In practical terms, it is impossible to completely remove all Li from the positive electrode (i.e. to charge a battery to 100%) because doing so would require an infinite amount of energy.
