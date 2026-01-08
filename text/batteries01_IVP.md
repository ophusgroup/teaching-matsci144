---
title: 4.1 Current, Voltage, and Power
numbering:
  enumerator: 4.1.%s
---

As we have seen in earlier modules, the electrical power equals the current multiplied by the voltage. A battery delivers electrical power at a voltage $V$ for a given current $I$. Hence, the unit of power—the **Watt (W)**—is defined as:

$$
\begin{aligned}
1\ \text{Watt} &= 1\ \text{Joule/sec} \\
&= (1\ \text{Ampere}) \times (1\ \text{Volt}) \\
&= (1\ \text{Coulomb/sec}) \times (1\ \text{Volt})
\end{aligned}
$$

In other words, 1 Watt (W) is the rate at which electrical work is done when 1 Ampere (A) flows through a potential difference of 1 Volt.

A commonly used analogy compares electrical current to flowing water. Current is analogous to a flow rate (liters per second), while voltage is analogous to a height difference (meters). The power produced by a hydroelectric plant is proportional to both the flow rate and the fall height (Current $\times$ Voltage). To convert from electrical power to electrical work, we integrate the power over time:

$$
\text{Energy} = \int \text{Power}(t) \, \dd t
$$

The unit for energy is the Joule (J), where $1\ \text{J} = 1\ \text{W} \cdot \text{s}$ (i.e. 1 Watt sustained for 1 second). In batteries we often use the term *Watt-hour*, which is 1 Watt delivered for 1 hour (1 Wh = 3600 J).


```{figure} ../images/batteries/currentvoltage.png
:label: fig:current_voltage
:align: center
:width: 500px

Two different ways to display the voltage of a battery during charge and discharge
```

Batteries are also characterized by their total charge capacity:

$$
\text{Capacity} = \int I(t) \, \dd t
$$

Two common units for capacity are:
- **Coulomb:** the charge passed by 1 Ampere in one second.
- **Ampere-hour:** the charge passed by 1 Ampere in one hour.

The **state of charge** is the percentage of capacity remaining. For instance, if a battery has a capacity of 1 Ampere-hour, a state of charge of 50% means 0.5 Ampere-hour remains. Charging the battery by 0.5 Ampere-hour would restore it to 100%.

To describe the charging/discharging rate, the **C-rate** is used. A rate of $C/n$ indicates that it takes $n$ hours to fully charge or discharge the battery. For example, 1 C means 1 hour, 0.2 C (i.e. $C/5$) means 5 hours, and 2 C indicates 30 minutes.

Finally, the electrical work consumed or released during charge/discharge is given by

$$
\text{Energy} = \int I(t)V(t)\, \dd t
$$

and the **roundtrip efficiency** $\eta$ is defined as:

$$
\eta = \frac{\text{Work}_{\text{discharge}}}{\text{Work}_{\text{charge}}}
$$

A good battery typically has a roundtrip efficiency above 90%.
