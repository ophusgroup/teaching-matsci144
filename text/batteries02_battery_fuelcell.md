---
title: Battery as a Closed Fuel Cell
numbering:
  enumerator: 4.2.%s
---

Recall that in Module 2 we examined a fuel cell schematic (see [](#fig:module_2_fuelcell)). The voltage of the fuel cell is given by the Nernst equation:

```{math}
:enumerated: false
\mathsf{V} = -\frac{1}{\mathscr{F}} \Bigl( \mu_{e^-_\text{C}} - \mu_{e^-_\text{A}} \Bigr)
= \frac{1}{4\mathscr{F}} \Biggl[
\mu^0_{\text{O}_2} + 2\mu^0_{\text{H}_2} - 2\mu^0_{\text{H}_2\text{O}} + RT \ln  \frac{(p_{\text{H}_2}/p_{\text{ref}})^2 \; (p_{\text{O}_2}/p_{\text{ref}})}{(p_{\text{H}_2\text{O}}/p_{\text{ref}})^2}
\Biggr]
```


```{figure} ../images/batteries/fuelcellschematic.png
:label: fig:module_2_fuelcell
:align: center
:width: 500px

Schematic of a fuel cell from Module 2
```

At first glance a fuel cell appears very different from a battery. Fuel cells convert chemical energy into electrical work, whereas batteries store electrical work. However, consider a modified fuel cell (see [](#fig:closed_fuelcell)): instead of an open system with a constant flow of oxygen and hydrogen gas to maintain partial pressures, the number of gas molecules is fixed.

```{figure} ../images/batteries/fuelcellclosed.png
:label: fig:closed_fuelcell
:align: center
:width: 500px

Schematic of a closed fuel cell.
```

As current is drawn, the partial pressures $p_{\text{H}_2}$, $p_{\text{O}_2}$, and $p_{\text{H}_2\text{O}}$ change. Suppose the initial conditions are:

- $p_{\text{H}_2} = p_{\text{H}_2,\text{init}}$
- $p_{\text{O}_2} = p_{\text{H}_2,\text{init}}/2$
- $p_{\text{H}_2\text{O}} = p_{\text{H}_2\text{O},\text{init}}$

Then the voltage becomes

$$
\mathsf{V} = \frac{1}{4\mathscr{F}} \Biggl[
\mu^0_{\text{O}_2} + 2\mu^0_{\text{H}_2} - 2\mu^0_{\text{H}_2\text{O}} + RT \ln \frac{(p_{\text{H}_2,\text{init}}(1-x))^2 \; (p_{\text{H}_2,\text{init}}(1-x)/2)}{(p_{\text{H}_2\text{O},\text{init}} + p_{\text{H}_2,\text{init}}x)^2}
\Biggr]
$$

where $x$ is the fraction of $\text{H}_2$ molecules that have reacted (the extent of reaction) and the reference pressure has been dropped for convenience. As $x$ approaches 1, almost all hydrogen is consumed and the water partial pressure increases to $p_{\text{H}_2\text{O},\text{init}} + p_{\text{H}_2,\text{init}}$. Plotting $\mathsf{V}$ as a function of $x$ gives the curve shown in [](#fig:closed_fuelcell_voltage).

```{figure} ../images/batteries/closedfuelcellvoltage.png
:label: fig:closed_fuelcell_voltage
:align: center
:width: 500px

The voltage of a closed fuel cell decreases as the hydrogen fuel is consumed.
```

After prolonged operation the voltage approaches 0 because almost no hydrogen fuel remains. At that point, the gases reach equilibrium and no further reaction occurs. To restore the cell, one can reverse the process—splitting water into hydrogen and oxygen by applying a voltage (electrolysis). In the quasi-static (very slow) limit, the voltages for both the fuel cell and the reverse fuel cell are identical.

Thus, in fuel cell mode the device converts chemical energy into electrical energy (discharge), and in reverse fuel cell mode (electrolysis) it converts electrical energy into chemical energy (charge). Notice that as hydrogen is consumed, the voltage changes. Later we will see that in a Li-ion battery the voltage similarly changes with the amount of Li inserted into the electrodes.
