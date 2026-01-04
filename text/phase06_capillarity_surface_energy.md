---
title: Capillarity and Surface Energy
numbering:
  enumerator: 3.6.%s
---

Surface energy matters whenever an interface is created. In nanoscale systems the surface-to-volume ratio is large, so surface terms can compete with bulk thermodynamics.

We characterize an interface by its surface energy $\gamma$ (units: J/m$^2$). Creating new interfacial area $\dd A$ increases the free energy by

$$
\dd G_{\text{surface}} = \gamma\,\dd A.
$$

For a spherical particle of radius $r$, the surface contribution to the Gibbs free energy scales as

$$
G_{\text{surface}} = \gamma A = 4\pi r^2 \gamma,
$$

while the bulk free energy scales as volume, $G_{\text{bulk}}\propto r^3$. This scaling is the origin of many “size effects” in phase equilibrium.


A second key capillarity result is the Laplace pressure for a curved interface. For a spherical interface with radius $r$,

$$
\Delta P = P_{\text{inside}} - P_{\text{outside}} = \frac{2\gamma}{r}.
$$

A minimal derivation follows from a reversible, infinitesimal change in the droplet radius. Consider a spherical interface with surface energy $\gamma$ and radius $r$ that expands by $\dd r$.

The surface area is $A = 4\pi r^2$, so the surface-energy change is

$$
\dd G_{\text{surface}} = \gamma\,\dd A = \gamma \,(8\pi r\,\dd r).
$$

If the pressure inside exceeds the outside by $\Delta P$, then the mechanical work done by the system during this expansion is

$$
\dd W = \Delta P\,\dd V,
$$

with $V = \frac{4}{3}\pi r^3$ and $\dd V = 4\pi r^2 \dd r$, giving

$$
\dd W = \Delta P \,(4\pi r^2 \dd r).
$$

At mechanical equilibrium, an infinitesimal increase in radius does not change the total free energy, so the pressure work balances the surface-energy cost:

$$
\Delta P \,(4\pi r^2 \dd r) = \gamma \,(8\pi r\,\dd r).
$$

Canceling common factors yields

$$
\Delta P = \frac{2\gamma}{r}.
$$

This relation shows that curvature creates an effective pressure difference that grows as $1/r$, which is why nanoscale interfaces strongly modify equilibrium conditions.


<!-- A second key capillarity result is the Laplace pressure for a curved interface. For a spherical interface with radius $r$,

$$
\Delta P = P_{\text{inside}} - P_{\text{outside}} = \frac{2\gamma}{r}.
$$
 -->
:::{seealso}
- In [Evaporation](phase05_evaporation.md), we discuss equilibrium vapor pressure for a flat interface. Curvature modifies that equilibrium, which we develop next.
- In [Two-Phase Electrode and Solid Phase Transformations](batteries07_twophase_battery.md), the same surface/curvature ideas reappear as particle-size-dependent phase behavior.
:::
