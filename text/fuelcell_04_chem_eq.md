---
title: Chemical Equilibrium
numbering:
  enumerator: 2.4.%s
label: sec:chem_eq
---

The Gibbs free energy allows us to define equilibrium conditions for a system at constant $T$ and $P$, which means three conditions need to be satisfied for a system to be at equilibrium:

1. There is no **net** flow of energy or matter *within* the system.

2. There is no **net** exchange of energy or matter with the outside world.

3. There are no unbalanced driving forces or thermodynamic potentials.

When we say there is no "net" flow/exchange of energy and matter, it doesn't mean there isn't any flow or exchange of energy and matter, but such flow/exchange should be balanced out when summed in all available directions. 
More formally, $G$ is minimized with respect to perturbations in the composition of the system at constant $T$ and $P$.


```{math}
\dd G\big|_{T, P}=\sum_i \mu_i \dd n_i = 0
```

In other words, an infinitesimal change in the composition of the system yields no change in the Gibbs free energy.
For example, in a chemical reaction at constant $T$ and $P$, the number of moles of each species (A, B, C, D)  does not change independent of each other as seen in the following reaction formula

```{math}
a\text{A} + b\text{B} \Leftrightarrow c\text{C} + d\text{D}
```

where $a$, $b$, $c$, and $d$ are the stoichiometric coefficients. To make this more concrete, consider the reaction $2\text{H}_2 + \text{O}_2 \Leftrightarrow 2\text{H}_2\text{O}$. 
The convention is to consider the forward reaction, where the stoichiometric coefficients are $-2$, $-1$, and $2$ for $\text{H}_2$, $\text{O}_2$, and $\text{H}_2\text{O}$, respectively.
Now, let's write out the infinitesimal change in the Gibbs free energy for the above equation.

```{math}
:label: eq:dG_4_dn
\begin{aligned}
\dd G \big|_{T, P} &= \sum_i \mu_i\dd n_i \\
&= \mu_{\text{A}} \dd n_{\text{A}} + \mu_{\text{B}} \dd n_{\text{B}} +\mu_{\text{C}} \dd n_{\text{C}} +\mu_{\text{D}} \dd n_{\text{D}}
\end{aligned}
```

As written in [Equation %s](#eq:dG_4_dn), it may seem like $\dd G$ has 4 degrees of freedom, namely the change in the number of moles for each of the four species ($\dd n_{\text{A}}, \dd n_{\text{B}}, \dd n_{\text{C}}, \dd n_{\text{D}}$). However, since we are dealing with a chemical reaction with fixed stoichiometric coefficients, in order to observe conservation of mass, the $\dd n_i$ variables do not change independently from each other. More specifically, for every $a$ moles of species A consumed, $b$ moles of species B must also be consumed, while $c$ moles of species C and $d$ moles of species D must be produced.

As a result, since the four $\dd n_i$ variables need to change in concert, there is only 1 true degree of freedom. We name this degree of freedom as extend of the reaction, denoted by $\dd \xi$. If we consider the forward reaction from reactants to products, we can write

```{math}
\begin{aligned}
\dd n_{\text{A}} &= -a\,\dd \xi \\
\dd n_{\text{B}} &= -b\,\dd \xi \\
\dd n_{\text{C}} &= c\,\dd \xi \\
\dd n_{\text{D}} &= d\,\dd \xi
\end{aligned}
```

Substituting these expressions into [Equation %s](#eq:dG_4_dn), we then get

```{math}
:label: eq:reaction_eq
\begin{aligned}
\dd G \big|_{T, P}&= -a\mu_{\text{A}}\,\dd \xi - b\mu_{\text{B}}\,\dd \xi + c\mu_{\text{C}}\,\dd \xi + d\mu_{\text{D}}\,\dd \xi \\
&= \left(-a\mu_{\text{A}}-b\mu_{\text{B}}+c\mu_{\text{C}}+d\mu_{\text{D}}\right)\dd \xi\\
\left(\frac{\partial G}{\partial \xi}\right)_{T, P} &= -a\mu_{\text{A}}-b\mu_{\text{B}}+c\mu_{\text{C}}+d\mu_{\text{D}}=0
\end{aligned}
```

We can see that at constant $T$ and $P$, the Gibbs free energy is minimized with respect to changes in the extent of the chemical reaction.
[Equation %s](#eq:reaction_eq) can be generalized to describe chemical equilibria with the following expression

```{math}
:label: eq:general_reaction_eq
\left(\frac{\partial G}{\partial \xi}\right)_{T, P} = \sum_i v_i \mu_i = 0
```

where $v_i$ is the stoichiometric coefficient of species $i$ in the chemical reaction (negative for reactants and positive for products). 
Finally, we can express the condition of chemical equilibrium for the water production reaction ($2\text{H}_2 + \text{O}_2 \Leftrightarrow 2\text{H}_2\text{O}$) as
```{math}
\left(\frac{\partial G}{\partial \xi}\right)_{T, P} = -2 \mu_{\text{H}_2} - \mu_{\text{O}_2} + 2 \mu_{\text{H}_2\text{O}}= 0
```