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

The first three terms within the square bracket define the (inverse) standard chemical potential of the reaction,

```{math}
:label: eq:std_rxn_mu
\Delta \mu^0_{\text{rxn}} = \mu^0_{\text{products}} - \mu^0_{\text{reactants}} = -\left(2 \mu_{\text{H}_2}^0 +  \mu_{\text{O}_2}^0 - 2\mu_{\text{H}_2\text{O}}^0\right)
```

The standard reaction chemical potential is the change in the Gibbs free energy of the system per mole of the extent of the reaction when the reactants and the products all have their partial pressure equal to $p_{\text{ref}}$. The last term describe the configurational-entropic contribution to the change in the standard reaction chemical potential. Not suprisingly, [Equation %s](#eq:reaction_voltage_partial_pressure) states that the open-circuit voltage of the fuel cell not only depends on the types of reactants and products, but also on the concentration/partial pressure of each species.


## A Note on Units
In [Equation %s](#eq:reaction_voltage_partial_pressure), since $\mathscr{F}$ is defined as Coulomb per mole of electrons, the open-circuit voltage in that equation are in units of volt per mole of electrons. That being said, it is equally valid to define voltage in terms of volt per single electron, and with proper conversion factors, [Equation %s](#eq:reaction_voltage_partial_pressure) becomes

```{math}
:label: eq:open_circuit_v_per_e
\mathsf{V} = \frac{1}{4e}\bigg[\left(2 \mu_{\text{H}_2}^0 +  \mu_{\text{O}_2}^0 - 2\mu_{\text{H}_2\text{O}}^0\right) + k_{\text{B}}T \ln{\frac{\left(p_{\text{H}_2}/p_{\text{ref}}\right)^2 \left(p_{\text{O}_2}/p_{\text{ref}}\right)}{\left(p_{\text{H}_2\text{O}}/p_{\text{ref}}\right)^2}} \bigg]
```

Here, $\mu_i$ is the chemical potential of a *single molecule/atom* of a species in units of electron-volts ($\text{eV}$), rather than the chemical potential of a mole of the species with units of $\text{J/mol}$. An electron-volt if the potential energy of an electron across the voltage of 1 $\text{V}$. The charge of a single electron is $e$ as seen in [Equation %s](#eq:open_circuit_v_per_e), which is equal to $-1.6\times 10^{-19}\;\text{Coulombs}$. In summary, all the constants in [Equation %s](#eq:open_circuit_v_per_e) differ from those in [Equation %s](#eq:reaction_voltage_partial_pressure) by Avogadro's number $N_{\text{A}}$, where $\mathscr{F}=N_{\text{A}}\times e$, $R = N_{\text{A}}\times k_{\text{B}}$, and $\mu_i$ in [Equation %s](#eq:reaction_voltage_partial_pressure) is equal to $N_\text{A}$ multiplied by $\mu_i$ in [Equation %s](#eq:open_circuit_v_per_e).

For this course, we will mostly use $\mathscr{F}$, $R$ and $\mu_i$ in units of per mole. These units are more typical of chemistry. More physics-oriented courses tend to use $e$, $k_{\text{B}}$, and $\mu_i$ in units of per electron/molecule. You are welcome to use whatever units you feel more comfortable, and sometimes there are scenarios when one convention leads to numbers that are easier to work with than those under the other convention. Make sure you don't mix up the units in a single equation. If you mix them up, you may get unphysical quantities on the order of $10^{\pm 20}\; \text{V}$ for the open-circuit voltage. If you do find yourself getting such values, check that you are using consistent units.

## Dependence of Voltage on Partial Pressure
To gain a deeper understanding of the open-circuit voltage's dependence on partial pressure, we plot the voltage as a function of the natural log of partial pressure of each species in [](#fig:voltage_partial_pressure). Here, only one component's partial pressure is varied at a time. When $p_i=p_{\text{ref}}$, the fuel cell's voltage is only given by the standard reaction chemical potential (this is shown as the same voltage-axis intercept for all three chemical species in [](#fig:voltage_partial_pressure)). We can see that the voltage increases when the partial pressure of oxygen or hydrogen gases increases; the voltage decreases when the partial pressure of water increases.

```{figure} ../images/fuelcell/voltagepresure.png
:label: fig:voltage_partial_pressure
:align: center
:width: 500px

The voltage of a fuel cell as a function of the natural log of partial pressures. The intercept is determined by $\Delta \mu_{\text{rxn}}^0$ and can be changed by modifying the chemistry of the reaction. Increasing the reactant concentrtion increases the voltage, while increasing the product concentration decreases it.
```

To make sense of why the voltage increases with increasing oxygen or hydrogen partial pressures but decreases with increasing water partial pressure, let's revisit the net fuel cell reaction where hydrogen and oxygen react to form water, $2\mathrm{H}_2 + \mathrm{O}_2 \Leftrightarrow 2\mathrm{H}_2\mathrm{O}$. Let us imagine a fuel cell with lots of water and very little hydrogen and oxygen gases (i.e., high $p_{\text{H}_2\text{O}}$, low $p_{\text{H}_2}$ and low $p_{\text{O}_2}$). In such a fuel cell, there is almost no driving force to produce more water. Accordingly, this fuel cell has a small voltage since there is no driving force for hydrogen and oxygen to react to form more water. Alternatively, if a fuel cell has lots of hydrogen and oxygen gases but very little water (i.e., low $p_{\text{H}_2\text{O}}$, high $p_{\text{H}_2}$ and high $p_{\text{O}_2}$), there will be a significant driving force for hydrogen and oxygen gases to react to form water, leading to a high voltage. Such trends for voltage vs. partial pressure of reactants and product are consistent with the voltage lines plotted in [](#fig:voltage_partial_pressure).

## Voltages with Different Fuels
The voltage of a fuel cell depends on the type of the chemical species involved. So far, we have only considered hydrogen and oxygen gases as reactants and water as the product. From [Equation %s](#eq:std_rxn_mu), with tabulated values at the standard condition, we can calculate the standard reaction chemical potential to be $\Delta \mu^0_{\text{rxn}}=-475000\,\text{J/mol}$ of $\text{O}_2$ consumed. Thus, $-\frac{\Delta \mu^0_{\text{rxn}}}{4\mathscr{F}} = 1.23\, \mathrm{V}$ at $1\;\text{atm}$ and $300\;\text{K}$.

Now let's change the mobile ion from the oxygen ions ($\text{O}^{2-}$) to the protons ($\text{H}^+$). In such a fuel cell, the reactions become:

```{math}
\begin{aligned}
\text{Anode}   &: 2\text{H}_2 \Leftrightarrow 4\text{H}^{+} + 4e^{-} \\
\text{Cathode} &: \text{O}_2 + 4\text{H}^{+} + 4e^{-} \Leftrightarrow 2\text{H}_2\text{O} \\
\text{Overall} &: 2\text{H}_2 + \text{O}_2 \Leftrightarrow 2\text{H}_2\text{O}
\end{aligned}
```

Since the total number of electrons transferred and the overall reaction are the same as the fuel cell with $\text{O}^{2-}$ as the mobile ions, this alternative fuel cell with $\text{H}^{+}$ ions has the same open-circuit voltage expression as that in [Equation %s](#eq:reaction_voltage_partial_pressure). Such equivalence is underpinned by an important concept in thermodynamics: the Gibbs free energy and subsequently the open-circuit voltage are two thermodynamic variables that are state variables. That is to say these two variables are independent of the path taken in-between the initial and final states. Here, regardless of the mobile carrier being oxygen or hydrogen ions, the change in the molar Gibbs free energy is the same since the initial and final states in both overall reactions are the same, with the initial state being 2 moles of $\text{H}_2$, 1 mole of $\text{O}_2$ and the final state being 2 moles of  $\text{H}_2\text{O}$. Thus, the open-circuit voltage of a fuel cell based on proton conduction is equal to that of one based on oxygen ion conduction.

Finally, let's change the hydrogen gas to methane. If oxygen ions can traverse through the membrane, the chemical reactions become:

```{math}
\begin{aligned}
\text{Anode}   &: \text{CH}_4 + 4\text{O}^{2-} \Leftrightarrow \text{CO}_2 + 2\text{H}_2\text{O} + 8e^{-}  \\
\text{Cathode} &: 2\text{O}_2 + 8e^{-} \Leftrightarrow 4\text{O}^{2-} \\
\text{Overall} &: \text{CH}_4 + 2\text{O}_2 \Leftrightarrow \text{CO}_2 + 2\text{H}_2\text{O}
\end{aligned}
```

Here, $\Delta \mu_{\text{rxn}}^0=-763000\,\text{J/mol}$ at $300\,\text{K}$, and $-\frac{\Delta \mu^0_{\text{rxn}}}{8\mathscr{F}} = 1.10\, \mathrm{V}$. This voltage differs from the hydrogen-oxygen fuel cell because the replacement of hydrogen with methane changes the bond energy difference upon reaction of methane and oxygen into water and carbon dioxide, which leads to a significant difference in the initial and final states of the overall reaction. In a nutshell, while changing the mobile ions in fuel cells while keeping the initial and final states the same in the overall reaction does not change the open-circuit voltage, changing the types of chemical species can.
