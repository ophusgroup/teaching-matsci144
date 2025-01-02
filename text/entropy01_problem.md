---
title: The Problem
numbering:
  enumerator: 1.1.%s
---

## Overview

Human civilization emits millions of tons of CO₂ into Earth's atmosphere every year. 
Natural processes which reduce atmospheric CO{sub}`2` concentration include:
- Dissolution in sea water.
- Incorporation into the terrestrial biosphere, especially forests and grasslands. 
- Weathering of silicate rocks.
- Accumulation of organic material under anaerobic conditions such as in wetlands or peat bogs. 

Unfortunately, these natural processes cannot keep pace with the CO₂ released by human industrial, transportation and agricultural production. The net result has been a consistent rise in atmospheric CO₂ concentration over the past few hundred years, shown in [](#co2_atmosphere). 


```{figure} ../images/entropy/co2_atmosphere.png
:label: co2_atmosphere
:align: center
:width: 500px
Atmospheric concentration of CO₂ (Tg) compared to CO{sub}`2` produced by human civilization (ppmv). Adapted and used with permission from ML Machala, [Carbon-Neutral Synthetic Fuel](http://large.stanford.edu/courses/2011/ph240/machala2/).
```

[](#correlation_co2_temp) demonstrates the atmospheric CO₂ is very highly correlated to the global mean temperature. Historically, CO₂ concentration has not risen above ~325 ppmv, but in May 2023 it rose to 424 ppmv ([NOAA Global Monitoring Lab](https://gml.noaa.gov/ccgg/trends/data.html)). This recent rise or CO₂ concentration over the past ~200 years is extremely rapid compared to the geological timescales of previous CO₂ oscillations. 

```{figure} ../images/entropy/correlation_co2_temp.png
:label: correlation_co2_temp
:align: center
:width: 500px

Correlations between concentration of CO₂, CH₄ and temperature. Courtesy of the [Intergovernmental Panel on Climate Change (2001)](http://www.ipcc.ch), @doi:10.1126/science.1103618, @doi:10.1038/nature03301.
```

The scientific consensus is that increased greenhouse gas emissions (primarily CO₂) is driving anthropogenic (human-caused) climate change (@wiki:Scientific_consensus_on_climate_change). To tackle this issue, many researchers have proposed various methods of CO₂ capture and sequestration, either directly from the atmosphere or from industrial or agricultural processes before the CO₂ is released into the atmosphere. For example, we could capture CO₂ from a flue, which is a pipe or channel that transports exhaust gases from industrial processes, such as power plants, cement production, or steel manufacturing. This captured CO₂ could then be compressed, transported, and stored underground in geological formations, or utilized in processes like enhanced oil recovery or the production of synthetic fuels and materials. 

Comparing CO₂ capture from the atmosphere or a flue, which process is more economical? Typically the more economical process is the one which requires less energy. [](#capture_co2) shows the relationship between the energy required to extract CO₂ from a gas mixture as a function of the CO₂ concentration. 


```{figure} ../images/entropy/co2_capture.png
:label: capture_co2
:align: center
:width: 500px

The dependence of the thermodynamic minimum energy to capture CO₂ from a gas mixture (kJ/kg CO₂) at 298 K on the initial CO₂ molar concentration. Adapted from @doi:10.1016/j.ccst.2023.100145.
```

There is a large energy difference between extracting CO₂ from the atmosphere versus extracting it from common flue gas concentrations, including NGCC, PCC, and IGCC. The energy difference is also somewhat large between these different power plants. In this chapter, we will learn how to construct this type of graph and thereby evaluate the thermodynamic viability of different CO₂ capture processes.



## The Thermodynamic Problem

The principles of thermodynamics set the minimum energy required to capture and separate CO₂ from other gases. Keep in mind that in the real world, the actual energy requirements are always higher - the thermodynamic minimum is the energy required in an ideal case without real world losses. We begin with a description of the problem:

- The atmosphere consists of many different gases, primarily N₂ and O₂. CO₂ is a trace atmospheric gas, taking up approximately ~0.04% by volume.
- The gas mixture in a smokestack of a coal combustion plant consist mainly of CO₂ (a few tens of %), H₂O, and N₂, with smaller amounts of CO, SO₂, NOₓ, and others.
- The CO₂ capture process will separate CO₂ from the other gases, depicted in [](#fig:problem_sep).

```{figure} ../images/entropy/problem_sep.png
:label: fig:problem_sep
:width: 400px
:align: center
Separating CO₂ from the other gases.
```

We can more precisely define our *initial* and *final* states. Thermodynamics does not define the time-dependent behavior of a system, so we can describe the problem using gas mixtures rather than flow rates. Specifically, we will consider a close volume of gas, potentially with internal partitioning as shown above.

The *initial* states is a fixed volume of CO₂ and other gases. The *final* state has the same volume, but is divided into two partitions, with a barrier between which does not allow any gas to flow between them. Our goal is to calculate the absolute minimum amount of energy required to perform this separation; the best-case scenario. We will show later that any process requiring less energy is thermodynamically impossible and is therefore a perpetual motion machine.

One last note on notation: we will often consider thermodynamic [state variables](wiki:State_variable), which are variables which are an inherent characteristic of a system in a particular state. Examples of state variables include:
- Temperature ($T$)
- Pressure ($P$)
- Volume ($V$)
- Gibbs free energy ($G$)
- Enthalpy ($H$)
- Entropy ($S$)

Some other variables we will come across that are not state variables include:
- Heat ($Q$)
- Work ($W$)

We will describe the total quantity of state variables using uppercase letters, for example $U$ is equal to the total internal energy in units of kJ. We will use a letter with a bar over it to represent a given quantity normalized by the system size, for example $\bar{U} = U/n$ is the total energy of the system divided by the system size given by the number of moles of a given species $n$, in units of kJ/mole. A lowercase letter represents the derivative of a given state variable with respect to $n$, which is often referred to as the partial molar quantity. For example, $u = \partial U / \ \partial n$ is the partial molar internal energy, also given in units of kJ/mole.



## The Ideal Gas Law

Before we introduce the First and Second Law of Thermodynamics, we first define an important relationship between the state variables of a gaseous system, namely pressure, volume, number of molecules, and temperature. The equation of state relating these variables is known as the Ideal Gas Law, which we will now derive.

Recall that pressure $P$ is defined as perpendicular force $F_\perp$ applied per unit area $A$
```{math}
:label: ideal_gas_law_1
P = \frac{F_\perp}{A},
```

and that momentum $\vec{p}$ is defined as mass $m$ times velocity $\vec{v}$

```{math}
:label:ideal_gas_law_2
\vec{p} = m \cdot \vec{v}.
```

Force $\vec{F}$ is defined as the change in momentum $d\vec{p}/dt$, which combined with Equation [](#ideal_gas_law_2) gives

```{math}
:label: ideal_gas_law_3
\vec{F} 
&= m \frac{d\vec{p}}{dt} \\
&= m \frac{d\vec{v}}{dt} \\
&= m \cdot \vec{a},
```

where acceleration $\vec{a}$ is equal to the time derivative of velocity $\vec{a}=d\vec{v}/dt$. If the change in momentum occurs in discrete time steps, we can also define the force in terms of the average rate $\lambda$ of these changes

```{math}
:label: ideal_gas_law_4
\vec{F} = \Delta \vec{p} \cdot \lambda,
```
where $\Delta \vec{p}$ is the momentum transfer per event.


```{embed} #entropymolecule
:label: entropymolecule
:remove-output: false
:remove-input: true
:width: 400px
:align: center
```

Now, consider a box containing gas molecules. As shown above, as each molecule bounces off the walls it will impart outward momentum to the walls. As we add more molecules to the box, the momentum transferred to the walls of the box will increase in proportion to the total mass $m$ of the gas. This transfer of momentum to the container walls is what we perceive as pressure. Next, we will derive the dependence of this pressure on the temperature $T$ and number of gas molecules $N$.

First, we make some assumptions, which define an ideal gas:
1. The molecule-wall collisions are elastic, meaning no energy is lost.
2. The molecules are much smaller than the box.
3. The molecules do not interact with each other.

First, we will calculate the force imparted by a single molecule along the $y$-axis
$$
F_y = \Delta p_y * \lambda
$$
The momentum change of the molecule along the $y$-axis will be its final momentum minus its initial momentum, while the momentum change of the wall is the same value in the opposite direction
$$
\Delta p_y 
&= -1(p_y^{\rm{final}} - p_y^{\rm{initial}}) \\
&= -1(m (-v_y) - (m  v_y)) \\
&= 2 m v_y.
$$

We can find the rate $\lambda$ at which this molecule will hit the wall by considering how long it must travel between strikes. For a cube with side length $l$, this rate is given by
$$
\lambda = \frac{v_y}{l}.
$$
The units of a rate should be events per second; checking the units here we get (length/time)/(length) = (1/time). If we combine these expressions, the force along the $y$-axis becomes
$$
F_y = \frac{2 m {v_y}^2}{l}.
$$

We next expand this expression to the full 3D box and to $N$ total molecules, giving a total force
$$
F_{\rm{total}}
&= \frac{2 m N}{l}({v_x}^2+{v_y}^2+{v_z}^2) \\
&= \frac{2 m N |\vec{v}|^2}{l}.
$$

The total area $A_{\rm{total}}$ of our box is equal to
$$
A_{\rm{total}} = 6 \, l^2
$$

We can combine these expressions with Equation [](#ideal_gas_law_1)to get
$$
\label{entropypressure1}
P 
&= 
\frac{2 m N |\vec{v}|^2}{l}
\frac{1}{6 \, l^2} \\
&= \frac{m N |\vec{v}|^2}{3 l^3} \\
&= \frac{m N |\vec{v}|^2}{3 V},
$$
where $V$ is the total box volume.

We next consider the internal energy $U$ of all $N$ molecules, which is equal to the sum of the kinetic energy of each molecule traveling with velocity $\vec{v}_i$
$$
U = \frac{1}{2} \sum_i^N m |\vec{v_i}|^2.
$$

The total energy can be therefore be rewritten in terms of the the @wiki:Expected_value (average value) of translational kinetic energy $⟨E_k⟩_{\rm{trans}} = \frac{1}{2}m⟨|\vec{v}|^2⟩$ over the population of all $N$ molecules
$$
\label{entropyenergy1}
U = N ⟨E_k⟩_{\rm{trans}}.
$$

Combining Equations [](#entropypressure1) and [](#entropyenergy1) gives 
$$
\label{eq:PUV}
P 
&= \frac{2}{3} \frac{N \frac{1}{2} m |\vec{v}|^2}{V} \\
&= \frac{2}{3} \frac{N ⟨E_k⟩_{\rm{trans}}}{V} \\
&= \frac{2}{3} \frac{U}{V}
$$

As a sanity check, we can confirm that $U/V$ has the same units as pressure
$$
\frac{U}{V}
&= \frac{\rm{energy}}{\rm{volume}} \\
&= \frac{\rm{force} \cdot \rm{length}}{\rm{length^3}} \\
&= \frac{\rm{force}}{\rm{length^2}} \\
&= \frac{\rm{force}}{\rm{area}} \\
$$

Rearranging Equation [](#eq:PUV) we get
$$
\label{eq:PV}
P \, V
= \frac{2}{3} U.
$$

We next rescale $U$ to a more convenient value that is easier to work with, by recognizing that $U \propto T$, i.e. the internal energy $U$ is proportional to temperature $T$. We can also select a prefactor for $T$ which scales with the boiling and freezing points of water, defining

$$
100 
= T_{\rm{H_2O}}^{\rm{boiling}}
- T_{\rm{H_2O}}^{\rm{freezing}},
$$

which is of course the temperature scale units of Centrigrade or Kelvins. With these units, we further define
$$
\label{eq:boltzmann}
U 
&= N ⟨E_k⟩_{\rm{trans}} \\
&= \frac{3}{2} k_B T.
$$
This is the origin of the Boltzmann constant $k_B$. 
This result ultimately comes from the equipartition theorem, which states that each degree of freedom contributes $\frac{1}{2} k_B T$ to the average energy, and the relationship between momentum transfer and pressure in kinetic theory. 
The molecules moving in 3 dimensions (and thus have 3 degrees of freedom) therefore contribute $\frac{3}{2} k_B T$ total energy.

If we substitute Equation [](#\label{eq:boltzmann}) into [](#eq:PV), we get
$$
\label{eq:PV_NkBT}
PV = N k_B T.
$$

The Boltzmann constant is related to another important constant, the universal gas constant $R$, by a factor of Avagadro's number $N_A$ (equal to one mole), giving
```{math}
:label: eq:gas_const_avagadro_boltzmann
R = N_A k_B
```
Here,Avogadro’s number $N_A$ represents the number of molecules in one mole, connecting the microscopic scale ($k_B T$) to macroscopic quantities ($R$).

We can then perform the final substitution into Equation [](#eq:PV_NkBT) to get
$$
P V 
= \frac{N}{N_A} R T.
$$
Recognizing that 
```{math}
:label: eq:num_moles
n = N / N_A,
```
is the number of moles of gas molecules, we can write:

:::{admonition} The Ideal Gas Law
:class: danger
```{math}
:label: eq:ideal_gas_law
P V = n R T
```
:::

In summary, this equation relates the pressure $P$, volume $V$, number of molecules $n$, and temperature $T$ of an ideal gas, and demonstrated that the pressure exerted on a container is due to the thermal motion of gas molecules.



<!-- ```{figure} #entropymolecule
:label: entropymolecule
:align: center
:width: 400px
``` -->


<!-- ```{embed} #entropymolecule
:label: entropymolecule
:remove-output: false
:remove-input: true
:width: 400px
:align: center
``` -->


 <!-- ![](#entropymolecule) -->

