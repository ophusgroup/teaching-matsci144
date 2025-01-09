---
title: Chemical Work
numbering:
  enumerator: 2.2.%s
---

From {numref}`Equation {number} <work_pressure_volume>`, we know that the _mechnical work_ is defined as $\int P dV$. However, this is not the only type of work available. Let us consider a thought experiment, as shown in [](#thought-exp). The hydrogen and oxygen gases (both assumed to be ideal gas) are put inside an isolated container (impermeable to the exchange of energy and matter), and the two gases are separated by a barrier (highlighted in purple) that is impermeable to the exchange of matter. Both sides are at the same temperature ($T_0$) and pressure ($P_0$). Let's now break the barrier. Intuitively, we would suppose the following chemical reaction to happen

$$
2\mathrm{H}_2+\mathrm{O}_2 \rightarrow 2\mathrm{H}_2\mathrm{O}
$$

We highlight 3 points here:

1. The total number of hydrogen and oxygen atoms remains fixed, as a result of the outer container wall (shown in black color) is impermeable to exchange of mass.
(point-2)=
2. Two moles of hydrogen gas react with one mole oxygen gas to form one mole of water. The chemical bonds rearrange while conserving the total number of atoms, not the number of molecules.
(point-3)=
3. If we assume this reaction to be spontaneous (a one-sided reaction where the precursors automatically combine to yield the product without added energy or being influenced by any "external factor"), it is necessarily exothermic (heat is released) and therefore we expect the temperature inside the container to increase.

```{figure} ../../images/fuel-cell/OHbarrier.png
:label: thought-exp
:align: center
:width: 500px

Thought experiment to demonstrate different types of work
```

As defined in [](#tab:systems), for an isolated system, neither exchange of energy (heat and work) nor matter
is allowed with the surroundings. Thus, we know $Q=W=0$, and with the First Law we can conclude
$\Delta U=Q-W=0$. Since there is no change in the internal energy, there should be *no change in the temperature* if
we assume the gases behave ideally. This contradicts [Point 3](#point-3) since an exothermic reaction would release heat, raising
the temperature inside the container. However, since the First Law must be observed (i.e., temperature should increase),
our previous definition of work ($W=\int P dV$) is incomplete, and we are missing other contributions to $W$.

If we look at [Point 2](#point-2), we can see that so far we have not explicitly considered the effect of chemical bond rearrangement
(i.e., the energy transfer that comes with breaking and form chemical bond). This missing contribution is related to such energy transfer called **chemical work**.

:::{admonition} Definition of Chemical Work
:class: danger
Chemical work is the transfer of potential energy contained in the chemical bonds of materials to the kinetic
energy of a system. Its mathematical definition is
```{math}
:label: chemical_work_def
\mathrm{Chemical\;Work}=-\int \mu dn
```
where $\mu$ is the **chemical potential** and $dn$ is the differential change in number of moles. The minus sign
in front of the integral is to ensure consistency with our sign conventions, where the formation of new species
(i.e., $dn>0$) means the formation of new chemical bonds, which releases heat. This is similar to the mechanical work case where the piston is being compressed, where the work is being done on the system, increasing the temperature, and vice versa.
:::

Just like mechanical work that can be converted into internal energy to increase the temperature (e.g., compressing piston to increase the air temperature inside), chemical work can also increase the temperature
of a system since temperature is a measurement of the average kinetic energy of the atoms inside such system.
Like $T$ and $P$, the chemical potential is independent of the quantity of the materials. It depends upon the
potential energy stored within chemical bonds, as well as bond configuration within the system. We will introduce
a more rigorous definition of the chemical potential later on.

For now, the chemical potential defined in [Equation %s](#chemical_work_def) is only concerned with a single chemical species. For our example system, we have 3 different species: the hydrogen gas, the oxygen gas, and water. For a more complete description of all types of possible chemical work conversions, we can sum the chemical work for the $i^{\text{th}}$ species of the system as in [Equation %s](#multi_species_chemwork)

```{math}
:label: multi_species_chemwork
\mathrm{Chemical\;Work}=-\sum_i \left(\int \mu_i dn_i\right)
```

By incorporating both mechanical and chemical work, we can write an expanded First Law of thermodynamics for a reversible system (i.e., where $Q_{\text{rev}}=\int T dS$) in [Equation %s](#expanded_first_law)

$$
\label{expanded_first_law}
\begin{aligned}
\Delta U_{\text{rev}} &= Q_{\text{rev}} - W \\
&= \int T dS - \left(\int P dV - \sum_i \int \mu_i dn_i\right) \\
&= \int T dS - \int P dV + \sum_i \int \mu_i dn_i
\end{aligned}
$$

The corresponding differential form is
```{math}
:label: expanded_first_law_diff
dU_{\text{rev}}=T dS - P dV + \sum_i \mu_i dn_i
```

In summary, [Equation %s](#expanded_first_law_diff) says for a **reversible** change in the internal energy of the system, the first term is the heat added to or removed from the system; the second term is the mechanical work done on or by the system; the third term is the chemical energy transferred in or out of the system via the rearrangement of bonds and/or the exchange of mass.

Remember that $U$ is a state function, so $dU_{\text{rev}}=dU_{\text{irrev}}$ since the internal energy only depends on the initial and final state of the process, not the path taken (whether irreversible or reversible). It is worth emphasizing that in the irreversible case, we can neither conclude $W=\int P dV -\sum_i \int \mu_i dn_i$ nor $Q=\int T dS$. However, we can always find a reversible process with the same initial and final states as the irreversible process such that $dU_{\text{rev}}=dU_{\text{irrev}}$, but each individual term in the reversible equation does not necessarily needs to be equal to its counterpart in the irreversible equation. As a result, there is no reason to explicitly differentiate between irreversible and reversible processes when it comes to change in the internal energy.

```{math}
:label: expanded_first_law_final
dU=dU_{\text{rev}}=dU_{\text{irrev}}=T dS - P dV + \sum_i \mu_i dn_i
```