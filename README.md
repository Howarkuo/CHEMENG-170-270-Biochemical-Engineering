# CHEMENG-170-270-Biochemical-Engineering
## Lec9. Mass Balances for Two-Phase Bioreactors
- Resistance gas mass transfer, well mixed liquid, well-mixed gas / plug flow gas
## Lec10. Gas-Liquid Mass Transfer and kLa
- Experimental determination of kLa


## Gas–Liquid Mass Transfer in a Bioreactor — Question 5
<img width="675" height="405" alt="Screenshot 2026-11-05 at 12 21 35 AM" src="https://github.com/user-attachments/assets/a08901e5-ed81-408a-be55-cfa3d753ac3d" />


> **CBE 170A/270A study notes** | Physical classification, oxygen mass balances, and plug-flow gas derivation

## 1. Physical classification

The fermentor is a **two-phase gas–liquid contactor** with different mixing models for the two phases:


| Property | Gas phase | Liquid phase |
|---|---|---|
| Idealization | Plug flow (PFR-like) | Perfectly mixed (CSTR-like) |
| Oxygen variable | Gas-phase mole fraction, $y(z,t)$ | Dissolved oxygen, $C_{\text{O}_2}(t)$ |
| Axial gradient | Present: $\partial y/\partial z \neq 0$ | Neglected: $\partial C_{\text{O}_2}/\partial z = 0$ |
| At steady state | $y=y(z)$ | $C_{\text{O}_2}$ is uniform and constant |
| Oxygen transfer | **Sink**: oxygen leaves gas bubbles | **Source**: oxygen enters liquid |
---

Gas enters at **$z=0$** with oxygen mole fraction **$y_{\text{in}}$**, rises along reactor height **$Z$**, and exits at **$z=Z$** with **$y_{\text{out}}$**. The gas loses oxygen to the well-mixed liquid along the way.

```
             GAS OUT: y_out   (z = Z)
                     ↑
        ┌───────────────────────┐
        │  ○  ↑   ○  ↑   ○      │
        │  GAS: y = y(z,t)      │     O₂ transfers
        │                       │  ───────────────→ liquid
        │  LIQUID: C_O2(t)      │
        │  (perfectly mixed)    │
        │  ○  ↑   ○  ↑   ○      │
        └──────────┬────────────┘
                   ↑
             GAS IN: y_in    (z = 0)
```

**Important:** Steady state means $\partial y/\partial t=0$; it **does not** mean $\partial y/\partial z=0$. The gas still loses oxygen as it rises.

## 2. Conservation principle: how the gas is balanced

Apply the oxygen species balance to a *thin horizontal gas-containing slice* from $z$ to $z+dz$:

$$
\boxed{\text{Accumulation}=\text{O}_2\text{ in}-\text{O}_2\text{ out}-\text{O}_2\text{ transferred to liquid}}
$$

The transfer term is negative in the **gas** balance, but positive in the **liquid** balance.

### 2.1 Differential control-volume interpretation

For a conventional local balance, let:

- $A$ = total tank cross-sectional area ($\mathrm{m}^2$)
- $\varepsilon_g$ = local gas holdup ($\mathrm{m}^3\,gas/\mathrm{m}^3\,reactor$)
- $u_s$ = superficial gas velocity ($\mathrm{m/s}$)
- $C_g=Py/(RT)$ = oxygen concentration in gas ($\mathrm{mol/m^3\,gas}$)
- $A_L\,dz$ = liquid volume associated with the differential slice ($\mathrm{m^3\,liquid}$)
- $K_ga$ = overall gas-side transfer coefficient **per liquid volume**, so $K_ga(Py-HC_{\text{O}_2})$ has units of oxygen-transfer rate per liquid volume

Then:

**Accumulation**

$$
\varepsilon_g A\,dz\frac{\partial C_g}{\partial t}
$$

**Convective inlet and outlet**

$$
\dot n_{\mathrm{in}}=u_s A C_g(z),\qquad
\dot n_{\mathrm{out}}=u_s A C_g(z+dz)
$$

Using a first-order Taylor expansion,

$$
C_g(z+dz)=C_g(z)+\frac{\partial C_g}{\partial z}dz+\cdots
$$

so

$$
\dot n_{\mathrm{in}}-\dot n_{\mathrm{out}}
=-u_s A\frac{\partial C_g}{\partial z}dz.
$$

**Oxygen transferred to liquid**

$$
\dot n_{g\rightarrow L}=K_ga\,A_Ldz\,(Py-HC_{\text{O}_2}).
$$

Combining these terms and dividing by $A\,dz$ gives

$$
\boxed{
\varepsilon_g\frac{\partial}{\partial t}\left(\frac{Py}{RT}\right)
=-u_s\frac{\partial}{\partial z}\left(\frac{Py}{RT}\right)
-\frac{A_L}{A}K_ga(Py-HC_{\text{O}_2})
}
$$

This is a **physical explanation** of the balance. The exact phase-volume and velocity convention must be kept consistent when comparing it with the equation supplied by the exam; do **not** interchange $V_g$, $V_L$, $A$, and $\varepsilon_g$ without redefining the coefficients.

## 3. Equation supplied in Question 5

The question *provides* the following gas-phase equation; use it directly for the requested mathematical derivation:

$$
\boxed{
\frac{\partial}{\partial t}\left(\frac{PV_g}{RT}y\right)
=-u_s\frac{\partial}{\partial z}\left(\frac{PV_g}{RT}y\right)
-K_gaV_LP\left(y-\frac{H}{P}C_{\text{O}_2}\right)
}
$$

| Symbol | Meaning |
|---|---|
| $P$ | Total gas pressure |
| $T$ | Absolute temperature |
| $R$ | Ideal gas constant |
| $V_g$ | Gas volume (as defined in the given model) |
| $V_L$ | Liquid volume (as defined in the given model) |
| $u_s$ | Gas velocity in the given model |
| $y$ | Oxygen mole fraction in gas |
| $z$, $Z$ | Vertical coordinate and reactor height |
| $C_{\text{O}_2}$ | Dissolved oxygen concentration, uniform in the liquid |
| $H$ | Henry's law constant, with $P_{\text{O}_2}=HC_{\text{O}_2}$ |
| $K_ga$ | Overall gas-side volumetric mass-transfer coefficient |

### Why the three terms have these signs

1. **Accumulation:** local change in moles of oxygen held in the gas.
2. **$-u_s\,\partial(\cdots)/\partial z$ (axial convection):** net oxygen flow *into* the control volume from below minus oxygen flow *out* above. For oxygen absorption, $dy/dz<0$, making net convective supply positive.
3. **$-K_gaV_LP(y-HC_{\text{O}_2}/P)$ (interphase transfer):** oxygen leaves the gas and dissolves into the liquid when $y>HC_{\text{O}_2}/P$.

The balance is an **advection–interphase-transfer PDE**, not a well-mixed-gas CSTR balance.

## 4. Henry's law and the driving force

At equilibrium between a gas and a liquid concentration:

$$
P_{\text{O}_2}^{*}=HC_{\text{O}_2}.
$$

Define the equivalent gas-phase equilibrium mole fraction:

$$
\boxed{y^{*}=\frac{HC_{\text{O}_2}}{P}}
$$

The gas-side driving force is $y-y^*$:

- $y>y^*$: oxygen transfers **gas → liquid**.
- $y=y^*$: **no net** interphase transfer.
- $y<y^*$: oxygen would transfer **liquid → gas**.

Since the liquid is well mixed, $C_{\text{O}_2}$ and $y^*$ are independent of height (at a given time).

## 5. Question 5: steady-state gas-phase derivation

**Assumptions used for this derivation:** steady state; negligible variation of pressure with height; constant $T$, $u_s$, $V_g$, $V_L$, $K_ga$; spatially uniform liquid $C_{\text{O}_2}$.

**Step 1 — Eliminate accumulation**

$$
\frac{\partial}{\partial t}\left(\frac{PV_g}{RT}y\right)=0.
$$

Hence

$$
0=-u_s\frac{PV_g}{RT}\frac{dy}{dz}
-K_gaV_LP(y-y^*).
$$

**Step 2 — Isolate the axial gradient**

$$
\boxed{
\frac{dy}{dz}
=-\frac{K_gaV_LRT}{u_sV_g}(y-y^*)
}
$$

Define $\lambda=K_gaV_LRT/(u_sV_g)$ for compactness:

$$
\frac{dy}{dz}=-\lambda(y-y^*).
$$

**Step 3 — Separate and integrate**

$$
\frac{dy}{y-y^*}=-\lambda dz.
$$

With $y(0)=y_{\text{in}}$ and $y(Z)=y_{\text{out}}$:

$$
\int_{y_{\text{in}}}^{y_{\text{out}}}\frac{dy}{y-y^*}
=-\lambda\int_0^Z dz.$$

Therefore,

$$ \ln\!\left(\frac{y_{\text{out}}-y^ast}{y_{\text{in}}-y^ast}\right) = -\lambda Z$$


or

$$
\boxed{
\ln\!\left(\frac{y_{\text{in}}-y^ast}{y_{\text{out}}-y^ast}\right)
=\frac{K_gaV_LRTZ}{u_sV_g}
}
$$

**Step 4 — Solve for the overall gas-side coefficient**

$$
\boxed{
K_ga=\frac{u_sV_g}{V_LRTZ}
\ln\!\left(
\frac{y_{\text{in}}-HC_{\text{O}_2}/P}{y_{\text{out}}-HC_{\text{O}_2}/P}
\right)
}
$$

This step uses the **specific normalization in the equation supplied by Question 5**.

### Equivalent oxygen profile

Solving the ODE with $y(0)=y_{\text{in}}$ gives

$$
\boxed{y(z)=y^ast+(y_{\text{in}}-y^ast)e^{-\lambda z}}.
$$

The profile is exponential because oxygen flux becomes weaker as the gas approaches equilibrium with the liquid.

## 6. From the gas-side coefficient to $k_La$

The lecture's **two-film resistance model** states:

$$
\boxed{\frac{1}{K_ga}=\frac{1}{k_ga}+\frac{H}{k_La}}
$$

where all volumetric coefficients must be expressed on a **consistent interfacial-area / liquid-volume basis**.

Rearranging:

$$
\boxed{k_La=\frac{H}{\displaystyle\frac{1}{K_ga}-\frac{1}{k_ga}}}
$$

If the gas-film coefficient $k_ga$ is independently known, substitute the calculated $K_ga$ to determine $k_La$.

**Liquid-film-controlled approximation:** For sparingly soluble oxygen, the lecture often neglects gas-film resistance:

$$
\frac{1}{k_ga}\ll\frac{H}{k_La}
\quad\Rightarrow\quad
\boxed{k_La\approx HK_ga}.
$$

Then the simplified answer using Question 5's given model is

$$
\boxed{
k_La\approx\frac{Hu_sV_g}{V_LRTZ}
\ln\!\left(
\frac{y_{\text{in}}-HC_{\text{O}_2}/P}{y_{\text{out}}-HC_{\text{O}_2}/P}
\right)
}
$$

> **Qualification:** The problem statement does **not** explicitly say gas-film resistance is negligible. Without that assumption (or a known $k_ga$), inlet/outlet data determine $K_ga$, not uniquely $k_La$.

## 7. Liquid-phase balance: where does the transferred oxygen go?

For a well-mixed liquid with constant liquid volume and liquid volumetric flow $F$:

$$
\boxed{
V_L\frac{dC_{\text{O}_2}}{dt}
=F(C_{\text{O}_2,\text{in}}-C_{\text{O}_2})
+V_L\overline{OTR}-V_L OUR
}
$$

where:

- $F(C_{\text{O}_2,\text{in}}-C_{\text{O}_2})$ = net oxygen input in liquid streams;
- $V_L\overline{OTR}$ = oxygen gained from the gas;
- $V_L\,OUR$ = oxygen consumed by microorganisms.

For a height-independent liquid-volume-based coefficient, a uniform phase-area distribution, and the plug-flow solution above:

$$
\overline{OTR}=K_gaP(\bar y-y^*),
\qquad
\bar y=\frac{1}{Z}\int_0^Z y(z)\,dz.
$$

Let $n=\lambda Z$. Integration gives

$$
\boxed{
\bar y=y^ast+(y_{\text{in}}-y^ast)\frac{1-e^{-n}}{n}
}
$$

This explains why the lecture introduces a **height-averaged gas composition**: the gas oxygen mole fraction varies along the vessel, even though the liquid concentration is uniform.

## 8. Physical checks and common exam mistakes

- **Do not assume gas and liquid are both CSTRs.** Only the liquid is well mixed in Question 5.
- **Steady state is not spatial uniformity:** $\partial y/\partial t=0$, but $dy/dz$ can remain nonzero.
- **Sign of transfer:** gas loses oxygen; liquid gains the same transferred oxygen before consumption.
- **Equilibrium at the interface is not bulk equilibrium:** $P_i=HC_i$, but generally $P_g\neq HC_{\text{O}_2}$.
- **Driving force during absorption:** expect $y_{\text{in}}>y_{\text{out}}>y^*$ so the logarithm is positive.
- **Do not confuse $K_ga$ with $k_La$.** Convert using the two-film resistance relation.
- **Do not mix coefficient bases:** $a$ per unit liquid volume versus $a'$ per gas volume produce different numerical volumetric coefficients.
- **Watch dimensional conventions in the supplied equation:** its volume factors belong to its own model; a conventional local conservation law uses phase holdup and gas-flow cross section explicitly (Section 2).

## 9. Equations

$$
\underbrace{\frac{\partial}{\partial t}\left(\frac{PV_g}{RT}y\right)}_{\text{Gas O₂ accumulation}}
=-\underbrace{u_s\frac{\partial}{\partial z}\left(\frac{PV_g}{RT}y\right)}_{\text{Axial gas transport}}
-\underbrace{K_gaV_LP(y-y^*)}_{\text{O₂ transferred to liquid}}
$$

At steady state:

$$
\boxed{
\frac{dy}{dz}=-\frac{K_gaV_LRT}{u_sV_g}(y-y^*)
}
$$

Integrate between reactor bottom and top:

$$
\boxed{
K_ga=\frac{u_sV_g}{V_LRTZ}
\ln\left(\frac{y_{\text{in}}-y^ast}{y_{\text{out}}-y^ast}\right),
\qquad y^*=\frac{HC_{\text{O}_2}}{P}
}
$$

If liquid-film resistance dominates:

$$
\boxed{k_La\approx HK_ga}
$$

**Core principle:** In a plug-flow gas / mixed-liquid fermentor, gas oxygen composition changes **with height**, liquid oxygen concentration is **uniform in space**, and the gas-to-liquid transfer term appears as a **sink in the gas balance** and a **source in the liquid balance**.

---

