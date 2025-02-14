---
title: 3.4 Clausius-Clapeyron
numbering:
  enumerator: 3.4.%s
---


## Boiling Water at Different Pressures

By convention, we define the melting point $T_m$ and boiling point $T_b$ of water as 0°C and 100°C, respectively. However, in reality, these temperatures depend on pressure.

For example, a pressure cookerraises the boiling point above 100°C, allowing food to cook faster. In igh-altitude cities like Denver, where atmospheric pressure is lower than at sea level, water boils at temperatures below 100°C, requiring adjustments to cooking times. Conversely, in a vacuum, water boils at room temperature or lower.

These observations show that the boiling point of water is not fixed, but rather a function of pressure. This dependence follows from **Gibbs’ phase rule**, which determines how many independent variables (such as temperature and pressure) must be specified to define a system at equilibrium.

## Gibbs’ Phase Rule

### Degrees of Freedom in a System

Consider a system where water is **not** undergoing a phase transition. If we specify the temperature, the pressure can still vary independently, and vice versa. However, during boiling, where liquid and vapor coexist, pressure and temperature are linked; changing one determines the other.

This difference in behavior arises because each phase transition removes a degree of freedom from the system. A **degree of freedom** refers to how many independent variables must be specified to fully define the state of the system.

To formalize this, we revisit Equation [](eq:ideal_gas_law), the ideal gas law:

```{math}
PV = nRT
```

This equation has four variables: pressure $P$, volume $V$, temperature $T$, and number of moles $n$ (with $R$ being a constant). If we fix $n$, there are three variables and one equation, meaning we have **two degrees of freedom**. We must specify two values (e.g., $P$ and $V$) to determine the third ($T$). This general principle extends to all thermodynamic systems.

:::{admonition} **Gibbs’ Phase Rule**
:class: danger

The number of **degrees of freedom** $f$ in a system is:

```{math}
:label: eq:gibbs_phase_rule
f = c - p + 2
```

where $c$ is the number of hemical components in the system and $p$ is the number of phases present.
:::

For pure liquid water, we have a single chemical component ($c = 1$) and one phase present ($p = 1$). Applying Gibbs' phase rule:

```{math}
f = (1) - (1) + 2 = 2
```

This means there are **two degrees of freedom**, so temperature and pressure can vary independently.

However, during boiling where liquid and vapor coexist, we have two phases present ($p = 2$), and therefore:

```{math}
f = (1) - (2) + 2 = 1
```

This means temperature and pressure are no longer independent—fixing one determines the other. The mathematical relationship between them is given by the **Clausius-Clapeyron relation**, which we will derive in the next section.

### Phase Equilibrium Conditions

At equilibrium, a system undergoing a **phase transition** must satisfy three conditions:

1. **Thermal equilibrium**: The temperature of the coexisting phases must be equal.

```{math}
T_{\text{liquid}} = T_{\text{gas}}
```

2. **Mechanical equilibrium**: The pressure of the two phases must be equal.

```{math}
P_{\text{liquid}} = P_{\text{gas}}
```

3. **Chemical equilibrium**: The chemical potential of the two phases must be equal.

```{math}
\mu_{\text{liquid}} = \mu_{\text{gas}}
```

These conditions ensure that, at equilibrium, the rates of mass, heat, and energy transfer between the phases are balanced, so the system remains in a steady state



###  Gibbs’ Phase Rule Implications

The consequence of **Gibbs' phase rule** is that in a single-phase system, pressure and temperature can vary independently. However, during oiling, the system has only one degree of freedom. This explains why:

- At a fixed pressure the boiling temperature is uniquely determined.
- At a fixed temperature, the boiling pressure is uniquely determined.

For example:
- **At sea level** ($P = 1$ atm), water boils at **100°C**.
- **In Denver** ($P < 1$ atm), water boils at **<100°C**.
- **In a pressure cooker** ($P > 1$ atm), water boils at **>100°C**.
- **In space** ($P \approx 0$ atm), water boils at **room temperature** or lower.

The relationship between temperature and pressure during boiling is described by the **Clausius-Clapeyron equation**, which we derive next.




## Equilibrium of Liquid and Gas

The boiling point of water is often stated as 100°C, but as we saw above, it depends on pressure. 
Similarly, the boiling pressure of water will also depend on the temperature.
To understand why, we analyze the equilibrium condition during a phase transition:

```{math}
\text{H}_2\text{O} \, (\text{liquid}) 
\rightleftharpoons
\text{H}_2\text{O} \, (\text{gas})
```

By definition, we have $T=T_b$ and $P=P_b$, the temperature and pressure of the system at the boiling point. For both phases, we write the Gibbs free energy as:
```{math}
:label: eq:deriv_gibbs_gas_liquid
\begin{aligned}
\dd G_{\text{liquid}}
&=
- S_{\text{liquid}} \dd T_b
+ V_{\text{liquid}} \dd P_b
+ \mu_{\text{liquid}} \dd n_\text{liquid}
\\

\dd G_{\text{gas}} 
&= 
- S_{\text{gas}} \dd T_b
\,\,\,\,\, + V_{\text{gas}} \dd P_b
\,\,\,\, + \mu_{\text{gas}} \dd n_\text{gas}
\\
\end{aligned}
```

From the integral forms of internal energy and Gibbs Free energy given by Equations [](#expanded_first_law) and [](#eq:gibbs_free_energy), we can derive

```{math}
\begin{aligned}
G_\text{liquid}
&=
\mu_{\text{liquid}}
n_{\text{liquid}}
\\
G_\text{gas}
&=
\mu_{\text{gas}}
n_{\text{gas}}
\\
\end{aligned}
```

Applying the [product rule](wiki:Product_rule) gives
```{math}
\begin{aligned}
\dd G_\text{liquid}
&=
\mu_{\text{liquid}} \dd n_{\text{liquid}}
+ n_{\text{liquid}} \dd \mu_{\text{liquid}} 
\\
\dd G_\text{gas}
&=
\mu_{\text{gas}} \dd n_{\text{gas}}
\,\,\,\,\,\,\,\,\, + n_{\text{gas}} \dd \mu_{\text{gas}} 
\\
\end{aligned}
```

Combining these expressions with Equation [](#eq:deriv_gibbs_gas_liquid) yields
```{math}
\begin{aligned}
 n_\text{liquid} \dd \mu_{\text{liquid}} 
&=
- S_{\text{liquid}} \dd T_b
+ V_{\text{liquid}} \dd P_b
\\

 n_\text{gas} \dd \mu_{\text{gas}}
&= 
- S_{\text{gas}} \dd T_b
\,\,\,\,\, + V_{\text{gas}} \dd P_b
\\
\end{aligned}
```

Dividing by the number of mols of liquid and gas gives us the derivative of the chemical potentials as a function of specific entropy and volume:
```{math}
:label: eq:water_liquid_gas_eq1
\begin{aligned}
\dd \mu_{\text{liquid}} 
&=
- \bar{S}_{\text{liquid}} \dd T_b
+ \bar{V}_{\text{liquid}} \dd P_b
\\

\dd \mu_{\text{gas}}
&= 
- \bar{S}_{\text{gas}} \dd T_b
\,\,\,\,\, + \bar{V}_{\text{gas}} \dd P_b
\\
\end{aligned}
```

The boiling point occurs when the two phases are in equilibrium, so the chemical potentials of liquid and gas phases are equal ($\mu_{\text{liquid}} = \mu_{\text{gas}}$). Thus we can set the expressions in Equation [](#eq:water_liquid_gas_eq1) equal to each other:

```{math}
- \bar{S}_{\text{liquid}} \dd T_b
+ \bar{V}_{\text{liquid}} \dd P_b
=
- \bar{S}_{\text{gas}} \dd T_b
+ \bar{V}_{\text{gas}} \dd P_b
```

Rearranging this expression, we can write

```{math}
:label: eq:cc_deriv_1
\frac{\dd T_b}{\dd P_b}
= 
\frac{
  \bar{V}_\text{gas} - \bar{V}_\text{liquid}
}{
  \bar{S}_\text{gas} - \bar{S}_\text{liquid}
}
```

To simplify this expression, we define the **latent heat of boiling** $L_b$ to be
```{math}
L_b = \frac{Q_\text{rev}}{n}
```
where $Q$ is the heat exchanged during boiling and $n$ is the number of mols of the boiled substance. The latent heat of boiling $L_b$ has been measured for many materials, including water.

Recall Equation [](#eq:work_TdS), which states that for a reversible process the heat flow $Q_\text{rev}$ will be equal to the temperature $T$ multiplied by the change in entropy $\Delta S$. We can now simplify Equation [](#eq:cc_deriv_1):
```{math}
\begin{aligned}
\frac{\dd T_b}{\dd P_b}
&= 
\frac{
  \bar{V}_\text{gas} - \bar{V}_\text{liquid}
}{
  \Delta \bar{S}
}
\\
&= 
\frac{T_b}{\bar{Q}}
\left( \bar{V}_\text{gas} - \bar{V}_\text{liquid} \right)
\\
&= 
\frac{T_b n}{ Q}
\left( \bar{V}_\text{gas} - \bar{V}_\text{liquid} \right)
\end{aligned}
```


:::{admonition} **The Clausius-Clapeyron Relation**
:class: danger

```{math}
\frac{\dd T_b}{\dd P_b}
=
\frac{T_b}{L_b}
\left( \bar{V}_\text{gas} - \bar{V}_\text{liquid} \right)
```

This expression relates the boiling temperature of a liquid to the pressure.
:::

The molar volume of water vapor is approximately 30 L / mol (at 100°C and 1 atm), which is much higher than the molar volume of liquid water which is approximately 0.018 L / mol. We can therefore make the approximation $\bar{V}_\text{gas} >> \bar{V}_\text{liquid}$, giving a simpler Clausius-Clapeyron Relation for water:

```{math}
:label: eq:Clausius_Clapeyron_water
\frac{\dd T_b}{\dd P_b}
=
\frac{T_b \bar{V}_\text{gas}}{L_b}

```

This expression is plotted for water in [](#fig:clausius_clapeyron_water). Above the red line, the liquid phase is stable. Below the red line, the gas phase is stable. Along the red line, both phases coexist.

```{figure} ../images/phase/clausius.png
:label: fig:clausius_clapeyron_water
:align: center
:width: 400px

The approximate Clausius-Clapeyron relationship for water, given by Equation [](#eq:Clausius_Clapeyron_water).
```


