---
title: 3.8 Nucleation and Ripening
numbering:
  enumerator: 3.8.%s
---

Many transformations require forming a new phase separated by an interface. Even if the new phase is thermodynamically favored in bulk, creating an interface costs surface energy, producing a barrier to nucleation.

## Classical nucleation (minimal thermodynamic model)

Consider forming a spherical nucleus of a new phase with radius $r$. The total free-energy change is modeled as

$$
\Delta G(r) = 4\pi r^2 \gamma + \frac{4}{3}\pi r^3 \Delta g_v,
$$

where $\gamma$ is the interfacial energy and $\Delta g_v$ is the bulk free-energy change per unit volume (negative when the new phase is favored).

The critical radius $r^*$ occurs where $\partial \Delta G/\partial r = 0$:

$$
r^* = -\frac{2\gamma}{\Delta g_v}.
$$

The barrier height is

$$
\Delta G^* = \frac{16\pi \gamma^3}{3(\Delta g_v)^2}.
$$

This is the key thermodynamic result: nucleation is controlled by a competition between a surface penalty ($\propto r^2$) and a bulk driving force ($\propto r^3$).

## Ostwald ripening (thermodynamic directionality)

Because $\mu(r)$ increases as $r$ decreases (see [](phase07_gibbs_thomson_kelvin.md)), small particles are at higher chemical potential than large particles. Material tends to diffuse from small to large particles, coarsening the distribution over time.

A minimal statement of the directionality is:

- smaller $r$ $\Rightarrow$ larger $\mu$ $\Rightarrow$ higher equilibrium concentration/pressure,
- net transport from small to large reduces total free energy.

## Preview for kinetics: LSW scaling

To connect this thermodynamic picture to a measurable time dependence, the Lifshitz–Slyozov–Wagner (LSW) theory considers *diffusion-limited* ripening in a dilute dispersion (particles far apart, approximately spherical) with a quasi-steady diffusion field around each particle.

The key prediction is a coarsening law for a characteristic particle radius:

$$
\langle r \rangle^3 - \langle r_0 \rangle^3 \propto t,
$$

often summarized as $\langle r \rangle \propto t^{1/3}$.

Interpretation:

- Gibbs–Thomson sets a higher equilibrium concentration adjacent to small particles than large ones.
- That concentration difference drives diffusion through the matrix.
- The result is a systematic shift of material from small to large particles, and a characteristic length scale that grows as $t^{1/3}$ under diffusion control.

:::{seealso}
- The curvature dependence used here comes directly from [Gibbs–Thomson / Kelvin](phase07_gibbs_thomson_kelvin.md).
- This “barrier + coarsening” framework will be useful later when interpreting two-phase coexistence, metastability, and microstructure evolution in [](batteries07_twophase_battery.md).
:::
