# Seepage Analysis: Study Guide

The equation sheet is provided on the exam, so this guide does not ask you to memorize equations. It is about what the quantities mean, why the methods work, when their assumptions fail, what controls the answer, and how to read a result.

## Outline of Main Concepts

### 1. Hydraulic Head

* **Head is energy per unit weight of water**, written as a length.
    * **Elevation head:** height above a datum. Any datum works, but use one per problem; only differences in head matter.
    * **Pressure head:** pore pressure divided by the unit weight of water: how high water rises in a piezometer above the point.
    * **Velocity head:** negligible for groundwater, so it is dropped.
    * **Total head** = elevation head + pressure head: the elevation of the water level in a piezometer at the point.
* **Pore pressure.** Below a still water table it is hydrostatic, growing with depth. A piezometer fills until its water column balances the pore pressure at its tip.
* **Water flows from high total head to low total head**, not from high pressure or from high elevation.
    * Still water in a tank of soil: a deeper point has more pressure but less elevation, so the heads are equal and nothing flows.
    * Equal pressure at the top and bottom of a column: the top has the higher head, so water flows down.
* **Head along a flow path.** In uniform soil with a constant cross-section, total head drops linearly. For the pore pressure at a point: total head by proportion, minus elevation, times the unit weight of water.
* **Common mistakes:** confusing pressure head with total head, mixing datums, and assuming water flows from high pressure to low.

### 2. Darcy's Law

* **Darcy's law.** Flow is proportional to the head difference and the area, and inversely proportional to the length (Darcy, 1856, sand filters in Dijon).
* **Hydraulic conductivity, $k$:** how easily water passes through a soil, in units of velocity.
    * It spans about twelve orders of magnitude, from clean gravel to unweathered clay.
    * A site measurement beats a table value; within an order of magnitude is often the best estimate.
* **Hydraulic gradient:** head lost per unit length of path. It has no units, and it is a gradient in total head, not pressure. Where the flow area narrows, the gradient steepens.
* **Two velocities.**
    * **Discharge velocity:** flow divided by the gross area. Use it for volumes of flow.
    * **Seepage velocity:** discharge velocity divided by the effective porosity, the actual speed in the pores. Use it for travel time.
    * **Effective porosity:** the fraction of the section that carries flow. Close to the total porosity in sand and gravel; far smaller in clay.
    * Using the discharge velocity for travel time makes a contaminant arrive later than it really does: the unsafe direction.
* **When Darcy's law holds:** laminar flow, a pore Reynolds number below about 1 to 10. That covers nearly all soils; it can fail in clean coarse gravel, rockfill, and right at a pumping well.
* **Layered soils.**
    * **Along the layers:** same gradient, flows add. The equivalent $k$ is a weighted average, and the most permeable layer carries most of the water.
    * **Across the layers:** same flow, head losses add. The equivalent $k$ is controlled by the least permeable layer, which takes most of the head loss.
    * $k$ along the layers is always at least $k$ across them, one reason layered soil conducts better horizontally.

### 3. Governing Equations

* **Anisotropy.** $k$ depends on direction. The directions of largest and smallest $k$ (the principal axes) are at right angles. In most deposits, horizontal $k$ exceeds vertical $k$ because of layering. When the bedding is tilted, a gradient in $x$ alone also drives flow in $y$.
* **The governing equation.**
    * Comes from a mass balance on a small piece of soil plus Darcy's law. Assumes saturated soil, Darcy's law valid, constant water density.
    * Steady flow with no sources or sinks: what flows in flows out. In uniform isotropic soil it is the Laplace equation.
    * Its solution is the head everywhere; velocities, pore pressures, and flow rates follow from it.
* **Three ways to solve it:** flow nets (graphical), analytical solutions (simple geometry), and numerical methods (finite differences, finite elements).
* **Boundary conditions.** Every part of the boundary needs one, or there is no unique answer.
    * **Specified head:** ground under a reservoir, ditch, or pumped excavation; the head is the water level.
    * **No flow:** impervious base, sheet pile, line of symmetry, the far ends of a model.
    * **Exit face (seepage face):** where water may leave a slope. Pressure is zero where it leaves; where it leaves is part of the answer.
    * **Specified flux:** a known rate across the boundary, such as recharge.
    * **The phreatic surface is not a boundary condition.** It is part of the answer: the line of zero pressure.
* **Reading a solution.** Crowded head contours mean head is lost quickly. In uniform soil that means high gradient and fast flow; across a low-$k$ zone it means the zone takes the head loss, not that much water flows there.

### 4. Flow Nets

* **What a flow net is:** a graphical solution for 2D, steady, saturated flow in isotropic soil, made of flow lines and equipotential lines (lines of constant total head).
    * Ground under water is an equipotential line; an impervious base and a sheet pile are flow lines.
* **Rules for drawing.**
    * Flow lines and equipotential lines cross at right angles.
    * Every cell is the same shape (squares are easiest), so every channel carries the same flow and every drop is the same head loss.
    * Count partial channels and drops as fractions; check corner cells by subdividing them.
* **Reading the net.**
    * **Head and pressure:** count drops from upstream for the total head, subtract the elevation for the pressure head, multiply by the unit weight of water.
    * **Gradient:** small cells mean high gradient and velocity, such as at a sheet pile tip.
    * **Flow rate:** depends only on $k$, the total head lost, and the ratio of flow channels to drops. It is per unit length of the structure.
* **Unconfined flow (earth dams).** The line of seepage (phreatic surface) is not known in advance.
    * It is both a flow line and a line of zero pressure, so equipotentials meet it at equal steps of elevation.
    * It leaves the upstream face at right angles.
* **Anisotropic soil.** A true-scale net is not square. Draw it on a transformed section (horizontal distances rescaled), and use the geometric mean of $k_x$ and $k_y$.
* **Common mistakes:** cells that are not square, lines not at right angles, forgetting zero pressure on the line of seepage, and using $k_x$ or $k_y$ alone.

### 5. Analytical Solutions

* **Why use them.** For simple geometry, a formula gives a quick estimate and shows what controls the answer. A 2D section works when flow is mainly in that vertical plane.
* **Dupuit assumptions.**
    * The exit point is at the tailwater (really it is higher, on the downstream face).
    * Flow is horizontal: the gradient is the same all the way down a vertical line.
    * The gradient equals the slope of the free surface (the tangent, where the sine is correct). Good for gentle surfaces, within 2% up to about 10°; poor where the surface is steep, near a drain or well, though the flow rate often stays right.
* **Rectangular section.** The free surface is a parabola that steepens downstream, because the same flow passes through a thinner saturated thickness. Infiltration makes the flow change along the section.
* **Confined layer.** Constant flow area, so the head drops linearly and the flow is proportional to the head difference.
* **In practice:** screening estimates of flow from a line source (river) to a line sink (drain). A real drain also collects water around its ends, so check a design with a numerical model.
* **Earth dam (Casagrande).** The line of seepage is a parabola, corrected to leave the upstream face at right angles. Find where it exits on the downstream face, then compute the flow below that point with the gradient equal to the slope of the face.

### 6. Wells

* **Wells are radial flow** in plan, not a cross-section. The cone of depression is steep near the well because the same flow passes through ever smaller cylinders.
* **Confined aquifer, steady (Thiem).**
    * The aquifer stays full, so the flow area does not change. Head plots as a straight line against the log of distance.
    * **Assumptions:** homogeneous, constant thickness, infinite extent, fully penetrating well, horizontal starting level, steady flow.
    * **Radius of influence, $R$:** enters only through a logarithm, so a rough estimate is enough.
    * **Transmissivity:** $k$ times the aquifer thickness.
    * **Superposition:** drawdowns from several wells add, which is how a ring of wells lowers water across a site.
* **Unconfined aquifer, steady.**
    * The water table itself drops, so the flow area shrinks near the well.
    * The equation gives the right flow rate but the wrong water table shape near the well.
    * **Superposition:** $H^2 - h^2$ adds, not drawdown. Adding drawdowns leaves the water table too high between wells.
* **Steady pumping tests.** Back-calculate $k$ from the rate and drawdown. Gives an average horizontal $k$ over a large area; works best in high-$k$ soils; steady state is hard to judge. Observation wells remove the need to know $R$.
* **Transient flow.**
    * At first, water comes from storage around the well and the cone grows, until it reaches a source such as a river.
    * **Storativity (confined):** water released by compression of the soil and expansion of the water. Tiny.
    * **Specific yield (unconfined):** water drained from the pores as the water table drops, about 0.1 to 0.3. Far larger than storativity, so the cone spreads much more slowly.
    * **Theis:** an infinite confined aquifer has no $R$; the cone keeps growing. Drawdown depends on $r^2/t$.
    * **Cooper–Jacob:** late in time, Theis becomes Thiem with an $R$ that grows with time. A steady $R$ really stands for a pumping time.
    * **Unconfined:** same solution in the $H^2 - h^2$ form with specific yield, while drawdown is small compared with the thickness.
    * **Rate changes:** a change in rate acts as a new well pumping the change; stopping a pump adds a well pumping $-q$.
* **Transient pumping tests.** Plot drawdown against log time and fit the later points: slope gives transmissivity, intercept gives storage. In unconfined tests the early points come from elastic release (delayed yield), so fit the late ones.

### 7. Construction Dewatering

* **Goal:** lower the water so an excavation can be built in the dry.
* **Methods.** The choice depends on permeability, drawdown needed, and how long the system runs.
    * **Wellpoints:** closely spaced suction wells, limited to about 5 to 6 m of lift per stage. Sands and silty sands.
    * **Deep wells:** submersible pumps, no suction limit. Deeper drawdowns, more permeable soils.
    * **Sumps and ditches:** pumping from the excavation floor. Shallow drawdowns in gravel, rock, or stiff clay; in sand they can wash out fines.
    * **French drains and trenches:** gravity drains along a line.
    * **Slurry cutoff wall:** a low-$k$ wall keyed into the low-$k$ layer below. It cuts off inflow, so wells pump only stored water and leakage. Worth it when wells alone would pump too much, when outside drawdown would hurt neighbors, or when discharge is hard to dispose of.
* **Designing to a deadline.** Water must be at or below the target everywhere inside the excavation by the deadline; the middle comes down last.
    * **$Q_{min}$:** the smallest total pumping rate that meets the deadline.
    * **A well can go dry:** pump too hard and the saturated thickness at the well runs out. A bigger pump does not help.
    * **Schedule:** the rate is cut back as cones spread, then drops to a holding rate. Size pumps for $Q_{min}$.
    * **Deadline:** shorter needs a higher rate but less total water. Each set of wells has a fastest possible time.
    * **Wells and layout:** more wells shorten the fastest time and add margin but barely change the total rate. Moving wells saves only a few percent.
* **Uncertainty in $k$.** $Q_{min}$ is very sensitive to $k$. Too high a $k$ means more pumping; too low means wells go dry and no rate works. Design over a range: pumps for the high end, wells for the low end.
* **Anisotropic soil.** Heads at the well screens fall fast, but the water table lags while stored water drains down across the layers. Add a margin.
* **Analytical or numerical.** Leakage through a cutoff wall is like flow to a trench, but a wall is a boundary the well equations cannot include, so it needs a numerical model. A numerical model is also worth it when layering or far boundaries matter. Check it against a case you can solve by hand.

### 8. The Finite Element Method

* **The idea.** Divide the section into elements joined at nodes; the unknowns are the nodal heads. Elements follow any boundary and soil zone, and can be small where the head changes fast. The answer is approximate.
* **How it works.**
    * Inside an element, head varies simply between its nodes; Darcy's law turns that into flows at the nodes.
    * At each node, the flows must balance: one equation per node.
    * **1D element:** flow is the conductance ($k$ times area over length) times the head difference. In series, the largest head drop is across the smallest conductance, as with soil layers.
    * **Assembly:** element matrices add into one global matrix, which is symmetric and banded, so large meshes are practical.
* **Boundary conditions in the matrix.** A specified head fixes its node; a specified flow goes in the flow vector; a node with nothing specified is no flow. A forgotten boundary condition is silently a no-flow boundary.
* **Elements and meshes.**
    * Linear triangles have a constant gradient; quadratic elements let the head curve and are more accurate per node.
    * Zone boundaries must follow element edges. A sheet pile is a slot whose two sides do not share nodes.
* **Accuracy.**
    * Errors are largest where the gradient is highest: pile tips, corners, drains, exit points, and contacts between very different $k$.
    * Refining locally there beats refining everywhere. Change element size gradually and avoid slivers.
    * The mesh is fine enough when refining it no longer changes the answer you care about.

### 9. Seepage Analysis in XSLOPE

* **Why it is here.** Slope stability needs pore pressures, and the seepage analysis computes them on the same model.
* **Analysis types.**
    * **Steady or transient:** one solution, or a solution at each time.
    * **Confined or unconfined:** with no phreatic surface, one solve; with one (or any exit face), the program iterates. This "confined" is not the same as a confined aquifer.
* **Inputs.**
    * **Conductivity:** a larger and a smaller $k$ at right angles, and the angle of the larger. Horizontal layering: larger $k$ horizontal, angle 0.
    * **Boundary conditions:** specified head, specified flux, exit face, reservoir (transient), and no flow, which is everything left unmarked. Check where the markers stop.
    * A sheet pile is a crack in the geometry; an impervious blanket is a no-flow boundary that lengthens the flow path.
* **Unconfined solution.**
    * Above the phreatic surface the pressure is negative and $k$ is reduced. The program solves, reduces $k$ where pressure is negative, and repeats until the heads settle.
    * Exit face nodes are sorted into wet (water leaves, head = elevation) and dry.
    * The choice of unsaturated model hardly matters for stability; it matters more for the flow rate.
* **Checking and reading results.**
    * **Confined check:** every head must lie between the highest and lowest specified heads.
    * **Piping:** water leaving the ground at a gradient near 1 can carry soil with it.
    * **Singular points:** at a pile tip or blanket edge the exact gradient is infinite, so a finer mesh just reports more. Read the design gradient a short distance away.
    * **Model width:** a gradient near zero at the ends says the model is wide enough.
    * **Zoned dam:** a clay core takes almost all the head loss, and most of the flow goes under the dam.
    * **Stability uses the positive pressures** and ignores suction unless you ask for it.
    * **Flow nets on zoned sections** use one material's $k$. They are a way to read the solution, not a check on it.

### 10. Transient Seepage

* **Why transient.** Many problems depend on conditions that are still changing: a reservoir drawdown, a storm, a flood. The pore pressures depend on when you look.
* **Storage.** The steady equation plus a storage term.
    * **Specific storage:** water released by compression below the phreatic surface. Units of 1/length.
    * **Specific yield:** water drained as the phreatic surface falls through the pores. Much the larger effect.
    * **Opposite trends:** soft clay has the largest specific storage and the smallest specific yield; clean gravel is the reverse.
    * **Drainage rate:** about vertical $k$ over specific yield. If the pool falls faster than a zone can drain, that zone holds water.
* **Running an analysis.**
    * It starts from a steady solution with the boundaries at their time-zero values. Solve it as steady first.
    * Only saved times (frames) are kept. Never interpolate between frames.
    * **Specified head vs reservoir boundary:** a specified head holds nodes above a falling pool at their value, which wrongly pulls water out of the face. A reservoir boundary turns uncovered nodes into exit face.
* **Reading a drawdown.**
    * The phreatic surface lags behind the pool, and water seeps back out of the upstream face. That lag is the pressure a steady analysis at the low pool misses.
    * A clay core barely moves while the pool falls and drains over months.
    * Inflow and outflow differ because water comes out of storage, so transient frames have no flow nets. Use velocity vectors.
    * Head histories at a few points show the lag; the water budget is a check on the run.

---

## 20 True/False Questions

1. **True or False:** Two points in a soil have the same pore pressure, so no water flows between them. **False** *(Flow depends on total head. If one point is higher, its total head is higher, and water flows from it to the other.)*
2. **True or False:** Moving the datum can change which way water flows. **False** *(The datum shifts every head by the same amount. Only differences in head matter.)*
3. **True or False:** To estimate how soon a contaminant reaches a well, use the seepage velocity, not the discharge velocity. **True** *(The seepage velocity is how fast the water actually moves through the pores.)*
4. **True or False:** For flow across the layers of a deposit, a thin clay layer can control the flow and take nearly all of the head loss. **True** *(The same flow passes through every layer, so the least permeable layer needs the largest gradient.)*
5. **True or False:** In an anisotropic soil whose bedding is tilted, a gradient in $x$ alone produces flow only in $x$. **False** *(The cross terms of the conductivity tensor are not zero, so the gradient in $x$ also drives flow in $y$.)*
6. **True or False:** The phreatic surface must be entered as a boundary condition before an unconfined seepage problem can be solved. **False** *(It is part of the solution: the line where the pressure is zero.)*
7. **True or False:** In a flow net with square cells, every flow channel carries the same flow. **True**
8. **True or False:** Two piezometers with their tips on the same equipotential line show the same water level, even if the tips are at different depths. **True** *(The total head is the same at both tips.)*
9. **True or False:** The Dupuit assumptions work best where the free surface is steep. **False** *(They work best where it is nearly flat and the flow is mainly horizontal.)*
10. **True or False:** The unconfined well equation, built on the Dupuit assumptions, gives a good flow rate but the wrong shape of the water table near the well. **True**
11. **True or False:** A rough estimate of the radius of influence is good enough for the steady well equations. **True** *(It enters only through a logarithm, so the answer is not very sensitive to it.)*
12. **True or False:** In an infinite confined aquifer with no river or lake to supply water, the cone of depression keeps growing as long as the well pumps. **True** *(That is the Theis solution, which has no $R$.)*
13. **True or False:** A bigger pump lets a well that has gone dry pump more water. **False** *(The water at the well has reached the bottom of the aquifer; there is no saturated thickness left to carry more flow.)*
14. **True or False:** Once there are enough wells to meet the deadline, adding more wells greatly reduces the total pumping rate needed. **False** *(The rate is set by the water that has to come out. More wells shorten the fastest possible time and add a margin.)*
15. **True or False:** In a finite element seepage model, a boundary node with nothing specified is a no-flow boundary. **True**
16. **True or False:** For flow under a sheet pile, a mesh refined only at the pile tip can be more accurate than a uniformly fine mesh with twice as many nodes. **True** *(The error is largest where the gradient is highest, at the tip.)*
17. **True or False:** On a dam with a clay core, the head contours crowd together across the core, so most of the water flows through the core. **False** *(Crowded contours across a low-$k$ zone mean it takes most of the head loss. Little water gets through it.)*
18. **True or False:** For a stability analysis, the choice of unsaturated conductivity model has a large effect on the pore pressures that matter. **False** *(The pressures that matter are below the phreatic surface, and they barely change with the model.)*
19. **True or False:** A specified head boundary is the right type for the upstream face of a dam whose reservoir is drawn down. **False** *(It would hold uncovered nodes at the lower pool level, a suction pulling water out of the face. Use a reservoir boundary.)*
20. **True or False:** A transient XSLOPE frame shows flow lines, just as a steady solution does. **False** *(With water coming out of storage, inflow does not equal outflow for each piece of soil, so there is no flow net. Use velocity vectors.)*

---

## 30 Multiple Choice Questions

1. A piezometer has its tip at a point in saturated soil. Measured from the datum, the level the water rises to in the piezometer is the:

    > A) Pressure head at the point<br>
    > B) Total head at the point<br>
    > C) Elevation head of the tip<br>
    > D) Depth below the water table<br>
    > **Answer: B) Total head at the point.** The water rises above the tip by the pressure head, and the tip is at its elevation, so the water level is the elevation plus the pressure head.

2. A tank of soil sits under still water. Point A is in the water near the surface, and point B is deep in the soil. Which is true?

    > A) Water flows from B to A, because the pressure is higher at B<br>
    > B) Water flows from A to B, because A is higher<br>
    > C) No water flows, because the total heads at A and B are equal<br>
    > D) No water flows, because the soil blocks the flow<br>
    > **Answer: C) No water flows, because the total heads at A and B are equal.** B is lower than A, but its pressure head is larger by the same amount.

3. Water flows down through a vertical column of uniform soil. Along the column, the total head:

    > A) Is the same everywhere<br>
    > B) Increases with depth, because the pressure increases<br>
    > C) Drops only at the outlet<br>
    > D) Drops linearly from top to bottom<br>
    > **Answer: D) Drops linearly from top to bottom.** In a uniform soil the head is lost at a steady rate along the flow path.

4. Why is the seepage velocity larger than the discharge velocity?

    > A) The same flow must pass through only the pore area, not the whole cross-section<br>
    > B) $k$ is larger inside the pores<br>
    > C) The gradient is larger inside the pores<br>
    > D) Gravity accelerates the water in the pores<br>
    > **Answer: A) The same flow must pass through only the pore area.** The discharge velocity divides the flow by the gross area; the water actually moves through the smaller area of the pores that carry flow.

5. You estimate how long a contaminant will take to reach a well, using the discharge velocity instead of the seepage velocity. Your estimate is:

    > A) Too short, which is conservative<br>
    > B) Too long, which is conservative<br>
    > C) Correct, because the flow rate is the same<br>
    > D) Too long, which is unsafe<br>
    > **Answer: D) Too long, which is unsafe.** The discharge velocity is slower than the real water speed, so the contaminant would arrive sooner than you predicted.

6. A deposit has a sand layer, a thin clay layer, and a gravel layer. Water flows vertically down across all three. Where is most of the head lost?

    > A) In the gravel<br>
    > B) In the clay<br>
    > C) In the sand<br>
    > D) Equally in all three<br>
    > **Answer: B) In the clay.** The same flow passes through every layer, so the layer with the lowest $k$ needs the largest gradient.

7. Two parallel ditches drain a field of identical strips, with rain falling between them. In a model of one strip, the vertical line midway between two ditches should be:

    > A) A no-flow boundary<br>
    > B) A specified head<br>
    > C) An exit face<br>
    > D) A specified flux<br>
    > **Answer: A) A no-flow boundary.** The water on each side flows to its own ditch, so none crosses the midline. It is a line of symmetry.

8. The right boundary condition along the downstream slope of an earth dam is:

    > A) A specified head equal to the tailwater level<br>
    > B) No flow<br>
    > C) An exit face<br>
    > D) A specified flux equal to the rainfall<br>
    > **Answer: C) An exit face.** Where water seeps out, the head equals the elevation, and where on the slope that happens is not known in advance: the solution finds it.

9. A soil's bedding dips at 30° from horizontal. Compared with horizontal bedding, what changes in Darcy's law written in $x$ and $y$?

    > A) Nothing, because $k_1$ and $k_2$ have not changed<br>
    > B) The soil becomes isotropic<br>
    > C) The velocity in $x$ now depends on the gradient in both $x$ and $y$<br>
    > D) Water can flow only along the bedding<br>
    > **Answer: C) The velocity in $x$ now depends on the gradient in both $x$ and $y$.** The principal axes no longer line up with $x$ and $y$, so the cross terms of the conductivity tensor are not zero.

10. In a flow net with square cells, a region where the cells are much smaller than elsewhere has:

    > A) A high gradient and a high velocity<br>
    > B) Less flow per channel<br>
    > C) A lower $k$<br>
    > D) Zero pressure<br>
    > **Answer: A) A high gradient and a high velocity.** Every drop is the same head loss, so where the cells are short, that head is lost over a shorter distance.

11. A flow net under a sheet pile has 3 flow channels and 6 equipotential drops. A redesign with a longer flow path gives a net with 3 flow channels and 12 drops, with the same soil and the same head difference. The flow:

    > A) Doubles<br>
    > B) Is cut to a quarter<br>
    > C) Does not change<br>
    > D) Is cut in half<br>
    > **Answer: D) Is cut in half.** The flow depends on $k$, the head lost, and the shape factor (channels over drops), which falls from 3/6 to 3/12.

12. A flow net for an anisotropic soil is drawn on a transformed section and then stretched back to true scale. At true scale:

    > A) The cells are still squares<br>
    > B) The lines no longer cross at right angles<br>
    > C) There are more flow channels than on the transformed section<br>
    > D) The flow rate uses the horizontal $k$<br>
    > **Answer: B) The lines no longer cross at right angles.** Stretching the net back distorts the cells, but the numbers of channels and drops are unchanged, and the net is correct for the anisotropic soil. The flow rate uses the geometric mean of $k_x$ and $k_y$.

13. The Dupuit assumptions work best where:

    > A) The free surface is nearly flat and the flow is mainly horizontal<br>
    > B) The free surface is steep, close to a drain<br>
    > C) The flow is mainly vertical<br>
    > D) The water exits high on the downstream face<br>
    > **Answer: A).** They assume horizontal flow and use the tangent of the free surface slope in place of the sine, which is accurate only for gentle slopes.

14. Under the Dupuit assumptions, the free surface through a rectangular section between two water levels is:

    > A) A straight line<br>
    > B) A parabola that gets flatter downstream<br>
    > C) A parabola that gets steeper downstream<br>
    > D) Horizontal<br>
    > **Answer: C) A parabola that gets steeper downstream.** The same flow passes through a thinner saturated thickness downstream, so the gradient has to increase.

15. A French drain 150 m long runs parallel to a river, and its inflow is estimated with a 2D rectangular-section solution. The real inflow is probably:

    > A) Smaller, because the Dupuit assumptions overestimate the flow<br>
    > B) Zero, because the drain is lower than the river<br>
    > C) The same<br>
    > D) Larger, because water also reaches the drain around its ends and from the landward side<br>
    > **Answer: D).** The 2D section misses the flow around the ends of a short drain and the groundwater from the far side.

16. In a confined aquifer, why does the cone of depression get steeper close to the well?

    > A) $k$ is higher near the well<br>
    > B) The flow area gets smaller toward the well<br>
    > C) The pump's suction pulls harder near the well<br>
    > D) The aquifer is thinner near the well<br>
    > **Answer: B) The flow area gets smaller toward the well.** The water converges through cylinders of smaller and smaller area, and Darcy's law needs a larger gradient to push the same flow through less area.

17. Two wells pump from an unconfined aquifer. If you add the drawdowns from each well, as you would in a confined aquifer, the predicted water table is:

    > A) Too high, most of all between the wells<br>
    > B) Correct<br>
    > C) Too low everywhere<br>
    > D) Correct between the wells, but wrong far away<br>
    > **Answer: A) Too high, most of all between the wells.** In an unconfined aquifer it is $H^2 - h^2$ that adds. Where the saturated thickness is smallest, the error is largest.

18. In a pumping test in an unconfined aquifer, the early points follow a much smaller storage value. If you fit the line through the early points, the specific yield you get is:

    > A) About right<br>
    > B) Far too large<br>
    > C) Far too small<br>
    > D) Unaffected by which points you use<br>
    > **Answer: C) Far too small.** Early on, the aquifer releases water elastically, as a confined one does (delayed yield). Fit the late points.

19. A contractor proposes one row of wellpoints at the ground surface to lower the water 12 m. What is wrong?

    > A) Nothing<br>
    > B) Wellpoints cannot be used next to an excavation<br>
    > C) Wellpoints work only in clay<br>
    > D) One stage of wellpoints cannot lift water 12 m<br>
    > **Answer: D) One stage of wellpoints cannot lift water 12 m.** Suction limits a stage to about 5 to 6 m of lift. Use deep wells, whose submersible pumps have no suction limit, or add stages on benches.

20. Partway through a dewatering design, a pumping test shows that $k$ is lower than the design assumed. The main risk is:

    > A) The pumps are too large<br>
    > B) No pumping rate meets the deadline<br>
    > C) None, because a lower $k$ means less pumping<br>
    > D) The cutoff wall leaks more<br>
    > **Answer: B) No pumping rate meets the deadline.** The ground can't feed the wells fast enough, so they go dry first. A lower $k$ than estimated is the dangerous mistake. The fix is more wells, which is hard once the job has started.

21. In a layered soil with a horizontal $k$ much larger than the vertical $k$, why does the water table inside an excavation lag behind the heads at the well screens?

    > A) The wells pump less in layered soil<br>
    > B) The heads at the screens fall slowly<br>
    > C) The stored water drains slowly across the layers<br>
    > D) Layered soil has no specific yield<br>
    > **Answer: C) The stored water drains slowly across the layers.** The wells pull water along the layers, so the heads at depth fall fast, but the water stored near the water table has to cross the low vertical $k$ to reach the screens.

22. Three 1D finite elements in series carry the same flow. Which one has the largest head drop?

    > A) The one with the smallest conductance<br>
    > B) The longest one<br>
    > C) The one with the largest conductance<br>
    > D) They are all equal<br>
    > **Answer: A) The one with the smallest conductance.** With the same flow through each, the element that conducts least needs the largest head difference.

23. In a finite element seepage model, you forget to assign a boundary condition along one side. That side is:

    > A) An error the solver always catches<br>
    > B) An exit face<br>
    > C) A specified head of zero<br>
    > D) A no-flow boundary<br>
    > **Answer: D) A no-flow boundary.** A node with nothing specified has zero flow. That is why you check where the boundary markers are on the mesh.

24. How do you tell whether a finite element mesh is fine enough?

    > A) Use the largest mesh the computer can handle<br>
    > B) Refine it and solve again<br>
    > C) Check that the head contours look smooth<br>
    > D) Use quadratic elements, which are always accurate<br>
    > **Answer: B) Refine it and solve again.** When the answer you care about (a flow rate, an exit gradient, a pore pressure) stops changing, the mesh is fine enough.

25. XSLOPE solves a model as unconfined, iterating to find the phreatic surface, when the model:

    > A) Has more than one material<br>
    > B) Uses quadratic elements<br>
    > C) Has an exit face<br>
    > D) Has a specified flux<br>
    > **Answer: C) Has an exit face.** A model with no exit face is solved as confined, in one solve.

26. The maximum gradient reported at the tip of a sheet pile goes up every time the mesh is refined. This means:

    > A) The mesh is still too coarse<br>
    > B) The soil will pipe at the tip<br>
    > C) The pile is leaking<br>
    > D) The tip is a singular point<br>
    > **Answer: D) The tip is a singular point.** The exact gradient there is infinite, so a finer mesh just reports a higher number. Read the design gradient a short distance away.

27. On a zoned dam, the flow net drawn with the clay core as the base material has hundreds of flow channels. What should you do?

    > A) Choose a different base material<br>
    > B) Refine the mesh<br>
    > C) Switch to a different unsaturated model<br>
    > D) Switch to quadratic elements<br>
    > **Answer: A) Choose a different base material.** Square cells need a single $k$. Pick the zone most of the water flows through. The base material only sets how the net is drawn; the computed flow does not change.

28. During a reservoir drawdown, the clay core of a dam can drain at about 0.17 m/day and the shell at about 2.3 m/day. The pool falls 0.36 m/day. What happens?

    > A) Both zones keep up with the pool<br>
    > B) The shell keeps up; the core lags<br>
    > C) The core keeps up; the shell lags<br>
    > D) Neither zone drains until the pool stops falling<br>
    > **Answer: B) The shell keeps up; the core lags.** The shell drains faster than the pool falls, and the core drains slower, so the core is left holding water.

29. You need the pore pressures at day 40 of a drawdown, but frames were saved only at days 30 and 47. You should:

    > A) Use the day 47 frame, the nearer one<br>
    > B) Interpolate linearly between the two frames<br>
    > C) Use a steady solution at the day 40 pool level<br>
    > D) Add day 40 to the save times and run again<br>
    > **Answer: D) Add day 40 to the save times and run again.** The nearer frame is the wrong time, a blend of two solutions is not a solution of anything, and a steady solution would miss the lag.

30. During a reservoir drawdown, a frame reports zero inflow and an outflow ten times the steady flow. Where is the water coming from?

    > A) The foundation rock<br>
    > B) A numerical error<br>
    > C) Water released from storage as the dam drains<br>
    > D) The tailwater<br>
    > **Answer: C) Water released from storage as the dam drains.**

---

## 20 Short Answer Questions

1. **What does total head mean physically, and how could you measure it at a point?**
   It is the energy of the water per unit weight, written as a length. Install a piezometer with its tip at the point: the elevation of the water level in it, measured from the datum, is the total head.

2. **Why is the velocity head dropped in seepage problems?**
   Groundwater moves very slowly. Even at 1 ft/s, much faster than seepage, the velocity head is only about a sixtieth of a foot.

3. **The pore pressure is the same at the top and the bottom of a soil column. Can water flow between them? Explain.**
   Yes. The top is higher, so its elevation head and its total head are larger. Water flows from the top to the bottom. Total head decides the flow, not pressure.

4. **When do you use the discharge velocity, and when the seepage velocity?**
   Use the discharge velocity (or the flow rate) for volumes of flow. Use the seepage velocity for how fast the water, and anything dissolved in it, actually travels, such as a contaminant's travel time.

5. **Why is the effective porosity smaller than the porosity, and in which soils is the difference largest?**
   Dead-end pores and voids filled with fines hold water that is nearly still, so not all of the pore space carries flow. The difference is largest in clays; in sands and gravels the two are close.

6. **Why is a measured $k$ for the site worth much more than a value from a table?**
   $k$ varies over about twelve orders of magnitude, and the range for one soil type is wide. Even a good estimate may only be within an order of magnitude, so a site measurement is far more reliable than a table value.

7. **Name two situations where Darcy's law may not hold, and say why.**
   High velocities in clean coarse gravel or rockfill, and close to a pumping well. In both, the flow in the pores may no longer be laminar, and the head loss grows faster than the velocity.

8. **Why does a layered deposit usually conduct water better horizontally than vertically?**
   Along the layers, the permeable layers carry most of the flow. Across them, the same flow has to pass through the least permeable layer, which controls the result. So the equivalent $k$ along the layers is always at least as large as across them.

9. **Why isn't the phreatic surface a boundary condition in an unconfined seepage model?**
   Its location is not known in advance. It is part of the answer: the line where the pressure is zero, found when the problem is solved.

10. **Why do flow lines and equipotential lines cross at right angles in an isotropic soil?**
    Water flows in the direction of the steepest drop in total head, which is perpendicular to the lines of constant head.

11. **The line of seepage in a dam is both a flow line and a line of zero pressure. What does each property tell you when you draw a flow net?**
    As a flow line, no water crosses it, so it is the top flow line of the net. As a line of zero pressure, its head equals its elevation, so the equipotential lines meet it at equal steps of elevation.

12. **How do you find the pore pressure at a point from a flow net?**
    Divide the total head loss by the number of drops to get the head lost per drop. Count the drops from the upstream side to the point to get its total head. Subtract the point's elevation to get the pressure head, and multiply by the unit weight of water.

13. **When would you trust a Dupuit-based solution, and when would you not?**
    Trust it where the free surface is gentle and the flow is mainly horizontal. Be careful where the free surface is steep, such as near a drain, a well, or an exit face, where the shape of the free surface is wrong even if the flow rate is often still right.

14. **In an unconfined aquifer, why do you add $H^2 - h^2$ from several wells instead of adding the drawdowns?**
    The governing equation for unconfined flow is linear in the square of the saturated thickness, not in the head, so superposition applies to $H^2 - h^2$. Adding drawdowns leaves the water table too high.

15. **What is the physical difference between storativity and specific yield, and why does it make the cone spread more slowly in an unconfined aquifer?**
    Storativity is water released by the soil compressing and the water expanding while the aquifer stays saturated; it is tiny. Specific yield is water that drains from the pores as the water table falls; it is far larger. So an unconfined aquifer gives up much more water for the same drop in head, and its cone spreads much more slowly.

16. **Why can a well go dry, and why doesn't a bigger pump fix it?**
    The more a well pumps, the deeper its cone. At some rate the water at the well reaches the bottom of the aquifer, and there is no saturated thickness left to carry more flow. A bigger pump only pumps it dry sooner.

17. **Why does a shorter dewatering deadline need a higher pumping rate but less water in total?**
    To get the water down sooner, the wells have to pump harder. With a long deadline, the cone spreads far out and the wells drain a much larger area to get the same drawdown under the excavation, so more water is pumped in total.

18. **Why is refining the mesh at the tip of a sheet pile more efficient than making the whole mesh finer?**
    The error is largest where the gradient is highest, at the tip. Small elements there remove most of the error, while uniform refinement adds many elements where the head hardly changes.

19. **A confined XSLOPE model has specified heads of 13 m and 10 m and no sources inside. The solution shows a head of 14 m somewhere. What does that tell you?**
    Something is wrong with the model. With no sources inside, every head must lie between the boundary heads. Check the inputs, such as the boundary values or a flux you did not intend.

20. **Why can't a reservoir drawdown be modeled as a steady analysis at the lower pool level?**
    The phreatic surface in the dam lags behind the pool, most of all in low-$k$ zones, because the soil has to release stored water. A steady analysis at the low pool assumes the dam has already drained and misses that water pressure.

---

## 15 Open Response (Essay) Questions

1. **Explain why water flows from higher to lower total head, not from higher to lower pressure. Use a soil column with equal pressures at its top and bottom, and a tank of soil under still water.**
   Total head is the energy of the water per unit weight: elevation head plus pressure head (velocity head is negligible in soil). Water flows where there is a difference in that energy. In the soil column, the pressures at the top and bottom are equal, but the top is higher, so its total head is higher and water flows down. In the tank, a deep point has a higher pressure, but it is lower by the same amount, so the total heads are equal and nothing flows. In both cases, a piezometer at each point would show it: water flows from the point where the piezometer level is higher.

2. **Explain how layering affects seepage. Where does the flow go when water flows along the layers, where is the head lost when it flows across them, and what does this mean for a soil's anisotropy?**
   Along the layers, every layer has the same gradient, so each carries flow in proportion to its $k$ and thickness. The most permeable layers carry most of the water; a thin gravel layer can carry nearly all of it. Across the layers, the same flow must pass through every layer, so the head losses add and the least permeable layer takes most of the head; a thin clay layer can take nearly all of it, and the pore pressure changes most steeply across it. The equivalent $k$ along the layers is always at least as large as across them, which is one reason layered soils conduct better horizontally than vertically.

3. **For a cofferdam (an excavation between two rows of sheet piles, pumped down below the water table) and for an earth dam on an impervious foundation, describe the boundary conditions you would use and why. What is not a boundary condition?**
   Cofferdam: outside the piles, the head on the ground is the water level above it (specified head); on the excavation floor, the head is the pumped-down level (specified head); the sheet piles and the impervious base are no-flow; the far sides are no-flow, placed far enough away not to affect the flow near the cofferdam. Earth dam: the upstream face under the reservoir has a specified head equal to the reservoir level; the base is no-flow; the downstream slope is an exit face, where the head equals the elevation wherever water seeps out. The phreatic surface in the dam is not a boundary condition. It is part of the solution, where the pressure is zero, and the exit point is found along with it.

4. **Explain why a flow net works. Why does a constant cell shape give equal flow in every channel and equal head loss in every drop, and what can you read from a finished net?**
   No water crosses a flow line, so the flow through every cell of a channel is the same. By Darcy's law, a cell's flow is $k$ times its head drop over its length, times its width. If every cell has the same length-to-width ratio, equal drops give equal flows: every channel carries the same flow and every drop is the same head loss. From a finished net you can read the total head anywhere by counting drops, the pore pressure by subtracting the elevation, the flow rate from $k$, the head lost, and the shape factor (channels over drops), and the places where small cells show high gradients and velocities, such as the tip of a sheet pile.

5. **Explain how anisotropy changes a flow net and how a transformed section handles it. What changes and what doesn't?**
   A flow net solves the Laplace equation, which holds only for isotropic soil. In an anisotropic soil drawn at true scale, flow lines and equipotential lines do not cross at right angles. Multiplying the horizontal distances by $\sqrt{k_y/k_x}$ (so the section gets narrower when $k_x$ is larger) turns the equation back into the Laplace equation, so on the transformed section the soil behaves as if isotropic, and a square-cell net can be drawn. Stretched back to true scale, the cells are no longer square and the lines don't cross at right angles, but the numbers of channels and drops are unchanged. The flow uses a single equivalent conductivity, the geometric mean of $k_x$ and $k_y$.

6. **Explain the three Dupuit assumptions, when they hold and when they fail, and how you would use a Dupuit solution to estimate the flow from a river to a nearby drain. What does the estimate miss?**
   One: the exit point is at the tailwater (really it is higher, on the exit face). Two: the gradient is the same down a vertical line, so the flow is horizontal. Three: the gradient equals the slope of the free surface, using the tangent where the sine is correct, which is accurate up to about 10° but poor on steep surfaces. They hold where the free surface is gentle and the flow is mainly horizontal, and fail near drains, wells, and steep faces, although the flow rate is often still right there. For a drain parallel to a river, treat the soil between them as a rectangular section with the river level on one side and the drain level on the other, on a low-permeability base. It is a screening estimate: a short drain also collects water around its ends and from the landward side, so the real flow is larger. Check a design with a numerical model.

7. **Compare steady flow to a well in a confined aquifer and in an unconfined aquifer: the flow area, what superposition adds, and how good the Dupuit-based equations are.**
   In a confined aquifer, the layer stays full as the head drops, so the flow area at each radius is fixed. The equation is linear in the head, so the drawdowns from several wells add, and overlapping cones lower the water across a site. In an unconfined aquifer, the water table itself drops, so the saturated thickness, and the flow area, shrink near the well, and the flow has a vertical component. The equation is linear in the square of the saturated thickness, so $H^2 - h^2$ adds, not the drawdown; adding drawdowns would leave the water table too high between the wells. The unconfined equation, built on the Dupuit assumptions, gives the correct flow rate, but the water table shape near the well is wrong. In both, the answer is not very sensitive to $R$, because it enters through a logarithm.

8. **Explain how the cone of depression grows after a well starts pumping, what the radius of influence in a steady equation really represents, and why a transient pumping test is better than a steady one.**
   When the pump starts, the water comes out of storage around the well: the soil compresses and the water expands in a confined aquifer, or the pores drain in an unconfined one. The cone spreads as more of the aquifer gives up water. If it reaches a boundary that supplies water, such as a river or lake, it stops growing; otherwise it keeps growing (Theis). At late time, the Theis solution becomes the steady equation with an $R$ that grows with the square root of time, so a steady $R$ really stands for a pumping time. A steady test needs steady state, which is hard to recognize. A transient test plots drawdown against the log of time; the late points fall on a straight line whose slope gives the transmissivity and whose intercept gives the storage, with no wait. In an unconfined aquifer, fit the late points, because delayed yield makes the early ones follow a much smaller storage.

9. **How would you choose a dewatering method for (a) a shallow excavation in stiff clay, (b) a deep excavation in sand, and (c) a site in very permeable ground next to a river with buildings nearby? Explain each choice.**
   (a) Sumps and ditches can work for shallow drawdowns in stiff clay, gravel, or rock; in sand, pumping from the floor could wash out fines. (b) Wellpoints lift only about 5 to 6 m per stage by suction, so a deep excavation needs several stages on benches, or deep wells, whose submersible pumps have no suction limit and suit deeper drawdowns and more permeable soils. (c) Wells alone would pump a great deal, with the river feeding the cone, and the drawdown could settle the neighboring buildings. A slurry cutoff wall keyed into the low-$k$ layer cuts off the inflow, so the wells inside pump only the stored water and the leakage, and the water outside hardly moves. The decision rests on the permeability, the drawdown needed, and how long the system must run.

10. **Explain how a ring of wells is designed to meet a deadline: what $Q_{min}$ is, why the rate is cut back, how the deadline and the number of wells affect the design, and why $k$ matters so much.**
    $Q_{min}$ is the smallest total rate that gets the water down everywhere inside the excavation by the deadline; the middle, farthest from the wells, comes down last. The rate cannot stay at $Q_{min}$: as the cones spread, each well can take less, and pumping too much would drive the water at a well to the bottom of the aquifer, so the rate is cut back to keep every well from going dry. Once the excavation is dewatered, a much lower holding rate keeps it dry. A shorter deadline takes a higher rate but less water in total, and each set of wells has a fastest possible time. The deadline sets the fewest wells; more wells beyond that add margin but barely change the rate, which is set by the water that has to come out. $Q_{min}$ is highly sensitive to $k$: a $k$ well above the estimate takes much more pumping, and a lower $k$ can mean the wells go dry and no rate works. So measure $k$ with a pumping test and design over a range around it.

11. **When is a slurry cutoff wall worth building, what does it change about the pumping and about the area outside the site, and how is it modeled?**
    It is worth it when wells alone would pump too much (very permeable ground, or a river or lake nearby), when drawdown outside would settle neighbors or dry up their wells, or when the discharge is hard to dispose of or must be treated. The wall, keyed into the low-$k$ layer, cuts off the inflow, so the wells pump only the stored water and the leakage through the wall. That means a lower pumping rate, fewer wells, far less water to discharge, and a water table outside that barely moves. The trade is the cost of the wall, and defects or a poor key leak more, so allow a margin. The leakage is modeled like flow to a trench, using the wall's $k$ and thickness. Because the well equations assume a uniform aquifer with no boundaries, the design with a wall uses a numerical solution in which the wall is a band of low $k$.

12. **Explain how a finite element program solves a seepage problem, from the mesh to the solved heads. How do boundary conditions enter, and what happens on a boundary you leave alone?**
    The section is divided into elements joined at nodes, each element in one soil zone, and the unknowns are the heads at the nodes. Inside each element, the head varies simply between its nodal heads; Darcy's law turns that into flows at the element's nodes, through a matrix that depends on the element's geometry and conductivity. Each element's matrix is added into a global matrix at its nodes' rows and columns, and at every node the flows must balance. The global matrix is symmetric and banded, so it is easy to store and solve. A specified head replaces its node's row; a specified flow goes into the flow vector; a node with nothing specified has zero flow, so a boundary you leave alone is automatically no-flow. After solving for the heads, the flows at the known-head nodes and the velocity in each element follow.

13. **Explain how to design a mesh for a seepage problem and how to tell whether it is good enough, using flow under a sheet pile as the example.**
    The solution is approximate, and the error is largest where the head changes quickly: at the tip of a sheet pile or cutoff, at corners, drains, and exit points, and at boundaries between very different $k$. So put small elements there, let the element size grow gradually away from them, and avoid slivers. Under a sheet pile, a coarse mesh refined at the tip was more accurate than a uniform fine mesh with more than twice as many nodes. Quadratic elements beat linear ones on a uniform mesh, but once the tip was refined the two were about the same, because the error came from the tip. To check a mesh, refine it and solve again; when the answer you care about stops changing, the mesh is good enough. A gradient at a singular point, such as the pile tip, never stops changing, so read it a short distance away.

14. **Explain how XSLOPE solves an unconfined problem such as a zoned earth dam, and what the results show. How much does the choice of unsaturated model matter?**
    The whole section is solved as one region. XSLOPE starts with the saturated $k$ everywhere and solves; then, wherever the pressure head is negative, it reduces $k$ by the relative conductivity and solves again, repeating until the heads stop changing. The phreatic surface is the line of zero pressure head. The downstream slope is marked as an exit face, and its nodes are sorted into wet (head equal to elevation, water leaving) and dry (no flow) until that set stops changing. On a dam with a low-$k$ clay core, almost the whole head drop is across the core, the phreatic surface falls steeply through it, and most of the flow goes under the dam through the foundation. Pore pressures are positive below the phreatic surface and negative above it; stability uses the positive ones. The unsaturated model barely moves the phreatic surface, so it hardly matters for stability; it changes the total flow by a few percent, so it deserves more thought when the flow through unsaturated soil is what you need.

15. **Describe a transient analysis of a reservoir drawdown through a dam with a clay core: what storage does, how to judge which zones will lag, why the upstream face is a reservoir boundary, and how to read the results.**
    A transient analysis adds a storage term: as the head falls, the soil gives up water, mostly through the specific yield in the band the phreatic surface is crossing. A zone's drainage rate is about its vertical $k$ over its specific yield; a granular shell drains faster than the pool falls and keeps up, while a clay core drains much slower and is left holding water. The upstream face is a reservoir boundary: submerged nodes are held at the pool level, uncovered nodes become an exit face where the still-saturated soil seeps back into the reservoir, and nodes not yet reached are no-flow. A specified head boundary would instead hold the uncovered nodes at the low pool level, wrongly pulling water out of the face. The run starts from a steady solution at full pool and keeps only the saved frames; any other time needs a new run, never an interpolation. The frames show the phreatic surface in the core staying high while the pool falls, inflow dropping to zero and outflow rising to many times the steady flow, all from storage. There are no flow lines, because inflow does not equal outflow while storage changes, so velocity vectors, head histories at chosen points, and the water budget are used to read the run.

---

## Glossary of Key Terms

| Term | Definition |
|:-----|:-----------|
| **Anisotropic Soil** | A soil whose $k$ depends on direction, usually larger along the bedding than across it. |
| **Aquitard** | A low-$k$ layer that confines an aquifer; the well equations treat it as impermeable. |
| **Base Material** | In XSLOPE, the material whose $k$ is used to draw a flow net with square cells. |
| **Conductance** | $k$ times the area over the length of a 1D element: the flow it carries per unit head difference. |
| **Cone of Depression** | The cone-shaped drop in the head or water table around a pumping well. |
| **Confined Aquifer** | A permeable layer between an impermeable base and an aquitard; it stays saturated as the head drops. |
| **Confined Problem** | A seepage problem in which the soil is saturated everywhere and all boundaries are known; one solve gives the heads. |
| **Cutoff Wall** | A low-$k$ wall around a site, keyed into the low-$k$ layer, that cuts off inflow from outside. |
| **Delayed Yield** | Early in an unconfined pumping test, the aquifer releases water elastically, and the pores drain later. |
| **Discharge Velocity** | The flow rate divided by the gross area of soil and voids; not the real speed of the water. |
| **Drawdown** | How far the head has fallen from its level before pumping. |
| **Dupuit Assumptions** | Exit point at the tailwater, the same gradient down a vertical line, and gradient equal to the slope of the free surface. |
| **Effective Porosity** | The fraction of a cross-section whose pores actually carry flow. |
| **Elevation Head** | The height of a point above the datum. |
| **Equipotential Line** | A line of constant total head. |
| **Equivalent $k$** | One $k$ that stands for a stack of layers: a thickness-weighted average along the layers, a harmonic average across them. |
| **Exit Face** | A boundary where water may seep out of the ground, also called a seepage face; where it is wet, the head equals the elevation. |
| **Flow Channel** | The space between two adjacent flow lines; each carries the same flow in a square-cell net. |
| **Flow Line** | A path that water follows; no water crosses it. |
| **Frame** | A saved solution of a transient analysis at one time. |
| **Holding Rate** | The lower pumping rate that keeps an excavation dry once it has been dewatered. |
| **Hydraulic Conductivity ($k$)** | How easily water flows through a soil, in units of velocity. |
| **Hydraulic Gradient** | The total head lost per unit length of flow path; no units. |
| **Phreatic Surface** | The top of the saturated zone, where the pore pressure is zero; also the line of seepage or free surface. |
| **Piezometer** | An open tube with its tip at a point in the soil; the water level in it shows the total head there. |
| **Pressure Head** | The height water rises in a piezometer above a point. |
| **Principal Axes** | The directions of largest and smallest $k$ in an anisotropic soil, at right angles to each other. |
| **$Q_{min}$** | The smallest total pumping rate that dewaters an excavation by the deadline. |
| **Radius of Influence ($R$)** | The distance from a well at which the drawdown dies out. |
| **Relative Conductivity** | The fraction, 0 to 1, of the saturated $k$ that applies in unsaturated soil. |
| **Reservoir Boundary** | XSLOPE's boundary for a pool that rises and falls: held when submerged, an exit face when uncovered, no-flow before the water reaches it. |
| **Seepage Velocity** | The average speed of the water in the pores. |
| **Shape Factor** | The number of flow channels over the number of equipotential drops in a flow net. |
| **Singular Point** | A point, such as the tip of a sheet pile, where the exact gradient is infinite. |
| **Specific Storage** | The water a unit volume of saturated soil releases per unit drop in head, from compressing the soil and expanding the water. |
| **Specific Yield** | The water drained from the pores per unit area as the water table falls by one unit. |
| **Specified Head** | A boundary condition that holds the total head at a known value, such as a pool or tailwater level. |
| **Storativity** | The water a confined aquifer releases per unit area per unit drop in head; tiny compared with specific yield. |
| **Superposition** | Adding the effects of several wells, or of changes in a well's rate: drawdowns in a confined aquifer, $H^2 - h^2$ in an unconfined one. |
| **Total Head** | Elevation head plus pressure head: the level water rises to in a piezometer, measured from the datum. |
| **Transformed Section** | A section with its horizontal distances multiplied by $\sqrt{k_y/k_x}$, so an anisotropic soil can be drawn with a square-cell flow net. |
| **Transmissivity** | $k$ times the aquifer thickness: how much water the full thickness can carry. |
| **Unconfined Aquifer** | An aquifer whose top is the water table; pumping drains its pores and shrinks its saturated thickness. |
| **Unconfined Problem** | A seepage problem with a phreatic surface whose location is part of the answer; XSLOPE iterates to find it. |
| **Wellpoint** | A small, closely spaced well on a header pipe, pumped by suction, with a lift of about 5 to 6 m per stage. |
