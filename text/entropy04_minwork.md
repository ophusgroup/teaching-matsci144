---
title: Minimum Work for Separating CO₂
numbering:
  enumerator: 1.4.%s
---




## Minimum Work 

To calculate the minimum work required to separate and capture carbon dioxide, we begin by considering the thermodynamic principles governing the process. For a closed, isothermal system, the First Law of Thermodynamics gives:

```{math}
\Delta U = Q - W = 0 \quad \Rightarrow \quad Q = W,
```

where $Q$ is the heat transferred, $W$ is the work done, and $\Delta U$ is the change in internal energy. Combining this with the Second Law of Thermodynamics:

```{math}
Q \leq T \Delta S,
```

yields:

```{math}
W_\text{min} \leq T \Delta S.
```

The lower bound of this inequality represents the **minimum work** $W_{\text{min}}$, which corresponds to a reversible process.


## Mixing and Demixing

Consider the system depicted in [](#fig:problem_sep), where a partition separates carbon dioxide (CO$_2$) and another gas. When the wall is removed, the gases mix, increasing the entropy of the system. Conversely, demixing (or separating the gases) requires work to decrease the entropy. Because mixing and demixing are opposite processes, their associated entropy changes are equal in magnitude but opposite in sign:

```{math}
\Delta S_{\text{demix}} = -\Delta S_{\text{mix}}.
```

The minimum work for demixing is therefore given by:

```{math}
W_{\text{min}} = -T \Delta S_{\text{mix}}.
```

This work represents the energy required to carry out the process reversibly.


## Entropy of Mixing


When gases mix, their individual volumes expand, increasing their entropy. 
To calculate the entropy of mixing, we define the following parameters:
- $\alpha$: Volume fraction of CO$_2$.
- $n_{\text{tot}}$: Total moles of gas.
- $V_{\text{tot}}$: Total volume of gas.

From Equations [](#eq:gas_const_avagadro_boltzmann) and [](#eq:num_moles), we can write 
```{math}
NkB = nR
```

Recall Equation [](#eq:entropy_gas_lattice)


Using the expression for entropy derived earlier:

```{math}
S = -n R \ln \left( \frac{n}{V} \right) + \text{constant},
```

where $n$ is the number of moles, $V$ is the volume, and $R$ is the universal gas constant. For a mixture of CO$_2$ and another gas, the entropy change upon mixing is:

```{math}
\Delta S_{\text{mix}} = S_{\text{final}} - S_{\text{initial}} = -n_{\text{tot}} R \left( \alpha \ln \alpha + (1 - \alpha) \ln (1 - \alpha) \right).
```

This result captures the dependence of entropy change on the fraction of CO$_2$ ($\alpha$).

### Minimum Work for Gas Separation

The minimum work required for gas separation is:

```{math}
W_{\text{min}} = T \Delta S_{\text{demix}} = -T \Delta S_{\text{mix}},
```

giving:

```{math}
W_{\text{min}} = n_{\text{tot}} R T \left( \alpha \ln \alpha + (1 - \alpha) \ln (1 - \alpha) \right).
```

The minimum work per mole of CO$_2$ is:

```{math}
W_{\text{min,CO}_2} = \frac{RT}{\alpha} \left( \alpha \ln \alpha + (1 - \alpha) \ln (1 - \alpha) \right).
```

This equation shows that separating CO$_2$ from a source with low concentrations (e.g., atmospheric CO$_2$) requires significantly more work than separation from sources with higher concentrations (e.g., flue gas).

### Pressure-Based Representation

Alternatively, the minimum work can be expressed in terms of partial pressures, where $p_{\text{CO}_2} = \alpha P_{\text{tot}}$ and $p_{\text{other}} = (1 - \alpha) P_{\text{tot}}$, with $P_{\text{tot}}$ as the total pressure. The work per mole of CO$_2$ becomes:

```{math}
W_{\text{min,CO}_2} = RT \left[ \ln \frac{p_{\text{CO}_2}}{P_{\text{tot}}} + \frac{p_{\text{other}}}{p_{\text{CO}_2}} \ln \frac{p_{\text{other}}}{P_{\text{tot}}} \right].
```

### Conclusion

Fig. 1.15 illustrates how the minimum work depends on the fraction of CO$_2$. As $\alpha$ approaches 0 or 1, the entropy change and, consequently, the minimum work approach zero. However, for intermediate values of $\alpha$, the work is significant, highlighting the challenge of separating CO$_2$ from dilute sources such as the atmosphere. This relationship underscores why carbon capture is more energy-intensive for low-concentration sources compared to high-concentration ones.

