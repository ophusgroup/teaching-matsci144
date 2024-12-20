---
title: The Problem
numbering:
  enumerator: 1.%s
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
- The CO₂ capture process will separate CO₂ from the other gases:

```{image} ../images/entropy/problem_sep.png
:width: 400px
:align: center
```

We can more precisely define our *initial* and *final* states. Thermodynamics does not define the time-dependent behavior of a system, so we can describe the problem using gas mixtures rather than flow rates. Specifically, we will consider a close volume of gas, potentially with internal partitioning as shown above.

The *initial* states is a fixed volume of CO₂ and other gases. The *final* state has the same volume, but is divided into two partitions, with a barrier between which does not allow any gas to flow between them. Our goal is to calculate the absolute minimum amount of energy required to perform this separation; the best-case scenario. We will show later that any process requiring less energy is thermodynamically impossible and is therefore a perpetual motion machine.

One last note on notation: we will often consider thermodynamic state variables, which are variables which are an inherent characteristic of a system in a particular state. Examples of state variables include:
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



```{figure} #entropymolecule
:name: entropy-molecule
caption
```

% Embed both the input and output
```{embed} #entropy_molecule_volume
:remove-output: false
:remove-input: false
```

![](#entropymolecule)

