---
title: 3.4 Clausius-Clapeyron
numbering:
  enumerator: 3.4.%s
---


## Boiling Water at Different Pressures

By convention, we define the melting point $T_m$ and boiling point $T_b$ of water as 0°C and 100°C, respectively. However, in reality, these temperatures depend on pressure.

For example, a pressure cooker raises the boiling point above 100°C, allowing food to cook faster. In high-altitude cities like Denver, where atmospheric pressure is lower than at sea level, water boils at temperatures below 100°C, requiring adjustments to cooking times. Conversely, in a vacuum, water boils at room temperature.

These observations show that the boiling point of water is not fixed, but rather a function of pressure. This dependence follows from Gibbs’ phase rule, which describes how many variables (such as temperature and pressure) can be independently controlled in a system at equilibrium.

## Gibbs’ Phase Rule

Consider a system where water is not undergoing a phase transition. If we specify the temperature, the pressure can still vary independently, and vice versa. However, during boiling, where liquid and vapor coexist, pressure and temperature are linked; changing one determines the other.

This difference in behavior arises because each phase transition removes a degree of freedom from the system. A degree of freedom refers to how many independent variables must be specified to fully define the state of the system.

To formalize this, we revisit Equation [](#eq:ideal_gas_law), the ideal gas law:

```{math}
PV = nRT
```

This equation has four variables: pressure $P$, volume $V$, temperature $T$, and number of moles $n$ (with $R$ being a constant). If we fix $n$, there are three variables and one equation, meaning we have two degrees of freedom. We must specify two values (e.g., $P$ and $V$) to determine the third ($T$). We can generalize this concept:


:::{admonition} Gibbs’ Phase Rule
:class: danger

The number of degrees of freedom $f$ in a system is:

```{math}
:label: eq:gibbs_phase_rule
f = c - p + 2
```
where:
$c$ is the number of chemical components and $p$ is the number of phases present.
:::


For pure liquid water we have a single chemical component $(c=1)$ and one phase present $(p=2)$. Gibbs' phase rule shows that we have 2 degrees of freedom:
```{math}
f = (1) - (1) + 2 = 2
```

In the case of liquid water, these 2 degrees of freedom are the temperature and pressure of the water.

For boiling water, where liquid and vapor coexist, we have two phases present $(p=2)$, and therefore only 1 degree of freedom:

```{math}
f = (1) - (2) + 2 = 1
```
This means temperature and pressure are no longer independent - setting one automatically determines the other. The relationship between these values is described by the **Clausius-Clapeyron** relation, which we will derive below.



## Equilibrium of Liquid and Gas

For a phase transition between liquid and gas, we consider the equilibrium condition:

```{math}

\text{H}_2\text{O} \, (\text{liquid}) 
\rightleftharpoons
\text{H}_2\text{O} \, (\text{gas})
```


We can use Equation []() to write down $G(T,P,n)$ for both phases:

```{math}
\begin{aligned}



\end{aligned}
```





## The Clausius-Clapeyron Equation

Since boiling occurs at constant temperature and pressure, the total Gibbs free energy of the system is:

```{math}
dG = -S dT + V dP + \sum_i \mu_i d n_i
```




At equilibrium, the total Gibbs free energy change is the sum of the individual phase contributions:


```{math}
dG = dG_\text{liquid} + dG_\text{gas}
```

Each phase’s Gibbs free energy follows:

```{math}
dG_\text{liquid} = - S_\text{liquid} dT + V_\text{liquid} dP
```

```{math}
dG_\text{gas} = - S_\text{gas} dT + V_\text{gas} dP
```

At equilibrium, the chemical potentials of liquid and gas must be equal:

```{math}
\mu_\text{liquid} = \mu_\text{gas}
```

Additionally, mass conservation requires:

```{math}
d n_{\text{liquid}} = - d n_{\text{gas}}
```

Substituting these into our expressions, we find:

```{math}
- S_\text{liquid} dT + V_\text{liquid} dP = - S_\text{gas} dT + V_\text{gas} dP
```

Rearranging:

```{math}
(V_\text{gas} - V_\text{liquid}) dP = (S_\text{gas} - S_\text{liquid}) dT
```


We introduce the latent heat of boiling $L_b$, which represents the heat required to convert 1 mol of liquid to gas at constant temperature:

```{math}
L_b = T_b (S_\text{gas} - S_\text{liquid})
```

Substituting this into our equation:

```{math}
\frac{dT_b}{dP} = \frac{T_b}{L_b} (V_\text{gas} - V_\text{liquid})
```

This is the Clausius-Clapeyron equation, which describes how the boiling temperature of a liquid changes with pressure.

In most practical cases, the molar volume of a liquid is much smaller than the molar volume of a gas:

```{math}
V_\text{liquid} \ll V_\text{gas}
```

Thus, we can approximate:

```{math}
\frac{dT_b}{dP} \approx \frac{T_b V_\text{gas}}{L_b}
```

This simplified form highlights the key thermodynamic principle: raising pressure increases the boiling point, while lowering pressure decreases it.

{figure}
Copy
Edit
:label: fig:clausius_clapeyron
:align: center
:width: 400px

The Clausius-Clapeyron relation shows how boiling temperature varies with pressure. The red line represents equilibrium where liquid and vapor coexist.
This equation explains why:

Water boils at lower temperatures at high altitudes.
Pressure cookers raise the boiling temperature to cook food faster.
Water in a vacuum evaporates at room temperature.
This powerful relationship applies not just to water, but to any phase transition between two phases of a pure substance.