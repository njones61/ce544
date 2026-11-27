# Seepage Analysis: Study Guide

The equation sheet is provided on the exam, so this guide does not ask you to memorize equations. It is about what the quantities mean, why the methods work, when their assumptions fail, what controls the answer, and how to read a result.

## Outline of Main Concepts

### 1. Hydraulic Head

* **Pore pressure.** The water in the soil pores is under pressure, the pore pressure. Below a water table, with the water at rest, it is hydrostatic: it grows in proportion to the depth below the water table.
* **Piezometer.** A piezometer is an open tube with its tip at a point in the soil. Water rises in it until the weight of the water column balances the pore pressure at the tip. With still water, it fills to the water table.
* **Head is energy.** Head is the energy of the water per unit weight, written as a length. Bernoulli's equation adds up the work it takes to move water from one point to another: lifting it, changing its speed, and pushing it from one pressure to another.
* **Elevation head.** The height of the point above a datum. The datum can be anywhere, but every point in a problem must use the same one. Only differences in head matter, and those come out the same for any datum.
* **Pressure head.** The pore pressure divided by the unit weight of water. It is the height the water rises in a piezometer above the point.
* **Velocity head.** The part of the head from the water's speed. Groundwater moves so slowly that it is negligible: even at 1 ft/s it is only about a sixtieth of a foot, and seepage is far slower than that. So it is dropped.
* **Total head for groundwater.** Elevation head plus pressure head. Physically, it is the elevation of the water level in a piezometer at the point. Think of it as how high the water would stand in a tube placed there.
* **What makes water flow.** Water flows from higher total head to lower total head. Neither the pressure alone nor the elevation alone decides the direction.
* **Still water, no flow.** In a tank of soil under still water, a deep point has a higher pressure than a shallow one, but it is lower by exactly the same amount. The total heads are equal, and no water flows.
* **Equal pressure, flow anyway.** In a soil column where the pore pressure is the same at the top and the bottom, the top point is higher, so its total head is higher, and water flows down. At equal elevations, the point with the higher pressure has the higher head.
* **Head along a flow path.** In a column or tube of uniform soil with a constant cross-section, the total head drops linearly along the flow path. To find the pore pressure at a point: find its total head by proportion along the path, subtract its elevation to get the pressure head, and multiply by the unit weight of water.
* **Common mistakes.** Confusing pressure head with total head, using different datums for different points, and assuming water flows from high pressure to low pressure.

### 2. Darcy's Law

* **Darcy's experiment.** In 1856, Henry Darcy measured flow through sand columns for the water filters of Dijon, France. The flow rate was proportional to the head difference and to the area, and inversely proportional to the length of the sample. The constant of proportionality, $k$, depends on the soil.
* **Hydraulic conductivity, $k$.** How easily water passes through a soil, in units of velocity. It is also called the coefficient of permeability.
* **$k$ varies enormously.** It spans about twelve orders of magnitude, from more than 1 cm/s in clean gravel to $10^{-10}$ cm/s or less in unweathered clay. A measured $k$ for the site is worth far more than a value from a table, and an estimate within an order of magnitude is often the best available.
* **Hydraulic gradient.** The head lost per unit length of flow path. It has no units. A gradient of 0.1 means the water loses 1 ft of head for every 10 ft it travels. It is a gradient in total head, not in pressure.
* **Where the path narrows.** If the flow area gets smaller along the path, the same flow must pass through less area, so the gradient increases and the head falls faster.
* **The minus sign.** Head decreases in the direction of flow, so when the gradient is written as a rate of change along the path, $i = -dh/ds$, the minus sign makes it positive.
* **Discharge velocity.** The flow rate divided by the gross area, soil grains and voids together. It is the speed the water would have if it filled the whole cross-section. Use it, or the flow rate, for volumes of flow.
* **Seepage velocity.** The average speed of the water in the pores. The same flow squeezes through only the pore space, so the water moves faster than the discharge velocity. Use it for how fast water, and anything dissolved in it, actually travels.
* **Effective porosity.** Not all pores carry flow. Dead-end pores and voids packed with fines hold water that is nearly still. The effective porosity is the fraction of the cross-section that actually carries flow. In sand and gravel it is close to the total porosity. In clay it can be far smaller, as low as 0.01 against a total porosity of 0.40 to 0.70. Measured values for clays vary a great deal, so use a site value when travel time matters.
* **Travel time.** The distance along the flow path divided by the seepage velocity. The path follows a flow line, crossing the head contours at right angles. If the gradient changes along the path (it increases near a well), add up the times for pieces where it is about constant.
* **Travel time mistake.** Using the discharge velocity overestimates the travel time by a factor of one over the effective porosity. You would think a contaminant arrives later than it really does, which is the unsafe direction. Dispersion also brings the first arrivals somewhat sooner than the average.
* **When Darcy's law holds.** It assumes laminar flow in the pores, so that the head loss is proportional to the velocity. A Reynolds number for the pores checks this; Darcy's law holds below about 1 to 10. That covers nearly all seepage through soils. It may fail at high velocities in clean coarse gravel and rockfill, and close to a pumping well.
* **Layered soils.** Most deposits are layered, and the layers' $k$ values can differ by orders of magnitude. An equivalent $k$ lets you treat the stack as one soil, but its value depends on the direction of flow.
* **Flow along the layers.** Every layer has the same gradient, and the flows add. The equivalent $k$ is a thickness-weighted average, and the flow goes mostly through the most permeable layers: a thin gravel layer can carry most of the water.
* **Flow across the layers.** The same flow passes through every layer, and the head losses add. The equivalent $k$ is a harmonic average, controlled by the least permeable layer, and the head loss concentrates there: a thin clay layer can take nearly all of the head. The pore pressure also changes most steeply across the low-$k$ layer.
* **Why layered soil is anisotropic.** The equivalent $k$ along the layers is always at least as large as the one across them. That is one reason a layered soil conducts water better horizontally than vertically.

### 3. Governing Equations

* **Darcy's law in 2D.** In a cross-section, the velocity has an $x$ (horizontal) and a $y$ (vertical) component. In an isotropic soil, $k$ is the same in every direction, and each component comes from the gradient in its own direction.
* **Anisotropy.** In an anisotropic soil, $k$ depends on direction. Soil is deposited in layers, and water moves more easily along the bedding than across it. The directions of largest and smallest $k$ are the principal axes, at right angles to each other.
* **Tilted principal axes.** When the bedding is tilted from $x$ and $y$, the velocity in $x$ depends on the gradient in both $x$ and $y$, and so does the velocity in $y$. The matrix that relates velocity to gradient is the conductivity tensor. Its cross terms vanish when the principal axes line up with $x$ and $y$.
* **In practice.** In most deposits the horizontal conductivity is larger than the vertical one, because the soil was laid down in layers.
* **Where the governing equation comes from.** A mass balance on a small box of soil, with Darcy's law for the velocities. The assumptions: the soil is saturated, Darcy's law is valid, mass is conserved, and the water's density is constant.
* **Conservation of mass.** The water that flows into a piece of soil, minus the water that flows out, plus what any source adds or minus what any sink removes, equals the change in the water stored there. For steady flow with no sources or sinks, whatever flows into a piece of soil flows out of it.
* **What the equation gives.** For steady, saturated flow the result is one equation in the head. In a uniform, isotropic soil it is the Laplace equation. Its solution is the head everywhere in the section. Velocities, pore pressures, and flow rates all follow from the head.
* **Three ways to solve it.** Flow nets (graphical), analytical solutions (formulas for simple geometry), and numerical solutions. Finite differences use a regular grid. Finite elements can follow any boundary and can be made small where the head changes quickly. XSLOPE uses finite elements.
* **Boundary conditions.** Every method needs a condition on every part of the boundary. Without them there is no unique answer.
* **Known (specified) head.** Where the ground is under a reservoir, the sea, a ditch, or a pumped-down excavation, the head is the water level above it.
* **No flow.** No water crosses an impervious base, a sheet pile, or a line of symmetry. For example, midway between two identical drains, the water on each side goes to its own drain, so none crosses the midline. The far sides of a model are often no-flow, placed far enough away that they don't affect the flow near the structure.
* **Exit face.** A slope where water may seep out, such as the downstream face of a dam. It is also called a seepage face. Where water comes out, the pressure is zero, so the head equals the elevation. Where on the face it comes out is not known ahead of time; the solution finds it.
* **Known (specified) flux.** A known rate of water crossing the boundary, such as rain recharging the ground.
* **The free surface is not a boundary condition.** In unconfined flow, the top of the saturated zone (the phreatic surface) is part of the answer: the line where the pressure is zero. You do not specify it.
* **Reading a solution.** Head contours crowd together where the head falls quickly. In a uniform soil, such as around the tip of a sheet pile, that means a high gradient and fast flow. Across a low-$k$ zone, such as a clay core, it means the zone takes most of the head loss, not that much water flows there.

### 4. Flow Nets

* **What a flow net is.** A graphical solution of the Laplace equation: two-dimensional, steady, saturated flow in an isotropic soil. It is made of flow lines, the paths the water follows, and equipotential lines, lines of constant total head.
* **Equipotential lines.** Two piezometers with their tips on the same equipotential line show the same water level, even if the tips are at different depths.
* **Boundaries in the net.** A ground surface under water is an equipotential line: its head is the water level above it. An impervious base and the buried face of a sheet pile are flow lines: water moves along them, not across them.
* **Rule 1: right angles.** In an isotropic soil, water flows in the direction of the steepest drop in total head, which is perpendicular to the lines of constant head. So flow lines and equipotential lines cross at right angles.
* **Rule 2: one cell shape.** No water crosses a flow line, so each flow channel carries the same flow through every cell along it. If every cell has the same length-to-width ratio, every channel carries the same flow and every equipotential drop is the same head loss. Squares (curvilinear squares) are easiest; a circle drawn in a square cell touches all four sides.
* **Partial channels and drops.** A net rarely comes out even. Count a partial drop or channel as a fraction.
* **Corners.** Where boundaries meet at an angle other than 90°, the corner cell cannot be square. Check it by subdividing: you should get three squares and one cell the same shape as the original.
* **Unconfined flow.** In flow through an earth dam, the top of the saturated zone is not known in advance. It is called the line of seepage, the free surface, or the phreatic surface.
* **The line of seepage is two things.** It is a flow line, because no water crosses it. It is also a line of zero pressure, so on it the total head equals the elevation. Since each drop is the same head loss, the equipotential lines meet it at equal steps of elevation. It leaves the upstream face at right angles, because that face is an equipotential line.
* **Reading heads and pressures.** Each equipotential drop is the total head lost divided by the number of drops. Count drops from the upstream side to get the total head at a point, subtract the point's elevation to get the pressure head, and multiply by the unit weight of water to get the pore pressure.
* **Reading gradients.** Every cell has the same head drop, so where the cells are small, the gradient and the velocity are high. Small cells mark the places to worry about, such as the tip of a sheet pile.
* **Flow rate.** The flow depends only on $k$, the total head lost, and the shape factor: the number of flow channels over the number of drops. The geometry enters only through the shape of the net. A longer flow path, with more drops for the same channels, means less flow.
* **Flow per unit length.** A flow from a 2D section is per unit length of the structure, for example per foot of wall. Multiply by the length for the total.
* **Anisotropic soils.** The Laplace equation holds only for isotropic soil. In an anisotropic soil drawn at true scale, flow lines and equipotential lines do not cross at right angles.
* **Transformed section.** Rescale the horizontal distances so the soil behaves as if it were isotropic (when $k_x$ is larger than $k_y$, the section gets narrower), draw a net with square cells, and stretch it back. The numbers of channels and drops don't change. The flow rate uses the geometric mean of $k_x$ and $k_y$.
* **Common mistakes.** Cells that are not square, lines that don't cross at right angles, forgetting that the line of seepage has zero pressure, and using $k_x$ or $k_y$ alone for an anisotropic soil.

### 5. Analytical Solutions

* **2D profile model.** A vertical cross section through the problem: an embankment, a pair of sheet piles around an excavation, or a cut through a valley. It works when the flow is mainly in that vertical plane, with little flow at right angles to it.
* **Why analytical solutions.** For simple geometry, the governing equation can be solved as a formula. That gives quick estimates and shows what controls the answer.
* **Dupuit assumption 1.** The exit point is at the tailwater. In reality, the line of seepage comes out on the downstream face above the tailwater, and the water runs down the face below the exit point.
* **Dupuit assumption 2.** The gradient is the same all the way down a vertical line, so the flow is horizontal. This is good when the flow is mainly horizontal.
* **Dupuit assumption 3.** The gradient equals the slope of the free surface. The water really flows along the surface, so the true gradient is the sine of the slope angle, and Dupuit uses the tangent. Up to about 10° they differ by less than 2%; at 30° by 15%; at 50° by more than 50%. Most free surfaces are gentle, so it usually works.
* **When Dupuit fails.** Where the free surface is steep, such as close to a drain or a well. Even there, the Dupuit flow rate can still be right while the shape of the free surface is wrong: this is true near a drain and for the unconfined well equation.
* **Dupuit–Forchheimer equation.** With these assumptions, continuity in a vertical strip of soil says the square of the saturated thickness varies linearly with distance.
* **Rectangular section.** Between two water levels on an impervious base, the free surface is a parabola that gets steeper downstream. The same flow has to pass through a thinner saturated thickness, so the gradient increases. The flow depends on the difference between the squares of the two water depths, not just the difference in levels.
* **With infiltration.** Rain adds water along the way, so the flow changes along the section instead of staying constant. Evaporation does the reverse.
* **Confined layer.** In a layer of constant thickness between two confining layers, the flow area does not change, the head drops in a straight line, and the flow is proportional to the head difference.
* **Using it in practice.** Rectangular-section solutions estimate flow from a line source (a river, stream, or pond) to a line sink (a drain, trench, or excavation). They are screening estimates. A short drain also collects water around its ends and from the landward side, so the real flow is larger than the 2D answer. Check a design with a numerical model.
* **Earth dam.** In Casagrande's solution, the line of seepage is a parabola that starts a little upstream of where the reservoir meets the upstream face (0.3 times the horizontal length of the wetted face), corrected to leave the face at right angles. It comes out on the downstream face some distance up from the toe.
* **How the dam solution works.** First find, from the geometry, how far up the downstream face the water exits. Then compute the flow through the vertical section under the exit point, with the gradient equal to the slope of the free surface there, which is the slope of the downstream face. The assumptions: the Dupuit assumptions, Darcy's law, a parabolic line of seepage, and an impervious base.

### 6. Well Equations

* **Wells are radial flow.** The well equations are not a cross-section. Water flows toward the well from every side, in plan, and the equations follow it along the radius.
* **Confined aquifer.** A permeable layer between an impermeable base and a confining layer above it, the aquitard. It stays full as the head drops, so the flow area does not change.
* **Cone of depression.** Pumping lowers the piezometric surface (the level water would rise to in wells in a confined aquifer), or the water table, into a cone around the well. The drawdown is how far the head has fallen from its starting level.
* **Thiem assumptions.** A homogeneous aquifer of constant thickness and infinite extent, an impermeable aquitard, a well that fully penetrates the aquifer, a horizontal initial water level and layer boundaries, no head loss at the well, and steady flow.
* **Why the cone is steep near the well.** Water flows radially inward through cylinders that get smaller toward the well. The same flow through less area needs a larger gradient. In a confined aquifer, the head plotted against the log of distance is a straight line, which is why pumping tests are plotted on semi-log paper. In an unconfined aquifer it is $h^2$ that plots as a straight line.
* **Radius of influence, $R$.** The distance at which the drawdown dies out. It enters the equations only through a logarithm, so the answer is not very sensitive to it. A rough estimate from a formula such as Sichardt's is good enough.
* **Transmissivity.** $k$ times the aquifer thickness: how much water the full thickness of the aquifer can carry.
* **Steady pumping tests.** Pump at a known rate, measure the drawdown, and back-calculate $k$. The limits: the method works well only in high-$k$ soils, it gives an average horizontal $k$ over a large region, it is hard to tell when steady state has been reached, and flow unrelated to the well (a sloping water table) can confuse it. Observation wells remove the need to know $R$.
* **Superposition, confined.** The confined equation is linear in the head, so the drawdowns from several wells add. Between the wells the cones overlap, and the drawdown is deeper than either well makes alone. That is how a ring of dewatering wells lowers the water across a site.
* **Unconfined aquifer.** The water table itself is drawn down. The saturated thickness shrinks near the well, so the flow area shrinks too, and the flow has a vertical component.
* **Unconfined well equation.** Built on the Dupuit assumptions, it gives the correct flow rate, but the shape of the water table near the well is wrong.
* **Superposition, unconfined.** The governing equation is linear in the square of the saturated thickness, so it is $H^2 - h^2$ that adds, not the drawdown. Adding drawdowns leaves the water table too high, most of all between the wells, where the saturated thickness is smallest.
* **Superposition in time.** A change in a well's pumping rate acts like a new well at the same spot, pumping the change from that time on. When a pump stops, add a well pumping $-q$ from that time, and the water level recovers.
* **Where the water comes from at first.** When the pump starts, the water comes out of storage around the well, and the cone grows. If it reaches a boundary that supplies water, such as a river or lake, it stops growing and the flow becomes steady.
* **Storativity (confined).** When the head drops, the soil compresses slightly and the water expands slightly, releasing a little water. Per unit area per unit drop in head, that is the storativity. It is tiny (about $10^{-5}$ to $10^{-3}$) and larger for a thicker aquifer.
* **Specific yield (unconfined).** When the water table drops, the pores near it drain by gravity. Per unit area per unit drop, that is the specific yield, about 0.1 to 0.3. It is less than the porosity because the soil holds some water against gravity. It is far larger than storativity, so an unconfined aquifer gives up much more water for the same drop, and its cone spreads much more slowly.
* **Theis solution.** Transient drawdown in an infinite confined aquifer pumped at a constant rate. It has no $R$: with no boundary to supply water, the cone keeps growing. The drawdown depends on distance and time together, through $r^2/t$.
* **Cooper–Jacob.** Late in the test, or close to the well, the Theis solution becomes the Thiem equation with an $R$ that grows with the square root of time. So the $R$ in a steady equation really stands for a pumping time.
* **Unconfined transient flow.** The same solution works in the $H^2 - h^2$ form with the specific yield, as long as the drawdown is small compared with the aquifer thickness. With a large specific yield, the cone can take years to spread far.
* **Transient pumping tests.** Plot drawdown against the log of time. The later points fall on a straight line; its slope gives the transmissivity and its intercept gives the storage, with no wait for steady state. The earliest points fall below the line, so fit the later ones.
* **Delayed yield.** In an unconfined test, the aquifer first releases water elastically, as a confined one does, and the pores drain later. Fit the late points, or the specific yield comes out far too small.

### 7. Construction Dewatering

* **Goal.** Lower the water so an excavation can be built in the dry.
* **Wellpoints.** Closely spaced small wells on a header pipe, pumped by suction and usually jetted into place. Suction limits the lift to about 5 to 6 m (15 to 20 ft) below the header, so a deeper excavation needs a second stage of wellpoints on a bench. They suit sands and silty sands.
* **Deep wells.** Larger wells, each with a submersible pump that pushes the water up, so there is no suction limit. Fewer wells, farther apart, for deeper drawdowns and more permeable soils.
* **Sumps and ditches.** Pumping from the floor of the excavation. This works for shallow drawdowns in gravel, rock, or stiff clay, but in sands it can wash out fines and loosen the bottom.
* **French drains and trenches.** Gravel-filled trenches that drain by gravity to a sump. They work along a line, for example to cut off water coming from a river. A bio-polymer slurry trench builds a deeper drain without an open trench: the slurry holds the trench open and then biodegrades.
* **Slurry cutoff wall.** A trench around the site filled with a very low-$k$ soil-bentonite mix and keyed into the low-$k$ layer below the aquifer. It cuts off inflow from outside, so the wells inside pump only the stored water and the leakage through the wall.
* **Why use a wall.** When wells alone would pump too much (very permeable ground, or a river or lake nearby). When drawdown outside would settle neighboring buildings or dry up neighbors' wells. When the discharge is hard to get rid of or must be treated. The wall costs money; it buys smaller pumps, fewer wells, far less water, and little drawdown outside. Defects and a poor key leak more than an intact wall, so allow a margin.
* **Choosing a method.** The soil's permeability, the drawdown needed, and how long the system must run decide it.
* **Design questions.** What pumping rate? How many wells, and where? Would a drain or trench be better? Analytical solutions are often used; numerical models such as MODFLOW give more accuracy.
* **Heads from the low-$k$ layer.** The well equations measure heads up from the bottom of the aquifer. The goal is water at or below the required level everywhere inside the excavation by the deadline.
* **The deadline drives the design.** It is a transient problem. Each well follows the Theis solution in the $H^2 - h^2$ form, and $H^2 - h^2$ adds over all the wells and over every change in the pumping rate. The middle of the excavation, farthest from the wells, comes down last.
* **$Q_{min}$.** The smallest total pumping rate that gets the water down everywhere in the excavation by the deadline. Pump less, and the middle is still too high on the deadline.
* **A well can go dry.** The more a well pumps, the deeper its cone. Pump too much, and the water at the well reaches the bottom of the aquifer: there is no saturated thickness left to carry more flow. A bigger pump does not help; it only pumps the well dry.
* **Pumping schedule.** As the cones spread, each well can take less, so the rate is cut back over time to keep every well from going dry. Once the excavation is dewatered, the rate drops to a much lower holding rate. Size the pumps for $Q_{min}$, and plan the discharge for the holding rate.
* **Shorter or longer deadline.** A shorter deadline needs a higher rate but pumps less water in total. With a long deadline, the cone spreads far out, and the wells drain a much larger area to get the same drawdown under the excavation. Each set of wells has a fastest possible time; no rate can beat it.
* **Number of wells.** The deadline sets the fewest wells that can work. Beyond that, more wells shorten the fastest possible time and add a margin, but they barely change the total rate: the rate is set by the water that has to come out.
* **Layout.** Moving wells to where the water comes down last, such as the middle of the long sides, saves only a few percent of the pumping. The deadline, the number of wells, and $k$ matter far more.
* **Sensitivity to $k$.** $Q_{min}$ is highly sensitive to $k$. A $k$ well above the estimate takes much more pumping. A lower $k$ is the dangerous mistake: the ground can't feed the wells fast enough, they go dry, and no rate meets the deadline. The fix is more wells, which is hard once the job has started. Get $k$ from a pumping test and run the design over a range around it: pump capacity for the high end, enough wells for the low end.
* **Anisotropic soil.** In layered deposits the horizontal $k$ is several to many times the vertical $k$. The heads at the well screens fall fast, but the water stored near the water table has to drain down across the layers, so the water table lags. The well equations ignore vertical flow, so estimate the time the water table takes to drain down. A short deadline compared with that drainage time takes more pumping, so add a margin to the pump capacity.
* **Modeling a cutoff wall.** Leakage through the wall is like flow to a trench, using the wall's $k$ and thickness. The well equations assume no boundaries, and the wall is one, so a design with a wall needs a numerical solution, with the wall as a band of low $k$.
* **Analytical or numerical model.** A full numerical model is worth it when the layering or far boundaries (rivers, lakes, recharge) matter. Otherwise the answer is so sensitive to $k$ that the extra effort may not buy much, and a preliminary design is usually enough, because pumps are oversized and the rate is adjusted on site. Check any numerical model against a case you can solve by hand.

### 8. The Finite Element Method

* **The idea.** Divide the section into small elements joined at nodes. The unknowns are the heads at the nodes. The answer is approximate; smaller elements give a closer answer.
* **Why finite elements.** Elements can follow any boundary and any number of soil zones, and they can be made small where the head changes quickly. The price is complexity and computing, which is why a program does it.
* **Three steps.** Inside each element, the head varies simply between its nodal heads. Darcy's law turns that head into flows at the element's nodes. At each node, the flows from the elements around it must balance: they add to zero, or to a known flow at a boundary. That gives one equation per node, together a matrix equation for the heads.
* **1D element.** A tube of soil between two nodes. Its flow is its conductance ($k$ times the area, over the length) times the head difference. What enters at one end leaves at the other.
* **Elements in series.** The same flow passes through every element, so the largest head drop is across the element with the smallest conductance. It is the same idea as flow across soil layers.
* **Assembly.** Each element's small matrix is added into the global matrix at the rows and columns of its nodes. Where elements share a node, their entries add.
* **The global matrix.** It has one row per node. It is symmetric, and with sensible node numbering it is banded, because each node is linked only to its neighbors. That makes it easy to store and solve, which is what makes meshes with tens of thousands of nodes practical.
* **Boundary conditions in the matrix.** A specified head replaces its node's row. A specified flow, such as a well or recharge, goes into the flow vector. A boundary node with nothing specified has zero flow, so it is automatically a no-flow boundary. A forgotten boundary condition is silently a no-flow boundary.
* **After solving.** Once the heads are known, the flows at the specified-head nodes come from the node equations, and the velocity in each element comes from its gradient.
* **Zones and elements.** Each element belongs to one soil zone with its own $k$, so zone boundaries must follow element edges. The mesh generator fits the elements to the zones.
* **Element types.** Linear triangles (3 nodes), quadratic triangles (6), linear quadrilaterals (4), and quadratic quadrilaterals (8 and 9). In a linear triangle the head is a flat plane, so the gradient and velocity are constant over the element. Quadratic elements let the head curve inside an element, so they are more accurate for the same number of nodes. Triangles mesh any shape more flexibly; quadrilaterals often give faster, more accurate solutions.
* **Element matrix.** For any element, it depends on the element's geometry and its conductivity. For the linear triangle it comes from three steps: heads to gradient, gradient to velocity (Darcy's law), and velocity to flows at the nodes.
* **Sheet piles in a mesh.** The pile is a thin slot. The elements on its two sides do not share nodes, so water has to go around the tip.
* **Where the errors are largest.** Where the gradient is highest: at the tips of sheet piles and cutoffs, at corners, drains, and exit points, and at boundaries between soils of very different $k$.
* **Refine locally.** For flow under a sheet pile, a coarse mesh refined at the pile tip can be more accurate than a uniformly fine mesh with more than twice as many nodes. On a uniform mesh, quadratic elements beat linear ones; once the tip is refined they are about the same, because the error comes from the tip.
* **Good mesh practice.** Use small elements where the head changes quickly, let the element size change gradually rather than in jumps, and keep elements well shaped, without long thin slivers.
* **Is the mesh fine enough?** Refine it and solve again. If the answer you care about (a flow rate, an exit gradient, a pore pressure) stops changing, the mesh is fine enough.

### 9. Seepage Analysis in XSLOPE

* **Why XSLOPE does seepage.** Slope stability needs pore pressures. The seepage analysis computes them on the same model, and they go straight into a stability analysis later in the course.
* **What it gives.** Total head, pore pressure, velocity, gradient, total flow, and the flow net.
* **Meshing.** XSLOPE meshes the soil zones automatically, using the element type and target size you choose. Linear triangles are adequate for seepage alone. A finite element stability analysis needs quadratic elements. The mesh can be made finer near features where the head changes quickly, such as pile tips, corners, and thin zones.
* **Steady or transient.** Steady: the heads do not change with time, and there is one solution. Transient: the heads change with time, the model needs storage properties, the boundary values can change with time, and there is a solution at each time.
* **Confined or unconfined.** Confined: the soil is saturated everywhere and the boundaries are known, so one solve gives the heads. Unconfined: the location of the phreatic surface is part of the answer, so XSLOPE iterates. A model with an exit face is treated as unconfined. Here "confined" means no phreatic surface; it is not the same as a confined aquifer in the well equations.
* **Conductivity input.** $k_1$ (the larger), $k_2$ (the smaller, at right angles), and the angle of $k_1$ counterclockwise from $x$. Isotropic: $k_1 = k_2$. Horizontal layering: $k_1$ horizontal, $k_2$ vertical, and an angle of 0.
* **Unsaturated soil.** Above the phreatic surface, the pores hold air and water, the pressure is negative, and water still moves, but less easily. XSLOPE multiplies the saturated $k$ by a relative conductivity between 0 and 1 that depends on the pressure head (head minus elevation).
* **Does the unsaturated model matter?** XSLOPE has several models for the relative conductivity, used only in unconfined problems. For stability, the choice hardly matters. On a zoned dam, the models gave the same phreatic surface to within half a foot; the total flow differed by about 5%. If you need the flow through a dam with a lot of unsaturated soil, the choice deserves more thought.
* **Boundary condition types.** Specified head: the head held along a line (a pool, the tailwater). Specified flux: a rate of water across the boundary (rain, drains). Exit face: a slope where water may leave; it takes no value, because where the water leaves is part of the answer. No flow: everything not specified (rock, the ends of the section, a sheet pile). A fifth type, the reservoir boundary, is for a moving pool in a transient analysis.
* **No-flow is invisible.** You never enter a no-flow boundary, so the only way to check it is to see where the boundary markers stop on the mesh.
* **How an unconfined problem is solved.** Solve with the saturated $k$ everywhere. Compute the pressure head at every point. Where it is negative, reduce $k$ by the relative conductivity. Solve again, and repeat until the heads stop changing. The phreatic surface is the line of zero pressure head.
* **How the exit face is handled.** Mark the whole slope as exit face. As it iterates, XSLOPE sorts the exit face nodes into wet nodes, where water leaves and the head equals the elevation, and dry nodes, where nothing crosses. It stops when that set stops changing.
* **Sheet piles and blankets.** A sheet pile is modeled as a thin crack in the geometry, so the water has to go around its tip. An impervious clay blanket on the ground upstream of a pile is a no-flow boundary that lengthens the flow path.
* **Checking a confined solution.** With no sources inside, every computed head must lie between the highest and lowest specified heads. A head outside that range means a mistake in the model.
* **Gradient and piping.** The gradient shows where the head falls fastest. Where water comes out of the ground at a gradient near the critical value, about 1, it can start carrying soil with it.
* **Singular points.** The gradient is largest at sharp points of the boundary, such as the tip of a sheet pile and the upstream edge of an impervious blanket. At those points the exact gradient is infinite, so a finer mesh just reports a higher number. Read a design gradient a short distance away. A gradient near zero at the ends of the model says the model is wide enough.
* **Zoned earth dam.** With a clay core far less permeable than the shell and the foundation, almost the whole head drop happens across the core, the phreatic surface falls steeply through it, and most of the flow goes under the dam through the foundation.
* **Pore pressure.** Positive below the phreatic surface and negative (suction) above it. The stability analysis uses the positive pressures and ignores suction unless you ask for it. So the pressures that matter are set by the saturated conductivities and the boundary conditions.
* **Flow nets on zoned sections.** Square cells need a single $k$: the base material's. Choose the zone the water mostly flows through. The wrong choice gives less than one flow channel, or hundreds. The flow net is drawn from the computed flow, so it is a way to read the solution, not a check on it.

### 10. Transient Seepage

* **Why transient.** Many problems are governed by conditions that are still changing: a reservoir drawn down over weeks, a storm, a river in flood. The pore pressures that matter depend on when you look.
* **What it adds.** Storage properties for each material (specific storage and specific yield), a schedule of boundary values over time, a run duration and the times to save, and a starting state. The result is a series of saved solutions called frames.
* **The equation.** The steady equation plus a storage term: the flow into a piece of soil minus the flow out equals the rate at which water is stored there (negative when the soil releases water). With no storage, it is the steady equation.
* **Time stepping.** The solution steps through time. Each step is a finite element solve that starts from the heads at the end of the step before. Steps are short while the heads change fast and long when they barely move.
* **Specific storage.** The water released by a unit volume of saturated soil when the head drops by one, from compressing the soil and expanding the water. It acts below the phreatic surface. Its units are 1/length.
* **Specific yield.** The water drained from the pores as the phreatic surface falls through them, per unit area per unit drop. It acts only in the band the phreatic surface is crossing. It is much the larger effect.
* **Opposite trends.** A soft clay is the most compressible soil, so it has the largest specific storage, but it holds its water against gravity, so it has the smallest specific yield. A clean gravel is the reverse.
* **How fast a zone drains.** About the vertical $k$ over the specific yield: the conductivity that moves the water, over the volume that has to move. Compare it with how fast the boundary moves. If the pool falls faster than a zone can drain, that zone lags behind and holds water.
* **Starting state.** A transient run starts from a steady solution with every boundary at its value at time zero; that is the first frame. Holding the boundary at its starting value for a short time lets you check that the next frame matches. Solve the model as steady first: it checks the model, and it is the reference for everything after.
* **Saved frames.** The run takes many steps but keeps only the saved times. A time you did not save needs a new run. Never interpolate between two frames: a blend of two solutions is not a solution of anything.
* **Specified head or reservoir boundary.** Both hold submerged nodes at the pool level. A specified head boundary holds every node at its value all the time, even nodes above a falling pool, which pulls water out of the face as a suction: wrong for a pool face, right for a drain. A reservoir boundary holds submerged nodes at the current level, makes uncovered nodes an exit face, and keeps nodes the water hasn't reached yet as no-flow.
* **What happens in a drawdown.** The phreatic surface in the dam lags behind the pool. It leaves the upstream face above the pool, and the still-saturated soil seeps back out into the reservoir. The exit point moves down the face with the pool. That lag is the water pressure a steady analysis at the low pool would miss.
* **A dam with a clay core.** In the shell, the phreatic surface follows the pool down a few meters behind it. In the core it barely moves while the pool falls, and the core then drains over months.
* **Reading frames.** Each frame reports inflow and outflow separately, because water comes out of storage. During a drawdown the inflow can drop to zero and the outflow can be many times the steady flow, all of it from storage. Transient frames have no flow lines: a flow net needs the inflow to equal the outflow for every piece of soil, which is not true while storage is changing. Use velocity vectors instead.
* **Head histories and water budget.** Following a few points through the frames shows the lag: a point in the shell falls with the pool, while a point in the core falls much less and later. The run's water budget, the water that left against the water released from storage, is its own check.

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
