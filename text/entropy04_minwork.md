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

[](#fig:entropy_co2_frac) shows a closed isothermal system, where the left chamber contains a volume fraction $alpha$ of CO₂ equal to
```{math}
\alpha = \frac{V_\text{CO₂}}{V_\text{total}},
```
where $V_\text{CO₂}$ and $V_\text{total}$ are the volumes of the CO₂-containing portion and the total system respectively. We will assume both compositions are ideal gases, and thus the volumes vary linearly with the number of moles of each substance. We can therefore define $\alpha$ as the number fraction, equal to
```{math}
\alpha = \frac{n_\text{CO₂}}{n_\text{total}},
```
where $n_\text{CO₂}$ and $n_\text{total}$ are the number of moles of the CO₂-containing portion and the total system respectively. 


```{figure} ../images/entropy/entropy_co2_fractions.png
:label: fig:entropy_co2_frac
:align: center
:width: 700px
Three boxes partitioned into two chambers under identical pressure $P$, consisting of varying fractions $\alpha$ moles of CO₂ and ($1-\alpha$) moles of another gas.
```

Let's consider what happens when we remove the partition as a function of $\alpha$ for the 3 scenarios in [](#fig:entropy_co2_frac):
- a) Both gases double in volume.
- b) CO$_2$ expands to $5 \times$ its volume, and the other gases to $(5/4) \times$ their original volume.
- c) CO$_2$ expands to $10 \times$ its volume, and the other gases to $(10/9) \times$ their original volume.

We see that the volume expansion of each side depends on the fraction $\alpha$. Specifically, the ratio of the initial volume $V_1$ to the final volume $V_2$ for CO₂ is equal to
```{math}
\left.
\frac{V_1}{V_2} 
\right|_\text{CO2}
=
\alpha,
```
and the volume ratio for the other gases is equal to
```{math}
\left.
\frac{V_1}{V_2} 
\right|_\text{other}
=
1-\alpha.
```

Next, let's consider the entropy of mixing $\Delta S$ before and after mixing
```{math}
\Delta S = S_\text{final} - S_\text{initial}.
```

From the ideal gas law given in Equation [](#eq:ideal_gas_law) we know that pressure and volume are inversely proportional when $n$ and $T$ are kept constant. We can therefore rewrite Equation [](#eq:DeltaS_pressure) to be
```{math}
:label: eq:DeltaS_volume
\Delta S = - n R \ln
  \left(
    \frac{V_1}{V_2}
  \right)
```

We can plug in the volume ratios given above to compute the total change in entropy
```{math}
:label: eq:entropy_CO2_mixing
\Delta S_\text{mix}
&=
\Delta S_\text{CO2} + \Delta S_\text{other} \\
&=
  - n_\text{CO2} R \ln  \alpha
  - n_\text{other} R \ln (1-\alpha) \\
&=
  - \alpha \, n_\text{total} R \ln \alpha
  - (1-\alpha) n_\text{total} R \ln (1-\alpha) \\
&= 
  - n_\text{total} R 
  \Big[
  \alpha \ln \alpha
  +
  (1-\alpha) \ln (1 - \alpha)
  \Big]. \\
```

Whenever deriving a new mathematical relationship, we should always ask ourselves if the result is sensible. Let's consider the edge cases for $\alpha$, specifically when $\alpha=0$ and $\alpha=1$. In both of these cases, both logarithmic terms in Equation [](#eq:entropy_CO2_mixing) will go to zero and thus $\Delta S_\text{mix}=0$. This makes sense, as if there is no partition, removing it cannot change the entropy of the system.

Next, we examine the values of $\Delta S_\text{mix}$ for values $0 < \alpha < 1$, plotted in [](#fig:entropy_co2_mixing). We can see that the entropy of mixing has mirror symmetry about the $\alpha=0.5$ line, which makes sense because both sides of the chamber contain ideal gases at the same pressure value. 

```{figure} #entropy_co2_mixing
:label: fig:entropy_co2_mixing
:align: center
Entropy of mixing for CO₂ and the other gases.
```

The entropy of mixing has mirror symmetry about $\alpha = 0.5$, which makes sense because both sides of the chamber contain ideal gases at the same pressure. At $\alpha = 0.5$, the two gases are present in equal amounts, with half CO₂ and half of the other gas. This creates the maximum disorder because each gas expands into the largest possible fraction of the total volume. But why doesn’t $\alpha = 0.25$ (or $\alpha = 0.75$) result in more entropy of mixing, since one gas occupies 75% of the volume? The answer lies in how both gases contribute to the entropy, shown explicitly in [](#fig:entropy_co2_mixing_contributions).


At $\alpha = 0.25$, CO₂ occupies 25% of the total volume, so it contributes less to the entropy compared to $\alpha = 0.5$, where CO₂ occupies 50%. Meanwhile, the other gas, which occupies 75% of the volume at $\alpha = 0.25$, has fewer ways to mix compared to $\alpha = 0.5$, where it also occupies 50%. The key point is that both gases contribute to the entropy of mixing, and the total entropy is maximized when the contributions from both gases are balanced, which happens when $\alpha = 0.5$. 

To understand this intuitively, imagine mixing red and blue balls in a box. When you have an equal number of red and blue balls, there are far more ways to arrange them compared to when one color dominates. This balance maximizes the number of possible arrangements (microstates), which corresponds to the maximum entropy of mixing at $\alpha = 0.5$. 

```{figure} #entropy_mixing_contributions
:label: fig:entropy_co2_mixing_contributions
:align: center
Entropy of mixing for CO₂ and the other gases, with individual contributions from each shown.
```

So far, we have only considered the total entropy of mixing. However, for the CO₂ separation application, instead we need to consider the entropy of mixing normalized by how much CO₂ we separate from other gases. This normalization will make it much easier to compare CO₂ separation between different applications, such as those shown in [](#capture_co2).

We therefore need to calculate the **minimum work required to separate CO₂ per mole of CO₂**. If we assume this work is dominated by the entropy of mixing, this value will be the result of Equation [](#eq:entropy_CO2_mixing) divided by the number of moles of CO₂, equal to
```{math}
\Delta \overline{S}_\text{mix, CO2}
&= 
  \frac{\Delta S_\text{mix}}{n_\text{CO2}} \\
&= 
  -R \frac{n_\text{total}}{n_\text{CO2}}
  \Big[
  \alpha \ln \alpha
  +
  (1-\alpha) \ln (1 - \alpha)
  \Big] \\
&= 
  - \frac{R}{\alpha}
  \Big[
  \alpha \ln \alpha
  +
  (1-\alpha) \ln (1 - \alpha)
  \Big]. \\
```
This expression is plotted in [](#fig:specific_entropy_co2), which as we can see matches the result shown in [](#capture_co2) up to a numerical scaling factor. We can identify several key features from this model:
- As $\alpha \rightarrow 0$, the work required to separate each mole of CO₂ approaches infinity. This intuitively makes sense, as gathering extremely small amounts of a dilute gas would require a lot of sorting target molecules from all of the others.
- As $\alpha \rightarrow 1$, the work required to separate each mole of CO₂ approaches zeros. This also intuitively makes sense, as at $\alpha=1$ we already have a volume of pure CO₂ and thus do not need to perform the any further separation.
- As $\alpha$ increases, the work required to separate each mole of CO₂ decreases. 
- Beyond $\alpha \approx 0.2$, the work required decreases approximately linearly.

```{figure} #specific_entropy_co2
:label: fig:specific_entropy_co2
:align: center
Specific entropy of mixing for CO₂.
```

## Minimum Work for Gas Separation

To conclude, we now have all of the pieces required to quantitatively compute the thermodynamic minimum work required to separate CO₂ or any other gas, as a function of the number of moles of gas and temperature.


<!-- For a mixture of CO$_2$ and another gas, the entropy change upon mixing is:

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

Fig. 1.15 illustrates how the minimum work depends on the fraction of CO$_2$. As $\alpha$ approaches 0 or 1, the entropy change and, consequently, the minimum work approach zero. However, for intermediate values of $\alpha$, the work is significant, highlighting the challenge of separating CO$_2$ from dilute sources such as the atmosphere. This relationship underscores why carbon capture is more energy-intensive for low-concentration sources compared to high-concentration ones. -->

