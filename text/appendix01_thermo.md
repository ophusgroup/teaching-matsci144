---
title: Thermodynamics Toolkit
numbering:
  enumerator: A.1.%s
---

(sign_conv)=
## Thermodynamic Sign Convention

In thermodynamics, defining the 1st law as $\Delta U = Q - W$ leads to the following sign convention:
- ($Q > 0$) Heat added to the system is positive.
- ($Q < 0$) Heat leaving the system is negative.
- ($W > 0$) Work is done **by the system** (onto its surroundings).
- ($W < 0$) Work done **to the system** (by its surroundings).

With this sign convention, applying positive pressure ($\Delta P > 0$) to reduce the volume of a system, we calculate the work to be $W = \int P \, \dd V$.
This results in a negative value for work ($W<0$), indicating that work is done on the system, increasing its internal energy $\Delta U > 0$.

:::{seealso}
This convention is used throughout the course, including:
- In [The First Law of Thermodynamics](entropy02_1st_law.md), where we define $Q$ and $W$ and track energy flows.
- In [Evaporation](phase05_evaporation.md), where pressure–volume work appears in phase-change reasoning.
:::

---

(reservoirs)=
## Control Variables: Reservoirs, Pistons, and “What Is Held Fixed?”

Thermodynamic potentials are most useful when a system is coupled to idealized “reservoirs” that hold certain variables fixed:

- **Thermal reservoir**: fixes temperature $T$ (system can exchange heat).
- **Mechanical reservoir / piston**: fixes external pressure $P$ (system can do $P\,\dd V$ work).
- **Particle reservoir**: fixes chemical potential(s) $\mu_i$ (system can exchange species $i$).

These idealizations provide an operational meaning for “constant $T$” and “constant $P$” and clarify which thermodynamic potential is minimized at equilibrium.

:::{seealso}
- In [Chemical Work](fuelcell_02_chem_work.md), we motivate the need for thermodynamic potentials beyond $U$.
- In [Gibbs Free Energy](fuelcell_03_gibbs_energy.md), we use realistic control conditions (fixed $T,P$) to motivate $G$.
:::

---

(potentials)=
## Thermodynamic Potentials and Natural Variables

A compact starting point is the differential form of internal energy for a simple compressible system:
$$
\dd U = T\,\dd S - P\,\dd V + \sum_i \mu_i\,\dd N_i.
$$

Legendre transforms swap extensive variables (e.g., $S,V$) for their conjugate intensive variables (e.g., $T,P$). The most common potentials in this course are:

:::{list-table} Thermodynamic potentials (single-phase, simple compressible system)
:header-rows: 1
:widths: 12 24 24 40

* - Potential
  - Definition
  - Natural variables
  - Differential
* - $U$
  - $U$
  - $S, V, \{N_i\}$
  - $\dd U = T\,\dd S - P\,\dd V + \sum_i \mu_i\,\dd N_i$
* - $H$
  - $H = U + PV$
  - $S, P, \{N_i\}$
  - $\dd H = T\,\dd S + V\,\dd P + \sum_i \mu_i\,\dd N_i$
* - $F$
  - $F = U - TS$
  - $T, V, \{N_i\}$
  - $\dd F = -S\,\dd T - P\,\dd V + \sum_i \mu_i\,\dd N_i$
* - $G$
  - $G = U + PV - TS$
  - $T, P, \{N_i\}$
  - $\dd G = -S\,\dd T + V\,\dd P + \sum_i \mu_i\,\dd N_i$
:::

:::{seealso}
- In [Gibbs Free Energy](fuelcell_03_gibbs_energy.md), we focus on $G(T,P,\{N_i\})$ for chemical systems.
:::

---

(minimization)=
## Equilibrium Criteria via Minimization

When the environment fixes particular control variables, equilibrium corresponds to minimizing the relevant potential at fixed values of those variables:

- Fixed $S,V,\{N_i\}$: equilibrium minimizes $U$.
- Fixed $T,V,\{N_i\}$: equilibrium minimizes $F$.
- Fixed $S,P,\{N_i\}$: equilibrium minimizes $H$.
- Fixed $T,P,\{N_i\}$: equilibrium minimizes $G$.

For most chemistry/electrochemistry in this course, the default control conditions are fixed $T$ and $P$, so $G$ is the central potential.

:::{seealso}
- In [Chemical Equilibrium](fuelcell_04_chem_eq.md), we apply $G$ minimization at fixed $T,P$.
- In [Two-Phase Electrode and Solid Phase Transformations](batteries07_twophase_battery.md), we use $G$ to interpret phase coexistence.
:::

---

(chem_pot)=
## Chemical Potential: Definition and Interpretation

Chemical potential is defined (for species $i$) as the partial derivative of $G$:
$$
\mu_i \equiv \left(\frac{\partial G}{\partial N_i}\right)_{T,P,N_{j\ne i}}.
$$

Interpretation:
- $\mu_i$ is the incremental Gibbs free energy cost of adding species $i$ at fixed $T,P$.
- Under exchange of species $i$ between phases, equilibrium requires equal chemical potentials:
$$
\mu_i^{(\alpha)} = \mu_i^{(\beta)} = \cdots
$$

:::{seealso}
- In [Chemical Equilibrium](fuelcell_04_chem_eq.md), chemical potential provides a compact statement of equilibrium.
- In [Chemical Potential of "Li" (in Positive Electrode)](batteries04_cathode_Li.md) and [Chemical Potential of Li (in Negative Electrode)](batteries05_anode_Li.md), we interpret voltage using $\mu_{\mathrm{Li}}$.
:::

---

(ideal_mix)=
## Ideal Mixtures: Why Logs of Composition Appear

For ideal mixtures, chemical potentials take a log(activity) form:
$$
\mu_i = \mu_i^\circ(T,P) + RT\ln a_i,
$$
where $a_i$ is the activity. In an ideal solution, $a_i \approx x_i$ (mole fraction). In an ideal gas, $a_i \approx p_i/p^\circ$.

The $\ln(\cdot)$ term is the thermodynamic fingerprint of configurational entropy and underlies:
- equilibrium constants and the law of mass action,
- concentration dependence of thermodynamic driving forces,
- lattice-gas / vacancy analogies in solids.

:::{seealso}
- In [The Second Law of Thermodynamics](entropy03_2nd_law.md), we connect entropy to free energy and spontaneous direction.
- In [Law of Mass Action](fuelcell_08_law_mass_action.md), we convert $\Delta G$ into equilibrium constants and composition dependence.
:::

---

(reaction_mass_action)=
## Reaction Free Energy and the Law of Mass Action

For a reaction $\sum_i \nu_i A_i = 0$ (products have $\nu_i>0$, reactants have $\nu_i<0$), define the reaction Gibbs free energy:
$$
\Delta_r G = \sum_i \nu_i \mu_i.
$$

Using the ideal-mixture form in {ref}`ideal_mix`, we obtain:
$$
\Delta_r G = \Delta_r G^\circ + RT\ln Q,
$$
where the reaction quotient is $Q=\prod_i a_i^{\nu_i}$.

At equilibrium, $\Delta_r G=0$, so:
$$
K = \exp\!\left(-\frac{\Delta_r G^\circ}{RT}\right).
$$

:::{seealso}
In [Law of Mass Action](fuelcell_08_law_mass_action.md), we apply these relations to fuel-cell chemistry.
:::

---

(voltage_bridge)=
## Electrochemical Work and Voltage: Connecting $\Delta G$ to $V$

At fixed $T,P$, the maximum non-$P\,\dd V$ work obtainable from a process is:
$$
W_{\mathrm{nonPV,max}} = -\Delta G.
$$

For an electrochemical process transferring $n$ electrons, electrical work is $W_{\mathrm{elec}} = n F V$, so:
$$
\Delta G = -n F V.
$$

:::{seealso}
- In [Voltage of a Fuel Cell](fuelcell_06_voltage_fuelcell.md), we derive and apply $\Delta G=-nFV$.
- In [Voltage of a Battery](batteries03_battery_voltage.md), we reuse the same bridge for battery electrodes.
:::

---

(summary)=
## Summary

- Use $G(T,P,\{N_i\})$ as the default potential for chemical and electrochemical systems.
- Chemical potentials $\mu_i$ are partial derivatives of $G$; equilibrium under exchange requires equality of $\mu_i$.
- Log(activity) forms arise from configurational entropy and enable mass-action relations.
- Fuel-cell and battery voltages follow directly from $\Delta G=-nFV$.
