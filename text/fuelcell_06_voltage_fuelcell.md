---
title: Voltage of a Fuel Cell
numbering:
  enumerator: 2.6.%s
---

## Standard Chemical Potential

[Equation %s](#eq:fuel_cell_eq_electron_diff) shows that the chemical potential difference between reactants and products in the fuel cell overall reaction leads to a difference in the electron chemical potential in the cathode and the anode. Such an electron chemical potential difference can be measured with a voltmeter as the open-circuit voltage $\mathsf{V}$,

```{math}
:label: eq:open_circuit_voltage
\mathsf{V}=-\frac{1}{\mathscr{F}}\left(\mu_{e_{\text{C}}^-}-\mu_{e_{\text{A}}^-}\right)
```

where $\mathscr{F}$ is Faraday's constant and $\mathscr{F}=96485\frac{\mathrm{C}}{\mathrm{mol}\,e^-}$ ($\mathrm{C}$ is Coulomb; $\mu$ can be in units of $\mathrm{J}/\mathrm{mol}$ or $\mathrm{eV}/\text{single atom or molecule}$). The negative sign is a result of the electrons being negatively charged. Thus, an electric potential higher in magnitude means an electron under the influence of such potential will have more negative electron energy. With [Equation %s](#eq:open_circuit_voltage) and [Equation %s](#eq:fuel_cell_eq_electron_diff) combined, we obtain the open-circuit voltage for our fuel cell,

```{math}
:label: eq:nernst_pot
\mathsf{V}=-\frac{1}{\mathscr{F}}\left(\mu_{e_{\text{C}}^-}-\mu_{e_{\text{A}}^-}\right)=-\frac{1}{4\mathscr{F}}\left(-2 \mu_{\text{H}_2} - \mu_{\text{O}_2} + 2\mu_{\text{H}_2\text{O}}\right)
```

The voltage (also known as the Nernst potential) is a direct measure of the difference in chemical potentials for the species involved in the overall fuel cell reaction. As mentioned before, the fuel cell develops a precise voltage difference between the cathode and the anode to balance out the chemical potential difference between the reactants and the product in the two electrodes, such that the equilibrium is achieved in the anode, cathode and the electrolyte/membrane as seen in [](#tab:fuelcell_species).

We now want to relate the difference in chemical potential and the open-circuit voltage to the partial pressure of each species in the overall fuel cell reaction. Recall from [Equation %s](#eq:partial_molar_mu_h_s) that the chemical potential of species $i$ is the difference between its partial molar enthalpy ($h_i$) and the product between the temperature and its partial molar entropy ($s_i$):

```{math}
:enumerated: false
\mu_i = h_i - T s_i
```

As the reaction proceeds, consider how this chemical potential would change: the partial molar enthalpy $h_i$ represents the chemical energy stored in each bond of species $i$, which does not change with the extent of the reaction; the partial molar entropy $s_i$ represents the infinitesimal change in the configurational entropy with an infinitesimal amount change in the number of moles of species $i$, which would change as the species $i$ is consumed or produced. Thus, throughout the course of the reaction, $h_i$ would remain fixed, but $s_i$ would change with varying concentrations of species $i$. From [Equation %s](#eq:entropy_pressure), we learned that for an ideal gas, its entropy depends on the pressure of the gas. Modified for a system with multiple ideal gas species, we can write the total entropy as

```{math}
:label: eq:sum_partial_entropy
\begin{aligned}
S &= \sum_i S_i \\
&= \sum_i -n_i R \ln{p_i} + \text{constant}
\end{aligned}
```

where $S_i$ is the entropic contribution from $i^{\text{th}}$ species to the total entropy, $n_i$ is the number of moles of species $i$, and $p_i$ is its partial pressure ($p_i = \frac{n_i}{n_{\text{tot}}}P$; $P$ is the total pressure here). The simple summation over every species is made possible by the fact that gas molecules do not interact with one another for ideal gases. Using the [definition of partial molar quantities](#def:partial_molar_quantity), we have

```{math}
:label: eq:partial_entropy_i
\begin{aligned}
s_i &= \left(\frac{\partial S}{\partial n_i}\right)_{T, P, n_{j\neq i}} \\
&= \left[\frac{\partial}{\partial n_i} \left(-n_i R \ln{p_i}\right) \right]_{T, P, n_{j\neq i}} \\
&= \left\{\frac{\partial}{\partial n_i} \left[-n_i R \ln{\left(\frac{n_i}{n_{\text{tot}}}P\right)}\right] \right\}_{T, P, n_{j\neq i}} \\
&= -R \left[ \ln{\left(\frac{n_i}{n_{\text{tot}}}P\right)} + n_i \cdot \frac{n_{\text{tot}}}{n_i P} \cdot \frac{P}{n_{\text{tot}}} \right]_{T, P, n_{j\neq i}} \\
&= -R \left( \ln{p_i} + 1 \right)
\end{aligned}
```

Note that the summation sign over $i$ in [Equation %s](#eq:sum_partial_entropy) disappears when we take the partial derivative with respect to $n_i$. This is due to fact that we are holding $n_{j\neq i}$ constant, where only one term within the summation will have $n_i$ dependence. Furthermore, when $P$ is held constant, what we really mean is that the total pressure is held constant. Some of you may wonder how can the total pressure be held constant when $n_i$ is allowed to vary but all other $n_{j\neq i}$ terms are held constant. One way to maintain the total pressure is as $n_i$ increases or decreases, we allow the total volume of the system to increase or decrease accordingly. For [Equation %s](#eq:partial_entropy_i), when the $i^{\text{th}}$ species is in the dilute limit (i.e., $p_i \ll 1\;\text{atm}$, thus $|\ln{p_i}| \gg 1$ ), we can make an additional approximation where $s_i \approx -R \ln{p_i}$. Strictly speaking, the argument of a natural logarithm should be unitless. We can resolve this issue by expressing $s_i$ as some initial $s_i^0$ measured at some reference pressure and adding to it the difference in partial molar entropy measured between the reference pressure and the actual partial pressure. Mathematically, this is shown as follows,

```{math}
:label: eq:partial_molar_s_std_p
\begin{aligned}
s_i &= s_i^0 + \Delta s_i \\
&= s_i^0 + (s_i - s_i^0) \\
&= s_i^0 - R \left[\ln{p_i} + 1 - (\ln{p_{\text{ref}}} + 1) \right] \\
&= s_i^0 - R \ln{\left(\frac{p_i}{p_{\text{ref}}}\right)}
\end{aligned}
```

Here, $p_{\text{ref}}$ is the standard pressure such that $s_i=s_i^0$ when $p_i=p_{\text{ref}}$. For this class, we typically choose 1 atm or 1 bar as $p_{\text{ref}}$ in the problem sets and exams. Combining [Equation %s](#eq:partial_molar_mu_h_s) with [Equation %s](#eq:partial_molar_s_std_p), we then have

```{math}
:label: eq:partial_molar_s_pi
\begin{aligned}
\mu_i &= h_i - T\left[ s_i^0 - R \ln{\left(\frac{p_i}{p_{\text{ref}}}\right)} \right] \\
&= h_i - Ts_i^0 + RT \ln{\left(\frac{p_i}{p_{\text{ref}}}\right)}
\end{aligned}
```

An extra note on $s_i^0$: it does not only account for the configurational partial molar entropy at the standard state, but also accounts for all other sources of entropy, such as the vibrational, rotational and electronic partial molar entropy. Now, we can also combine the first two terms in [Equation %s](#eq:partial_molar_s_pi) into a single term that we will call **the standard chemical potential of species $i$**, which we will denote as $\mu_i^0$. This allows us to separate the chemical potential into two parts, with one part being independent of the partial pressure and the other being dependent on the partial pressure.

```{math}
:label: eq:mu_pi_over_pref
\begin{aligned}
\mu_i^0 &\equiv h_i - Ts_i^0 \\
\mu_i &= \mu_i^0 + RT \ln{\left(\frac{p_i}{p_{\text{ref}}}\right)}
\end{aligned}
```

Since all partial molar quantities are defined at constant temperature and pressure, the standard chemical potential is usually defined at room temperature and room pressure (i.e., $300\;\text{K}$ and 1 atm). The reason for defining such standard chemical potential is that, with a standard state, one can measure and tabulate the chemical potentials of many common chemical species. Since measuring partial pressure differences is much easier than directly measuring a new chemical potential, when the partial pressure of the species $i$ deviates from the reference pressure, one can simply calculate the new chemcial potential using [Equation %s](#eq:mu_pi_over_pref) by looking up the tabulated standard chemical potentials and accounting for the partial pressure difference.

Going back to the [open-circuit voltage](#eq:nernst_pot), we can express all the chemical potentials in the same form as [Equation %s](#eq:mu_pi_over_pref),

```{math}
:enumerated: false
\begin{aligned}
\mathsf{V} &= -\frac{1}{4\mathscr{F}}\left(-2 \mu_{\text{H}_2} - \mu_{\text{O}_2} + 2\mu_{\text{H}_2\text{O}}\right) \\
&= -\frac{1}{4\mathscr{F}}\bigg[
  -2 \left(\mu_{\text{H}_2}^0 + RT \ln{\frac{p_{\text{H}_2}}{p_{\text{ref}}}} \right) \\
&\qquad\qquad\;\, - \left( \mu_{\text{O}_2}^0 + RT \ln{\frac{p_{\text{O}_2}}{p_{\text{ref}}}} \right) \\
&\qquad\qquad\;\, + 2\left( \mu_{\text{H}_2\text{O}}^0 + RT \ln{\frac{p_{\text{H}_2\text{O}}}{p_{\text{ref}}}} \right)
  \bigg] \\
&= -\frac{1}{4\mathscr{F}}\bigg[
  -2 \mu_{\text{H}_2}^0 -  \mu_{\text{O}_2}^0 + 2\mu_{\text{H}_2\text{O}}^0 \\
&\qquad\qquad\;\, - RT \ln{\left(\frac{p_{\text{H}_2}}{p_{\text{ref}}}\right)^2} - RT \ln{\left(\frac{p_{\text{O}_2}}{p_{\text{ref}}}\right)} + RT \ln{\left(\frac{p_{\text{H}_2\text{O}}}{p_{\text{ref}}}\right)^2}\bigg]
\end{aligned}
```

Collecting all like-terms, we obtain partital pressure dependent open-circuit voltage
```{math}
:label: eq:reaction_voltage_partial_pressure
\mathsf{V} = \frac{1}{4\mathscr{F}}\bigg[\left(2 \mu_{\text{H}_2}^0 +  \mu_{\text{O}_2}^0 - 2\mu_{\text{H}_2\text{O}}^0\right) + RT \ln{\frac{\left(p_{\text{H}_2}/p_{\text{ref}}\right)^2 \left(p_{\text{O}_2}/p_{\text{ref}}\right)}{\left(p_{\text{H}_2\text{O}}/p_{\text{ref}}\right)^2}} \bigg]
```

The first three terms within the square bracket define the (inverse) standard chemical potential of the reaction, $\Delta \mu^0_{\text{rxn}} = \mu^0_{\text{products}} - \mu^0_{\text{reactants}} = -\left(2 \mu_{\text{H}_2}^0 +  \mu_{\text{O}_2}^0 - 2\mu_{\text{H}_2\text{O}}^0\right)$. The standard reaction chemical potential is the change in the Gibbs free energy of the system per mole of the extent of the reaction when the reactants and the products all have their partial pressure equal to $p_{\text{ref}}$. The last term describe the configurational-entropic contribution to the change in the standard reaction chemical potential. Not suprisingly, [Equation %s](#eq:reaction_voltage_partial_pressure) states that the open-circuit voltage of the fuel cell not only depends on the types of reactants and products, but also on the concentration/partial pressure of each species.


## A Note on Units

## Dependence of Voltage on Partial Pressure

## Voltages with Different Fuels
