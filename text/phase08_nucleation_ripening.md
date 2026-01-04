---
title: Nucleation and Ripening
numbering:
  enumerator: 3.8.%s
---

Many transformations require forming a new phase separated by an interface. Even if the new phase is thermodynamically favored in bulk, creating an interface costs surface energy, producing a barrier to nucleation.

## 3.9.1 Classical nucleation (minimal model)

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

This is the key thermodynamic result: nucleation is controlled by a competition between a surface penalty ($r^2$) and a bulk driving force ($r^3$).

## 3.9.2 Ostwald ripening (driven by Gibbs–Thomson)

Because $\mu(r)$ increases as $r$ decreases (see [](phase07_gibbs_thomson_kelvin)), small particles are at higher chemical potential than large particles. Material tends to diffuse from small to large particles, coarsening the distribution over time.

A minimal statement of the directionality is:

- smaller $r$ $\Rightarrow$ larger $\mu$ $\Rightarrow$ higher equilibrium concentration/pressure,
- net transport from small to large reduces total free energy.

(If you want one quantitative law here, the classic LSW result is that the characteristic radius grows as $r(t)^3 - r(0)^3 \propto t$ under diffusion-limited ripening, but it is optional depending on how kinetics-heavy you want MATSCI 144 to be.)

:::{seealso}
- The curvature dependence used here comes directly from [Gibbs–Thomson / Kelvin](phase08_gibbs_thomson_kelvin.md).
- This “barrier + plateau” way of thinking will be useful later when interpreting phase transformations and metastability in [](batteries07_twophase_battery.md).
:::
