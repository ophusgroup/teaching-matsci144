---
title: A.2 Bridge to Kinetics
numbering:
  enumerator: A.2.%s
---

(bridge_why)=
## Why thermodynamics appears inside kinetic models

Kinetics answers the question “how fast?”, but it cannot be posed without a thermodynamic statement of “which way?” and “how strongly?”. In practice, kinetic models are built from three ingredients:

1. **Driving force (thermodynamics)**: differences in chemical potential or Gibbs free energy that favor one state over another.
2. **Transport/response law (near-equilibrium)**: how fluxes respond to gradients in chemical potential (diffusion) and how interfaces respond to supersaturation (growth).
3. **Activation barrier (rate theory)**: Arrhenius sensitivity of rates to temperature via an activation free energy.

In MATSCI 144, you already used (1) repeatedly (e.g., $\Delta G$ sets the maximum useful work and voltage). In MATSCI 145, the same $\mu$ and $G$ concepts become inputs to diffusion, nucleation, growth, and ripening.

:::{seealso}
- Review of thermodynamic control variables, potentials, and chemical potential: [Thermodynamics Toolkit](appendix01_thermo.md)
- Surface/size thermodynamics introduced in Module 3: [Capillarity and surface energy](phase06_capillarity_surface_energy.md), [Gibbs–Thomson / Kelvin](phase07_gibbs_thomson_kelvin.md), [Nucleation and ripening](phase08_nucleation_ripening.md)
:::

---

(bridge_mu_driving)=
## Chemical potential as the universal driving force

A compact way to express “thermodynamic driving force” is in terms of chemical potential. In kinetics, chemical potential appears in two closely related but distinct ways:

1. **Reaction / phase-transformation driving force**: “which phase or composition is favored?”
2. **Transport driving force**: “which direction does material flow in space?”

Keeping these two roles separate avoids a common confusion: $\Delta G$ (a *difference between states*) sets *spontaneous direction* for reactions/transformations, while $\nabla \mu$ (a *spatial gradient*) sets *material flux*.

### 1) Reaction and phase transformation: $\Delta_r G$ from chemical potentials

For a reaction written as
$$
\sum_i \nu_i A_i = 0
\quad
(\nu_i>0\ \text{products},\ \nu_i<0\ \text{reactants}),
$$
the reaction Gibbs free energy is
$$
\Delta_r G = \sum_i \nu_i \mu_i.
$$

Interpretation at fixed $T,P$:

- If $\Delta_r G < 0$, the reaction proceeds spontaneously forward (as written).
- If $\Delta_r G > 0$, the reverse direction is favored.
- At equilibrium, $\Delta_r G = 0$.

This same logic applies to **phase coexistence**: at equilibrium a species has equal chemical potential in each phase,
$$
\mu_i^{(\alpha)} = \mu_i^{(\beta)},
$$
and departures from equality provide the thermodynamic push toward redistribution or transformation.

### 2) Transport in space: flux driven by $-\nabla \mu$

If $\mu_i$ varies with position, the system can reduce $G$ by moving material “downhill” in chemical potential. That is the thermodynamic origin of diffusion and many transport laws.

- A spatial **gradient** ($\nabla\mu_i \ne 0$) produces flux.
- The sign convention is “downhill”: flux points from higher $\mu_i$ toward lower $\mu_i$.

### 3) Curved interfaces: curvature shifts $\mu$ and connects to kinetics

At curved interfaces, surface energy raises $\mu$ for small radii (Kelvin / Gibbs–Thomson). This makes small particles effectively “higher $\mu$,” which directly feeds nucleation barriers and ripening.

---

(bridge_linear_response)=
## Thermodynamics to diffusion: flux driven by gradients in $\mu$

A useful near-equilibrium statement is that flux is proportional to the gradient of chemical potential:

$$
\bm{J}_i = -M_i c_i \, \nabla \mu_i,
$$

where $c_i$ is a concentration (number density) and $M_i$ is a mobility. This form is powerful because it extends beyond “ideal” diffusion: if you can write $\mu_i(c_i)$, you can write a transport law.

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

Thermodynamics and kinetics appear together because the **net** rate of a forward/backward pair is the difference of two activated rates, and the ratio of forward to backward rates is set by the free-energy difference between the states.

---

(bridge_gibbs_thomson)=
## Size-dependent equilibrium: Kelvin / Gibbs–Thomson

Curvature increases the chemical potential of a phase relative to a flat interface. For a spherical particle (or droplet) with radius $r$:

$$
\mu(r) \approx \mu(\infty) + \frac{2\gamma \Omega}{r},
$$

where $\gamma$ is an appropriate interfacial energy and $\Omega$ is a molar (or atomic) volume.

Consequences:
- **Small objects are less stable** (higher $\mu$), so they dissolve more readily.
- **Equilibrium solubility and vapor pressure increase** as $r$ decreases (Kelvin relation).
- **Nucleation is harder at small length scales** because creating curved interfaces is costly.

:::{seealso}
- Derivation and physical interpretation: [Gibbs–Thomson / Kelvin](phase07_gibbs_thomson_kelvin.md)
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

where $J_0$ packages kinetic factors (attempt frequencies, diffusion supply, Zeldovich factor, etc.). The exponential sensitivity to $\Delta G^*$ is why modest changes in supersaturation or temperature can switch nucleation “on” or “off”.

### Heterogeneous nucleation (site-assisted)

In heterogeneous nucleation, the nucleus forms at a pre-existing site that lowers the free-energy barrier by reducing the amount of *new* interface that must be created and/or by lowering effective interfacial energies (through wetting, epitaxy, or local chemistry). A common minimal model is nucleation on a flat surface, where the nucleus forms as a spherical cap and the barrier is reduced by a geometric/wetting factor $f(\theta)$:

$$
\Delta G^*_{\mathrm{het}} = f(\theta)\,\Delta G^*_{\mathrm{hom}},
\quad 0 < f(\theta) < 1,
$$

where $\theta$ is the contact angle (better wetting $\rightarrow$ smaller $\theta$ $\rightarrow$ smaller $f(\theta)$).

More generally, site-assisted nucleation can occur at many microstructural features:

- **Free surfaces and interfaces** (substrates, container walls, electrode surfaces, liquid–vapor interfaces).
- **Steps, edges, and corners** on surfaces (line/vertex sites).
- **Grain boundaries and phase boundaries**.
- **Dislocations and strain fields**.
- **Vacancies, pores, and voids**.
- **Second-phase particles / impurities / “seeds”**.

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

i.e., the free-energy cost per unit area of creating interface.

:::{seealso}
- Surfaces are a full chapter in the MATSCI 145 reader (broken-bond model, Wulff construction, and the role of surface energy in nucleation and growth).
:::

---

(bridge_growth)=
## Growth: diffusion-limited vs attachment-limited regimes

After nucleation, growth consumes supersaturation. Two limiting cases are common:

### Diffusion-limited growth
The bottleneck is moving material through the surrounding phase to the interface. For simple geometries and constant transport properties, diffusion control often produces **parabolic** kinetics, e.g.
$$
r^2 - r_0^2 \propto t,
$$
or (equivalently) $r \propto t^{1/2}$ once $r \gg r_0$.

### Attachment-limited growth
The bottleneck is incorporation at the interface (e.g., an attachment barrier or slow surface reaction). Growth is then controlled by an interfacial kinetic coefficient and can be less sensitive to transport distances than the diffusion-limited case.

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
- Thermodynamic origin and the role of Gibbs–Thomson: [Gibbs–Thomson / Kelvin](phase07_gibbs_thomson_kelvin.md)
- Kinetic interpretation and “ripening” context: [Nucleation and ripening](phase08_nucleation_ripening.md)
:::

---

(bridge_vls)=
## VLS nanowire growth: a thermodynamics–kinetics case study

Vapor–Liquid–Solid (VLS) growth combines:
- **thermodynamics** (phase equilibria and chemical potentials that define supersaturation in the catalyst droplet),
- **transport** (delivery through vapor and/or diffusion through the liquid catalyst),
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
