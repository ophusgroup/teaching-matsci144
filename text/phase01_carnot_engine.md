---
title: 3.1 The Carnot Engine
numbering:
  enumerator: 3.1.%s
---


A geothermal power plant needs a way to convert heat into work and, ultimately, electricity. A heat engine performs this conversion. In this section, we discuss the Carnot engine, the most efficient heat engine possible.


```{figure} ../images/phase/isothermalpiston.png
:label: fig:isothermal_piston
:align: center
:width: 500px
Isothermal expansion of a piston connected to a heat reservoir. The walls of the piston allow heat transfer, but not exchange of matter.
```


## Isothermal Expansion of Gas

To understand the Carnot engine, we first consider a piston in contact with a heat reservoir, shown in [](#fig:isothermal_piston). The piston walls allow heat transfer but are impermeable to matter. The temperature inside the piston matches the reservoir, but the pressure is higher than the surroundings. As a result, the gas expands, pushing the piston outward and doing work while maintaining a constant temperature. This process is called isothermal expansion.

We assume the expansion happens quasistatically, meaning the external pressure is only slightly lower than the internal pressure at every step. The behavior of the gas follows the ideal gas law:

```{math}
PV = nRT
```
Since n and T are constant, we get:

```{math}
PV = \text{constant}
```

```{figure} ../images/phase/isothermalexpansion.png
:label: fig:isothermal_expansion
:align: center
:width: 700px
The change of pressure, volume, entropy and temperature during isothermal gas expansion.
```

The left panel of [](#fig:isothermal_expansion) shows the relationship between pressure and volume. Recalling Equation [](#work_pressure_volume), we know that the work done by the gas during expansion is:

```{math}
dW = P  dV
```

The expanding gas is doing work, which can be harvested through the motion of the piston. Since energy is conserved, the heat absorbed from the reservoir equals the work done by the gas:

```{math}
dU = dQ - dW = 0
```
For a reversible process, we know from Equation [](#eq:work_TdS) that heat transfer is given by:

```{math}
:label: eq:carnot_TdS
dQ_{\text{rev}} = T dS
```
Therefore, the entropy of the gas must increase as it expands. This agrees with what we learned in [](#sec:second_law): lower pressure corresponds to higher disorder (entropy).

If the piston expands indefinitely, we would have a system converting heat entirely into work with 100% efficiency. However, to continuously extract work, the piston must return to its original state.
To restore the system, we compress the gas back to its original temperature and pressure. During compression, work is done on the gas. 

The right panel of [](#fig:engine_cycle) shows the piston’s expansion and compression cycle. Starting from initial values of $(V_1,P_1)$, the piston expands to $(V_2,P_2)$, and then returns to $(V_1,P_1)$.
The left panel of [](#fig:engine_cycle) shows the T-S diagram during this cycle. Starting from initial values of $(S_1,T)$, the piston expansion increases the entropy to $(S_2,T)$, and then its compression returns the system to $(S_1,T)$.


```{figure} ../images/phase/enginecycle.png
:label: fig:engine_cycle
:align: center
:width: 700px
Isothermal expansion and then compression of a piston. Each cycle performs no net work. 
```

Graphically, integrating $PdV$ in [](#fig:engine_cycle) does not generate any network since expansion and compression steps cancel each other out. 
A complete isothermal cycle can be modeled by the expression 
```{math}
\oint P dV = 0
```
where the $\oint$ symbol represents a closed path integral, indicating that the system undergoes a full cycle and returns to its initial state.

Similarly, the heat absorbed from $(S_1,T)$ to $(S_2,T)$ exactly equals the heat released as we traverse back from $(S_2,T)$ to $(S_1,T)$. Thus we have no net conversion of heat to work.
This means the total work done by the gas during expansion cancels out the work required to compress it. Similarly, the heat absorbed during expansion equals the heat released during compression:
```{math}
\oint T dS = 0
```
Thus, no net heat is converted to work.



## The Carnot Cycle

To extract net work, the work done by the gas must exceed the work required to restore the system. This means that more heat must be absorbed during expansion than is released during compression. Considering Equation [](#eq:carnot_TdS), to absorb more heat while keeping the entropy the same at the start and end of the cycle, we must increase temperature during expansion and decrease temperature during compression. This creates a complete cycle, plotted in [](#fig:carnotcycle_entropy).


```{figure} ../images/phase/carnotcycle_entropy_2.png
:label: fig:carnotcycle_entropy
:align: center
:width: 700px
The P-V and T-S diagrams for the Carnot cycle.
```

The left panel of [](#fig:carnotcycle_entropy) shows the pressure-volume (P-V) diagram, while the right panel shows the temperature-entropy (T-S) diagram. The four steps of the Carnot cycle are:

1. **Isothermal Expansion** (1 → 2): The gas expands at high temperature $T_\text{H}$, absorbing heat.
2. **Adiabatic Expansion** (2 → 3): The gas expands without heat transfer, cooling to $T_\text{C}$.
3. **Isothermal Compression** (3 → 4): The gas is compressed at $T_\text{C}$, releasing heat.
4. **Adiabatic Compression** (4 → 1): The gas is compressed without heat transfer, raising its temperature back to $T_\text{H}$.

Since adiabatic expansion and compression involve no heat exchange $(Q = 0)$, we can ignore steps 2 and 4 and use:


```{math}
dU = - dW
```
The total work done by the cycle is:

```{math}
W_{\text{cycle}} = Q_{\text{in}} - Q_{\text{out}}
```

We define efficiency $\eta$ as:

```{math}
:label: eq:efficiency
\eta = \frac{\text{net work done}}{\text{heat in}}
```

We could use Equation [](#work_pressure_volume) to calculate the work done, but there is an easier way. We can instead use the First Law and our knowledge that the cycle begins and ends at the same temperature:

```{math}
\Delta U_{\text{cycle}} = Q - W = 0
```

We therefore only need to sum up all net contributions to $Q$, which is shown in [](#fig:carnotcycle_diagram).


```{figure} ../images/phase/carnotcycle_diagram.png
:label: fig:carnotcycle_diagram
:align: center
:width: 700px
The 4 steps of the Carnot cycle shown for a piston, with the associated changes in $T$, $S$ and heat $Q_\text{rev}$ for all steps.
```

The net heat transferred (and therefore work performed) is therefore equal to:

```{math}
Q_{\text{cycle}} = W_{\text{cycle}} = (T_H - T_C)(S_2 - S_1)
```

The efficiency of the Carnot cycle simplifies to:

```{math}
:label: eq:eff_carnot
\begin{aligned}
\eta_{\text{Carnot}} 
&= \frac{\text{net work done}}{\text{heat in}} \\
&= \frac{(T_H - T_C)(S_2 - S_1)}{T_H(S_2 - S_1)} \\
&= 1 - \frac{T_C}{T_H} \\
\end{aligned}
```
This is the Carnot efficiency, the maximum efficiency of an ideal heat engine which alternates between two temperatures (in units of Kelvins). This efficiency is shown graphically in [](#fig:carnot_efficiency). The Carnot efficiency for a cold reservoir at 300K is plotted in [](#fig:carnot_efficiency_300K).


```{figure} ../images/phase/carnotefficiencygraphic.png
:label: fig:carnot_efficiency
:align: center
:width: 400px
Heat input vs work output for the Carnot Cycle.
```

```{figure} ../images/phase/carnotefficiency.png
:label: fig:carnot_efficiency_300K
:align: center
:width: 500px
The Carnot efficiency at 300K, as a function of the hot reservoir temperature.
```





## Irreversibility and Efficiency

The Carnot cycle is an ideal process, but real-world engines always have some irreversible components. Any deviation from perfect reversibility lowers efficiency.

For instance, consider a modification where the adiabatic steps (2 → 3 and 4 → 1) are not reversible. Instead of quasistatic changes in pressure and volume, real processes often involve stepwise changes, as shown in [](#fig:irreversible_adiabats).


```{figure} ../images/phase/irreversible_adiabats.png
:label: fig:irreversible_adiabats
:align: center
:width: 400px
The P-V diagram of an approximate Carnot cycle which includes non-quasistatic adiabatic steps.
```

If we again consider the process shown in [](#fig:isothermal_piston), we know that in the real world when external pressure changes suddenly, the piston volume takes time to adjust. Friction and turbulence cause energy losses, reducing efficiency:

```{math}
\eta < \eta_{\text{Carnot}}
```
We can analyze this efficiency loss in terms of entropy. For a reversible process:

```{math}
dS = \frac{dQ}{T}
```
But for an irreversible process:

```{math}
dS > \frac{dQ}{T}
```
Thus, entropy increases, meaning some energy is lost as waste heat each cycle. This is shown schematically in [](#fig:irreversibleTS). Each change in temperature is accompanied by a slight increase in entropy of the universe, which causes a decrease in the efficiency loss. We could perform a similar analysis for [](#fig:irreversible_adiabats).

```{figure} ../images/phase/irreversibleTS.png
:label: fig:irreversibleTS
:align: center
:width: 500px
A non-ideal thermodynamic cycle where the entropy of the system increases slightly at steps (2 → 3) and (4 → 1).
```

The Carnot cycle sets the upper limit on efficiency. Any real cycle with irreversible steps will be less efficient, as energy is lost due to friction, turbulence, and heat dissipation.
