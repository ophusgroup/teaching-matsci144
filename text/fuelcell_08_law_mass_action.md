---
title: 2.8 Law of Mass Action
numbering:
  enumerator: 2.8.%s
---

From chemical equilibrium, we would like to derive an expression that tells us how a system might behave when it is away from equilibrium. Starting from the open-circuit voltage in [Equation %s](#eq:reaction_voltage_partial_pressure), if a reaction is at equilibrium, this means there is no net driving force towards more products (positive voltage) or more reactants (negative voltage). Thus, the open circuit voltage should be 0 at equilibrium. We can then rearrange [Equation %s](#eq:reaction_voltage_partial_pressure) to be:

```{math}
\begin{aligned}
-\left(2 \mu_{\text{H}_2}^0 +  \mu_{\text{O}_2}^0 - 2\mu_{\text{H}_2\text{O}}^0\right) &= RT \ln{\frac{\left(p^{\text{eq}}_{\text{H}_2}/p_{\text{ref}}\right)^2 \left(p^{\text{eq}}_{\text{O}_2}/p_{\text{ref}}\right)}{\left(p^{\text{eq}}_{\text{H}_2\text{O}}/p_{\text{ref}}\right)^2}} \\
2 \mu_{\text{H}_2}^0 +  \mu_{\text{O}_2}^0 - 2\mu_{\text{H}_2\text{O}}^0 &= RT \ln{\left[\frac{\left(p^{\text{eq}}_{\text{H}_2}/p_{\text{ref}}\right)^2 \left(p^{\text{eq}}_{\text{O}_2}/p_{\text{ref}}\right)}{\left(p^{\text{eq}}_{\text{H}_2\text{O}}/p_{\text{ref}}\right)^2}\right]^{-1}} \\
\frac{2 \mu_{\text{H}_2}^0 +  \mu_{\text{O}_2}^0 - 2\mu_{\text{H}_2\text{O}}^0}{RT} &= \ln{\frac{\left(p^{\text{eq}}_{\text{H}_2\text{O}}/p_{\text{ref}}\right)^2}{\left(p^{\text{eq}}_{\text{H}_2}/p_{\text{ref}}\right)^2 \left(p^{\text{eq}}_{\text{O}_2}/p_{\text{ref}}\right)}}
\end{aligned}
```
Recall that $\Delta \mu^0_{\text{rxn}}=-\left(2 \mu_{\text{H}_2}^0 +  \mu_{\text{O}_2}^0 - 2\mu_{\text{H}_2\text{O}}^0\right)$, and by taking the exponential of both sides of the equation, we get

```{math}
:label: eq:h2_o2_keq
\exp{\left(-\frac{\Delta \mu^0_{\text{rxn}}}{RT}\right)} = \frac{\left(p^{\text{eq}}_{\text{H}_2\text{O}}/p_{\text{ref}}\right)^2}{\left(p^{\text{eq}}_{\text{H}_2}/p_{\text{ref}}\right)^2 \left(p^{\text{eq}}_{\text{O}_2}/p_{\text{ref}}\right)}
```

Since $\Delta \mu^0_{\text{rxn}}$ is a constant for any reaction measured at the standard condition, if we know the temperature, we can solve for the ratio of equilibrium partial pressures of the products over those of the reactants, raised to their respective stoichiometric coefficients. If we allow the hydrogen-oxygen fuel cell reaction to equilibrate over a long period of time, the final measured partial pressures will observe [Equation %s](#eq:h2_o2_keq). This expression is generally useful for calculating the theoretical yield of the product(s) at a given temperature, if we know the concentration/partial pressures of the reactants and the tabulated chemical potentials of all species at the standard condition.

We will now generalize this derivation for any arbitrary reaction $a\text{A} + b\text{B} \Leftrightarrow c\text{C} + d\text{D}$. Recall that at constant $T$ and $P$, the condition of equilibrium is given by [Equation %s](#eq:reaction_eq). Substituting [Equation %s](#eq:mu_pi_over_pref) into [Equation %s](#eq:reaction_eq), we get

```{math}
:label: eq:
\begin{aligned}
0 &= -a\left[\mu^0_{\text{A}} + RT \ln{\left(\frac{p^{\text{eq}}_{\text{A}}}{p_{\text{ref}}}\right)}\right]
- b\left[\mu^0_{\text{B}} + RT \ln{\left(\frac{p^{\text{eq}}_{\text{B}}}{p_{\text{ref}}}\right)}\right] \\
&\quad + c\left[\mu^0_{\text{C}} + RT \ln{\left(\frac{p^{\text{eq}}_{\text{C}}}{p_{\text{ref}}}\right)}\right]
+ d\left[\mu^0_{\text{D}} + RT \ln{\left(\frac{p^{\text{eq}}_{\text{D}}}{p_{\text{ref}}}\right)}\right] \\
0 &= -a \mu^0_{\text{A}} - b\mu^0_{\text{B}} + c\mu^0_{\text{C}} + d\mu^0_{\text{D}} + RT \ln{\left[\frac{\left(\frac{p^{\text{eq}}_{\text{C}}}{p_{\text{ref}}}\right)^c \left(\frac{p^{\text{eq}}_{\text{D}}}{p_{\text{ref}}}\right)^d}{\left(\frac{p^{\text{eq}}_{\text{A}}}{p_{\text{ref}}}\right)^a \left(\frac{p^{\text{eq}}_{\text{B}}}{p_{\text{ref}}}\right)^b}\right]}
\end{aligned}
```

The last line of equation above tells us that at equilibrium, the entropic contribution exactly balances out the enthalpic contribution to the reaction chemical potential.
After rearranging, for any arbitrary reaction, we can define an equilibrium constant $K_{\text{eq}}$ where

```{math}
:label: eq:keq
K_{\text{eq}} \equiv \exp{\left(-\frac{\Delta \mu^0_{\text{rxn}}}{RT}\right)} = \frac{\left(\frac{p^{\text{eq}}_{\text{C}}}{p_{\text{ref}}}\right)^c \left(\frac{p^{\text{eq}}_{\text{D}}}{p_{\text{ref}}}\right)^d}{\left(\frac{p^{\text{eq}}_{\text{A}}}{p_{\text{ref}}}\right)^a \left(\frac{p^{\text{eq}}_{\text{B}}}{p_{\text{ref}}}\right)^b}
```

[Equation %s](#eq:keq) is the Law of Mass Action, where the reactants' and products' partial pressures are related to the standard chemical reaction potential and temperature. A more general relationship for the Law of Mass Action is shown below:

```{math}
K_{\text{eq}}=\exp{\left(-\frac{\sum_i v_i \mu_i}{RT}\right)} = \prod_i \left(\frac{p_i^{\text{eq}}}{p_{\text{ref}}}\right)^{v_i}
```

where for reactants, $v_i < 0$ and for products $v_i > 0$. The $\prod$ symbol just means the product of all the terms enclosed. If the chemical reaction is not at equilibrium, one can define another ratio as the reaction quotient $\mathsf{Q}$ by removing the equilibrium superscripts in the partial pressures (i.e., the partial pressure of each species is not necessarily at equilibrium):

```{math}
:label: eq:react_quotient
\mathsf{Q} = \prod_i \left(\frac{p_i}{p_{\text{ref}}}\right)^{v_i}
```

As you may recall from your chemistry class, if $\mathsf{Q} < K_{\text{eq}}$, there is an excess of reactants, the reaction will proceed toward the products; if $\mathsf{Q} > K_{\text{eq}}$, there is an excess of products, the reaction will then proceed toward the reactants. If $\mathsf{Q} = K_{\text{eq}}$, the reaction is at equilibrium.

The Law of Mass Action is another manifestation of the well-known Le Chatelier's principle, where the system will counteract perturbations away from the equilibrium condition to restore equilibrium. It can be found throughout many topics in the physical, chemical and biological sciences. It governs relationships as diverse as the number of free elecrtons in a semiconductor, the yield of ammonia produced in a chemical plant, the kinetics of digestion enzymes, the rate at which an infectious disease spreads in a population, and many more.