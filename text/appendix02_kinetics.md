---
title: Bridge to Kinetics
numbering:
  enumerator: A.2.%s
---

(bridge_why)=
## Why thermodynamics appears inside kinetic models

Kinetics answers the question “how fast?” but it cannot be posed without a thermodynamic statement of “which way?” and “how strongly?” In practice, kinetic models are built from three ingredients:

1. **Driving force** (thermodynamics): differences in chemical potential, or in Gibbs free energy, that favor one state over another.
2. **Transport law** (near-equilibrium response): how fluxes respond to chemical potential gradients (diffusion) and how interfaces respond to supersaturation (attachment).
3. **Activation barrier** (rate theory): the Arrhenius sensitivity of rates to temperature via an activation free energy.

In MATSCI 144, you already used (1) repeatedly (e.g., $\Delta G$ sets the maximum useful work and voltage). In MATSCI 145, the same $\mu$ and $G$ concepts become inputs to diffusion, nucleation, growth, and ripening.

:::{seealso}
- Review of thermodynamic control variables, potentials, and chemical potential: [Thermodynamics Toolkit](appendix01_thermo.md)
- Surface/size thermodynamics introduced in Module 3: [Capillarity and surface energy](phase07_capillarity_surface_energy.md), [Gibbs–Thomson / Kelvin](phase08_gibbs_thomson_kelvin.md), [Nucleation and ripening](phase09_nucleation_ripening.md)
:::

---

(bridge_mu_driving)=
## Chemical potential as the universal driving force

A compact way to write “thermodynamic driving force” is in terms of chemical potential.

- **Across phases**: at equilibrium, a species has equal chemical potential in each phase:
  $$
  \mu_i^{(\alpha)} = \mu_i^{(\beta)}.
  $$
  Departures from this equality create a driving force for transformation.

- **Across space**: if $\mu_i$ varies with position, the system can reduce $G$ by moving material down the chemical potential gradient. That is the thermodynamic origin of diffusion and many transport laws.

- **At curved interfaces**: surface energy raises $\mu$ for small radii, leading to size-dependent equilibrium (Kelvin / Gibbs–Thomson). This directly feeds into nucleation barriers and ripening.

---

(bridge_linear_response)=
## Thermodynamics to diffusion: flux driven by gradients in $\mu$

A useful near-equilibrium statement is that flux is proportional to the gradient of chemical potential:

$$
\bm{J}_i = -M_i c_i \, \nabla \mu_i,
$$

where $M_i$ is a mobility and $c_i$ a concentration (or number density). This form is powerful because it remains valid beyond “ideal” diffusion: if you can write $\mu_i(c_i)$, you can write a transport law.

### Recovering Fick’s first law (ideal solution)

For an ideal solution (or dilute species), chemical potential has a log form:

$$
\mu_i = \mu_i^\circ + RT\ln c_i,
$$

so

$$
\nabla \mu_i = RT\, \nabla \ln c_i = RT\, \frac{\nabla c_i}{c_i}.
$$

Substitute into the flux law:

$$
\bm{J}_i = -M_i c_i (RT)\frac{\nabla c_i}{c_i} = -(M_i RT)\nabla c_i.
$$

Define the diffusion coefficient $D_i \equiv M_i RT$ (Einstein relation), giving Fick’s first law:

$$
\bm{J}_i = -D_i\,\nabla c_i.
$$

### Fick’s second law

Combine flux with conservation of mass (continuity):

$$
\frac{\partial c_i}{\partial t} = -\nabla\cdot \bm{J}_i,
$$

to obtain, for constant $D_i$,

$$
\frac{\partial c_i}{\partial t} = D_i \nabla^2 c_i.
$$

:::{seealso}
- Vacancy thermodynamics that motivates $\ln c$ terms: [Dilute defects and vacancies](appendix01_thermo.md#dilute-vacancies)
- Diffusion topics emphasized in the MATSCI 145 reader include boundary conditions, defect-mediated diffusion, and interdiffusion (e.g., Kirkendall and Darken relations).
:::

---

(bridge_arrhenius)=
## Activation barriers: why rates are exponentially sensitive to $T$

Most atomic-scale kinetic steps are thermally activated (diffusion hops, attachment/detachment at an interface, reactions). A minimal rate expression is Arrhenius:

$$
k = k_0\,\exp\!\left(-\frac{\Delta G^{\ddagger}}{RT}\right),
$$

where:
- $k_0$ is a prefactor (attempt frequency × geometric factors),
- $\Delta G^{\ddagger}$ is an activation free energy (not the thermodynamic driving force).

Thermodynamics and kinetics appear together because the **net** rate of a forward/backward pair is the difference of two activated rates, whose ratio is set by the free-energy difference between states.

---

(bridge_gibbs_thomson)=
## Size-dependent equilibrium: Kelvin / Gibbs–Thomson

A key result is that curvature increases the chemical potential of a phase relative to a flat interface. For a spherical particle (or droplet) with radius $r$:

$$
\mu(r) \approx \mu(\infty) + \frac{2\gamma \Omega}{r},
$$

where $\gamma$ is an appropriate interfacial energy and $\Omega$ is a molar (or atomic) volume.

Consequences:
- **Small objects are less stable** (higher $\mu$), so they dissolve more readily.
- **Equilibrium solubility and vapor pressure increase** as $r$ decreases (Kelvin relation).
- **Nucleation is harder at small length scales** because creating curved interfaces is costly.

:::{seealso}
- Derivation and physical interpretation: [Gibbs–Thomson / Kelvin](phase08_gibbs_thomson_kelvin.md)
:::

---

(bridge_nucleation_thermo)=
## Nucleation: combining bulk driving force with surface cost

The thermodynamic core of nucleation is the competition between:
- a **bulk** free-energy change that favors the new phase (volume term),
- a **surface** free-energy penalty to create an interface (area term).

For a spherical nucleus of radius $r$:

$$
\Delta G(r) = \frac{4}{3}\pi r^3\,\Delta g_v + 4\pi r^2\gamma,
$$

where $\Delta g_v$ is the Gibbs free energy change per unit volume for forming the new phase (negative when the new phase is thermodynamically favored) and $\gamma$ is the relevant interfacial energy.

Setting $\partial \Delta G/\partial r = 0$ gives the critical radius:

$$
r^* = -\frac{2\gamma}{\Delta g_v}.
$$

Substituting $r^*$ back gives the nucleation barrier:

$$
\Delta G^* = \frac{16\pi\gamma^3}{3\,\Delta g_v^2}.
$$

These expressions make the control knobs explicit:
- increasing supersaturation or undercooling makes $\Delta g_v$ more negative (smaller $r^*$ and smaller $\Delta G^*$),
- lowering $\gamma$ (e.g., via a substrate) also lowers $\Delta G^*$.

---

(bridge_nucleation_rate)=
## Nucleation rate: turning a barrier into a timescale

A minimal form for the homogeneous nucleation rate is:

$$
J = J_0\,\exp\!\left(-\frac{\Delta G^*}{RT}\right),
$$

where $J_0$ packages kinetic factors (attempt frequencies, diffusion supply, Zeldovich factor, etc.). The exponential sensitivity to $\Delta G^*$ is why small changes in supersaturation or temperature can switch nucleation “on” or “off”.


### Heterogeneous nucleation (site-assisted)

In heterogeneous nucleation, the nucleus forms at a pre-existing site that lowers the free-energy barrier by reducing the amount of *new* interface that must be created and/or by lowering the effective interfacial energies (through better wetting, epitaxy, or local chemistry). The result is that heterogeneous sites can dominate nucleation even when they are rare, because the nucleation rate depends exponentially on the barrier.

A common minimal model is nucleation on a flat surface, where the nucleus forms as a spherical cap. In this case, the barrier is reduced by a geometric/wetting factor $f(\theta)$:

$$
\Delta G^*_{\mathrm{het}} = f(\theta)\,\Delta G^*_{\mathrm{hom}},
\quad 0 < f(\theta) < 1,
$$

where $\theta$ is the contact angle set by interfacial energy balance (better wetting $\rightarrow$ smaller $\theta$ $\rightarrow$ smaller $f(\theta)$).

More generally, “site-assisted” nucleation can occur at many common microstructural features:

- **Free surfaces and interfaces** (substrates, container walls, electrode surfaces, liquid–vapor interfaces).
- **Steps, edges, and corners** on surfaces (line/vertex sites), which can reduce the barrier more strongly than a flat surface because the nucleus can share more existing interface.
- **Grain boundaries and phase boundaries**, which provide high-energy regions and structural templates for a new phase.
- **Dislocations and strain fields**, which can locally lower the elastic mismatch penalty and/or attract solute (changing the local driving force).
- **Vacancies, pores, and voids**, which act as internal surfaces and can strongly favor nucleation.
- **Second-phase particles / impurities / “seeds”**, where epitaxy or favorable surface chemistry lowers the interfacial energy (common in precipitation and nanoparticle synthesis).

The thermodynamic takeaway is that heterogeneous nucleation changes the geometry and interfacial-energy bookkeeping in $\Delta G(r)$, reducing the effective barrier and shifting when nucleation becomes observable on experimental timescales.

:::{seealso}
- Capillarity quantities that enter $\gamma$ and wetting: [Capillarity and surface energy](phase06_capillarity_surface_energy.md)
- Thermodynamic cases and kinetic implications: [Nucleation and ripening](phase08_nucleation_ripening.md)
:::


---

(bridge_surfaces)=
## Surfaces: thermodynamics that controls both nucleation and growth

Surface energy enters kinetics in three distinct ways:

1. **Equilibrium shapes**: anisotropic $\gamma(\hat{n})$ sets equilibrium crystal shapes (Wulff construction).
2. **Nucleation barriers**: $\gamma$ determines $r^*$ and $\Delta G^*$.
3. **Growth kinetics**: the interface can impose an additional attachment barrier even when diffusion is fast.

A general thermodynamic definition is:

$$
\gamma \equiv \left(\frac{\partial G}{\partial A}\right)_{T,P},
$$

i.e. the free-energy cost per unit area of creating interface.

:::{seealso}
- Surfaces are a full chapter in the MATSCI 145 reader (broken-bond model, Wulff construction, and the role of surface energy in nucleation and growth).
:::

---

(bridge_growth)=
## Growth: diffusion-limited vs attachment-limited regimes

After nucleation, growth consumes supersaturation. Two limiting cases are common:

### Diffusion-limited growth
The bottleneck is moving material through the surrounding phase to the interface. A signature scaling is that growth slows as gradients relax; for many simple situations this yields:

$$
r \propto \sqrt{t}.
$$

### Attachment-limited growth
The bottleneck is incorporation at the interface (e.g., an attachment barrier or slow surface reaction). Growth rate is then controlled by an interfacial kinetic coefficient and can be less sensitive to particle size than the diffusion-limited case.

Real systems often cross over between these regimes as $r$ changes or as transport conditions change.

---

(bridge_ripening)=
## Ripening: why “small dissolves, large grows”

Because $\mu(r)$ increases as $r$ decreases, small particles are at higher chemical potential than large particles. If particles exchange material through a surrounding phase, the system lowers total $G$ by transferring material from small to large particles. This is Ostwald ripening.

The hallmark is a coarsening law (in the classic diffusion-limited LSW picture):

$$
\langle r \rangle^3 - \langle r_0 \rangle^3 \propto t,
$$

meaning the characteristic size grows slowly while the number density decreases.

:::{seealso}
- Thermodynamic origin and the role of Gibbs–Thomson: [Gibbs–Thomson / Kelvin](phase08_gibbs_thomson_kelvin.md)
- Kinetic interpretation and “ripening process” context: [Nucleation and ripening](phase09_nucleation_ripening.md)
:::

---

(bridge_vls)=
## VLS nanowire growth: a thermodynamics–kinetics case study

Vapor–Liquid–Solid (VLS) growth combines:
- **thermodynamics** (phase equilibria and chemical potentials that define supersaturation in the catalyst droplet),
- **transport** (diffusion through vapor and/or liquid catalyst),
- **interface kinetics** (attachment at vapor–liquid and liquid–solid interfaces).

A helpful way to organize VLS is to list serial “resistances”:
1. diffusion through vapor to the catalyst,
2. transport across the vapor–liquid interface,
3. diffusion through the liquid catalyst,
4. transport across the liquid–solid interface.

The slowest step sets the growth rate, and different regimes appear depending on which resistance dominates.

:::{seealso}
The MATSCI 145 reader includes a dedicated VLS chapter that explicitly separates thermodynamics of the growth process from kinetics of transport (and discusses transport-limited vs diffusion-limited regimes).
:::

---

(summary_bridge)=
## Summary

Thermodynamics provides $\mu$ and $G$ (driving forces and equilibria); kinetics combines those with transport laws and activated barriers to predict time dependence (diffusion, nucleation, growth, and ripening).
