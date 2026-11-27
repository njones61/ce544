# Seepage Analysis: Study Guide

## Outline of Main Concepts

### 1. Hydraulic Head

* Below the water table, with the water at rest, the pore pressure is $u = \gamma_w h_w$, where $h_w$ is the depth below the water table and $\gamma_w = \rho g$ = 9.81 kN/m³ or 62.4 lb/ft³.
* Bernoulli's equation comes from the work done to move a unit mass of water from A to B: lifting it, $W_1 = gz$; changing its speed, $W_2 = (v_b^2 - v_a^2)/2$; and compressing it, $W_3 = (u_b - u_a)/\rho_w$. Dividing the total work by $g$ gives work per unit weight, a length, which is head.
* Total head at a point: $h = z + v^2/2g + u/\gamma_w$, the elevation head plus the velocity head plus the pressure head.
* Elevation head, $h_{el} = z$, is the height above a datum. The datum is arbitrary, but the same datum must be used for every point.
* Velocity head is negligible for groundwater: $v = 10^{-6}$ ft/s gives $v^2/2g = 1.6 \times 10^{-14}$ ft, and even 1 ft/s gives only 0.016 ft.
* Pressure head, $h_p = u/\gamma_w$, is the height the water rises in a piezometer above the point.
* Total head for groundwater: $h = z + u/\gamma_w$, the level the water rises to in a piezometer at the point, measured from the datum.
* Water flows only where the total head changes, from higher to lower total head, whatever the pressures. Water flows from A to B when $u_a = u_b$ and $z_a > z_b$, and also when $z_a = z_b$ and $u_a > u_b$.
* Example 3 (datum at C): $h_a = 7 + 2 = 9$ ft and $h_c = 0 + 2 = 2$ ft. The head drops linearly in uniform soil, so $h_b = 9 - \tfrac{3}{7}(7) = 6$ ft, $u_b/\gamma_w = 6 - 4 = 2$ ft, and $u_b = 124.8$ psf. The pore pressure is the same at A, B, and C, and water still flows from A to C.

### 2. Darcy's Law

* Darcy's 1856 sand column tests in Dijon, France, gave $q = kA(h_2 - h_1)/L$. $k$ is the hydraulic conductivity, or coefficient of permeability [L/T], and $A$ is the gross cross-sectional area.
* Short form: $q = kiA$, with the dimensionless hydraulic gradient $i = \Delta h/L$. Differential form: $i = -dh/ds$; the minus sign is there because head decreases in the direction of flow.
* Discharge velocity (Darcian velocity, specific discharge): $v_d = q/A = ki$.
* Seepage velocity, the average speed of the water in the pores: $v_s = v_d/n = ki/n$, always greater than $v_d$.
* Not all voids conduct flow (dead-end pores, voids filled with fines). Effective porosity $n_e = A_f/A = \lambda n$, and $v_s = ki/n_e$. For clay, $n$ = 0.40 to 0.70 and $n_e$ = 0.01 to 0.18.
* Travel time along a flow path: $t = L/v_s = Ln_e/(ki)$.
* $k$ ranges over about twelve orders of magnitude (Bear 1972). 1 cm/s = $10^{-2}$ m/s ≈ 2,835 ft/day.
* Darcy's law holds while flow in the pores is laminar, $\mathrm{Re} = \rho v_d d/\mu$ below about 1 to 10. It may not hold in coarse gravel, rockfill, or near well screens.
* Layered systems. Parallel to the layers, the gradient is the same in every layer and the flows add: $k_{eq} = \sum k_i H_i / \sum H_i$. Perpendicular, the flow is the same in every layer and the head losses add: $k_{eq} = \sum H_i / \sum (H_i/k_i)$. Parallel flow concentrates in the high-k layers; perpendicular head loss concentrates in the low-k layers.
* Example: 10 ft of sand, 2 ft of clay, and 8 ft of gravel. Parallel, $k_{eq}$ = 114.8 ft/day and 99% of the flow goes through the gravel. Perpendicular, $k_{eq}$ = 0.00283 ft/day and nearly all 5 ft of head is lost in the clay.

### 3. Governing Equations

* Isotropic soil in 2D: $v_x = -k\,\partial h/\partial x$ and $v_y = -k\,\partial h/\partial y$.
* In an anisotropic soil, $k$ is largest along one principal axis ($r$, $k_{max}$) and smallest at right angles to it ($s$, $k_{min}$). The matrix of conductivities is the conductivity tensor.
* In $x$ and $y$: $k_{xx} = k_r\cos^2\alpha + k_s\sin^2\alpha$, $k_{yy} = k_r\sin^2\alpha + k_s\cos^2\alpha$, and $k_{xy} = k_{yx} = \tfrac{1}{2}(k_r - k_s)\sin 2\alpha$. The cross term is zero when the principal axes line up with $x$ and $y$.
* In 3D the tensor is symmetric. In most cases $k_{xx} = k_{yy}$ and $k_{xx} > k_{zz}$.
* Assumptions: the soil is saturated, Darcy's law is valid, and mass is conserved, inflow − outflow = Δstorage/Δt + sources and sinks. For steady flow with no sources or sinks, inflow − outflow = 0.
* A mass balance on a small box, with constant density and Darcy's law, gives on the principal axes $k_x \partial^2 h/\partial x^2 + k_y \partial^2 h/\partial y^2 + k_z \partial^2 h/\partial z^2 = 0$. With $k_x = k_y = k_z$ it is the Laplace equation. The solution is $h(x, y, z)$.
* The course solves it three ways: flow nets, analytical solutions, and numerical solutions. XSLOPE uses finite elements.
* Every part of the boundary needs a boundary condition: known head (reservoir level), no flow (impervious foundation, sheet piles, lines of symmetry), exit face ($h = z$ where water seeps out), or specified flux (recharge). The free surface is part of the solution, not an input.

### 4. Flow Nets

* A flow net is a graphical solution to the 2D Laplace equation, made of flow lines (the paths water follows) and equipotential lines (lines of constant total head).
* Rule 1: flow is in the direction of maximum drop in total head, so flow lines and equipotential lines cross at 90°.
* Rule 2: cells have a uniform length-to-width ratio. Then every flow channel carries the same flow and every equipotential drop is equal. Construction is easiest with $l/b = 1$.
* Partial drops are counted: 5 full drops and a partial drop with $b/l = 0.2$ give $n_e = 5.2$. A non-square cell at a corner, subdivided, gives three squares and one non-square cell of the same shape.
* In unconfined flow the line of seepage (free surface, phreatic surface) is a flow line and a line of zero pressure.
* Head and pressure: each drop is $\Delta h = h/n_e$. In the sheet pile example (10 ft lost over 6 drops), point C at 4.5 drops has $h = 40 - 4.5(10/6) = 32.5$ ft; at 5 ft elevation, $h_p = 27.5$ ft and $u = 1716$ psf.
* Flow rate: $q = k\dfrac{n_f}{n_e}\dfrac{b}{l}h$, and for square cells $q = k\dfrac{n_f}{n_e}h$. With $k$ = 2 ft/day, $n_f$ = 3, $n_e$ = 6, and $h$ = 10 ft, $q$ = 10 ft³/day per foot.
* Anisotropic soil: flow lines and equipotential lines no longer cross at right angles. Transform the section with $\underline{x} = x\sqrt{k_y/k_x}$, draw square cells, and transform back. The flow uses $\underline{k} = \sqrt{k_x k_y}$: $q = \underline{k}\,(n_f/n_e)\,h$.

### 5. Analytical Solutions

* A 2D profile model is a vertical section in which the flow is mainly in the plane of the section.
* Dupuit assumptions: (1) the exit point coincides with the tailwater; (2) the hydraulic gradient is constant along a vertical line, good when flow is mainly horizontal; (3) the hydraulic gradient equals the slope of the free surface.
* Assumption 3 uses $\tan\alpha$ where the actual gradient is $\sin\alpha$. They differ by less than 2% up to about 10°.
* Continuity in a vertical strip of saturated thickness $h$ gives $\partial/\partial x(kh\,\partial h/\partial x) = 0$, the Dupuit–Forchheimer equation $\partial^2(h^2)/\partial x^2 = 0$.
* Rectangular section, $h = H_o$ at $x = 0$ and $H_D$ at $x = D$: $h = \sqrt{\dfrac{H_D^2 - H_o^2}{D}x + H_o^2}$ (a parabola) and $q = k\dfrac{H_o^2 - H_D^2}{2D}$.
* With infiltration $e$: $q_x = \dfrac{k(H_o^2 - H_D^2)}{2D} - e\left(\dfrac{D}{2} - x\right)$. Confined layer of thickness $B$: $q = kB(H_o - H_D)/D$.
* These solutions estimate flow from a line source (river, pond) to a line sink (drain, trench).
* Earth dam: the line of seepage is a parabola starting at $a'$, $0.3\Delta$ upstream of $a$. Equation 1: $q = kL\tan\alpha\sin\alpha$. Equation 2: $L = \dfrac{d}{\cos\alpha} - \sqrt{\dfrac{d^2}{\cos^2\alpha} - \dfrac{H^2}{\sin^2\alpha}}$. Compute $\alpha$, $\Delta$, $0.3\Delta$, and $d$; then $L$; then $q$.
* Example: 10 m dam, 3 m crest, 45° and 30° slopes, $H$ = 8 m, $k = 2\times10^{-2}$ m/day. $\Delta$ = 8 m, $d$ = 24.72 m, $L$ = 4.91 m, and $q$ = 0.0283 m³/day/m.

### 6. Well Equations

* Confined-aquifer assumptions include a homogeneous aquifer of constant thickness and infinite extent, an impermeable aquitard, a fully penetrating well, and no head loss at the well.
* Radial flow through area $2\pi rD$, integrated from $(r_w, H_w)$ to $(R, H)$, gives the Thiem equation: $q = 2\pi kD\dfrac{H - H_w}{\ln(R/r_w)}$. Head against $\log r$ is a straight line.
* Drawdown $s = H - h$ and transmissivity $T = kD$: $q = 2\pi T s_w/\ln(R/r_w)$.
* Pumping tests give $k$. Limitations: they work well only for high $k$, give an average horizontal $k$, make steady state hard to judge, and can be affected by flow independent of the well.
* The equations are not very sensitive to $R$: $\ln(R/r_w)$ goes from 2.3 to 9.2 as $R/r_w$ goes from 10 to 10,000. Sichardt: $R = 3000 s_w\sqrt{k}$ ($s_w$ in m, $k$ in m/s).
* Confined multiple wells: the drawdowns add, $s = \dfrac{1}{2\pi kD}\sum q_i\ln(R/r_i)$.
* Unconfined well: $q = \dfrac{\pi k(H^2 - H_w^2)}{\ln(R/r_w)}$. It gives the correct flow rate, but the line of seepage is wrong. With several wells, $H^2 - h^2$ adds, not $s$.
* Storativity $S$ ≈ $10^{-5}$ to $10^{-3}$ (confined); specific yield $S_y$ ≈ 0.1 to 0.3 (unconfined).
* Theis: $s = \dfrac{q}{4\pi T}W(u)$, $u = \dfrac{r^2S}{4Tt}$, with no $R$. Cooper–Jacob ($u < 0.05$): $s = \dfrac{q}{4\pi T}\ln\dfrac{2.25Tt}{r^2S}$, the Thiem equation with $R = 1.5\sqrt{Tt/S}$. Unconfined: $R = 1.5\sqrt{kHt/S_y}$.
* A transient pumping test plotted against $\log t$ gives $T = 2.3q/(4\pi\Delta s)$ and $S = 2.25Tt_0/r^2$ without waiting for steady state.

### 7. Construction Dewatering

* Wellpoints: closely spaced small wells on a header pipe, pumped by suction, which limits the lift to about 5 to 6 m (15 to 20 ft) per stage.
* Deep wells: a submersible pump in each well, no suction limit; fewer, larger wells for deeper drawdowns and more permeable soils.
* French drains and bio-polymer slurry trenches drain by gravity to a sump.
* A slurry cutoff wall (soil-bentonite, $k \approx 10^{-7}$ cm/s) is keyed into the low-k layer. The wells inside pump only the stored water and the leakage.
* Analytical solutions are often used for design; numerical models such as MODFLOW give more accuracy. Trench: $q = k(H_o^2 - H_D^2)/(2D)$.
* Heads are measured up from the low-k layer: $H = d_{base} - d_{wt}$ and $h_t = d_{base} - (d_{exc} + d_m)$. The goal is $h \le h_t$ everywhere inside the excavation by the deadline.
* The Dewater app sums the Theis solution, in the $H^2 - h^2$ form, over the wells and over every change in the pumping rate.
* $Q_{min}$ is the smallest total rate that dewaters the excavation by the deadline: 1,258 gpm for the class example (16 wells, 30 days).
* A well pumped too hard goes dry. The schedule starts at $Q_{min}$, is cut back each week so no well goes dry, and then drops to a holding rate (309 gpm).
* The deadline sets the rate and the fewest wells. $Q_{min}$ is highly sensitive to $k$.
* In anisotropic soil the water table lags the heads at the screens and catches up in about $t_d = 4S_yH/k_v$.
* Cutoff wall leakage: $q = k_w(H^2 - h_t^2)/(2t)$ and $Q = Pq$. With the wall, $Q_{min}$ drops from 1,258 to 550 gpm.

### 8. The Finite Element Method

* The domain is divided into elements joined at nodes, and the unknowns are the heads at the nodes. The solution is approximate; smaller elements give a closer answer.
* Inside each element $h$ varies simply, Darcy's law gives each element's flow into its nodes, and the flows balance at each node: $[T]\{h\} = \{q\}$, with $[T]$ the transmissibility matrix.
* 1D element: $q_1 = kA(h_1 - h_2)/L$, and the element matrix holds the conductance $C = kA/L$.
* Each element's matrix is added into the rows and columns of its nodes. The global matrix has one row per node and is symmetric and banded.
* A known head replaces its node's row. With $C_a = C_c = 2$, $C_b = 1$, $h_1 = 5$, and $h_4 = 1$: $h_2 = 4$, $h_3 = 2$, and $q_1 = 2$.
* Each 2D element belongs to one soil zone, so zone boundaries follow element edges. Element types: linear triangle (3 nodes), quadratic triangle (6), linear quadrilateral (4), and quadratic quadrilaterals (8 and 9). Quadratic elements are more accurate per node; triangles mesh more flexibly.
* Linear triangle: $h = a_1 + a_2x + a_3y$, so the gradient is constant. $\{i\} = [B]\{h\}$, $\{v\} = -[K]\{i\}$, $\{Q\} = -\Delta[B]^T\{v\}$, and $[T] = \Delta[B]^T[K][B]$.
* A boundary node with nothing specified has $q = 0$, a no-flow boundary.
* Sheet pile check problem (exact flow 5.0 m³/day per m): coarse uniform mesh 14.1% high; fine uniform, 1,063 nodes, 4.1% high; coarse refined at the pile tip, 418 nodes, 2.3% high.
* Use small elements where the head changes quickly, change sizes gradually, avoid slivers, and refine and re-solve until the answer stops changing.

### 9. Seepage Analysis in XSLOPE

* Outputs: head, pore pressure, velocity, gradient, total flow, and the flow net. The pore pressures are used in a stability analysis of the same model.
* gmsh meshes each soil zone with the element type and target size chosen in the Build Mesh dialog. Linear triangles are adequate for seepage; a finite element stability analysis needs quadratic elements.
* A confined problem is saturated everywhere with known boundaries and is solved directly. In an unconfined problem the phreatic surface is part of the solution, and XSLOPE iterates. A model with an exit face is unconfined.
* Conductivity: $k_1$ (larger), $k_2$ (smaller, at right angles), and $\alpha$ (angle of $k_1$, counterclockwise from $x$, in degrees).
* Unsaturated conductivity: $k = k_r(\psi)k_s$ with $\psi = h - y$, from the linear front (lf, the default), van Genuchten (vg), or Gardner (gard) model. These are used only for unconfined problems.
* Boundary conditions: specified head, specified flux, exit face, and nothing (no flow).
* Unconfined iteration: solve with $k_s$ everywhere, find $\psi$, use $k_rk_s$ where $\psi < 0$, and solve again until the heads stop changing. Exit face nodes are sorted into wet ($h = y$) and dry (no flow).
* SEEP-1 (sheet pile with a clay blanket): the pile is a crack in the geometry, and $q$ = 40.1 m³/yr per m. The maximum gradient is at singular points, the pile toe and the edge of the blanket.
* SEEP-2 (zoned earth dam): $q$ = 1.95 ft³/day per ft in 47 iterations; almost the whole 60 ft drop is across the core.
* Pore pressure $u = \gamma_w(h - y)$ is positive below the phreatic surface and negative above it.
* A model is an Excel workbook on the input template (main, mat, profile or polygon, seep bc), built in Excel or Studio. Base material sets the $k$ for square flow net cells.

### 10. Transient Seepage

* A transient analysis adds storage properties ($S_s$ and $S_y$), a schedule of boundary values, a run duration and save times, and a steady starting state. The result is a series of saved solutions called frames.
* Governing equation: $\dfrac{\partial}{\partial x}\left(k_x\dfrac{\partial h}{\partial x}\right) + \dfrac{\partial}{\partial y}\left(k_y\dfrac{\partial h}{\partial y}\right) = S\dfrac{\partial h}{\partial t}$. With $S = 0$ it is the steady equation.
* Specific storage $S_s$ [1/length] acts below the phreatic surface; storativity of a layer $b$ thick is $S = S_sb$. Specific yield $S_y$ acts only in the band the water table is crossing.
* In XSLOPE (linear front): $S = S_s$ where $\psi \ge 0$, $S = S_y/|h_0|$ where $h_0 < \psi < 0$, and $S \approx 0$ where $\psi \le h_0$.
* Drainage rate ≈ $k_2/S_y$: shell 2.3 m/day and core 0.17 m/day, against a pool falling 0.36 m/day, so the core lags.
* A time series on the tseep sheet (or Studio's Transient dialog) describes a changing boundary. A boundary follows a series when its value cell holds the series name.
* The starting state is a steady solve with every series at its $t = 0$ value. A time that was not saved needs a new run.
* A reservoir boundary holds submerged nodes at $h(t)$, makes uncovered nodes exit face, and keeps nodes not yet reached as no flow. A head boundary holds every node at its value all the time.
* SEEP-3: at day 47 the core water table is near 10.6 m against a 2 m pool. Transient frames report inflow and outflow and have no flow lines.

---

## 20 True/False Questions

1. **True or False:** Velocity head is neglected in groundwater problems because $v^2/2g$ is negligible at seepage velocities. **True**
2. **True or False:** Water always flows from higher pore pressure to lower pore pressure. **False** *(Water flows from higher to lower total head. In Example 3 the pore pressure is the same at A, B, and C, and water still flows.)*
3. **True or False:** The seepage velocity is always greater than the discharge velocity. **True** *($v_s = v_d/n_e$ and $n_e < 1$.)*
4. **True or False:** For flow perpendicular to soil layers, the equivalent $k$ is the thickness-weighted average of the layer conductivities. **False** *(That is parallel flow. Perpendicular flow uses the harmonic average, $\sum H_i/\sum(H_i/k_i)$.)*
5. **True or False:** The cross term $k_{xy}$ is zero when the principal axes of conductivity line up with $x$ and $y$. **True**
6. **True or False:** The free surface in an earth dam must be specified as a boundary condition. **False** *(It is part of the solution.)*
7. **True or False:** If flow net cells have a uniform length-to-width ratio, every flow channel carries the same flow. **True**
8. **True or False:** For an anisotropic soil, the flow from a flow net on the transformed section uses $\underline{k} = \sqrt{k_x k_y}$. **True**
9. **True or False:** Under the Dupuit assumptions, the free surface through a rectangular section is a straight line. **False** *(It is a parabola: $h^2$ varies linearly with $x$.)*
10. **True or False:** The error from using $\tan\alpha$ in place of $\sin\alpha$ grows as the free surface gets steeper. **True** *(Less than 2% up to about 10°; 15% at 30°.)*
11. **True or False:** The Thiem equation is very sensitive to the radius of influence $R$. **False** *($R$ enters through $\ln(R/r_w)$.)*
12. **True or False:** For several wells in an unconfined aquifer, the drawdowns are added. **False** *(Superposition is applied to $H^2 - h^2$. Adding drawdowns leaves the water table too high.)*
13. **True or False:** A wellpoint system lifts water by suction, which limits the lift to about 5 to 6 m per stage. **True**
14. **True or False:** In the class dewatering example, adding wells beyond 16 greatly reduces the rate needed for the 30-day deadline. **False** *(More wells dewater faster, but the rate barely changes.)*
15. **True or False:** The global transmissibility matrix is symmetric and banded. **True**
16. **True or False:** In a finite element seepage model, a boundary node with nothing specified is a no-flow boundary. **True**
17. **True or False:** In XSLOPE, a model with an exit face is solved as an unconfined problem. **True**
18. **True or False:** XSLOPE's unsaturated conductivity models are used in confined problems. **False** *(They are used only for unconfined problems.)*
19. **True or False:** The starting state of an XSLOPE transient analysis is a steady solution with every time series at its $t = 0$ value. **True**
20. **True or False:** A head boundary is the right type for the upstream face of a dam whose reservoir is drawn down. **False** *(A head boundary holds uncovered nodes at the lower pool level. A reservoir boundary makes them exit face.)*

---

## 30 Multiple Choice Questions

1. For groundwater flow, total head is:

    > A) $h = u/\gamma_w$<br>
    > B) $h = z + v^2/2g$<br>
    > C) $h = z + u/\gamma_w$<br>
    > D) $h = z\,u/\gamma_w$<br>
    > **Answer: C) $h = z + u/\gamma_w$.** The velocity head is neglected.

2. In Example 3, $h_a$ = 9 ft, $h_c$ = 2 ft, B is 3 ft down the 7 ft soil column, and $z_b$ = 4 ft. What is the pore pressure at B?

    > A) 62.4 psf<br>
    > B) 124.8 psf<br>
    > C) 249.6 psf<br>
    > D) 374.4 psf<br>
    > **Answer: B) 124.8 psf.** $h_b = 9 - \tfrac{3}{7}(7) = 6$ ft, $u_b/\gamma_w = 6 - 4 = 2$ ft, $u_b = 2(62.4)$.

3. The hydraulic gradient $i$ in $q = kiA$ is:

    > A) The head loss divided by the length of the flow path<br>
    > B) The pore pressure divided by $\gamma_w$<br>
    > C) The flow rate divided by the area<br>
    > D) The elevation change divided by the head loss<br>
    > **Answer: A) The head loss divided by the length of the flow path.** $i = \Delta h/L$, dimensionless.

4. Which expression gives the travel time over a distance $L$ along a flow path?

    > A) $t = Ln_e/(ki)$<br>
    > B) $t = L/(ki)$<br>
    > C) $t = L/(kin_e)$<br>
    > D) $t = Lk/(in_e)$<br>
    > **Answer: A) $t = Ln_e/(ki)$.** Travel time is $L$ over the seepage velocity, $ki/n_e$.

5. A block has 10 ft of sand, 2 ft of clay, and 8 ft of gravel. For flow perpendicular to the layers, where is most of the head lost?

    > A) In the gravel<br>
    > B) In the sand<br>
    > C) In the clay<br>
    > D) Equally in all three<br>
    > **Answer: C) In the clay.** The flow is the same in every layer, so the head loss concentrates in the least conductive layer.

6. Darcy's law may not hold:

    > A) In clays with very low $k$<br>
    > B) Whenever the soil is layered<br>
    > C) Whenever the soil is anisotropic<br>
    > D) In coarse gravel and rockfill, or near well screens<br>
    > **Answer: D) In coarse gravel and rockfill, or near well screens.** Darcy's law requires laminar flow, Re below about 1 to 10.

7. With principal conductivities $k_r$ and $k_s$ and $r$ at angle $\alpha$ from $x$, $k_{xy}$ is:

    > A) $\tfrac{1}{2}(k_r - k_s)\sin 2\alpha$<br>
    > B) $k_r\cos^2\alpha + k_s\sin^2\alpha$<br>
    > C) $\sqrt{k_r k_s}$<br>
    > D) $(k_r + k_s)\cos\alpha$<br>
    > **Answer: A) $\tfrac{1}{2}(k_r - k_s)\sin 2\alpha$.** From $K_{xy} = RK_{rs}R^T$.

8. Which is NOT an assumption in deriving the steady governing equation?

    > A) The soil is saturated<br>
    > B) Darcy's law is valid<br>
    > C) Mass is conserved<br>
    > D) The flow is one-dimensional<br>
    > **Answer: D) The flow is one-dimensional.** The derivation is three-dimensional.

9. Where water seeps out of the downstream face of an earth dam, the boundary condition is:

    > A) $h$ = reservoir level<br>
    > B) No flow<br>
    > C) $h = z$<br>
    > D) A specified flux<br>
    > **Answer: C) $h = z$.** It is an exit face; the pressure is zero.

10. A flow net has 3 flow channels and 6 equipotential drops, $h$ = 10 ft, and $k$ = 2 ft/day. What is $q$ per foot of wall?

    > A) 2.5 ft³/day<br>
    > B) 5 ft³/day<br>
    > C) 7.5 ft³/day<br>
    > D) 10 ft³/day<br>
    > **Answer: D) 10 ft³/day.** $q = 2(3/6)(10) = 10$ ft³/day.

11. The line of seepage in an unconfined flow net is:

    > A) A flow line and a line of zero pressure<br>
    > B) An equipotential line<br>
    > C) A line of constant elevation<br>
    > D) A line of constant head<br>
    > **Answer: A) A flow line and a line of zero pressure.** On it, total head equals elevation.

12. For $k_x = 4k_y$, the transformed coordinate is:

    > A) $\underline{x} = 4x$<br>
    > B) $\underline{x} = 2x$<br>
    > C) $\underline{x} = x/2$<br>
    > D) $\underline{x} = x/4$<br>
    > **Answer: C) $\underline{x} = x/2$.** $\underline{x} = x\sqrt{k_y/k_x} = x\sqrt{1/4}$.

13. Which is NOT a Dupuit assumption?

    > A) The exit point coincides with the tailwater<br>
    > B) The hydraulic gradient is constant along a vertical line<br>
    > C) The hydraulic gradient equals the slope of the free surface<br>
    > D) The flow is confined between two impermeable layers<br>
    > **Answer: D) The flow is confined between two impermeable layers.** The three Dupuit assumptions are A, B, and C.

14. For unconfined flow through a rectangular section, $q$ per unit width is:

    > A) $k(H_o - H_D)/D$<br>
    > B) $kD(H_o - H_D)$<br>
    > C) $k(H_o^2 - H_D^2)/D$<br>
    > D) $k(H_o^2 - H_D^2)/(2D)$<br>
    > **Answer: D) $k(H_o^2 - H_D^2)/(2D)$.** From the Dupuit–Forchheimer equation.

15. In the earth dam method, after $\alpha$, $\Delta$, $0.3\Delta$, and $d$, the next step is to:

    > A) Compute $q$ from equation 1<br>
    > B) Compute $L$ from equation 2<br>
    > C) Draw a flow net<br>
    > D) Compute the infiltration rate<br>
    > **Answer: B) Compute $L$ from equation 2.** Equation 1, $q = kL\tan\alpha\sin\alpha$, needs $L$.

16. In the Thiem equation, $D$ is:

    > A) The aquifer thickness<br>
    > B) The distance to an observation well<br>
    > C) The drawdown at the well<br>
    > D) The well diameter<br>
    > **Answer: A) The aquifer thickness.** Flow crosses a cylinder of area $2\pi rD$.

17. For unconfined wells, superposition is applied to $H^2 - h^2$ because:

    > A) The aquifer is anisotropic<br>
    > B) Unconfined aquifers are thin<br>
    > C) $R$ differs for each well<br>
    > D) Flow is linearly proportional to $h^2$, not $h$<br>
    > **Answer: D) Flow is linearly proportional to $h^2$, not $h$.** The governing equation is linear in $h^2$.

18. Which is true of the Theis equation?

    > A) It requires a radius of influence<br>
    > B) It applies only at steady state<br>
    > C) Drawdown depends on $r$ and $t$ only through $u = r^2S/(4Tt)$<br>
    > D) The drawdown stops growing soon after pumping starts<br>
    > **Answer: C) Drawdown depends on $r$ and $t$ only through $u = r^2S/(4Tt)$.** There is no $R$ in the Theis equation.

19. In a confined pumping test, the slope $\Delta s$ per log cycle of time gives:

    > A) $T = 2.3q/(4\pi\Delta s)$<br>
    > B) $S = 2.25Tt_0/r^2$<br>
    > C) $R = 1.5\sqrt{Tt/S}$<br>
    > D) $k = q/(2\pi Ds_w)$<br>
    > **Answer: A) $T = 2.3q/(4\pi\Delta s)$.** The intercept $t_0$ then gives $S$.

20. Which method has a submersible pump in each well and no suction limit?

    > A) Wellpoints<br>
    > B) Sumps and ditches<br>
    > C) French drains<br>
    > D) Deep wells<br>
    > **Answer: D) Deep wells.**

21. In the Dewater app, $Q_{min}$ is:

    > A) The holding rate<br>
    > B) The smallest total pumping rate that dewaters the excavation within the deadline<br>
    > C) The rate at which one well goes dry<br>
    > D) The leakage through a cutoff wall<br>
    > **Answer: B) The smallest total pumping rate that dewaters the excavation within the deadline.** 1,258 gpm for the class example.

22. In the class dewatering example, $k$ turns out a little lower than the estimate. What happens?

    > A) The pumps are oversized<br>
    > B) Nothing, because $Q_{min}$ is insensitive to $k$<br>
    > C) No rate meets the deadline<br>
    > D) The holding rate rises<br>
    > **Answer: C) No rate meets the deadline.** A lower $k$ than the estimate is the dangerous mistake.

23. In the 1D finite element example, $C_a = C_c = 2$, $C_b = 1$, $h_1 = 5$, and $h_4 = 1$. What are $h_2$ and $h_3$?

    > A) 4 and 2<br>
    > B) 3.67 and 2.33<br>
    > C) 4.5 and 1.5<br>
    > D) 3 and 3<br>
    > **Answer: A) 4 and 2.** $3h_2 - h_3 = 10$ and $-h_2 + 3h_3 = 2$.

24. In a linear triangle, the hydraulic gradient is:

    > A) Constant over the element<br>
    > B) Linear over the element<br>
    > C) Quadratic over the element<br>
    > D) Zero at the nodes<br>
    > **Answer: A) Constant over the element.** The head is a plane, so $i_x = a_2$ and $i_y = a_3$.

25. For the sheet pile check problem, which mesh gave the most accurate total flow?

    > A) Coarse uniform<br>
    > B) Fine uniform, 1,063 nodes<br>
    > C) Coarse, refined at the pile tip, 418 nodes<br>
    > D) All were equally accurate<br>
    > **Answer: C) Coarse, refined at the pile tip, 418 nodes.** 2.3% high, against 4.1% for the fine uniform mesh.

26. How does XSLOPE decide whether a problem is confined or unconfined?

    > A) The user selects it<br>
    > B) A model with an exit face is unconfined<br>
    > C) From the element type<br>
    > D) From the number of materials<br>
    > **Answer: B) A model with an exit face is unconfined.**

27. In XSLOPE's conductivity inputs, $\alpha$ is:

    > A) The angle of $k_2$ from vertical<br>
    > B) The ratio $k_1/k_2$<br>
    > C) The ground slope angle<br>
    > D) The angle of $k_1$, counterclockwise from $x$, in degrees<br>
    > **Answer: D) The angle of $k_1$, counterclockwise from $x$, in degrees.**

28. Base material in XSLOPE's solution plot sets:

    > A) Which material is meshed first<br>
    > B) The $k$ used to space flow lines for square cells<br>
    > C) The material used for stability<br>
    > D) The unsaturated model<br>
    > **Answer: B) The $k$ used to space flow lines for square cells.** $N_f = qN_d/(k\Delta h)$.

29. In XSLOPE with the linear front model, the storage coefficient in the draining band $h_0 < \psi < 0$ is:

    > A) $S_s$<br>
    > B) $S_y/|h_0|$<br>
    > C) $S_sb$<br>
    > D) Approximately zero<br>
    > **Answer: B) $S_y/|h_0|$.** $S_y$ is spread over the band's thickness $|h_0|$.

30. A transient frame in XSLOPE Studio reports:

    > A) A flow net and one total flow<br>
    > B) Inflow and outflow, with velocity vectors in place of flow lines<br>
    > C) Only the phreatic surface<br>
    > D) A factor of safety<br>
    > **Answer: B) Inflow and outflow, with velocity vectors in place of flow lines.** Storage releases water, so inflow and outflow differ, and transient frames have no flow lines.

---

## 20 Short Answer Questions

1. **What is pressure head?**
   $h_p = u/\gamma_w$, the height the water rises in a piezometer above the point.

2. **Two points have the same pore pressure, and A is higher than B. Which way does water flow?**
   From A to B. The pressure heads are equal and the elevation head is larger at A, so the total head is higher at A.

3. **Define discharge velocity and seepage velocity.**
   Discharge velocity is the flow rate per unit of gross area, $v_d = q/A = ki$. Seepage velocity is the average speed of the water in the pores, $v_s = ki/n_e$.

4. **Why is the effective porosity smaller than the porosity?**
   Not all voids conduct flow. Voids filled with fines and dead-end pores carry little flow, so $A_f$ is smaller than the pore area. $n_e = A_f/A = \lambda n$.

5. **Give the equivalent $k$ for flow parallel to and perpendicular to layers.**
   Parallel: $k_{eq} = \sum k_iH_i/\sum H_i$. Perpendicular: $k_{eq} = \sum H_i/\sum(H_i/k_i)$.

6. **What is the conductivity tensor?**
   The matrix that relates the velocity vector to the gradient vector in Darcy's law. It is diagonal when the axes line up with the principal axes of conductivity.

7. **Write the 2D Laplace equation and state when it applies.**
   $\partial^2 h/\partial x^2 + \partial^2 h/\partial y^2 = 0$, for steady saturated flow with no sources or sinks and $k_x = k_y$.

8. **List four types of boundary conditions, with an example of each.**
   Known head (reservoir level); no flow (impervious foundation, sheet pile); exit face, $h = z$ (downstream slope); specified flux (recharge).

9. **In a flow net, what are $n_f$ and $n_e$?**
   The number of flow channels and the number of equipotential drops, with partial ones counted as fractions.

10. **How is pore pressure found from a flow net?**
    Count the drops from the upstream boundary to get the total head, subtract the elevation head to get the pressure head, and multiply by $\gamma_w$.

11. **State the three Dupuit assumptions.**
    The exit point coincides with the tailwater; the gradient is constant along a vertical line; the gradient equals the slope of the free surface.

12. **What is the Dupuit–Forchheimer equation?**
    $\partial^2(h^2)/\partial x^2 = 0$, from continuity in a vertical strip, $\partial/\partial x(kh\,\partial h/\partial x) = 0$.

13. **Define storativity and specific yield.**
    Storativity is the water a confined aquifer releases per unit area per unit drop in head as the soil compresses and the water expands, about $10^{-5}$ to $10^{-3}$. Specific yield is the water drained by gravity per unit area per unit drop of the water table, about 0.1 to 0.3.

14. **What is the Cooper–Jacob approximation?**
    For $u < 0.05$, $W(u) \approx -0.5772 - \ln u$, so $s = \dfrac{q}{4\pi T}\ln\dfrac{2.25Tt}{r^2S}$: the Thiem equation with $R = 1.5\sqrt{Tt/S}$.

15. **Why does a well go dry if it is pumped too hard?**
    The more it pumps, the deeper its cone. When the water at the well reaches the bottom of the aquifer, there is no saturated thickness left to carry more flow.

16. **What does a slurry cutoff wall do in a dewatering system?**
    It encloses the site, keyed into the low-k layer, so the wells pump only the stored water and the leakage. The water table outside changes little.

17. **What are the three steps for a linear triangle's transmissibility matrix?**
    $\{i\} = [B]\{h\}$; $\{v\} = -[K]\{i\}$; $\{Q\} = -\Delta[B]^T\{v\}$. Together, $[T] = \Delta[B]^T[K][B]$.

18. **How is a sheet pile represented in an XSLOPE seepage model?**
    As a crack in the geometry: the profile line dips to the tip and back up, and the mesh has nodes on both faces. The faces have no specified condition, so they are no-flow.

19. **Why is the gradient at the pile toe not used directly for design?**
    The pile toe and the edge of the blanket are singular points, so design values are read a short distance away.

20. **How does a boundary condition follow a time series in XSLOPE?**
    The series, a named table of times and values, is on the tseep sheet or in Studio's Transient dialog. The boundary's value cell holds the series name in place of a number.

---

## 15 Open Response (Essay) Questions

1. **Derive Bernoulli's equation from the work done in moving a unit mass of water from A to B, and explain why total head for groundwater is $h = z + u/\gamma_w$.**
   Lifting the water a height $z$: $W_1 = gz$. Changing its speed: $W_2 = (v_b^2 - v_a^2)/2$. Compressing it: $W_3 = \Delta(PV)$; with $\Delta V \approx 0$ and $V = m/\rho_w$, $W_3 = (u_b - u_a)/\rho_w$. The sum is the total potential, $\varphi$. Dividing by $g$ gives work per unit weight, a length: $\Delta h_{a\to b} = (z_b + v_b^2/2g + u_b/\gamma_w) - (z_a + v_a^2/2g + u_a/\gamma_w)$. The total head at a point is $h = z + v^2/2g + u/\gamma_w$. The velocity head is negligible for groundwater, 0.016 ft even at 1 ft/s, so $h = z + u/\gamma_w$.

2. **Derive the equivalent $k$ for flow perpendicular to layers, and explain where the head loss concentrates.**
   The flow and velocity are the same in every layer: $k_{eq}(\Delta h/H) = k_1i_1 = k_2i_2 = k_3i_3$. The head losses add: $\Delta h = H_1i_1 + H_2i_2 + H_3i_3$. Substituting $i_n = k_{eq}\Delta h/(Hk_n)$ and dividing by $\Delta h$ gives $k_{eq} = H/(H_1/k_1 + H_2/k_2 + H_3/k_3)$, a harmonic average. With the same flow in every layer, the head loss is largest in the least conductive layer. In the sand, clay, and gravel example, $k_{eq}$ = 0.00283 ft/day, and nearly all 5 ft of head is lost in the 2 ft of clay.

3. **Explain discharge velocity, seepage velocity, and effective porosity, and why they matter for travel time.**
   The discharge velocity, $v_d = q/A = ki$, uses the gross area. Water moves only through the pores, so its average speed is $v_s = q/A_f$. Dead-end pores and voids filled with fines carry little flow, so the area of flow gives the effective porosity, $n_e = A_f/A$, and $v_s = ki/n_e$. For clay, $n_e$ can be as low as 0.01. Travel time is $t = Ln_e/(ki)$. Using $v_d$ would overestimate the travel time by $1/n_e$.

4. **Derive the governing equation for steady saturated flow from conservation of mass.**
   With a saturated soil, Darcy's law, and conservation of mass, steady flow with no sources or sinks has inflow − outflow = 0. On a box dx by dy by dz, the mass flow out of the $x$ face is $(\rho v_x)_{in} + \partial(\rho v_x)/\partial x\,dx$, so the $x$ contribution is $-\partial(\rho v_x)/\partial x\,dx\,dy\,dz$. Summing three directions and dividing by the volume gives $\sum \partial(\rho v_i)/\partial x_i = 0$. With constant density, $\partial v_x/\partial x + \partial v_y/\partial y + \partial v_z/\partial z = 0$. Substituting Darcy's law on the principal axes gives $k_x\partial^2h/\partial x^2 + k_y\partial^2h/\partial y^2 + k_z\partial^2h/\partial z^2 = 0$, and with equal $k$, the Laplace equation.

5. **Explain the rules for constructing a flow net and how the flow rate equation follows from them.**
   Flow is in the direction of maximum drop in head, so flow lines and equipotential lines cross at 90°. In one flow channel, Darcy's law gives $k(\Delta h_1/l_1)b_1 = k(\Delta h_2/l_2)b_2$, so equal drops mean equal $b/l$. Across one drop, equal flows also mean equal $b/l$. With uniform $b/l$, each channel carries the same flow and each drop is $h/n_e$. One channel carries $\Delta q = k(h/n_e)(b/l)$, and $n_f$ channels carry $q = k(n_f/n_e)(b/l)h$, or $k(n_f/n_e)h$ for square cells.

6. **Explain how to draw a flow net and compute the flow for an anisotropic soil.**
   With $k_x \ne k_y$, the equation is $k_x\partial^2h/\partial x^2 + k_y\partial^2h/\partial y^2 = 0$, and the lines do not cross at right angles. With $\underline{x} = x\sqrt{k_y/k_x}$, the chain rule gives $\partial^2h/\partial x^2 = (k_y/k_x)\partial^2h/\partial\underline{x}^2$, and the equation becomes the Laplace equation in $\underline{x}$ and $y$. Draw the section at the transformed scale (for $k_x = 4k_y$, horizontal distances halve), draw square cells, and transform back. Equating flows on the two scales gives $\underline{k} = \sqrt{k_xk_y}$, so $q = \underline{k}(n_f/n_e)h$.

7. **Derive the flow rate for unconfined flow through a rectangular section using the Dupuit assumptions.**
   Continuity in a vertical strip of saturated thickness $h$ gives $\partial/\partial x(kh\,\partial h/\partial x) = 0$, and since $h\,\partial h/\partial x = \tfrac12\partial(h^2)/\partial x$, $\partial^2(h^2)/\partial x^2 = 0$. Integrating twice, $h^2 = C_1x + C_2$. With $h = H_o$ at $x = 0$ and $h = H_D$ at $x = D$, $C_2 = H_o^2$ and $C_1 = (H_D^2 - H_o^2)/D$. Then $\partial h/\partial x = (H_D^2 - H_o^2)/(2hD)$, and $q = -k(\partial h/\partial x)h = k(H_o^2 - H_D^2)/(2D)$. The free surface is a parabola.

8. **Describe the method for seepage through an earth dam and apply it to the lecture example.**
   The line of seepage is a parabola from $a'$, $0.3\Delta$ upstream of $a$. With the Dupuit assumptions, the flow through the vertical section under the exit point is $q = kL\tan\alpha\sin\alpha$ (equation 1). Setting it equal to the flow through any section, $kz\,dz/dx$, and integrating gives $L$ (equation 2). For the example: $\alpha = 30°$, $\Delta = 8$ m, $0.3\Delta = 2.4$ m, and $d = 2.4 + 2 + 3 + 17.32 = 24.72$ m. Then $L$ = 4.91 m and $q = (0.02)(4.91)\tan 30°\sin 30° = 0.0283$ m³/day/m.

9. **Derive the Thiem equation and describe its use and limits in pumping tests.**
   Water flows radially through area $2\pi rD$; with flow toward the well positive, $q = k(dh/dr)2\pi rD$. Separating variables, $q\,dr/r = 2\pi kD\,dh$, and $q\ln r = 2\pi kDh + C$. Applying $h = H_w$ at $r_w$ and $h = H$ at $R$ and eliminating $C$: $q = 2\pi kD(H - H_w)/\ln(R/r_w)$. A pumping test solves it for $k$, or two observation wells replace $R$. It works well only in high-k soils, gives an average horizontal $k$ over a large region, and steady state is hard to judge.

10. **Explain superposition for wells in confined and unconfined aquifers.**
    Darcy's law is linear, so in a confined aquifer the drawdowns from several wells add: $s = \dfrac{1}{2\pi kD}\sum q_i\ln(R/r_i)$. In an unconfined aquifer the flow area is $2\pi rh$, so flow is linear in $h^2$. Superposition is applied to $H^2 - h^2$: $h^2 = H^2 - \dfrac{1}{\pi k}\sum q_i\ln(R/r_i)$. Adding drawdowns instead leaves the water table too high, most of all between the wells. The unconfined Theis form is also linear in $H^2 - h^2$, so several wells still add in time.

11. **Explain how the Theis equation and the Cooper–Jacob approximation relate to the Thiem equation and $R$.**
    Theis gives the drawdown around a well pumping at a constant rate in an infinite confined aquifer: $s = \dfrac{q}{4\pi T}W(u)$, $u = r^2S/(4Tt)$. It has no $R$. For $u < 0.05$, $W(u) \approx -0.5772 - \ln u$, giving $s = \dfrac{q}{4\pi T}\ln\dfrac{2.25Tt}{r^2S}$, which is the Thiem equation with $R = 1.5\sqrt{Tt/S}$. So $R$ grows with the square root of time. In an unconfined aquifer $R = 1.5\sqrt{kHt/S_y}$; for $k = 5\times10^{-4}$ cm/s, $H$ = 50 m, and $S_y$ = 0.2, $R$ is 16 m after 1 day and 298 m after 1 year.

12. **Describe how the Dewater app designs a well system for a deadline.**
    The app sums the Theis solution in the $H^2 - h^2$ form over the wells and every change in pumping rate. $Q_{min}$ is the smallest total rate that brings $h$ to $h_t$ or below everywhere in the excavation by the deadline: 1,258 gpm for 16 wells and 30 days. A well goes dry when the water at the well reaches the aquifer bottom, so the schedule cuts the rate back weekly, then drops to a 309 gpm holding rate. Pumps are sized for $Q_{min}$. $Q_{min}$ is highly sensitive to $k$. In anisotropic soil the water table lags, catching up in about $t_d = 4S_yH/k_v$, so the app adds a margin.

13. **Explain how the finite element method solves the three-element 1D example.**
    Each element's flows are its conductance $C = kA/L$ times the head differences. Each element's 2 × 2 matrix is added into its nodes' rows and columns, giving a symmetric, banded global matrix with $C_a + C_b$ and $C_b + C_c$ where elements meet. The inside nodes have $q_2 = q_3 = 0$. The known heads $h_1 = 5$ and $h_4 = 1$ replace their rows and move to the right side. With $C_a = C_c = 2$ and $C_b = 1$: $3h_2 - h_3 = 10$ and $-h_2 + 3h_3 = 2$, so $h_2 = 4$ and $h_3 = 2$, and $q_1 = 2$. The largest drop is across b, the lowest conductance.

14. **Explain how XSLOPE solves an unconfined seepage problem.**
    A model with an exit face is unconfined. XSLOPE solves with $k_s$ everywhere, computes $\psi = h - y$, uses $k = k_r(\psi)k_s$ where $\psi < 0$, and solves again until the heads stop changing. The phreatic surface is the line $\psi = 0$. The exit point is not known in advance, so the whole downstream slope is an exit face, and XSLOPE sorts its nodes into wet ($h = y$) and dry (no flow) until the set stops changing. For SEEP-2, 47 iterations gave 1.95 ft³/day per ft. The three unsaturated models gave the same phreatic surface within 0.5 ft.

15. **Explain what a transient analysis adds, using the SEEP-3 drawdown.**
    The equation adds $S\,\partial h/\partial t$, with $S = S_s$ below the phreatic surface and $S_y/|h_0|$ in the draining band. The pool series (0, 18), (2, 18), (47, 2) is on the tseep sheet, and the upstream face is a reservoir boundary bound to it. The run starts from a steady solve at full pool, 0.165 m³/day per m. The drainage rate $k_2/S_y$ is 2.3 m/day for the shell and 0.17 m/day for the core, against 0.36 m/day for the pool, so at day 47 the core water table is near 10.6 m against a 2 m pool. After day 2 nothing enters the dam, and the outflow peaks at about 1.7 m³/day per m, all from storage.

---

## Glossary of Key Terms

| Term | Definition |
|:-----|:-----------|
| **Conductance ($C$)** | $C = kA/L$ for a 1D finite element. |
| **Conductivity Tensor** | The matrix $[K]$ relating velocity to gradient in Darcy's law; diagonal on the principal axes. |
| **Cooper–Jacob Approximation** | $W(u) \approx -0.5772 - \ln u$ for $u < 0.05$. |
| **Darcy's Law** | $q = kiA$, valid for laminar flow. |
| **Discharge Velocity ($v_d$)** | $v_d = q/A = ki$; also Darcian velocity or specific discharge. |
| **Drawdown ($s$)** | $s = H - h$. |
| **Dupuit Assumptions** | Exit point at the tailwater; gradient constant along a vertical line; gradient equal to the free surface slope. |
| **Effective Porosity ($n_e$)** | $n_e = A_f/A = \lambda n$, the fraction of the cross-section that carries flow. |
| **Equipotential Line** | A line of constant total head. |
| **Exit Face** | A boundary where water may leave the ground, with $h = y$ where it is wet. |
| **Flow Channel** | The space between two adjacent flow lines. |
| **Frame** | A saved solution of a transient analysis at one time. |
| **Hydraulic Gradient ($i$)** | $i = \Delta h/L$, or $-dh/ds$. |
| **Laplace Equation** | $\partial^2h/\partial x^2 + \partial^2h/\partial y^2 = 0$. |
| **Phreatic Surface** | The top of the saturated zone, where $\psi = 0$; also the line of seepage or free surface. |
| **Pressure Head ($h_p$)** | $h_p = u/\gamma_w$. |
| **$Q_{min}$** | The smallest total pumping rate that dewaters the excavation within the deadline. |
| **Radius of Influence ($R$)** | The distance at which a well's drawdown dies out. |
| **Relative Conductivity ($k_r$)** | The factor, 0 to 1, in $k = k_r(\psi)k_s$ for unsaturated soil. |
| **Reservoir Boundary** | XSLOPE's boundary type for a pool that rises and falls. |
| **Seepage Velocity ($v_s$)** | $v_s = ki/n_e$, the average speed of the water in the pores. |
| **Specific Storage ($S_s$)** | Water released per unit volume of saturated soil per unit drop in head [1/L]. |
| **Specific Yield ($S_y$)** | Water drained as the water table falls, per unit drop. |
| **Storativity ($S$)** | Water released by a confined aquifer per unit area per unit drop in head; $S = S_sb$. |
| **Theis Equation** | $s = \dfrac{q}{4\pi T}W(u)$, $u = r^2S/(4Tt)$. |
| **Thiem Equation** | $q = 2\pi kD(H - H_w)/\ln(R/r_w)$. |
| **Total Head ($h$)** | $h = z + u/\gamma_w$ for groundwater. |
| **Transmissibility Matrix ($[T]$)** | The matrix in $[T]\{h\} = \{q\}$. |
| **Transmissivity ($T$)** | $T = kD$. |
| **Wellpoint** | A small, closely spaced well on a header pipe, pumped by suction. |
