---
title: The First Law of Thermodynamics
numbering:
  enumerator: 1.2.%s
---

(entropy02)=
## The First Law of Thermodynamics


Energy can be transferred into and out of a thermodynamic system in two ways:
1. Work
2. Heat


### Work

Work is one of the fundamental ways energy can be transferred between a thermodynamic system and its surroundings. In this section, we define and explore the concept of work in thermodynamics, derive key equations, and illustrate examples to build intuition.

In thermodynamics, **work** ($W$) is the transfer of energy that occurs when a system exerts a force or causes a displacement in its surroundings. Work does not always require directed motion in the classical sense; for instance, electromagnetic fields can perform work by altering potential energies or charges. In this section however we will focus on how work due to directed motion.

If you have taken a mechanics course, you may recall the definition of work as
```{math}
:label: work_def_simple
W = F \Delta x,
```
where $F$ is the force required to move an object, and $\Delta x$ is the displacement of the object. In this definition, force is a scalar and constant. We will generalize this expression to be

:::{admonition} Definition of Work
:class: danger
```{math}
:label: work_definition
W = \int \bm{F}(\bm{x}) d\bm{x}
```
:::
where $\bm{F}(\bm{x})$ is the force vector and $d\bm{x}$ is the infinitesimal displacement vector.

For a system like a gas in a piston, the force exerted by the gas is related to its pressure $P$ and the area $A$ of the piston by:

```{math}
:label: force_pressure
F = P A.
```
The displacement of the piston, $dx$, results in a volume change $dV$, where:

```{math}
:label: volume_change
dV = A \, dx.
```
Substituting these relationships into the definition of work:

```{math}
:label: work_pressure_volume
W &= \int P A \frac{dV}{A} \\
W &= \int P \, dV.
```
This integral form is widely used in thermodynamics to calculate the work done by or on a system.

In thermodynamics, the sign of work depends on the direction of energy transfer:

- Positive work: Work is done by the system on the surroundings (e.g., gas expansion).
- Negative work: Work is done on the system by the surroundings (e.g., gas compression).

**Example: Isothermal Expansion**

Consider a gas in a piston undergoing isothermal expansion which changes the volume from $V_1$ to $V_2$, where the temperature $T$ remains constant. From the Ideal Gas Law:

```{math}
:label: ideal_gas
P V = n R T \quad \Rightarrow \quad P = \frac{n R T}{V},
```
where $n$ is the number of moles of gas, $R$ is the universal gas constant, and $T$ is the absolute temperature. Substituting this into the work equation:

```{math}
:label: work_isothermal
W = \int_{V_1}^{V_2} \frac{n R T}{V} dV.
```
Performing the integration:

```{math}
:label: isothermal_result
W &= n R T \int \frac{1}{V} dV.
\\
W &= n R T \ln\left(\frac{V_2}{V_1}\right) 
\\
W &= n R T \ln\left(\frac{V_2}{V_1}\right).
```
This result shows that the work done in an isothermal process depends logarithmically on the ratio of final to initial volumes.

Example: Adiabatic Expansion
In an adiabatic process, no heat is exchanged with the surroundings ($Q = 0$). The First Law of Thermodynamics simplifies to:

```{math}
:label: adiabatic_first_law
\Delta U = -W.
```
For an ideal gas, the internal energy $U$ is related to the temperature by $U = \frac{n C_V T}{2}$, where $C_V$ is the molar heat capacity at constant volume. Using the Ideal Gas Law, $P V = n R T$, and the adiabatic condition, $P V^\gamma = \text{constant}$:

```{math}
:label: work_adiabatic
W = \frac{P_1 V_1 - P_2 V_2}{\gamma - 1}, \quad \gamma = \frac{C_P}{C_V}.
```
Work for Polytropic Processes
In a polytropic process, the relationship between pressure and volume is given by $P V^n = \text{constant}$, where $n$ is the polytropic index. Substituting into the work equation:

```{math}
:label: work_polytropic
W = \int_{V_1}^{V_2} P dV = \int_{V_1}^{V_2} \frac{C}{V^n} dV.
```
Performing the integration:

```{math}
:label: polytropic_result
W = \frac{P_2 V_2 - P_1 V_1}{1 - n}, \quad n \neq 1.
```
For $n = 1$, the process reduces to isothermal expansion, and the logarithmic relationship derived earlier is used.

Work in Cyclic Processes
In cyclic processes, the system returns to its initial state, so the change in internal energy is zero ($\Delta U = 0$). From the First Law of Thermodynamics:

```{math}
:label: cyclic_work
W_{\text{net}} = Q_{\text{net}}.
```

Graphically, the work done in a cyclic process corresponds to the area enclosed by the curve on a $P$-$V$ diagram. For example, in a Carnot cycle, the net work is the difference between the heat absorbed during isothermal expansion and the heat released during isothermal compression.

Work vs. Heat
Both work and heat are energy transfer mechanisms, but they differ fundamentally:

Work involves ordered energy transfer (e.g., moving a piston or transferring electrical energy).
Heat involves disordered energy transfer (e.g., random motion of particles).
The First Law of Thermodynamics relates these concepts:

```{math}
:label: first_law
\Delta U = Q - W,
```
where $\Delta U$ is the change in internal energy, $Q$ is heat transfer, and $W$ is work.

Summary

Work plays a critical role in thermodynamics, describing energy transfer through force and displacement. Key relationships like $W = \int P dV$ provide a framework for analyzing processes involving gases. Understanding the nuances of work and its distinction from heat allows for deeper insights into energy transfer in physical systems.


