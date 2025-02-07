---
title: 3.3 Phases of Water
numbering:
  enumerator: 3.3.%s
---


Understanding phase transitions is critical in applications like geothermal power, heat engines, and even planetary atmospheres. In the next sections, we will explore the role of phase changes in engineering applications.


## The Three Phases of Water

Water is essential to all known forms of life and one of the most abundant substances on Earth, covering over 70% of the planet’s surface.
It also plays a critical role in thermodynamics as the working fluid in many heat engines due to its high heat capacity, phase transition properties, and non-toxicity.

Water exists in three phases:
- Solid (ice)
- Liquid (water)
- Gas (water vapor). 

The stability of each phase depends on temperature and pressure, which can be analyzed through the **specific Gibbs free energy** $\bar{G}$ of water, shown in [](#fig:water_gibbs_phases). 
A specific quantity is represented with a bar over the variable, and is equal to that quantity divided by the number of mols $n$, for example $\bar{G} = G/n$
Equation [](#eq:gibbs_free_energy) derived an expression for the Gibbs free energy, which has a specific quantity equivalent:

```{math}
\bar{G} = \bar{H} - T \bar{S}
```

where $\bar{H}$ is the specific enthalpy, $T$ is temperature, and $\bar{S}$ is the specific entropy . The slope of $G(T) $ is equal to $-\bar{S}$, and the y-intercept represents $\bar{H}$. To simplify, we assume $\bar{H}$ and $\bar{S}$ do not depend on temperature.


```{figure} ../images/phase/solidliquidvapor.pdf
:label: fig:water_gibbs_phases
:align: center
:width: 400px

The specific Gibbs free energies $\bar{G}$ for the three phases of water as a function of temperature $T$.
The phase with the lowest value of $\bar{G}$ at a given $T$ is stable.
```

### Enthalpy & Bond Energy

The enthalpy $\bar{H}$ of each phase represents the strength of intermolecular bonds, and is given by the y-intercept of [](#fig:water_gibbs_phases).
Since water molecules in the solid phase (ice) are strongly hydrogen-bonded in a crystalline lattice, their enthalpy is lower than in liquid water, where the molecules move more freely due to their weaker chemical bonds. 
In the gaseous phase, the molecules are unbound and have the highest enthalpy. We can represent this relationship as

```{math}
\bar{H}_{\text{solid}} 
< 
\bar{H}_{\text{liquid}} 
< 
\bar{H}_{\text{gas}}
```

During **melting**, heat is absorbed to break intermolecular bonds to transform from the solid to the liquid phase.
Similarly, **vaporization** from the liquid to the gas phase requires additional energy input to separate molecules into a gas.
Both processes are **endothermic**. 


### Entropy & Molecular Disorder

Entropy measures molecular disorder. 
In solid ice, molecules are arranged in a fixed lattice which is highly regular. 
In liquid water, the molcules are close together but able to move somewhat freely.
In a gaseous water vapor, the molecules are highly disordered and move independently. 
This explains why the slope of $\bar{G}(T)$ shown in [](#fig:water_gibbs_phases) is most negative for gases, less negative for liquids, and least negative for solids. We can quantify this ordering as

```{math}
\bar{S}_{\text{solid}} 
<
\bar{S}_{\text{liquid}}
<
\bar{S}_{\text{gas}}
```

Entropy is always positive because it represents the number of ways molecules can be arranged. 
The relative entropy differences affect phase behavior.


### Phase Stability & Transitions

A system in equilibrium **minimizes Gibbs free energy**, as we saw in the [](#sec:chem_eq) chapter.
At the different temperatures shown in [](#fig:water_gibbs_phases), the most stable phase is the one with the lowest $\bar{G}$:


```{csv-table} 
**$T < T_m$**, Ice is stable.
**$T = T_m$**, Ice and liquid water coexist (melting point).
**$T_m < T < T_b$**, Liquid water is stable.
**$T = T_b$**, Liquid water and vapor coexist (boiling point).
**$T > T_b$**, Water vapor is stable.
```

At **phase transition points** (melting or boiling), two phases coexist in equilibrium, meaning their Gibbs free energies are equal:

```{math}
\bar{G}_{\text{solid}} 
= 
\bar{G}_{\text{liquid}} \quad \text{at} \quad T_m
```

```{math}
\bar{G}_{\text{liquid}} 
= 
\bar{G}_{\text{gas}} \quad \text{at} \quad T_b
```

A few notes for advanced readers:

- Supercooled liquid water can exist below $T_m$, but it is not in equilibrium and will freeze if nucleation sites become available. See [](wiki:Supercooling) for more information.

- Water ice can also directly transform into the gas phase at low partial pressures, a process known as sublimination. See [sublimation](wiki:Sublimation_(phase_transition)) for more information.

- There are actually at 19 known phases of solid crystalline water ice. When we colloquially talk about water ice, we typically mean the hexagonal form of ice stable at ambient pressure below $0^\circ$C known as $I_h$.
See [](wiki:Ice) and [](wiki:Phases_of_ice) for more information.




## Phase Transitions in Water

### Gibbs Energy of Boiling

At phase transition temperatures, heat is added or removed **without changing temperature**, leading to a transformation between phases. Consider **boiling** liquid water into vapor in an isolated system.

[](fig:water_boiling) shows the **total Gibbs free energy** before and after boiling. Initially, the system contains only liquid water. As boiling progresses, liquid converts to gas, and the system moves toward 100% vapor.


```{figure} ../images/phase/GibbsGasLiquid.pdf
:label: fig:water_boiling
:align: center
:width: 400px

Magnitude of Gibbs free energy before and after boiling. The sign of the Gibbs free energy depends on the value of enthalpy as the reference state.
```


Since boiling occurs at constant temperature and pressure, the Gibbs free energy change is:

```{math}
dG = -S dT + V dP + \sum_i \mu_i d n_i
```

At constant $T$ and $P$, this simplifies to:

```{math}
dG = \sum_i \mu_i d n_i
```
where $\mu_i$ is the chemical potential of species $i$. The chemical reaction which represents the coexistence of the liquid and gas phases of water is

```{math}
\text{H}_2\text{O} \, (\text{liquid}) 
\rightleftharpoons
\text{H}_2\text{O} \, (\text{gas}) 
```

We can write the total variation in Gibbs energy $dG$ as the combination of variation in the liquid and gas phases:

```{math}
dG
=
dG_\text{liquid}
+ 
dG_\text{gas}
```

Additionally, at equilibrium the chemical potentials of coexisting phases must be equal:

```{math}
\mu_{\text{liquid}} = \mu_{\text{gas}}
```

Since the total number of molecules remains constant:

```{math}
d n_{\text{liquid}} = - d n_{\text{gas}}
```

Substituting these conditions:

```{math}
:label: eq:gibbs_gas_liquid
\begin{aligned}
dG_\text{gas} 
&= \mu_\text{gas} dn_\text{gas} 
\\
dG_\text{liquid} 
&= \mu_\text{liquid} dn_\text{liquid} 
\\
&= -\mu_\text{gas} dn_\text{gas} 
\end{aligned}
```

You may wonder how the chemical potentials can be the same, yet the values of $dG$ have opposite sign. The answer lies in the molar change values $dn$. These values must have opposite sign, since each mol of boiling water will reduce the number of liquid phase molecules by 1 mol, while increasing the number of gas phase molecules by 1 mol.


The above derivations show that at equilibrium, the total Gibbs free energy does not change as long as temperature and pressure remain constant.


We can now complete [](fig:water_boiling). During boiling, the Gibbs free energy of both phases will vary following Equation [](#eq:gibbs_gas_liquid). This is shown schematically in [](#fig:water_boiling_full). 



```{figure} ../images/phase/GibbsGasLiquidFull.pdf
:label: fig:water_boiling_full
:align: center
:width: 400px

Magnitude of Gibbs free energies during boiling. 
```

As liquid water boils, its total Gibbs free energy decreases proportionally to the number of mols in the liquid phase. Simultaneously, water vapor forms and its Gibbs free energy increases. However, since the chemical potentials are equal at $T_b$, the total Gibbs free energy remains constant.



### Gibbs Energy of Freezing

The Gibbs energy path during the transformation of liquid water to solid ice is more complex than that of boiling. The primary reason is that transformation to solid ice requires **nucleation** of tiny initial crystalline grains of ice. The extra energy required for this process means that in practice, typically liquid water may need to be supercooled to below the freezing point before the transformation can begin. 
These complexities however are beyond the scope of this course.




