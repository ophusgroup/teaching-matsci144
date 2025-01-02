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


## Entropy of Gas Expansion

### Derivation from Microstates

When gases mix, their individual volumes expand, increasing their entropy. 
To calculate the entropy of mixing, we define the following parameters:
- $\alpha$: Volume fraction of CO$_2$.
- $n_{\text{tot}}$: Total moles of gas.
- $V_{\text{tot}}$: Total volume of gas.

From Equations [](#eq:gas_const_avagadro_boltzmann) and [](#eq:num_moles), we can write 
```{math}
:label: eq:num_moles_sub
N k_B = n R,
```
where $N$ is the total number of molecules, $k_B$ is the Boltzmann constant, $n$ is the number of moles, and $R$ is the gas constant. We know that $N$ is proportional to $n$ and number of lattice sites $J$ is proportional to volume $V$. Therefore, we can rewrite Equation [](#eq:entropy_gas_lattice) to be
```{math}
:label: eq:entropy_volume
S = - n R \ln
  \left(
    \frac{n}{V}
  \right)
  + \text{constant}.
```
where the added constant represents the proportionality constant inside the natural logarithm term.

We can see from Equation [](#eq:entropy_volume) that as the volume expands at constant $n$ and $T$, the entropy increases. This occurs because a larger volume provides more lattice sites, reducing the fraction of occupied sites and thus increasing the disorder of the gas. Another way to understand this expansion is to use the ideal gas law, Equation [](#eq:ideal_gas_law), and the assumption of constant temperature $T$ to get
```{math}
:label: eq:entropy_pressure
S = - n R \ln
  \left(
    P
  \right)
  + \text{constant}.
```
This expression shows that as the pressure decreases, the entropy if the system will increase. If we evaluate the change in entropy if the pressure changes from $P_1$ to $P_2$, we get
```{math}
:label: eq:DeltaS_pressure
\Delta S 
&= S_2 - S_1 \\
&= 
  - n R \ln
  \left(
    P_2
  \right)
  + \cancel{\text{constant}}
  -\left[
    - n R \ln
    \left(
      P_1
    \right)
    + \cancel{\text{constant}}
  \right] \\
&= -n R 
  \left[
    \ln(P_2) - \ln(P_1)
  \right] \\
&= -n R 
    \ln
    \left(
      \frac{P_2}{P_1}
    \right)
```



### Derivation from Thermodynamic Principles


We can also derive Equations [](#eq:entropy_pressure) and [](#eq:DeltaS_pressure) without needing to rely on the counting the microstates of the system. Starting from the First Law, we know that $\Delta U = Q − W$. In  a closed isothermal system we know that $\Delta U = 0$, and therefore $Q = W$. Recall that for a reversible process:
```{math}
Q_\text{rev} &= T \Delta S \\
\delta W &= P \, dV \\
W &= \int P \, dV,

```
where $P$ is the total pressure of the system. From these relations we can derive that
```{math}
\Delta S
&= \frac{Q_\text{rev}}{T} \\
&= \frac{W}{T} \\
&= \int \frac{P}{T} dV. \\
```
From the ideal gas Equation [](#eq:ideal_gas_law) we know that $V = (n R T) / P$, and therefore (when $n$ and $T$ are constant)
```{math}
dV &= n R T \frac{\partial}{\partial P}
  \left( 
    \frac{1}{P} 
  \right) \\ 
  &= - \frac{n R T}{P^2} dP. \\
```
Combining these equations and evaluating the integral we get
```{math}
\Delta S 
&= - \int \frac{P}{T} \frac{n R T}{P^2} dP \\
&= - n R \int \frac{1}{P} dP \\
&= - n R 
  \Big[
    \ln(P)
  \Big]_{P_1}^{P_2} \\
&= - n R \ln
  \left(
    \frac{P_2}{P_1}
  \right),
```
which is the same result as given in Equation [](#eq:DeltaS_pressure). Both approaches show that the change in entropy $\Delta S$ scales with $-\ln P$.


Previously, we derived the same entropy expression based on partial pressure using a statistical approach.
In this second approach, we derived the relation for a reversible, isothermal gas expansion using the ideal gas law and the Second Law of Thermodynamics.  Why are these methods equivalent? The ideal gas law is rooted in the statistical mechanics of microstates, so while the derivations appear different, they ultimately reflect the same underlying principles.


## Entropy of Mixing


For a mixture of CO$_2$ and another gas, the entropy change upon mixing is:

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

