---
title: 2.1 Introduction to Fuel Cells
numbering:
  enumerator: 2.1.%s
---

Our modern society depends on electricity. There are many ways to generate electricity via fossil fuels, hydroelectric dams, wind turbines, and solar cells. Among them, burning fossil fuels, such as petroleum, coal and natural gas, still remains as one of the dominant sources of electricity where the heat is converted into electricity with a heat engine. As we will learn in Module 3, such heat engines are often fairly inefficient (around 30% heat to electrical work). They are also difficult to scale down: for example, it is nontrivial for one to create a small and efficient natural gas heat engine to power a computer.

An alternative to convert fuel to electricity is a fuel cell. Fuel cells work by allowing hydrogen or methane (i.e., natural gas) to react with oxygen to form water or carbon dioxide. This process directly generates electricity, whereas the heat engine converts heat into mechanical work, and mechanical work is then converted into electricity. A fuel cell can achieve nearly 70% energy conversion efficiency, which is much better than that of a heat engine. The increase in conversion efficiency not only reduces fuel consumption but also minimizes the release of harmful greenhouse gases. Furthermore, fuel cells are scalable where they can be used to power a device as small as an integrated circuit chip, or as large as a city.

To understand fuel cells, let's consider mixing at ambient pressure two reacting gases, such as hydrogen and oxygen, in a chamber. If we ignite the mixture, the fuel mixture will combust and release heat. However, such thermal energy cannot be converted into work unless coupled to a heat engine. Next, let's consider what would happen if we separate the hydrogen and oxygen gases into separate chambers. For simplicity, let's assume the two chambers are separated by a membrane that only allow oxygen ions to pass through both ways, but not electrons or charge-neutral hydrogen or hydrogen ions (See [](#fuel-cell-oxygen)).

```{figure} ../images/fuelcell/SOFCMembrane.png
:label: fuel-cell-oxygen
:align: center
:width: 500px

Fuel cell schematic where the membrane only allows oxygen ions to pass through
```

As shown in [](#fuel-cell-oxygen), with the help of catalysts, some oxygen gas molecules will dissociate into oxygen ions and pass through the membrane to react with hydrogen. This chemical reaction at the anode (H{sub}`2` chamber) can be expresed as {numref}`Equation {number} <anode-react>`
```{math}
:label: anode-react
2\mathrm{H}_2+2\mathrm{O}^{2-}\rightarrow 2\mathrm{H}_2\mathrm{O}+4e^-
```
To extract elecrical work, we need to connect the anode with the cathode (O{sub}`2` chamber) to allow electrons to flow (i.e., electrical current), as seen in [](#fuel-cell-complete). The excess electrons will then combine with the oxygen gas to form oxygen ions, completing the reaction loop. The chemical reaction at the cathode can be expressed as {numref}`Equation {number} <canode-react>`.
```{math}
:label: canode-react
\mathrm{O}_2+4e^- \rightarrow 2\mathrm{O}^{2-}
```

```{figure} ../images/fuelcell/fuelcelllightbulbO2.png
:label: fuel-cell-complete
:align: center
:width: 500px

A functional fuel cell with a light bulb powered by the complete circuit
```

{numref}`Equation {number} <anode-react>` and {numref}`Equation {number} <canode-react>` are two half reactions that can be combined into a net reaction as seen in {numref}`Equation {number} <net-react>`.
```{math}
:label: net-react
2\mathrm{H}_2 + \mathrm{O}_2 \rightarrow 2\mathrm{H}_2\mathrm{O}
```

The difference in the chemical potentials of oxygen and hydrogen species give rise a voltage across the cathode and the anode, which we will go into more details in later sections.