---
title: The Second Law of Thermodynamics
numbering:
  enumerator: 1.3.%s
---


## Heating an Object

Heating as gas means increasing the random motion of its molecules. This heating process involves two key components:
- Increasing the average velocity of the gas molecules, i.e. increasing their kinetic energy $\langle E_k \rangle$.
- Increasing the randomness or disorder of the gas molecules.

These two processes do not always occur together. For example, consider the boiling process where liquid water is converted to water vapor. The key difference between the liquid and gas phase of $\rm{H}_2\rm{O}$ is that water vapor is in some sense more "random" than liquid water. At the precise point of boiling, the water temperature does not change, but instead only the randomness or disorder changes. 

What do we mean by increasing disorder? Consider the simple example shown in [](#molecules_4_2_1), where indistinguishable atoms are placed on a 4x4 lattice grid, and each lattice site is identical. We consider 3 cases:
1. The atoms are clustered together into 1 group of 4.
2. The atoms form 2 clusters, each containing 2 atoms. For simplicity we will assume the clusters cannot be rotated.
3. The atoms are dispersed into 4 separate groups of 1.


```{figure} ../images/entropy/molecules_4_2_1.png
:label: molecules_4_2_1
:align: center
:width: 600px
Molecules on a grid, in clusters of 1, 2, and 4 atoms, with clusters allowed to occupy the same grid points. The different arrangements have different amounts of disorder (entropy).
```

The disorder of any system is related to the number of unique ways to arrange its contents. A larger number of ways to arrange the components of the system means the disorder is increased. For our system of 4 atoms, we can count the number of unique arrangements for the 3 cases we considered:
{style=lower-alpha}
1. 4 atom clusters - 9 ways.
2. 2 atom clusters - $(12)(12) = 144$ ways.
3. 1 atom clusters - $(16)(16)(16)(16) = 16^4 = 65536$ ways.

For simplicity, we have overcounted the number of unique arrangements by allowing the atoms to occupy the same lattice sites. We are also ignoring the cases in (2) where the atoms are arranged into clusters of 4 atoms, and the cases in (3) where the atoms are arranged into clusters of 2 or 4 atoms.

Next, we suppose that the average kinetic energy $\langle E_k \rangle$ for all molecules in these 3 cases are equal. which of these transformations will require more energy?
- $(1) \rightarrow (2)$
- $(1) \rightarrow (3)$

Recall that heating is the transfer of energy into a system that increases its temperature, disorder (randomness), or both, depending on the process. In this case, the kinetic energy $\langle E_k \rangle$ for all 3 cases are the same, and therefore the degree of heating depends on the change in disorder. Because the transformation $(1) \rightarrow (3)$ produces a much greater increase in disorder than $(1) \rightarrow (2)$, the conversion $(1) \rightarrow (3)$ requires more heating.

From the previous concepts, we can now define heating as the produce of the average kinetic energy $\langle E_k \rangle$ and the change in disorder:
```{math}
:label: eq:heating_temp_entropy_init
\rm{heating} = \langle E_k \rangle \, (\rm{change \,\, in \,\, disorder})
```

If we consider thermodynamic states, heat input moving from one state to another is $\Delta Q$, average kinetic energy $\langle E_k \rangle$ is equivalent to temperature $T$, and the change in disorder is represented by the change in entropy $\Delta S$. We will give a more quantitative definition for the change in entropy $\Delta S$ (change in disorder) later. Substituting these variables in Equation [](#eq:heating_temp_entropy_init) gives us:


If we consider thermodynamic states, heat input moving from one state to another is $\Delta Q$, average kinetic energy $\langle E_k \rangle$ is equivalent to temperature $T$, and the change in disorder is represented by the change in entropy $\Delta S$. We will give a more quantitative definition for the change in entropy $\Delta S$ (change in disorder) later. Substituting these variables into Equation gives us:

:::{admonition} Thermodynamic Relationship Between Heat and Entropy 
:class: danger 
The heat transferred to or from a system during a reversible process is proportional to its absolute temperature and the corresponding change in entropy:
```{math}
:label: heating_temp_entropy
\Delta Q = T \Delta S,
```
where $\Delta Q$ is the heat input into the system, $T$ is the absolute temperature (assumed constant during the process), and $\Delta S$ is the change in entropy of the system. 
:::




## Reversible and Irreversible Processes

We will use an example to show that Equation [](#heating_temp_entropy) is only correct under very specific conditions. Consider a box partitioned into two volumes, one of which contains CO$_2$ gas and the other vacuum. We assume the walls are imperable to matter and the system is closed and isothermal. We could alternatively describe this system as part of a larger isolated system with uniform temperature, or consider the system to be isolated instead of closed.


```{figure} ../images/entropy/CO2_sep.png
:label: CO2_sep
:align: center
:width: 700px
A partitioned box containing initially separated CO$_2$ and vacuum, where the wall is removed.
```

What will happen if we remove the partition? The CO$_2$ fas will expand to fill the entire box. This process is known as the **free expansion of gas**, and it increases the disorder of the system because the number of accessible positions of gas molecules has increased. We can formalize this increase in disorder as a change in entropy:
```{math}
\Delta S = S_\text{final} - S_\text{initial} > 0.
```

Unlike the case of isothermal gas expansion examined in the [Work Section](#sec:work), no work is done during this process as long as we assume the effort required to remove the partition is negligible. You can imagine popping a balloon, which causes the rubber wall separating the gas inside to mix with the surrounding gases with negligible work required to remove the partition. Thus, $W=0$.


Additionally, because the box is closed and isothermal, the internal energy of this system must remain constant, giving 
```{math}
\Delta U = 0,
```
where $\Delta U$ is the difference between the final and initial states. Applying these two constaints in the First Law of Thermodynamics (Equation [](#first_law_thermodynamics)) yields
```{math}
Q = \Delta U - W = 0.
```

This result conflicts with Equation [](#heating_temp_entropy) and our earlier statement that the entropy of the system will increase when the wall is removed. The resolution lies in the fact that Equation [](#heating_temp_entropy) applies only to **reversible processeses**,  which are defined as a process where the system can be reverted to the original state without doing additional work. By contrast, an **irreversible process** cannot return to its original state without external work. The free expansion of gas is an irreversible process because no work is required for the gas to expand, yet work is necessary to compress it back to its initial state.

The key characteristics of an irreversible processes:
- They occur in one direction only.
- They happen spontaneously without external work.

By contrast, a reversible process occurs so slowly that the system is essentially in equilibrium at all times. These are also called **quasistatic processes**. Note that while all reversible processes are quasistatic, not all quasistatic processes are reversible. For example, consider adding a valve to the partition in [](#CO2_sep) that allows one molecule to flow through at a time. This expansion happens quasistatically (near equilibrium), but it is still  irreversible because work would still be needed to return the gas to its original state.

To make Equation [](#heating_temp_entropy) correct for irreversible processes, we must consider that the entropy increase will exceed the heat added to the system. We can therefore modify this equation to be:
```{math}
Q \leq T \Delta S,
```
where the equality holds for reversible processes:

```{math}
Q_\text{rev} = T \Delta S.
```
Here, the subscript "rev" indicates a reversible process. This distinction ensures consistency with the Second Law of Thermodynamics, which governs the direction of energy transfer and the irreversibility of natural processes.


## Defining the Second Law 


:::{admonition} The Second Law of Thermodynamics 
:class: danger 
The total entropy of an isolated system can never decrease over time. In any real process, entropy either increases or, in the ideal case of a reversible process, remains constant. 
:::

This law governs the direction of thermodynamic processes, indicating that energy spontaneously disperses and systems evolve toward states of higher disorder or maximum entropy. There are several equivalent ways to state the Second Law:
- An isolated system always tends toward a configuration that maximizes disorder (entropy).
- The disorder of an isolated system increases due to spontaneous and irreversible processes.
- Heat transfer: the relationship $Q/T \leq \Delta S$ holds, where $Q_{\text{rev}} / T = \Delta S$ is the reversible limit.

While the First Law of Thermodynamics specifies the conservation of energy, the Second Law specifies the direction of thermodynamic processes. For example, the First Law states that the internal energy of a system is conserved but does not dictate the sequence of events. In contrast, the Second Law explains why gas expands into a vacuum when a barrier is removed, as this process increases the system’s entropy.

<!-- Connecting Reversibility and the Second Law -->

For a closed isothermal or isolated system, the First Law tells us that the internal energy is fixed:
```{math}
\Delta U = Q - W = 0 \quad \Rightarrow \quad Q = W.
```
The Second Law adds that the entropy of the system must either stay constant or increase:
```{math}
Q \leq T \Delta S,
```
with equality holding for reversible processes. Combining these principles gives the inequality for work in an isolated system:
```{math}
W \leq T \Delta S.
```

This inequality means that to decrease the entropy of a system (e.g., separating a gas mixture into its components), work must be done on the system ($W < 0$). For reversible processes, the minimum work required to achieve this is:
```{math}
W_{\text{min}} = T \Delta S = Q_{\text{rev}}.
```
However, any irreversibility increases the magnitude of the work required. For example, separating a gas mixture containing carbon dioxide, oxygen, and nitrogen into pure components requires work to reduce the entropy, and the work needed is greater for irreversible processes.

When discussing the minimum work required, it’s important to clarify what “minimum” means. The term $W_{\text{min}}$ refers to the minimum **magnitude** of work done on the system, not the minimum numerical value. From the system’s perspective, work is negative because it is being done on the system. From the surroundings’ perspective, work is positive, as the surroundings perform the work. Regardless of the sign convention, $W_{\text{min}}$ corresponds to the least amount of work needed to achieve the desired reduction in entropy under reversible conditions.

The Second Law provides the essential framework for understanding the directionality and feasibility of thermodynamic processes. It introduces the concept of entropy as a measure of disorder and establishes that increasing entropy is the natural tendency of isolated systems. Additionally, it sets fundamental limits on the work required to manipulate a system’s entropy, distinguishing between reversible and irreversible processes.


## Entropy

To evaluate the minimum work required to separate and capture carbon dioxide, we need to understand **entropy**, which quantifies the disorder of a system. Boltzmann’s definition of entropy provides a framework for this analysis by relating it to the number of ways molecules can be arranged within a system.

Consider a lattice gas, as illustrated in [](#lattice_gas), where $J$ represents the total number of lattice sites, and $N$ is the number of gas molecules. Each lattice position can be occupied by at most one molecule. The number $\Omega$ of possible ways to arrange $N$ molecules in $J$ sites is given by:
```{math}
\Omega = \frac{J!}{(J-N)!},
```
where $!$ is the @wiki:Factorial numerical operator. The factorial accounts for the sequential placement of molecules. However, if the molecules are indistinguishable, this calculation overestimates the arrangements by a factor of $N!$, the number of permutations of $N$ identical objects. Correcting for this over-counting, the total number of distinct configurations becomes:
```{math}
\Omega = \frac{J!}{(J-N)!N!}.
```
Here, $\Omega$ represents the number of microstates, or distinct configurations, of indistinguishable gas molecules in the lattice.

```{figure} ../images/entropy/lattice_gas.png
:label: lattice_gas
:align: center
:width: 600px
A gas consisting of $N$ molecules arranged on $J$ lattice sites.
```



### Entropy and Boltzmann's Postulate

Boltzmann postulated that the entropy $S$ of a system is directly related to the number of possible configurations $\Omega$:

```{math}
S = k_B \ln \Omega,
```

where $k_B$ is the Boltzmann constant ($1.38 \times 10^{-23} \ \mathrm{J K^{-1}}$). Substituting the expression for $\Omega$, we have:

```{math}
S = k_B \ln \left( \frac{J!}{(J-N)!N!} \right).
```

### Simplification Using the Stirling Approximation

For large values of $M$, the Stirling approximation provides:

```{math}
\ln M! \approx M \ln M - M.
```

Applying this approximation to simplify the entropy expression:

```{math}
S = k_B \big[ J \ln J - J - (J-N) \ln (J-N) + (J-N) - N \ln N + N \big].
```

Simplifying further:

```{math}
S = k_B \big[ J \ln J - (J-N) \ln (J-N) - N \ln N \big].
```

### Low-Density Gas Approximation

When $J \gg N$ (i.e., the number of lattice sites far exceeds the number of molecules), the first term approaches zero, as $\ln(1) = 0$. This assumption is valid for most gases under low-density conditions, except at very high pressures. In this limit, the entropy simplifies to:

```{math}
S = -N k_B \ln \left( \frac{N}{J} \right).
```

This expression describes the entropy of a low-density gas in a lattice and captures the relationship between the number of molecules, the available space, and the degree of disorder in the system.




