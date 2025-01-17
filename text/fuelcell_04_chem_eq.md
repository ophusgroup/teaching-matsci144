---
title: Chemical Equilibrium
numbering:
  enumerator: 2.4.%s
---

The Gibbs free energy allows us to define equilibrium conditions for a system at constant $T$ and $P$, which means three conditions need to be satisfied for a system to be at equilibrium:

1. There is no **net** flow of energy or matter *within* the system.

2. There is no **net** exchange of energy or matter with the outside world.

3. There are no unbalanced driving forces or thermodynamic potentials.

When we say there is no "net" flow/exchange of energy and matter, it doesn't mean there isn't any flow or exchange of energy and matter, but such flow/exchange should be balanced out when summed in all available directions. More formally, $G$ is minimized against perturbation in the composition of the system at constant $T$ and $P$

```{math}
\dd G\big|_{T, P}=\sum_i \mu_i \dd n_i = 0
```

In other words, an infinitesimal change in the composition of the system yield no change in the Gibbs free energy. For example, in a chemical reaction at constant $T$ and $P$, the number of moles of each species (A, B, C, D)  does not change independent of each other as seen in the following reaction formula

```{math}
a\text{A} + b\text{B} \Leftrightarrow c\text{C} + d\text{D}
```

where $a$, $b$, $c$, and $d$ are the stoichiometry coefficients. To make this more concrete, consider the reaction $2\text{H}_2 + \text{O}_2 \Leftrightarrow 2\text{H}_2\text{O}$. The convention is to think in the forward direction, where the stoichiometric coefficients are $-2$, $-1$ and $2$ for $\text{H}_2$, $\text{O}_2$ and $\text{H}_2\text{O}$, respectively. Now, let's write out the infinitesimal change in the Gibbs free energy for the above equation.

```{math}
\begin{aligned}
\dd G &= \sum_i \mu_i\dd n_i \\
&= \mu_{\text{A}} \dd n_{\text{A}} + \mu_{\text{B}} \dd n_{\text{B}} +\mu_{\text{C}} \dd n_{\text{C}} +\mu_{\text{D}} \dd n_{\text{D}}
\end{aligned}
```