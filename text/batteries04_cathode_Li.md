---
title: 4.4 Chemical Potential of "Li" (Positive Electrode)
numbering:
  enumerator: 4.4.%s
---

First, we discuss the chemical potential of “Li”, or Li ions in the positive electrode. The “reaction” in Li-ion batteries consists of inserting Li atoms into a host lattice, in this case $\text{CoO}_2$. Therefore we want to investigate the Gibbs free energy per lattice site (specific Gibbs free energy, $\bar{G}$). This will depend on the composition $X$ of Li in $\text{Li}_X\text{CoO}_2$, where $X$ is the fraction of lithium sites that are occupied. The $X$ is related, but not exactly equal, to the state of charge of the battery. For positive electrodes, an $X$ of 1 usually indicates a fully discharged battery. That being said, many battery electrodes cannot be cycled stably from $X=0$ to $X=1$. Thus in practice, a state of $X=0.5$ may indicate that a battery is fully charged.

At constant temperature and pressure the chemical potential is defined as

```{math}
\mu = \left( \frac{\partial G}{\partial N} \right)_{T, P}
```

where $N$ is the number of Li atoms. Writing the composition as $X = N/J$, with $J$ the number of "lattice sites" within a $\text{CoO}_2$ host lattice, we have

```{math}
\mu = \frac{\partial G}{\partial N}\times \left(\frac{1/J}{1/J}\right) = \frac{\partial \bar{G}}{\partial X}
```

Then, in integral form,

$$
\bar{G} = \mu X 
$$

For a completely filled site ($X=1$) the specific Gibbs free energy per filled lattice site should equal the chemical potential of a purely lithiated (LCO) lattice, $\mu^0_{\text{LCO}}$, while for an empty site ($X=0$) it equals the chemical potential of the empty host, $\mu^0_{\text{CO}}$. A simple weighted-average model gives

$$
\bar{G}_{\text{“Li”}} = \mu^0_{\text{LCO}}\,X + \mu^0_{\text{CO}}\,(1-X) 
$$

or, rearranged,

$$
\bar{G}_{\text{“Li”}} = (\mu^0_{\text{LCO}} - \mu^0_{\text{CO}})X + \mu^0_{\text{CO}} 
$$

However, because $G = H - TS$ and there is a configurational entropy associated with mixing Li in the host lattice, the dependence on $X$ is modified. In fact, one writes

$$
\bar{G}_{\text{“Li”}} = \bar{G}_{\text{unmixed}} + \Delta \bar{G}_{\text{mix}} 
$$

with

$$
\Delta \bar{G}_{\text{mix}} = -T \Delta \bar{S}_{\text{mix}} 
$$

For a lattice gas the entropy of mixing is given by

$$
\Delta \bar{S}_{\text{mix}} = -R \{ X \ln X + (1-X) \ln (1-X) \}
$$

Thus, the full expression for the specific Gibbs free energy in the positive electrode becomes

$$
\bar{G}_{\text{“Li”}} = (\mu^0_{\text{LCO}} - \mu^0_{\text{CO}})X + \mu^0_{\text{CO}} + RT \{ X \ln X + (1-X) \ln (1-X) \} 
$$

```{figure} ../images/batteries/lattice_mixing_gibbs.png
:label: fig:positive_electrode_lattice_mixing
:align: center
:width: 500px

Specific Gibbs free energy $\bar{G}_{\text{“Li”}}$ for Li insertion in an ideal lattice-gas model, and the corresponding chemical potential $\mu_{\text{“Li”}}=\partial \bar{G}_{\text{“Li”}}/\partial X$.
```

Graphically (see [](#fig:positive_electrode_lattice_mixing)), the instantaneous chemical potential of Li in the positive electrode is the derivative of $\bar{G}_{\text{“Li”}}$ with respect to $X$, yielding

$$
\mu_{\text{“Li”}} = \mu^0_{\text{“Li”}} + RT \ln \frac{X}{1-X} 
\label{eq:mu_li_lattice_gas}
$$

where

$$
\mu^0_{\text{“Li”}} = \mu^0_{\text{LCO}} - \mu^0_{\text{CO}}
$$