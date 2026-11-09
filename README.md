# CHEMENG-170-270-Biochemical-Engineering
## Textbook
- Bailey, J. E., & Ollis, D. F. (1986). Biochemical engineering fundamentals (2nd ed.). McGraw-Hill.
- Blanch, H. W., & Clark, D. S. (1996). Biochemical engineering. Marcel Dekker.
- Chaudhry, M. A. (2024, October 15). Lessons in bioreactor scale-up, Part 4: Physiochemical factors affecting oxygen transfer and the volumetric mass-transfer coefficient in stirred tanks. BioProcess International, 22(10).
- Shuler, M. L., Kargi, F., & DeLisa, M. P. (2017). Bioprocess engineering: Basic concepts (3rd ed.). Prentice Hall.

## Lec9. Mass Balances for Two-Phase Bioreactors
- Resistance gas mass transfer, well mixed liquid, well-mixed gas / plug flow gas
- 9.1 CFD applications to bioreactor processes
- 9.2  Oxygen transport from bubbles to intracellular reaction sites /  oxygen supply to fermentation or cell-culture bioreactors
## Lec10. Gas-Liquid Mass Transfer and kLa
- Experimental determination of kLa
- probe response time and gas-phase dynamics
- Off-gas mass-balance method
- Maximum sustainable biomass and critical Disolved oxygen
-  Circulation-time oxygen limitation
-  Alternative k_La measurement methods
[Lessons in Bioreactor Scale-Up, Part 3-by Muhammad Arshad Chaudhry (September 9, 2024)
](https://www.bioprocessintl.com/bioreactors/lessons-in-bioreactor-scale-up-part-3-experimental-determination-and-application-of-oxygen-mass-transfer-rate-mass-transfer-coefficient-and-oxygen-uptake-rate)
# Connecting CFD, Oxygen Transport Resistances, and Bioreactor Mass Balances

The 2 lectures describe oxygen transport at different scales.

1. CFD: How fluid motion and mixing distribute oxygen throughout an industrial bioreactor.
2. Mass-transfer resistances: How oxygen travels from a gas bubble to a microorganism.
3. Rate limitation: Which transport step controls the amount of oxygen available for cellular metabolism.


$$
\boxed{ \text{Fluid flow} \longrightarrow \text{Mass-transfer coefficients} \longrightarrow OTR \longrightarrow \text{Cellular oxygen availability} }
$$

## 9.1.  CFD applications to bioreactor processes

<img width="1035" height="602" alt="Screenshot 2026-11-06 at 11 32 45 PM" src="https://github.com/user-attachments/assets/07290b1d-1077-4788-b3d4-90db6136c850" />

Compares liquid-phase velocity distributions in 40, 60, and 90 m³ bioreactors.

The colors indicate local velocity magnitude, from approximately 0 to 5 m/s. Red regions near impellers have relatively high velocities, whereas blue regions have low velocities.

### A. Governing equations for CFD

Computational fluid dynamics solves conservation equations describing fluid motion.

Continuity equation (incompressible liquid)

$$
\boxed{\nabla\cdot\mathbf{u}=0}
$$

Momentum balance (Navier–Stokes)

$$
\boxed{ \rho\left( \frac{\partial\mathbf{u}}{\partial t} +\mathbf{u}\cdot\nabla\mathbf{u} \right) = -\nabla P+\mu\nabla^2\mathbf{u} +\rho\mathbf{g}+\mathbf{f} }
$$

where $\mathbf{f}$ represents additional modeled forces, such as impeller or interphase forces.

| Symbol           | Physical meaning           | Unit  |
| ---------------- | -------------------------- | ----- |
| $\mathbf{u}$ | Liquid velocity vector     | m/s   |
| $\rho$       | Liquid density             | kg/m³ |
| $P$          | Pressure                   | Pa    |
| $\mu$        | Dynamic viscosity          | Pa·s  |
| $\mathbf{g}$ | Gravitational acceleration | m/s²  |

In solids and stationary fluids, mass transfer occurs mainly because of molecular diffusion. Most systems of bioprocessing interest, however, contain moving fluid, so both molecular diffusion and convective mass transfer are important considerations for bioreactor operation and scale-up.(Chaudhry, M. A. (2024, October 15).)




### B. How does velocity influence mass transfer?

For oxygen transported through liquid, the local species balance can be expressed as:

$$
\boxed{ \frac{\partial C}{\partial t} +\mathbf{u}\cdot\nabla C = \nabla\cdot(D_{\mathrm{eff}}\nabla C) +S_{O_2} }
$$

where:

$$
S_{O_2}=OTR-OUR
$$

This equation connects fluid motion to oxygen distribution.

- $\mathbf{u}\cdot\nabla C$: oxygen transported by bulk liquid movement (advection).
- $\nabla\cdot(D_{\mathrm{eff}}\nabla C)$: oxygen redistributed by molecular and modeled turbulent diffusion.
- $OTR$: Oxygen Transfer Rate, oxygen entering the liquid from gas bubbles, molar per unit liquid volume per second .
- $OUR$: Oxygen usage Rate, oxygen consumed by microorganisms,molar per unit liquid volume per second.

This is a more spatially resolved form of the familiar well-mixed oxygen balance:

$$
\boxed{\frac{dC}{dt}=OTR-OUR}
$$

In the well-mixed model, concentration gradients are neglected. In CFD, they can be explicitly calculated.

### C. Why does this matter during scale-up?

The 40, 60, and 90 m³ reactors show different flow patterns, despite broadly similar impeller arrangements.

Consequently, scaling up a bioreactor does not automatically preserve:

- Mixing time
- Local oxygen concentration
- Shear stress
- Gas–liquid mass-transfer performance

CFD helps identify whether parts of the vessel may have insufficient mixing or oxygen supply.

## 9.2.— Oxygen transport from bubbles to intracellular reaction sites /  oxygen supply to fermentation or cell-culture bioreactors
During cultivation, O2 transfers from sparged air (gas phase) through the gas–liquid interface to the bulk liquid medium. There, culturing cells consume the oxygen and produce CO2 through cellular respiration. Once excreted into the liquid medium, that CO2 passes through the gas–liquid interface and diffuses into the gas phase to be carried out of the bioreactor. Transfer of O2 or CO2 molecules from one phase to another occurs only when those phases have different concentrations. If, for example, O2 concentration is in equilibrium between two phases — e.g., when liquid medium is saturated with oxygen — then there will be no net O2 transfer in either direction. And if O2 mass transfer from gas bubbles is slow, the rate of cellular metabolism will depend on the rate of oxygen supply from the gas phase. Because O2 is a critical component of aerobic metabolism and is sparingly soluble in aqueous solutions, considerable research has gone into understanding its mass-transfer mechanisms — and into ways to improve the oxygen supply across the gas–liquid interface, especially in complex systems such as bioreactors. (Chaudhry, M. A. (2024, October 15).)

The lecture diagrams trace oxygen transport through nine numbered regions (0–8).
<img width="963" height="597" alt="Screenshot 2026-11-06 at 11 33 37 PM" src="https://github.com/user-attachments/assets/198d01f7-8d04-4626-a37e-dbd95c5f2a76" />


### A. Classify the resistances
<img width="738" height="371" alt="Screenshot 2026-11-06 at 11 34 06 PM" src="https://github.com/user-attachments/assets/7d29896f-dbbd-4516-8a20-a6c0a1c5dd37" />


| Region | Physical location                | Resistance indicated on      |
| ------ | -------------------------------- | --------------------------------- |
| 0      | Bulk gas                         | Low                               |
| 1      | Gas film inside bubble           | Low                               |
| 2      | Gas–liquid interface             | Low; local equilibrium assumed    |
| 3      | Liquid film around bubble        | High                              |
| 4      | Bulk liquid                      | Low; well mixed                   |
| 5      | Liquid film around microorganism | High                              |
| 6      | Liquid–cell interface            | Low; local equilibrium assumed    |
| 7      | Inside cell or solid             | High                              |
| 8      | Intracellular reaction site      | Reaction kinetics may be limiting |

The s particularly emphasize regions 3, 5, and 7, plus the oxygen-consuming reaction at region 8.

## 3. Region 3 — Gas–liquid film resistance

This is the resistance  described by the two-film model. ($$P_i$$, $$C_i$$:at the gas-liquid interface / in the bulk gas phase)
($$N_{O_2} $$:Molar flux of oxygen (rate of mass transfer per unit area))
($H$: Henry's law constant ($H = P_i / C_i$))

Gas-film flux:

$$
N_{O_2}=k_g(P_g-P_i)
$$

Liquid-film flux:

$$
N_{O_2}=k_L(C_i-C_L)
$$

Equilibrium at the interface (Henry's Law):

$$
P_i=HC_i
$$

### Step 1 — Express the interfacial values in terms of flux

Rearrange the gas-film and liquid-film flux equations. Here $C_L$ is the bulk-liquid oxygen concentration.

$$
P_i=P_g-\frac{N_{O_2}}{k_g},
\qquad
C_i=C_L+\frac{N_{O_2}}{k_L}
$$

### Step 2 — Substitute into Henry's law

Insert the expressions for $P_i$ and $C_i$ into $P_i=HC_i$.

$$
P_g-\frac{N_{O_2}}{k_g}
=H\left(C_L+\frac{N_{O_2}}{k_L}\right)
$$

### Step 3 — Collect the flux terms

Expand the right-hand side.

$$
P_g-\frac{N_{O_2}}{k_g}
=HC_L+\frac{H N_{O_2}}{k_L}
$$

Move $HC_L$ to the left and factor the flux on the right.

$$
P_g-HC_L
=\frac{N_{O_2}}{k_g}+\frac{H N_{O_2}}{k_L}
=N_{O_2}\left(\frac{1}{k_g}+\frac{H}{k_L}\right)
$$

### Step 4 — Solve for the oxygen flux

$$
N_{O_2}
=\frac{P_g-HC_L}{\dfrac{1}{k_g}+\dfrac{H}{k_L}}
$$

### Step 5 — Define the overall gas-side coefficient

The gas-side coefficient $K_g$ combines the gas-film resistance and the liquid-film resistance expressed on a gas-pressure basis.

$$
\frac{1}{K_g}=\frac{1}{k_g}+\frac{H}{k_L},
\qquad
N_{O_2}=K_g(P_g-HC_L)
$$

Multiplying the flux by the interfacial area per unit liquid volume $a$ gives $OTR=aN_{O_2}$. Dividing the resistance equation by $a$ gives the volumetric form.

$$
\boxed{\frac{1}{K_ga}=\frac{1}{k_ga}+\frac{H}{k_La}}
$$

The lecture assumes negligible gas-film resistance for oxygen.

Therefore:

$$
\frac{1}{K_ga}\approx\frac{H}{k_La}
$$

and:

$$
\boxed{OTR\approx k_La(C^*-C_L)}
$$

where:

$$
C^*=\frac{P_{O_2}}H
$$

### Flux and resistance on a liquid-concentration basis

The two films act like resistors in series. The same interfacial flux passes through both films, and the driving force equals the flux times the total resistance. For oxygen, let $J=N_{O_2}$ in mol/(m²·s). With the Henry's law convention $P=HC$, the equilibrium liquid concentration corresponding to the **bulk gas** is $C^{\ast}=P_g/H$. The actual interfacial liquid concentration is $C_i=P_i/H$.

Since $P_g-HC_L=H(C^{\ast}-C_L)$, the overall liquid-side coefficient is $K_L=HK_g$. The flux–resistance relation is

$$
J=K_L(C^{\ast}-C_L)
=\frac{C^{\ast}-C_L}{R_{\mathrm{total}}},
\qquad
R_{\mathrm{total}}=\frac{1}{K_L}
=\underbrace{\frac{1}{Hk_g}}_{R_G}
+\underbrace{\frac{1}{k_L}}_{R_L}.
$$

Here $K_L$ is in m/s, and both resistances are in s/m because they are expressed on the same liquid-concentration basis.

| Film | Location | Factors that affect resistance |
| --- | --- | --- |
| Gas film, $R_G=1/(Hk_g)$ | Gas side of the bubble interface | Gas diffusivity and circulation within the bubble |
| Liquid film, $R_L=1/k_L$ | Liquid immediately outside the bubble | Liquid diffusivity, viscosity, and turbulence near the interface |

### Which film controls the flux?

- **Liquid-film control** occurs when $Hk_g\gg k_L$. Then $R_G\ll R_L$ and $K_L\approx k_L$. With $H=P/C$, lower solubility corresponds to a larger $H$, which favors liquid-film control. The lecture uses this approximation for oxygen. Methane can also fall in this regime, depending on the film coefficients.
- **Gas-film control** occurs when $Hk_g\ll k_L$. Then $R_G\gg R_L$ and $K_L\approx Hk_g$. High solubility can favor this regime, for example during ammonia absorption. For volatile organic compounds, compare the actual resistances for the compound and operating conditions.

Under liquid-film control, $1/(K_ga)\approx H/(k_La)$. The volumetric oxygen transfer rate is

$$
OTR=aJ=K_La(C^{\ast}-C_L)\approx k_La(C^{\ast}-C_L).
$$

## Overall resistance of Gas Mass Transfer(R), Gas interfacial Flux(J):  follows an analogue of Ohm's Law-- Inverse proportional! 
<img width="747" height="815" alt="Screenshot 2026-11-07 at 5 26 03 PM" src="https://github.com/user-attachments/assets/6a359048-d79a-474f-a86f-4c68eabe4466" />


<img width="1089" height="711" alt="Screenshot 2026-11-07 at 5 39 47 PM" src="https://github.com/user-attachments/assets/0586afaa-bcf3-428e-8610-aa701b4dc4c7" />
<img width="1095" height="689" alt="Screenshot 2026-11-07 at 5 39 58 PM" src="https://github.com/user-attachments/assets/9b6d7b97-6fbb-44a8-8ff2-44418a5c299f" />
<img width="1107" height="695" alt="Screenshot 2026-11-07 at 5 40 59 PM" src="https://github.com/user-attachments/assets/fd86995b-29ad-45a9-bcde-46d1b8bf9c73" />
<img width="1091" height="698" alt="Screenshot 2026-11-07 at 5 41 08 PM" src="https://github.com/user-attachments/assets/4e4a92a6-cd54-4827-9ad7-7980f7969562" />
<img width="1098" height="474" alt="Screenshot 2026-11-07 at 5 41 30 PM" src="https://github.com/user-attachments/assets/e8160665-65a3-43aa-8da4-4d066c95806e" />
<img width="1065" height="600" alt="Screenshot 2026-11-07 at 5 41 57 PM" src="https://github.com/user-attachments/assets/afaefaab-8eef-4f4b-9d9d-8df4c25d8d83" />



### How does CFD connect to $k_La$?

Recall:

$$
\boxed{k_La=k_L\cdot a}
$$

where:

- $k_L$ is the liquid-film mass-transfer coefficient, m/s.
- $a$ is specific gas–liquid interfacial area, m²/m³.
- $k_La$ has units of s⁻¹.

Fluid motion can affect both.

Effect on $k_L$: Greater liquid-side mixing can increase transport near bubble surfaces and reduce the effective diffusion boundary-layer resistance.

A simplified film approximation is:

$$
\boxed{k_L\sim\frac{D_{O_2}}{\delta}}
$$

where $\delta$ is an effective diffusion-film thickness.

Effect on $a$: Bubble breakup and gas dispersion change the total interfacial area.

For approximately spherical of uniform diameter:

$$
\boxed{a=\frac{6\varepsilon_g}{d_b(1-\varepsilon_g)}}
$$

when $a$ is based on liquid volume, and $\varepsilon_g$ is gas holdup.

Thus, changes in flow pattern can change bubble size, gas holdup, and ultimately oxygen transfer.

Note that the CFD images display liquid velocity only. They do not directly show $k_La$, gas holdup, or oxygen concentration.

## 4. Region 5 — Liquid film around microorganisms

After oxygen reaches the bulk liquid, it must move toward the microorganisms.

For a simplified cell-surface mass-transfer model:

$$
\boxed{N_{O_2,\mathrm{cell}}=k_{L,\mathrm{cell}}(C_L-C_s)}
$$

where:

- $C_L$: dissolved oxygen concentration in bulk liquid.
- $C_s$: oxygen concentration at the cell surface.
- $k_{L,\mathrm{cell}}$: liquid-side transfer coefficient surrounding the cell.

The total oxygen transport into cells per liquid volume is approximately:

$$
\boxed{ r_{\mathrm{cell,transfer}} = k_{L,\mathrm{cell}}a_{\mathrm{cell}}(C_L-C_s) }
$$

Here $a_{\mathrm{cell}}$ is the total exposed cell-surface area per unit liquid volume.

Physical interpretation: Even if $k_La$ is high at the gas bubbles, cell uptake can still be limited if oxygen cannot reach the cell surface fast enough.

The lecture notes that for individual bacteria or yeast cells, the bubble-side liquid film (region 3) is often the greater resistance.

For large cell aggregates, region 5 can become important because oxygen must diffuse through the fluid layer surrounding the aggregate.

## 5. Region 7 — Intracellular diffusion resistance

Oxygen must also move through the cell or microbial aggregate to reach the site of oxygen consumption.

A simplified diffusion model is Fick's law:

$$
\boxed{\mathbf{J}_{O_2}=-D_{\mathrm{eff}}\nabla C}
$$

where:

- $\mathbf{J}_{O_2}$: diffusive oxygen flux, mol/(m²·s).
- $D_{\mathrm{eff}}$: effective oxygen diffusivity, m²/s.
- $\nabla C$: oxygen concentration gradient, mol/m⁴.

For a reaction–diffusion system, the governing equation is:

$$
\boxed{ \frac{\partial C}{\partial t} = \nabla\cdot(D_{\mathrm{eff}}\nabla C) -r_{O_2} }
$$

where $r_{O_2}$ is the local oxygen consumption rate per volume.

At steady state:

$$
\boxed{ \nabla\cdot(D_{\mathrm{eff}}\nabla C)=r_{O_2} }
$$

This equation becomes particularly useful for microbial pellets or cell aggregates because oxygen concentration may decrease toward the center.

For individual small cells, intracellular gradients are often less important than for large pellets, although the actual importance depends on uptake kinetics and diffusivity.

## 6. Region 8 — Intracellular oxygen consumption

The oxygen that reaches the intracellular reaction sites is consumed by metabolic reactions.

Lecture 10 expresses oxygen uptake in terms of biomass concentration.

$$
\boxed{OUR=q_{O_2}X}
$$

For growth-associated oxygen consumption:

$$
\boxed{OUR=\frac{\mu_gX}{Y_{X/O_2}}}
$$

These expressions describe oxygen demand rather than oxygen transfer from bubbles.

This is the distinction between OTR and OUR:

$$
\underbrace{OTR}_{\text{oxygen supplied}} \qquad\text{versus}\qquad \underbrace{OUR}_{\text{oxygen consumed}}
$$

At quasi-steady dissolved oxygen:

$$
\boxed{OTR=OUR}
$$

But this equality alone does not identify which transport resistance is controlling.

## 7. Connecting the complete pathway

Oxygen inside gas bubble

$P_{O_2}$

Region 3 — Gas–liquid mass transfer

$OTR\approx k_La(C^*-C_L)$

Region 4 — Bulk dissolved oxygen

$C_L$

Region 5 — Cell-surface transport

$N_{O_2,\mathrm{cell}}=k_{L,\mathrm{cell}}(C_L-C_s)$

Region 7 — Intracellular diffusion

$\mathbf J_{O_2}=-D_{\mathrm{eff}}\nabla C$

Region 8 — Cellular oxygen consumption

$OUR=q_{O_2}X$

## 8. Why different organisms have different controlling resistances


 3 compares the likely rate limitations across microbial systems.

| System                           | Likely important limitation                      | Engineering implication                             |
| -------------------------------- | ------------------------------------------------ | --------------------------------------------------- |
| Individual bacteria (1–2 µm)     | Region 3: bubble-side liquid film                | Improve gas dispersion and $k_La$               |
| Yeast (5–8 µm)                   | Often region 3                                   | Improve oxygen delivery                             |
| Large microbial pellets or flocs | Region 5 and possibly internal diffusion         | Improve external transport and consider pellet size |
| Dense microbial aggregates       | Region 7: internal diffusion                     | Evaluate internal oxygen gradients                  |
| Oxygen-limited metabolism        | Region 8: reaction kinetics may influence uptake | Evaluate oxygen consumption kinetics                |

These are the qualitative tendencies given by the lecture, not universal rankings of resistance.
# Lecture 10 — Measuring oxygen transfer and uptake

The methods below extend the well-mixed liquid balance from Lecture 9. Here $C$ denotes bulk dissolved oxygen (DO), $C^*$ is the liquid concentration in equilibrium with the bulk gas, and $V_L$ is liquid volume. OTR and OUR are volumetric rates, for example in mmol/(L·h).

## 1. Oxygen saturation and driving force

For air at 1 atm and 37 °C, the dry-air oxygen partial pressure is about 0.21 atm (160 mm Hg). The reference air-saturated DO in water is approximately 0.21 mmol/L (6.8 mg/L). Actual saturation depends on gas composition, pressure, temperature, and medium composition. With air saturation as the calibration reference, $\%\mathrm{DO}=100C/C^*_{\mathrm{air}}$. Oxygen enrichment raises $C^*$, and nitrogen sparging lowers it.

$$
\frac{dC}{dt}=k_La(C^{\ast}-C)
\qquad\Longrightarrow\qquad
\ln\!\left(\frac{C^{\ast}-C(t)}{C^{\ast}-C(t_0)}\right)
=-k_La(t-t_0)
$$

At equilibrium, the driving force is zero. A negative $C^*-C$ causes oxygen stripping. Respiration-generated carbon dioxide can travel in the opposite direction, from broth to bubbles and out through the exhaust.

## 2. Cell-free dynamic measurement of kLa

1. Establish stable DO under air sparging at the selected agitation and airflow.
2. Replace air with nitrogen to lower DO, then restore air at the original flow and record the recovery.
3. Fit the recovery over a suitable range, such as 20–80% air saturation, using the stable final DO as $C^*$.

With no cellular uptake and constant $C^*$ and $k_La$, integration gives

$$
\frac{dC}{dt}=k_La(C^ast-C)
\qquad\Longrightarrow\qquad
\ln\!\left(\frac{C^ast-C(t)}{C^ast-C(t_0)}\right)
=-k_La(t-t_0)
$$

The slope of the logarithmic plot is $-k_La$, and $1/(k_La)$ is the characteristic oxygen-transfer time.

| Assumption | Practical check |
| --- | --- |
| The liquid is well mixed | Compare DO traces at different locations when gradients are plausible, especially in large or viscous systems. |
| The DO probe is fast | Check that the probe time constant $\tau_p$ is much smaller than $1/(k_La)$. Probe lag can flatten the fitted response. |
| The probe surface film contributes little resistance | Check probe response under the agitation and viscosity of the measurement. |
| Gas composition and holdup settle quickly after the switch | Compare nitrogen stripping with an aeration interruption in a respiring culture under comparable conditions. Agreement supports treating gas transients as small. |

Two other measurement approaches are the gas oxygen balance, which uses measured gas-phase depletion and the liquid driving force, and sulfite oxidation, which chemically consumes dissolved oxygen. Sulfite results characterize the test liquid and conditions, whose bubble behavior can differ from culture broth.

## 3. Measuring OUR and specific oxygen uptake

The batch liquid balance links the three measurement methods.

$$
\frac{dC}{dt}=k_La(C^ast-C)-OUR,\qquad OUR=q_{O_2}X
$$

| Method | Measurements and calculation |
| --- | --- |
| Inlet–outlet gas balance | Use an oxygen analyzer and gas-flow measurements to determine OTR. Subtract liquid DO accumulation measured by the DO probe to obtain OUR. |
| Dynamic test with live cells | Briefly interrupt aeration and estimate $OUR\approx-dC/dt$ after residual transfer becomes negligible. Restore the original aeration and use the recovery trace to determine $k_La$. Keep the test above oxygen-limiting DO so uptake stays approximately constant. |
| DO profile with independently known OTR | Obtain the local DO slope and calculate $OUR=OTR-dC/dt$. If OTR is calculated from $k_La$, both $C^*$ and $C$ are also required. |

With negligible gas-phase oxygen accumulation, the general gas balance is

$$
OTR=\frac{\dot n_{g,\mathrm{in}}y_{O_2,\mathrm{in}}-\dot n_{g,\mathrm{out}}y_{O_2,\mathrm{out}}}{V_L}
$$

The gas molar flow rates and oxygen fractions must use the same wet or dry basis. If inlet and outlet volumetric flows are equal at the same reference conditions, this reduces to $OTR=(Q_g/V_L)(C_{g,\mathrm{in}}-C_{g,\mathrm{out}})$. For a short interval, the average OUR is the average OTR minus $\Delta C/\Delta t$. An independently measured cell or biomass concentration gives $q_{O_2}=OUR/X$ on the corresponding basis.

During recovery in the live-cell test, use the air-off estimate of OUR:

$$
k_La=\frac{dC/dt+OUR}{C^ast-C}
$$

A fit across the recovery interval can reduce the sensitivity to noisy pointwise slopes.

## 4. Aeration capacity and the cell-density limit

At a quasi-steady DO setpoint $C_{\mathrm{set}}$ and approximately constant $q_{O_2}$, setting $OTR=OUR$ gives

$$
X_{\mathrm{supported}}
=\frac{k_La(C^ast-C_{\mathrm{set}})}{q_{O_2}}
$$

The theoretical zero-DO ceiling is $X_{\max}=k_La C^ast/q_{O_2}$. A positive setpoint or minimum allowable DO gives an operating estimate. With $q_{O_2}$ in mmol/(cell·h) and OTR in mmol/(L·h), the result is in cells/L.

The article reports typical $q_{O_2}$ ranges of $2$–$8\times10^{-10}$ mmol/(cell·h) for CHO cells and $2$–$4\times10^{-10}$ mmol/(cell·h) for hybridoma and myeloma cells. Even with comparatively low per-cell demand, high-density fed-batch and perfusion cultures can exhaust the limited DO inventory rapidly. Oxygen-enriched sparging increases the driving force, while agitation, gas flow, and sparger or impeller design can increase transfer capacity.

### Circulation through a low-transfer zone

A vessel-average DO reading can conceal oxygen-poor regions. Model a circulating liquid parcel as leaving an impeller zone at $C_0$ and spending $t_c$ in a low-transfer zone with a constant local coefficient $K=(k_La)_{\mathrm{low}}$. With constant local $C^*$ and $q_{O_2}X$, the parcel balance gives

$$
C(t)=C^ast+(C_0-C^ast)e^{-Kt}
-\frac{q_{O_2}X}{K}(1-e^{-Kt})
$$

Taking $C_0\approx C^*$ and requiring $C(t_c)\ge C_{\mathrm{crit}}$ gives

$$
X\le X_{\mathrm{crit}}
=\frac{K(C^*-C_{\mathrm{crit}})}
{q_{O_2}(1-e^{-Kt_c})}
$$

In the limit of negligible local transfer, $X_{\mathrm{crit}}\to(C^*-C_{\mathrm{crit}})/(q_{O_2}t_c)$. Longer residence in the low-transfer zone gives cells more time to deplete oxygen before the next pass through the impeller zone.

## 5. Scale-up, technology transfer, and culture monitoring

- **Within an equipment platform.** Adjust gas flow, agitation, and hardware to reproduce oxygen transfer at the target culture conditions. Matching $k_La$ reproduces OTR only when the oxygen driving force also matches.
- **Across equipment platforms.** Use measured $k_La$ or OTR to compare vessels with different geometry, power input per volume, superficial gas velocity, or gas flow per liquid volume (vvm).
- **During a batch.** Cells, products, and metabolites can change viscosity and bubble coalescence. Changes in bubble size and holdup can shift $k_La$ over time, so a cell-free measurement is a baseline.
- **During culture monitoring.** OUR often rises during exponential growth and falls as metabolism slows. The specific rate $q_{O_2}$ varies with cell line, growth phase, and culture conditions. DO can rise as demand falls if aeration and agitation stay fixed. OUR can support cell-line characterization, fed-batch feeding decisions, or viable-cell estimation where a suitable $q_{O_2}$ calibration exists.

### Source

[Chaudhry, *Lessons in Bioreactor Scale-Up, Part 3*, BioProcess International (2024)](https://www.bioprocessintl.com/bioreactors/lessons-in-bioreactor-scale-up-part-3-experimental-determination-and-application-of-oxygen-mass-transfer-rate-mass-transfer-coefficient-and-oxygen-uptake-rate)

The probe criterion and cell-density equations above follow from dimensional consistency and the oxygen balance. The pasted source renders the probe criterion with units of inverse time on the right and the cell-density expression with multiplication by $q_{O_2}$.



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

