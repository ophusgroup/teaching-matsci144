---
title: Two-Phase Electrode and Solid Phase Transformations
numbering:
  enumerator: 4.7.%s
---

In a single-phase electrode we assume the crystal structure of the host remains constant. However, inserting sufficient Li into a host structure can cause the host to change its crystal structure. This change in structure alters the Gibbs free energy of Li insertion and hence the voltage during charging and discharging.

Consider two phases of a lithium metal oxide: $\text{LiMO}_2(\alpha)$ and $\text{LiMO}_2(\beta)$, where the transition metal is denoted by $\text{M}$. Here, $\alpha$ and $\beta$ denote different crystal structures with distinct bonding environments for Li, M, and O (see Figure 4.11).

Let us briefly review the thermodynamic background. Gibbs’ phase rule for a system with $p$ phases and $c$ components is

$$
f = c - p + 2
$$

In our system the two components that vary independently are the empty $\text{MO}_2$ lattice and the Li⁺ ion. With $p = 2$, we have $f = 2$; that is, when temperature and pressure are fixed, the thermodynamic properties remain fixed during phase coexistence.

We express the specific Gibbs free energy of each phase (per lattice site) as a function of the Li fraction $X$:

$$
\bar{G}_{\text{“Li”},\alpha} = (\mu^0_{\text{LMO},\alpha} - \mu^0_{\text{MO},\alpha})\,X + \mu^0_{\text{MO},\alpha} + RT \{ X_\alpha \ln X_\alpha + (1-X_\alpha) \ln (1-X_\alpha) \} 
$$

$$
\bar{G}_{\text{“Li”},\beta} = (\mu^0_{\text{LMO},\beta} - \mu^0_{\text{MO},\beta})\,X + \mu^0_{\text{MO},\beta} + RT \{ X_\beta \ln X_\beta + (1-X_\beta) \ln (1-X_\beta) \} 
$$

Similarly, the chemical potentials in each phase are

$$
\mu_{\text{“Li”},\alpha} = \mu^0_{\text{“Li”},\alpha} + RT \ln \frac{X_\alpha}{1-X_\alpha} 
$$

$$
\mu_{\text{“Li”},\beta} = \mu^0_{\text{“Li”},\beta} + RT \ln \frac{X_\beta}{1-X_\beta} 
$$

Below are several cases for the two-phase system:

### 4.7.1 Varying $\mu^0_{\text{MO},\cdot}$

If the only difference between the phases is in the chemical potential of the empty host lattice ($\mu^0_{\text{MO}}$) with

$$
\mu^0_{\text{MO},\alpha} < \mu^0_{\text{MO},\beta},
$$

then the $\alpha$ phase is lower in energy for all Li fractions $X$. No phase transformation will occur, and the electrode remains single-phase. (See Figure 4.12.)

### 4.7.2 Varying $\mu^0_{\text{LMO},\cdot}$

If instead the filled lattice potentials differ such that

$$
\mu^0_{\text{LMO},\alpha} > \mu^0_{\text{LMO},\beta},
$$

then the $\beta$ phase has a lower Gibbs free energy at all compositions, and the electrode will exist entirely as the $\beta$ phase. (See Figure 4.13.)

### 4.7.3 Varying Both Quantities

If both the empty and filled lattice chemical potentials differ (for example, $\mu^0_{\text{MO},\alpha} < \mu^0_{\text{MO},\beta}$ and $\mu^0_{\text{LMO},\alpha} > \mu^0_{\text{LMO},\beta}$), then the $\alpha$ phase is favored at low Li concentration while the $\beta$ phase is favored at high Li concentration. In the intermediate range, the electrode will consist of a mixture of both phases. In this region the chemical potentials of Li in both phases must be equal:

$$
\mu_{\text{“Li”},\alpha}(X_\alpha) = \mu_{\text{“Li”},\beta}(X_\beta) 
$$

### 4.7.4 Voltage during a Phase Transformation

During the phase transformation (when both $\alpha$ and $\beta$ are present), the overall specific Gibbs free energy of the electrode is given by the weighted average

$$
\bar{G}_{\text{tangent}} = (1-\phi)\,\bar{G}_\alpha(X_1) + \phi\,\bar{G}_\beta(X_2) 
$$

Here, $X_1$ and $X_2$ are the constant Li fractions in the $\alpha$ and $\beta$ phases during the transformation, and $\phi$ is the fraction of the electrode in the $\beta$ phase. Because the chemical potential (the slope of $\bar{G}$ versus $X$) is constant during the transformation, the battery voltage remains flat (see Figure 4.17).

### 4.7.5 Lever Rule

Conservation of Li requires that

$$
X = (1-\phi)X_\alpha + \phi X_\beta 
$$

This expression can be rearranged to yield the Lever rule:

$$
\phi = \frac{X - X_1}{X_2 - X_1} 
$$

Thus, when $X = X_1$, $\phi = 0$ (pure $\alpha$), and when $X = X_2$, $\phi = 1$ (pure $\beta$). For intermediate values of $X$, $\phi$ indicates the relative fraction of the $\beta$ phase.
