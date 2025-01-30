---
title: Fuel Cell vs. Heat Engine
numbering:
  enumerator: 2.7.%s
---

At the beginning of this module, we stated that a fuel cell can be much more efficient than a heat engine. Now, we will revisit this topic by defining and calculating the efficiency of a fuel cell and that of a heat engine.

Recall that the chemical work created by reactions in a fuel cell is obtained by directing electrons to flow in the circuit, which directly converts chemical energy stored in bonds as electrical work. We define the efficiency ($\eta$) as the maximum possible (electrical) work harvested ($\Delta \mu_{\text{rxn}}$) divided by the change in the bond energy, which is just the reaction enthalpy ($\Delta h_{\text{rxn}}$). At constant pressure, this efficiency is also known as the thermal efficiency $\eta_{\text{therm}}$.

:::{note} Short proof that $\delta Q_{\text{rev}}=\dd H$ at constant pressure
:class: dropdown

Based on [Equation %s](#eq:dH), we can see that with constant pressure ($\dd P = 0$),

```{math}
:enumerated: false
\begin{aligned}
\dd H\big|_{P} &= \dd U + P\dd V \\
& = T\dd S - \cancel{P\dd V} + \cancel{P\dd V} \\
& = \delta Q_{\text{rev}}
\end{aligned}
```

Thus, we can see that at constant pressure, $\delta Q_{\text{rev}} = \dd H$. This equivalence is why the efficiency at constant pressure can be called **thermal** efficiency.

:::

```{math}
\eta_{\text{therm}} = \frac{\Delta \mu_{\text{rxn}}}{\Delta h_{\text{rxn}}}
```

Using hydrogen and oxygen as reactants in the fuel cell, [](#fig:efficiency) shows that the fuel cell efficiency is higher at low temperatures and decreases with increasing temperature. The reason that the fuel cell efficiency decreases with increasing temperature is that the overall reaction's $2\text{H}_2 + \text{O}_2 \Leftrightarrow 2\text{H}_2\text{O}$ entropy decreases with creation of water (Intuititvely, you can rationalize this as 2 moles of $\text{H}_2\text{O}$ is created by consuming 2 moles of $\text{H}_2$ and 1 mole of $\text{O}_2$). The negative reaction entropy means heat is released to the environment rather than be utilized to contribute to the open-circuit voltage of the fuel cell. At higher temperatures, based on $\Delta G =\Delta H - T\Delta S$, the $T\Delta S$ term's contribution becomes more significant. With $\Delta S < 0$, $\Delta G$ will increase with increasing temperature. Most importantly, remember that the formation of water is an exothermic reaction, which means $\Delta H < 0$, and since the chemical bond energy change should not have strong temperature dependence, it can be treated as constant when we vary temperature. As a result, even though $\Delta G$ is increasing, it is becoming **less negative**, and it's **magnitude** decreases with increasing temperature. As a result, $\Delta \mu_{\text{rxn}}$'s magnitude decreases with increasing temperature and thus smaller open-circuit voltage, leading to a decreasing thermal efficiency of the fuel cell. That being said, there are other types of reactants where the voltage does not fall with increasing temperature, where at least as many moles of gas are created as those that are consumed ($\Delta S \geq 0$).


```{figure} ../images/fuelcell/fuelcellvscarnot.png
:label: fig:efficiency
:align: center
:width: 500px

The efficiency of a fuel cell compared to the Carnot efficiency of a heat engine.
```

As we will learn in the next module, the efficiency of a heat engine is defined by the Carnot efficiency:

```{math}
:label: eq:carnot_efficiency
\eta_{\text{Carnot}} = \frac{T_{\text{H}} - T_{\text{C}}}{T_{\text{H}}}
```

where $T_{\text{H}}$ is the temperature of the hot heat reservoir and $T_{\text{C}}$ is the temperature of the cold heat reservoir. From [](#fig:efficiency), the fuel cell efficiency is higher than that of a heat engine below $1170\,\text{K}$, and above this temperature, the heat engine is more efficient. Notice that both the fuel cell and heat engine can't achieve $100\%$ efficiency, even without heat loss or friction. There exists a fundamental thermodynamic limit where chemical/thermal energy cannot be converted into useful work (mechanical, electrical, etc.) at $100\%$.
