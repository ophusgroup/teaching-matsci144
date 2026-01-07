---
title: Particle Size Effects 
numbering:
  enumerator: 4.8.%s
---

In real battery electrodes, phase transformations do not occur in an infinite bulk crystal. Instead, they occur in finite particles with surfaces and interfaces. As a result, surface energy and curvature can shift equilibrium and introduce an additional barrier to forming a new phase.

## Gibbs–Thomson shift of equilibrium

For a curved interface, the chemical potential of Li in a phase can be shifted relative to the flat-interface (bulk) limit. A minimal expression for this curvature-induced shift is

$$
\mu(r) \approx \mu(\infty) + \frac{2\gamma \Omega}{r},
$$

where $\gamma$ is an appropriate interfacial energy, $\Omega$ is the partial molar volume associated with inserting Li in that phase, and $r$ is a characteristic particle or interface radius. The key implication is that smaller particles can have measurably different equilibrium chemical potentials, which leads to size-dependent voltages.

Using $\Delta G = -n\mathscr{F}V$ (from [](batteries03_battery_voltage.md)), a change in chemical potential $\Delta \mu$ corresponds to a voltage shift of order

$$
\Delta V \sim \frac{\Delta \mu}{\mathscr{F}} \sim \frac{1}{\mathscr{F}}\frac{2\gamma \Omega}{r}.
$$

This is the battery-relevant form of the Gibbs–Thomson (Kelvin) effect developed in [](phase07_gibbs_thomson_kelvin.md).


## Nucleation barrier and nucleation overpotential

Two-phase electrodes require creating a new phase separated by an interface, which costs surface energy. Even when the two-phase equilibrium voltage is well-defined, a finite particle may require an additional driving force to nucleate the new phase.

A minimal way to express this is that nucleation requires overcoming a barrier associated with forming an interface. The extra driving force often appears experimentally as a **nucleation overpotential** (a voltage deviation from the equilibrium plateau) that depends on particle size, defect structure, and interface energies.

The thermodynamic origin of this barrier is the same competition developed in [](phase08_nucleation_ripening.md): a surface-energy penalty that scales with area ($\propto r^2$) versus a bulk driving force that scales with volume ($\propto r^3$). Smaller particles can both (i) shift the equilibrium via Gibbs–Thomson and (ii) change the ease of nucleation.

:::{seealso}
- In [](batteries07_twophase_battery.md), we treat the ideal two-phase plateau assuming bulk coexistence. This subsection explains why real electrodes can show size-dependent plateau shifts and hysteresis.
:::
