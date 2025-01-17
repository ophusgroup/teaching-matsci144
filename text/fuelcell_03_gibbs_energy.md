---
title: Gibbs Free Energy
numbering:
  enumerator: 2.3.%s
---

## Chemical Potential

As seen in [Equation %s](#expanded_first_law_final), this expression has three independent variables: $(S, V, n_i)$. Consider the scenario where $S$ and $V$ are held constant, where $\dd S=0$ and $\dd V=0$. This means that in this system, the only change in the internal energy comes from the change in the chemical work,

```{math}
:label: dU_const_SV
\dd U\big|_{S, V}=\sum_i \mu_i \dd n_i
```

The subscripted $S$ and $V$ after $\big|$ mean that those variables are held constant. [Equation %s](#dU_const_SV) can also be rearranged to provide a more explicit definition of chemical potential $\mu_i$.

:::{admonition} Definition of Chemical Potential at Constant $S$, $V$ and $n_{j\neq i}$
:class: danger
```{math}
\mu_i = \left(\frac{\partial U}{\partial n_i}\right)_{S, V, n_{j\neq i}}
```

Again, the subscripted $S$, $V$, $n_{j\neq i}$ mean those varibale are kept constant. The notation $n_{j\neq i}$ just means the moles of all species except $i$ are kept constant, where $j$ is used to represent any other chemical species that is not $i$. In a nutshell, _when $S$, $V$ and $n_{j\neq i}$ are held constant_, the chemical potential of a chemical species $i$ is defined as the partial derivative of the internal energy with respective to the number of moles of the species $i$. This quantity is also referred to as the _partial molar internal energy_, which we will discuss in more detail in [Section "{name}"](#sec:partial_molar).
:::

## Legendre Transformation from $U(S, V, n_i)$ to $G(T, P, n_i)$

In practice, it is often difficult to keep $S$ and $V$ constant during chemcial processes since it's almost impossible to obtain complete heat insulation, and materials wants to expand or shrink in volume during heat exchange. It is oftentimes more convenient to control a different set of variables, such as $T$ and $P$. The temperature can be fixed by coupling the system to an external heat reservoir, and the pressured can be fixed by adjusting the volume of the container or adding/removing materials from the system. By changing the underlying control variable, we are effectively transforming into a new thermodynamic potential that is different from the initial thermodynamic potential (i.e., the internal energy in this case). To obtain the expression for this new thermodyanmic potential, we follow a 3-step process to transform from the internal energy $U$ that depends on $(S, V, n_i)$ to a new thermodynamic potential that depends on $(T, P, n_i)$.

### Step 1

Let's start by writing out the differential form of our initial thermodynamic potential as a function of all its independent variables:

```{math}
:label: eq:u_differential
\dd U = \left(\frac{\partial U}{\partial S}\right)_{V, n_i} \dd S + \left(\frac{\partial U}{\partial V}\right)_{S, n_i} \dd V + \sum_i \left(\frac{\partial U}{\partial n_i} \right)_{S, V, n_{j\neq i}} \dd n_i
```

By comparing [Equation %s](#eq:u_differential) to [Equation %s](#expanded_first_law_final)  , we can conclude

```{math}
:label: eq:u_partial_derivs
\begin{align}
\left(\frac{\partial U}{\partial S}\right)_{V, n_i} &= T  \\
\left(\frac{\partial U}{\partial V}\right)_{S, n_i} &= -P \\
\left(\frac{\partial U}{\partial n_i} \right)_{S, V, n_{j\neq i}} &= \mu_i
\end{align}
```

Here, the variables that immediately follow the $\dd$ operators are our independent/control variables, which are $S$, $V$, and $n_i$, whereas $T$, $P$, $\mu_i$ and $U$ are dependent variables.


### Step 2

For clarity, let's change one control variable at a time. One can either choose to change from $S$ to $T$ first, or change from $V$ to $P$ first. Here, we choose to change from $V$ to $P$ first.

After such change, the new potential should depend on $(S, P, n_i)$, with its differential form looking something like the following expression

```{math}
:label: eq:mystery_enthalpy
\dd \text{[?]}=T\dd S \pm \text{[??]}\dd P + \sum_i \mu_i \dd n_i
```

where [?] is this new thermodynamic potential, [??] is the unknown variable in front of $\dd P$, and $\pm$ sign just means that for now, we don't know if the sign before $\text{[??]}\dd P$ term should be a $+$ sign or a $-$ sign.

For now, since we are only change one independent variable from $V$ to $P$, while fixing the other two independent variables where $\dd S=0$ and $\dd n_i=0$, [Equation %s](#eq:u_differential) can be simplified as

```{math}
\dd U\big|_{S, n_i} = \left(\frac{\partial U}{\partial V}\right)_{S, n_i} \dd V = -P \dd V
```

which means that if we were to plot $U(V)$ at constant $S$ and $n_i$, the $U$ vs. $V$ curve should be monotonically decreasing since $P$ should be a positive number, and from [Equation %s](#eq:u_partial_derivs), the first-order partial derivative of $U$ with respect to $V$ at constant $S$ and $n_i$ is thus negative. We can even learn about the second-order partial derivative of $U$ with respect to $V$ at constant $S$ and $n_i$ as follows

```{math}
\left(\frac{\partial^2 U}{\partial V^2}\right)_{S, n_i}=\left[\frac{\partial}{\partial V}\left(\frac{\partial U}{\partial V}\right)_{S, n_i}\right]_{S, n_i}=\left[\frac{\partial}{\partial V}\left(-P\right)\right]_{S, n_i}=-\left(\frac{\partial P}{\partial V}\right)_{S, n_i}
```

We can use physical intuition to figure out the sign of this second-order partial derivative. At constant $S$ and $n_i$, we have an adiabatic system that also doesn't allow exchange of matter (e.g., a thermally insulated piston). For an infinitesimal increase in volume, we would expect the infinitesimal change in pressure of this system to be a decrease. This means that $(\partial P/\partial V)_{S, n_i}<0$, and thus

```{math}
\left(\frac{\partial^2 U}{\partial V^2}\right)_{S, n_i}=-\left(\frac{\partial P}{\partial V}\right)_{S, n_i}>0
```

Now, to transform from $U(V)\big|_{S, n_i}$ to $\text{[?]}(P)\big|_{S, n_i}$, we need to utilize a mathematical transformation called the Legendre transformation.

:::{admonition} Definition of the Legendre transformation
:class: danger

The Legendre transformation allows us to transform from an initial thermodynamic potential $\Phi_i$ that has $N$ independent variables, $\Phi_i(\phi_i^1, \phi_i^2, \ldots, \phi_i^N)$, to a final thermodyanmic potential $\Phi_f$ that may have a different set of $N$ independent variables, $\Phi_f(\phi_f^1, \phi_f^2, \ldots, \phi_f^N)$. In our case, since we are only changing one variable at a time (from $\phi_i^1$ to $\phi_f^1$), the final thermodynamic potential can be obtained from the initial thermodynamic potential by subtracting from the initial thermodynamic potential with the product between the independent variable $\phi_i^1$ that one wants to swap out and the partial derivative of the initial thermodynamic variable with respect to $\phi_i^1$. The mathematical expression is shown below,

```{math}
:label: eq:one_var_legendre
\Phi_f(\phi_f^1, \phi_i^2, \ldots, \phi_i^N) = \Phi_i(\phi_i^1, \phi_i^2, \ldots, \phi_i^N) - \left(\frac{\partial \Phi_i}{\partial \phi_i^1}\right)_{\phi_i^{n\neq 1}}\cdot \phi_i^1
```
:::

To make this more concrete, let's use the example from $U(S, V, n_i)$ to $\text{[?]}(S, P, n_i)$. According to [Equation %s](#eq:one_var_legendre),

```{math}
\text{[?]}(S, P, n_i) = U(S, V, n_i) - \left(\frac{\partial U}{\partial V}\right)_{S, n_i}\cdot V
```

From [Equation %s](#eq:u_partial_derivs), we know $(\partial U/\partial V)_{S, n_i}=-P$, thus we have

```{math}
\text{[?]}(S, P, n_i) = U(S, V, n_i) - (-P)\cdot V =  U(S, V, n_i) + PV
```

By convention, we name this new thermodynamic potential as the enthalpy, $H$.

```{math}
H =  U + PV
```

We can verify that $H$ only depends on $S$, $P$ and $n_i$ by writing out its total differential expression

```{math}
:label: eq:dH
\begin{align}
\dd H &= \dd (U+PV)\\
&=\dd U + \dd (PV)\\
&=\dd U + P\dd V + V\dd P\\
&=\left(T\dd S-\cancel{P\dd V}+\sum_i \mu_i \dd n_i\right)+ \cancel{P\dd V} + V\dd P\\
\dd H&=T\dd S + V\dd P + \sum_i \mu_i \dd n_i
\end{align}
```

We can see that the independent variables of $H$ are indeed $S$, $P$ and $n_i$, with no $V$ dependence. Here, we also note that
there is a new definition of chemical potential when $S$, $P$, and $n_{j\neq i}$ are held constant.

```{math}
:label: eq:chem_pot_h
\mu_i = \left(\frac{\partial H}{\partial n_i}\right)_{S, P, n_{j\neq i}}
```


#### Geometric Interpretation
There is also a geometric interpretation of the Legendre transformation formula

```{math}
H=U - \left(\frac{\partial U}{\partial V}\right)_{S, n_i}\cdot V
```

The left panel in the interactive figure below plots $U(V)$ with $(\partial U/\partial V)_{S, n_i}<0$ and $(\partial^2 U/\partial V^2)_{S, n_i}>0$,
as derived before. At constant $S$ and $n_i$, if one were to pick any point along this $U$ vs. $V$ curve, which we can denote as $(V_0, U_0)$, the partial derivative of $U$
with respect to $V$, evaluated at $V_0$, is the instantaneous tangent slope of $U(V)$ at this specific point. If we extend a tangent line all the way to $V=0$, we will find that
the product between the partial derivative and $V$, evaluated at this specfic point, becomes $\left(\frac{\partial U}{\partial V}\right)_{S, n_i}\big|_{V_0}\cdot V_0 = \frac{\Delta U_0}{\Delta V_0}\cdot (V_0-0)=\Delta U_0$.
Then, $H_0 = U_0 - \Delta U_0$, where $H_0$ is the intercept between the tangent line and the $V=0$ vertical axis, denoted by the green dot in the left panel of the interactive plot.
If one were to trace out the path traversed by $H$ as a function of $P$, we obtained the line plotted in the right panel.

```{figure} #legendre_u_to_h
:label: fig:legendre_u_to_h
:align: center
:width: 700px
```

:::{note} Alternative transformation from $U(S, V)$ to $F(T, V)$
:class: dropdown

We've presented the Legendre transformation from $U(S, V)$ to $H(S, P)$, but it is equally valid to first change the
independent variable from $S$ to $T$, as shown in the following animation. By convention, we name this new thermodynamic potential
as the Helmholtz free energy, denoted by $F$.

```{iframe} https://player.vimeo.com/video/815746822?h=5adc2842d3&amp;badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479
:width: 100%
Legendre transformation from $U(S, V)$ to $F(T, V)$
```


Here is an interactive version of the same transformation.

```{figure} #legendre_u_to_f
:label: fig:legendre_u_to_f
:align: center
:width: 700px
```
:::

### Step 3

Now, all that's left is to tranform the remaining independent variable from $S$ to $T$ since not only is $S$ hard to control,
but also difficult to measure/quantify in the first place.
Again by convention, we name this new thermodynamic potential as the Gibbs free energy, denoted by $G$.
Following the general recipe of the Legendre transformation, we subtract from $H$ with the product between the initial indepdendent variable ($S$) and the partial derivative of $H$ with respect to $T$, while holding all other independent variable constant.

```{math}
G=H-\left(\frac{\partial H}{\partial S}\right)_{P, n_i}\cdot S
```

From [Equation %s](#eq:dH), we know that $\left(\frac{\partial H}{\partial S}\right)_{P, n_i}=T$. Thus, we conclude

```{math}
\begin{aligned}
G &= H-TS \\
&= U + PV - TS
\end{aligned}
```

Again, we can verify that $G$ only depends on $T$, $P$ and $n_i$ by taking its total differential form,

```{math}
\begin{aligned}
\dd G &= \dd (H-TS) \\
&= \dd H - (T\dd S + S \dd T) \\
&= \left(\cancel{T\dd S} + V\dd P + \sum_i \mu_i \dd n_i\right) - \cancel{T\dd S} - S \dd T\\
\dd G &= -S\dd T + V\dd P + \sum_i \mu_i \dd n_i
\end{aligned}
```

Similar to the alternative definition of chemical potential in [Equation %s](#eq:chem_pot_h),
at constant $T$, $P$ and $n_{j\neq i}$, the chemical potential is defined as

```{math}
\mu_i = \left(\frac{\partial G}{\partial n_i}\right)_{T, P, n_{j\neq i}}
```

In most real-world chemical reactions, $T$ and $P$ are held constant while all $n_i$ terms are allowed to vary.
Under this scenario, we get

```{math}
:label: eq:dG_const_TP
\dd G\big|_{T, P} = \sum_{i}\mu_i \dd n_i
```

The significance of [Equation %s](#eq:dG_const_TP) will become apparent in the next section.
For now, let's recap two important lessons that we've learned so far.

1. The chemical potential of species $i$ can be defined as partial molar quanties of different thermodyanmic potentials under different control variables,
but these definitions are all equivalent.
```{math}
\mu_i = \left(\frac{\partial U}{\partial n_i}\right)_{S, V, n_{j\neq i}} = \left(\frac{\partial H}{\partial n_i}\right)_{S, P, n_{j\neq i}} = \left(\frac{\partial F}{\partial n_i}\right)_{T, V, n_{j\neq i}} = \left(\frac{\partial G}{\partial n_i}\right)_{T, P, n_{j\neq i}}
```

2. Legendre transformation allows us to transform from exisiting thermodynamic potentials to new ones with a different set of control variable.

The transformation path that is demonstrated here is
```{math}
U(S, V, n_i) \xrightarrow{+PV} H(S, P, n_i) \xrightarrow{-TS} G(T, P, n_i)
```
There is also an alternative transformation path as follows
```{math}
U(S, V, n_i) \xrightarrow{-TS} F(T, V, n_i) \xrightarrow{+PV} G(T, P, n_i)
```

These two paths yield the same final Gibbs free energy potential, as shown in [](#fig:legendre_3d)

```{figure} #legendre_3d
:label: fig:legendre_3d
:align: center
:width: 700px

3D visualization of Legendre transformation from $U(S, V, n_i)$ to $G(T, P, n_i)$
```

```{iframe} https://player.vimeo.com/video/804055211?h=125fe612d8&amp;title=0&amp;byline=0&amp;portrait=0&amp;badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479
:width: 100%
3D Legendre transformation from $U(S, V)$ to $G(T, P)$
```

## Why is it called Gibbs "free" energy

Some of you may wonder: why do we refer to these thermodyanmic potentials as **"free"** energies?
Here is a spoiler alert: with some simple mathematical derivations, we will see that **"free"** here actually mean **available** or **usable**.

Let's consider a system, as shown in [](#fig:gibbs_max_iso_sys), that consists of a piston filled with ideal gas in contact with a infinite heat and mechanical work reservoir. We label the piston system with the subscript $_{\text{sys}}$, and the reservoir with the subscript $_{\text{res}}$. Both $T$ and $P$ of the system and the reservoir remain constant. If we also fix $n_i$, along with $T$ and $P$, no change in the system's volume can happen, leading to no expansion or compression work done. By allowing $n_i$ to vary, according to [Equation %s](#multi_species_chemwork),
```{math}
W_{\text{chemical}} = -\sum_i \int \mu_i \dd n_i
```

```{figure} ../images/fuelcell/gibbsmaxwork.png
:label: fig:gibbs_max_iso_sys
:align: center
:width: 500px

An isolated system composed of a piston system, a heat reservoir and a work reservoir.
```

Since we assume the piston and the reservoir to make up a larger isolated system, due to the conservation of the internal energy, any change in the internal energy of the piston system must balance out the change in that of the reservoir.

```{math}
\dd U_{\text{iso}}=0=\dd U_{\text{sys}} + \dd U_\text{res}
```

By expanding out the terms in both $\dd U_{\text{sys}}$ and $\dd U_\text{res}$, we have
```{math}
\begin{aligned}
\dd U_{\text{sys}} &= T\dd S_{\text{sys}} - P\dd V_{\text{sys}} + \sum_i \mu_i \dd n_i \\
\dd U_{\text{res}} &= T\dd S_{\text{res}} - P\dd V_{\text{res}} - \delta W_{\text{other res}}
\end{aligned}
```

where $\delta W$ is the infinitesimal change in the work, and $\delta$ is used to denote an infinitesimal change for a non-state variable like work. For the reservoir, since we know there would be no reaction happening in the reservoir, there is no chemical work. In addition to mechanical/expansion work and chemical work, all forms of work (e.g., electrical, magnetic work) other than "$PV$" mechanical work are represented by $\delta W_{\text{other res}}$. Plugging in terms and rearranging for $\delta W_{\text{other res}}$, we have

```{math}
\delta W_{\text{other res}} = T(\dd S_{\text{sys}}+\dd S_{\text{res}}) - P(\dd V_{\text{sys}} + \dd V_{\text{res}}) + \sum_i \mu_i \dd n_i
```

If we assume all processes happens reversibly in this isolated system, there is no net entropy production $\dd S_{\text{iso}} = 0 = \dd S_{\text{sys}}+\dd S_{\text{res}}$, and intuitively we know the total volume of an isolated system stays constant, $\dd V_{\text{iso}} = 0 = \dd V_{\text{sys}}+\dd V_{\text{res}}$. Then we have

```{math}
\delta W_{\text{other res}} = \sum_i \mu_i \dd n_i
```

If $T$ and $P$ are held constant, and by comparing with [Equation %s](#eq:dG_const_TP), we can then conclude
```{math}
\delta W_{\text{other res}} = \sum_i \mu_i \dd n_i  = \dd G\big|_{T, P}
```

In a nutshell, $\dd G\big|_{T, P}$ is the maximum amount of non-$PV$ work that is available to be extracted from the system, at constant $T$ and $P$, when the system is coupled to other forms of external reservoirs. In a fuel cell, $T$ and $P$ can be controlled and maintained. As a result, $\dd G\big|_{T, P}$ is used to determine the upper theoretical limit of non-$PV$ work available to be used/extracted from the system.