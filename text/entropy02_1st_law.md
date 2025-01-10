---
title: The First Law of Thermodynamics
label: entropy02
numbering:
  enumerator: 1.2.%s
---

Energy can be transferred into and out of a thermodynamic system in two ways:
1. Work
2. Heat


(sec:work)=
## Work

Work is one of the fundamental ways energy can be transferred between a thermodynamic system and its surroundings.
In this section, we define and explore the concept of work in thermodynamics, derive key equations, and illustrate examples to build intuition.

In thermodynamics, **work** $W$ is the transfer of energy that occurs when a system exerts a force or causes a displacement in its surroundings.
Work does not always require directed motion in the classical sense; for instance, electromagnetic fields can perform work by altering potential energies or charges.
In this section however we will focus on work due to directed motion.

If you have taken a mechanics course, you may recall the definition of work as
```{math}
:label: work_def_simple
W = F \Delta x,
```
where $F$ is the force required to move an object, and $\Delta x$ is the displacement of the object.
In this definition, force is a scalar and constant.
We will generalize this expression to be

:::{admonition} Definition of Work
:class: danger
Work is the energy transferred through force acting on displacement, expressed as
```{math}
:label: work_definition
W = \int \bm{F}(\bm{x}) d\bm{x},
```
where $\bm{F}(\bm{x})$ is the force vector and $d\bm{x}$ is the infinitesimal displacement vector.
:::

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

Consider a gas in a piston undergoing isothermal expansion which changes the volume from $V_1$ to $V_2$, where the temperature $T$ remains constant.
From the Ideal Gas Law:

```{math}
:label: ideal_gas
P V = n R T \quad \Rightarrow \quad P = \frac{n R T}{V},
```
where $n$ is the number of moles of gas, $R$ is the universal gas constant, and $T$ is the absolute temperature.
Substituting this into the work equation:

```{math}
:label: work_isothermal
W = \int_{V_1}^{V_2} \frac{n R T}{V} dV.
```
After integration:

```{math}
:label: isothermal_result
W &= n R T \int_{V_1}^{V_2} \frac{1}{V} dV.
\\
&= n R T \Big[ \log(V) \Big]_{V_1}^{V_2}
\\
&= n R T \log\left(\frac{V_2}{V_1}\right).
```
This result shows that the work done in an isothermal process depends logarithmically on the ratio of final to initial volumes.


## Heat

The second fundamental way energy can be transferred between a thermodynamic system and its surroundings is **heat** $Q$.
In this and the following section, we define and explore the concept of heat in thermodynamics, derive key equations, and illustrate examples to build intuition.

Heating is the transfer of energy caused by random molecular motion.
Unlike work, which involves organized motion in a specific direction, such as a piston moving upward, heat is associated with disorganized, random motion of molecules.
For example, when heat is added to a system, the random velocities of the gas molecules increase, raising their average kinetic energy.
The sign of heat is positive when energy is added to the system and negative when energy leaves the system.

:::{admonition} Definition of Heat
:class: danger
In thermodynamics, **heat** $Q$ is the energy transferred between a system and its surroundings by microscopic processes such as conduction, radiation, or friction, distinct from macroscopic processes like work or matter transfer.
:::



## Heat Transfer

If you have taken an introductory physics course, you may recall that heat transfer is often expressed as:

```{math}
:label: heat_transfer_simple
Q = m c \Delta T,
```
where $m$ is the mass of the material, $c$ is its specific heat capacity in units of J/(kg·K), and $\Delta T$ is the change in temperature.
This equation describes the amount of heat required to change the temperature of a material.

In systems where the quantity of the material is more conveniently expressed in moles, we can rewrite this equation in terms of the number of moles $n$ and the molar heat capacity $c_p$ (at constant pressure) in units of J/(mol·K):
```{math}
:label: eq:heat_transfer_moles
Q = n c_p \Delta T,
```

In this section, we will generalize these expressions to account for heat transfer in a variety of systems and conditions.


Heat transfer occurs via four main mechanisms:
1. **Conduction** - Transfer of heat through a solid or stationary fluid due to molecular interactions.
2. **Advection** - Transfer of heat through the bulk motion of a moving fluid.
3. **Convection** - Combined heat transfer by conduction and advection in a fluid.
4. **Radiation** - Transfer of heat via electromagnetic waves without requiring a medium.


We typically describe heat transfer using the **heat transfer rate** $\dot{Q}$, equal to
```{math}
\dot{Q}
= \frac{\Delta Q}{\Delta t},
```
where $\Delta Q$ is the change in heat, and $\Delta t$ is the time interval.


### Conduction

Energy transfer through direct contact between molecules is known as conduction, and is governed by Fourier's law:
```{math}
:label: fourier_law
\dot{Q}
=
-k A \frac{\Delta T}{\Delta x},
```
where $k$ is the thermal conductivity, $A$ is the cross-sectional area, and $\Delta T/\Delta x$ is the temperature gradient or temperature difference $\Delta T$ over some distance $\Delta x$.


### Advection

Advection refers to energy transfer due to the bulk motion of a fluid, governed by the equation:

```{math}
:label: advection_equation
\dot{Q} = \rho \, c_p \, \bm{v} \, A \Delta T,
```
where $\rho$ is the fluid density, $c_p$ is the specific heat capacity of the fluid at constant pressure, $\bm{v}$ is the velocity vector of the fluid, $A$ is the area through which the fluid flows, and $\Delta T$ is the temperature difference in the fluid.

Advection is particularly important in processes involving strong bulk fluid flow, such as heat transport in pipelines, molten metal casting, or atmospheric heat distribution.

:::{admonition} Advection and Heat
:class: danger
Advection is **not** considered heat in thermodynamics because it transfers energy through the bulk motion of matter, not random molecular motion driven by temperature differences.
Instead, we consider advection to be a mechanism of energy transport.
:::


### Convection

Energy transfer through fluid motion is known as convection, which involves both conduction and advection. 
We can express it as:
```{math}
:label: convection
\dot{Q} = h A \Delta T,
```
where $h$ is the convective heat transfer coefficient, $A$ is the area through which the fluid flows, and $\Delta T$ is the temperature difference.


### Radiation

Energy transfer via electromagnetic waves is known as radiation, and is governed by the Stefan-Boltzmann law:
```{math}
:label: stefan_boltzmann
\dot{Q} = \sigma A \epsilon \left(T^4 - T_\text{env}^4\right),
```
where $\sigma$ is the Stefan-Boltzmann constant, $A$ is the area, $\epsilon$ is the emissivity of the surface, $T$ is the temperature of the object, and $T_\text{env}$ is the temperature of the surroundings.




## Heat vs Work

The distinction between heat and work lies in the nature of the motion.
In work, molecules move collectively in a coordinated direction to transfer energy.
In heat, energy transfer occurs through random motion in all directions.
Both heat and work involve energy transfer, but they do so in fundamentally different ways.
[](#heat_vs_work) illustrates this distinction by showing how work and heat manifest through the motions of gas molecules.


```{figure} ../images/entropy/heat_vs_work.png
:label: heat_vs_work
:align: center
:width: 680px
Increasing gas temperature via work or heat.
By time 3, the states are indistinguishable, meaning that we cannot determine if the increased temperature is due to heat transfer or applied work.
```

When we apply a force to the piston in [](#heat_vs_work), energy is transferred from the motion of the piston moving to the right, into increased motion of the gas molecules from collisions with the wall.
In contrast, adding heat directly to the enclosed volume in [](#heat_vs_work) increases the random velocities of gas molecules by raising their kinetic energy.




## Internal Energy and the First Law of Thermodynamics

The internal energy of a system, denoted $U$, is the total energy contained within the system.
This includes all forms of microscopic energy, such as the kinetic energy of molecular motion and the potential energy of molecular interactions.
Internal energy is a state function, meaning its value depends only on the current state of the system and not on the path taken to reach that state.


:::{admonition} The First Law of Thermodynamics
:class: danger
The First Law of Thermodynamics states that the change in internal energy of a system $\Delta U$ is equal to the heat $Q$ added to the system minus the work $W$ done by the system:
```{math}
:label: first_law_thermodynamics
\Delta U = Q - W.
```
:::

The first law of thermodynamics expresses the conservation of energy in a thermodynamic system.
Equation [](#first_law_thermodynamics) reflects the balance of energy within the system.
Each term represents a different mode of energy transfer which we discussed above:
- $Q$: Heat added to the system increases the internal energy.
- $W$: Work done by the system decreases the internal energy.


(sign_conv)=
### Thermodynamic Sign Convention


In thermodynamics, defining the 1st law as $\Delta U = Q - W$ leads to the following sign convention:
- ($Q > 0$) Heat added to the system is positive.
- ($Q < 0$) Heat leaving the system is negative.
- ($W > 0$) Work is done **by the system** (onto its surroundings).
- ($W < 0$) Work done **to the system** (by its surroundings).

With this sign convention, applying positive pressure ($\Delta P > 0$) to reduce the volume of a system, we calculate the work to be $W = \int P \dd V$. 
This results in a negative value for work ($W<0$), indicating that work is done on the system, increasing its internal energy $\Delta U > 0$.


### Chemistry Sign Convention

In this context, the 1st law is defined as $\Delta U = Q + W$, leading to the following sign convention:"
- ($Q > 0$) Heat added to the system is positive.
- ($Q < 0$) Heat leaving the system is negative.
- ($W < 0$) Work is done **by the system** (onto its surroundings).
- ($W > 0$) Work done **to the system** (by its surroundings).

With this sign convention, when we apply positive pressure ($\Delta P > 0$) to reduce the volume of a system, we calculate the work to be $W = - \int P \dd V$. 
This results in a positive value for work ($W>0$), indicating that work is done on the system, increasing its internal energy $\Delta U > 0$.



### Choosing a Convention

Why the difference? The choice of sign convention reflects whether the focus is on the system or its surroundings:

- **Thermodynamics Convention**: Widely used in physics and engineering, emphasizes energy flow and interactions with surroundings.
- **Chemistry Convention**: Focuses on the system itself, often aligning with experimental measurements like pressure-volume work.

In this course, we will use the sign convention defined above in Equation [](#first_law_thermodynamics). This convention is most often found in thermodynamic and engineering situations. One way to ensure that your calculations are always self-consistent is to remember that both must reduce to this form:
```{math}
\Delta U = Q - \int P \dd V
```


## Thermodynamic Systems

We can classify thermodynamic systems into 3 categories based on their interface conditions, summarized in [](#tab:systems) and illustrated in [](fig:systems):
1. An **open system** allows heat, work, and mass to cross its boundaries.
2. A **closed system** permits only heat and work transfer, while mass remains contained.
3. An **isolated system** allows no exchange of heat, work, or mass with its surroundings.

:::{list-table} Classification of thermodynamic systems by boundary conditions.
:label: tab:systems
:widths: 1 1 1
:header-rows: 1
* - System Type
  - Permeable to Heat and Work
  - Permeable to Matter
* - open
  - yes
  - yes
* - closed
  - yes
  - no
* - isolated
  - no
  - no
:::


```{figure} ../images/entropy/systems.png
:label: fig:systems
:align: center
:width: 720px
(left) An isolated thermodynamic system which contains a closed system, which itself contains an open system. (right) An isolated system which contains an open system.
```

Consider the closed system contained inside the isolated system in [](#fig:systems).
The first law of thermodynamics states
```{math}
U_{\rm{closed}} =
  Q_{\rm{input}} - Q_{\rm{output}}
- (
  W_{\rm{system}} - W_{\rm{surroundings}},
)
```
where $Q_{\rm{input}}$ and $Q_{\rm{output}}$ refer to heat transferred across the boundary, and $W_{\rm{system}}$ and $W_{\rm{surroundings}}$ refers to work done by the system on the surroundings and vice versa.
The total amount of energy in the closed system changes by exactly the amount of heat added/removed to the system and the work done by/to the system, i.e. total energy is conserved.

By definition, an isolated system has $Q_{\rm{isolated}} = W_{\rm{isolated}} = 0$, and therefore $U_{\rm{isolated}}$ remains constant.

We can also categorize thermodynamic systems or processes into 4 categories based on the constraints imposed on state variables:
1. **Isothermal** - The system undergoes a process at constant temperature $T$.
Heat transfer occurs to maintain thermal equilibrium as work is done or energy changes.
2. **Isobaric** - The system experiences a process at constant pressure $P$.
Heat transfer can lead to changes in volume and temperature.
3. **Isochoric** - The system's volume $V$ remains constant.
No work is done, and any energy transfer appears as heat.
4. **Adiabatic** - The system is thermally insulated, so no heat is exchanged ($Q = 0$).
Changes in the system's energy result entirely from work done on or by the system.



