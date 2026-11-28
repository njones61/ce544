# Slope Stability: Study Guide

The equation sheet is provided on the exam, so this guide does not ask you to memorize equations. It is about why slopes fail, what each method assumes, which strengths and pore pressures go into an analysis, what controls the answer, and how to read and check a result.

## Outline of Main Concepts

### 1. Causes of Slope Failure and Shear Strength

* **The stability requirement.** A slope fails when the shear stress driving failure exceeds the shear strength along some surface.
    * It gets there because the strength falls, the stress rises, or both.
    * This course analyzes slides: a mass of soil moving on a surface of rupture.
* **Two lists of causes.** Water is in both, and most failures involve water and clayey soils.
    * **Strength decreases:** rising pore pressure (the most common), cracks, swelling, strain softening, creep, and leached quick clay.
    * **Stress increases:** loads at the crest, water in a crack, a cut or erosion at the toe, a quick drop in the pool, and shaking.
* **Case histories.** Most failures have more than one cause.
    * Thistle: groundwater rose in an old slide already at residual strength.
    * Rissa: a small fill on the shore set off a slide in quick clay that grew back from the lake.
    * Lower San Fernando Dam: shaking liquefied loose hydraulic fill.
* **Effective stress.** Strength depends on total stress minus pore pressure. Raise $u$, and the strength falls.
* **Drained or undrained.** Compare how fast the soil drains with how fast it is loaded.
    * Sands drain in minutes; clays take years, so clays are undrained in the short term.
    * Undrained, the water takes the added load: effective stress and strength don't change until it drains.
* **Triaxial tests.**
    * **CD:** drained; gives $c'$ and $\phi'$ directly, but slowly in clay.
    * **CU with $u$ measured:** both envelopes, faster. NC clay: $u$ rises, undrained below drained. OC clay: $u$ falls, undrained above drained.
    * **UU:** every circle the same size, $\phi = 0$; gives $s_u$, the strength in the ground before it drains.
* **Strength details.**
    * $c'$ is a fitted intercept: fit it over the stresses in your slope.
    * In NC clay, $s_u$ grows with depth: a value at the top plus a rate, not one average.
    * Large displacement drops OC clay to its residual strength, often half the peak or less.
* **Which strength to use.**
    * Embankment on soft clay: safer as the clay drains, so the end of construction governs (undrained).
    * Excavation in clay: $u$ drops, then recovers, so the long term governs (drained).
    * Four conditions: end of construction, long term, rapid drawdown, and earthquake. Each sets each soil's strength and its pore pressures.

### 2. Limit Equilibrium, Part 1

* **The procedure.** Choose a surface, find the shear stress needed to hold the soil above it, compare it with the strength, and repeat. The lowest $F$ marks the critical surface.
* **Factor of safety.** Strength over the shear stress needed for equilibrium.
    * The same $F$ divides both $c$ and $\tan\phi$ everywhere on the surface: the developed strength.
    * $F = 1.5$ means the slope is using two thirds of its strength.
* **Indeterminate.** The unknowns (normal forces, side forces, where they act, and $F$) outnumber the equations.
    * Every method assumes something about the side forces.
    * Complete-equilibrium methods satisfy all three equations.
* **Surface shapes:** planar (infinite slope), circular, noncircular along weak layers, and composite (a circle cut off by a hard layer).
* **Infinite slope.**
    * Sand: $F$ depends only on $\phi$ and the slope angle, not depth, so the shallowest surface governs.
    * A search in sand ends on a skin along the face: real raveling, not the deep slide. Set a minimum slip depth.
    * Sand with seepage parallel to the slope and water at the surface: $F$ is about half the dry value. Hence shallow slides in heavy rain.
    * Still water over the slope: buoyancy reduces the normal and driving forces alike, so the friction term is unchanged.
* **The φ = 0 circle.** Normal stresses point at the center and have no moment, so one moment equation gives $F$. Water against the face resists rotation.
* **Method of slices.** With friction, strength depends on the unknown normal stress, so cut the mass into slices.
    * **OMS:** side forces ignored; no iteration; moment equilibrium only. With high pore pressures, effective normal forces come out too small or negative, so $F$ is too low.
    * **Bishop's simplified:** side forces horizontal; $N$ from vertical equilibrium; iterate. Close to the complete methods on circles.
    * With $\phi = 0$ on a circle, OMS, Bishop, and the φ = 0 circle give the same $F$.

### 3. Limit Equilibrium, Part 2

* **Simplified Janbu.** No interslice shear. $N$ from vertical equilibrium, $F$ from horizontal equilibrium of the whole mass, so any surface shape works.
    * No moment equilibrium; $F$ runs low, so a correction factor raises it, more for deep surfaces and cohesive soils.
* **Force equilibrium procedures** (Corps of Engineers, Lowe and Karafiath).
    * Assume the side force angle on every boundary, then march slice by slice from the toe; the right $F$ leaves no force out of the last slice.
    * The answer depends on the assumed angles. The Corps' usually gives the highest $F$ of the seven methods.
    * They can be far too high on a φ = 0 surface with a large vertical load, such as a submerged slope.
* **Spencer's method.** Side forces all parallel at one unknown angle; solve $F$ and the angle together. Satisfies complete equilibrium, on any surface.
    * The $F$ from moment equilibrium barely changes with the angle; the $F$ from force equilibrium changes a lot.
    * So Bishop lands near Spencer, while force methods depend on their assumed angle.
* **Line of thrust.** Where the side forces act. It should stay inside the mass; near a cohesive crest it often drops out, a sign of tension. A warning flags it; it doesn't change $F$.
* **Morgenstern–Price.** The side force angle varies along the surface by an assumed function. A constant function is Spencer's method, and $F$ hardly depends on the function chosen.
* **Comparison.** OMS and Bishop need circles; all but OMS iterate.
    * On circles, Spencer, Morgenstern–Price, and Bishop usually agree closely.
    * Force methods run high, and OMS low with high pore pressures.
* **Choosing.** Spencer for design. Bishop for comparison on a circle, force methods on a noncircular surface. OMS and simplified Janbu are mainly teaching tools.

### 4. Limit Equilibrium Analysis in XSLOPE

* **Materials.**
    * Total unit weights only ($\gamma$ above the water table, $\gamma_{sat}$ below). A buoyant weight takes the water off twice.
    * Drained: $c'$, $\phi'$, and a pore pressure source. Undrained: $s_u$ as $c$, $\phi = 0$, and no pore pressure.
    * Classic errors: a wet slope with no pore pressure ($F$ too high); an undrained strength that also reads the water (counted twice).
    * An elastic material can't fail, so the search stays out of it.
* **Water.** From a piezometric line, a seepage solution, or a ratio $r_u$; a line must run across the whole section.
    * A **piezometric** line assumes vertical equipotentials: conservative. A **phreatic** line assumes flow along it, giving less $u$ where it slopes.
    * Standing water is a load on the surface that pushes on the toe and raises $F$. Count it once.
* **Loads.** A weight (surcharge, fill, equipment) acts vertically. Entered normal to a slope face, it pushes into the hill and wrongly raises $F$.
* **Tension cracks.** Cohesion at the crest can put slice bases in tension, strength the soil doesn't have.
    * A crack removes it and lowers $F$; water in the crack lowers it more.
    * Add one when the field conditions call for it, not just to tidy a plot.
* **The search** refines the neighborhood it starts in.
    * Several starting circles help, but don't guarantee the global minimum. Search each mechanism, or grid search the whole model.
    * A circle can't follow a thin weak layer: run a noncircular search too.
    * Let a surface run along the base of the model only when the base is real, such as bedrock.
* **Reading and checking.**
    * Look at the search before the number: did it stop in the open, and is the surface a real mechanism?
    * Read the base stresses, the line of thrust, and the warnings. Give each method its own search.
    * Check with a hand calculation, a second method, or a chart. Back-analysis finds the strength that gives $F = 1$ for a slope that failed.

### 5. Soil Reinforcement

* **Why.** Soil carries little tension. Reinforcement crosses the slip surface and anchors in stable ground behind it.
* **Types.** Geogrids and geotextiles in fill, and steel strips in MSE walls.
    * Soil nails: grouted bars, loaded only as the soil moves.
    * Tiebacks: prestressed, with a bond length behind the slip surface.
* **How it fails:** rupture, pullout, or a surface that passes behind or under the reinforcement and gets no help from it.
* **Capacity.**
    * A geosynthetic loses strength to creep, installation damage, and degradation; the long-term strength is the test strength reduced for all three.
    * Pullout grows with buried length and overburden, so a layer can hold little near either end. The capacity at a point is the smallest of its strength and the pullout from each end.
* **In limit equilibrium,** a reinforcement force is known: one force where the surface crosses the layer, adding no unknowns.
* **Direction.** **Tangent** (along the slip surface) suits flexible sheets; **axial** (along the member) suits stiff bars.
    * In sand the choice hardly matters; in φ = 0 clay, tangent gives a higher $F$.
* **Divided by F or not.**
    * **Method A (Active):** allowable forces, not divided by $F$; the reinforcement reduces the driving force.
    * **Method B (Passive):** long-term capacities, divided by $F$ with the soil strength.
    * Match the values to the method. Unfactored values entered as Active put no factor of safety on the reinforcement.
* **Searching.** Start circles through the reinforced zone and behind or under it.
    * Layers too short let the critical surface go behind them; past some length, longer layers change nothing.

### 6. Piles and Walls

* **Stabilizing piles.** Rows of drilled shafts through the sliding mass into firm ground, close enough (about 2 to 4 diameters) for the soil to arch between them.
    * Best near the middle of the sliding mass. Bending governs, so a few large shafts beat many small ones.
    * A pile pushes back only as the slope moves.
* **In limit equilibrium,** a row is one known force, $H$, per unit width of slope where the surface crosses it.
    * **Entered $H$** (from a lateral load analysis or a wall's resistance): the same on every surface, so check that the critical surface is the one it was worked out for.
    * **Ito and Matsui:** the force of soil squeezing between the piles, recomputed on each surface from the strength, diameter, and spacing.
    * It assumes rigid vertical piles in level ground, spaced about 2 to 8 diameters apart.
    * The pile's shear and bending capacities cap it.
* **Look over and under the row.** A surface under the tips, or over the heads, gets nothing from the piles. Stronger piles can make a shallow surface over the heads critical.
* **Walls.**
    * Sheet pile walls are continuous; soldier pile walls are beams with lagging between them. Either can be tied back.
    * In limit equilibrium a wall is one force where the surface crosses it. It gives $F$, but no moment, shear, or deflection in the wall.
    * Behind a vertical wall the critical surface is close to a plane, so search noncircular wedges.
    * Each tieback's bond length must lie behind the critical surface.
* **Gravity and block walls** fail at their contacts: on the base, between courses, and at the backfill.
    * Limit equilibrium can't model that; the finite element method with joints can.

### 7. Seepage and Slope Stability

* **Why pore pressure governs.** Water carries part of the normal force on a slice base and adds nothing to friction. No method does better than the pore pressures it is given.
* **Flowing water changes $u$.**
    * Still water: hydrostatic below the water table.
    * Downward flow loses head: $u$ is lower, effective stress higher.
    * Upward flow: $u$ is higher, effective stress and strength lower. This is the case to watch.
* **Four ways to get $u$:** a flow net, a finite element seepage solution, a phreatic surface, or a piezometric line.
    * A seepage solution is the most accurate; XSLOPE reads it at the middle of each slice base.
    * Suction above the phreatic surface is set to zero for strength, because it can't be relied on.
* **When a line is good enough.** In a homogeneous slope with mostly horizontal flow, a line gives the same $F$ as the seepage solution.
* **When it isn't.** A dam on clay over a permeable sand: water passes under the dam in the sand and comes up through the clay at the toe.
    * The upward flow raises $u$ under the toe well above hydrostatic.
    * A line misses it and overstates $F$, on the unsafe side. Run the seepage analysis.

### 8. Rapid Drawdown

* **What happens.** The pool pushes on the face and buoys the slope.
    * Lower it quickly and that support goes, but low-permeability soil keeps its pore pressure.
    * The load rises, and the strength doesn't follow.
    * Under a full pool the driving weight is about half; a submerged slope is rarely critical.
    * A drained analysis at the low pool assumes the clay has already drained.
* **Which zones are undrained.** Compare drainage time with the drawdown time zone by zone: a sand shell can drain while a clay core can't.
* **Why undrained strengths.** Drawdown pore pressures include changes from shearing, which no seepage analysis gives. A measured undrained strength already includes them.
* **The three-stage method.** The full pool sets the strength; the lowered pool sets the load. All stages run on every trial surface.
    * **Stage 1:** an effective stress analysis at full pool, kept only for the stresses each slice consolidated under.
    * **Stage 2:** each low-permeability slice's undrained strength, from those stresses, then $F$ after drawdown, with drained strengths in free-draining zones.
    * **Stage 3:** where the drained strength after drawdown is lower, it replaces the undrained one. A dilating fill's negative pore pressure can't be counted on.
* **The stress ratio.** Soil already carrying shear builds less pore pressure on the way to failure, so it is stronger undrained.
    * The method interpolates between two envelopes, both from CU tests.
* **Typical pattern:** shallow parts of a surface governed by drained strength, deep parts by undrained.
* **Water before and after:** two piezometric lines, two steady seepage solutions, or two times in a transient run. A transient run can give a lower $F$ where a zone is still draining.
* **Checks.** Stage 1 must be stable. Dams that failed in drawdown come out near $F = 1$.

### 9. Seismic Slope Stability

* **Two effects:** shaking adds a driving force, and it can lower strength (pore pressure rise, liquefaction).
* **Which analysis.** Will the soils lose much strength?
    * Yes: the comprehensive (dynamic) approach, then stability after the earthquake with reduced strengths.
    * No: screen with a pseudostatic analysis. If $F$ meets the minimum, stop; if not, estimate displacement with Newmark's sliding block.
* **Pseudostatic analysis.** A static force, $k_h W$, at each slice's center of gravity.
    * It adds driving force. In the infinite slope and OMS, it also takes away normal force and friction.
    * It is held in one direction; real shaking lasts a moment and reverses. So $F < 1$ doesn't mean the slope fails.
* **Strengths are undrained:** shaking lasts seconds.
    * UU strengths for new slopes at the end of construction and for existing slopes.
    * New slopes in the long term: a two-stage analysis like rapid drawdown, or one stage with the R envelope, which needs the pore pressures from before the earthquake.
* **Screening.** A peak acceleration times a multiplier (often about 0.5) gives $k_h$.
    * Strength is reduced (often by 0.8), and $F$ must meet a minimum.
    * The values were set together for a tolerable displacement.
* **Newmark's sliding block.**
    * The yield coefficient $k_y$ is the $k_h$ that gives $F = 1$. Whenever shaking exceeds it, the block slips; the slips add up one way.
    * Displacement grows much faster than the shaking: double the record, and it grows many times over.
    * The surface with the lowest static $F$ need not have the lowest $k_y$, and in a dam a deep mass is shaken less.
    * Limits: a rigid block, and a strength that can't weaken during shaking.
* **After the earthquake.** Find which soils liquefy, reduce their strengths, and analyze with no seismic force. Some soils weaken further as they drain; use the lower of drained and undrained.

### 10. Reliability Analysis

* **What $F$ leaves out.** Every input is uncertain, so $F$ has a spread. Two slopes at the same $F$ can have very different odds of failure.
    * Required values of $F$ rise with the uncertainty and with the cost of a failure.
    * The LASH trench was cut at $F = 1.17$ with careful data, and failed.
* **Input uncertainty.** Standard deviation, and the coefficient of variation (COV), a dimensionless spread.
    * Unit weights are known well; undrained strength is the least certain.
    * From data, published COVs, or the highest and lowest conceivable values. People guess ranges too narrow, so divide by about 4 rather than 6.
* **From inputs to $F$.**
    * **Taylor series:** move each input one standard deviation up and down; the swings in $F$ give its spread and rank the inputs.
    * The Taylor series assumes $F$ changes linearly, and assumes a shape for its distribution.
    * **Monte Carlo:** draw inputs, solve, repeat thousands of times, and count failures. No assumed shape; rare failures need many runs.
    * **Response surface:** fit a formula to a few solves, check it, and sample the fit. For very small probabilities.
* **Reliability index, $\beta$:** how many standard deviations the most likely $F$ sits above 1. $P_f$ is the area of the distribution below $F = 1$; each step up in $\beta$ cuts it sharply.
* **What is acceptable.** No universal value. Conventional designs land near 1%. Weigh the probability against the cost of failure.
* **Practical points.**
    * The standard deviations move $P_f$ more than the choice of method.
    * Halving an input's uncertainty leaves $F$ unchanged but can cut $P_f$ sharply.
    * The surface with the lowest $F$ need not have the lowest $\beta$.

### 11. Finite Element Slope Stability

* **Strength reduction.** Divide $c$ and $\tan\phi$ of every soil by a trial $F$ until the slope can't stand. The surface is found, not chosen.
* **How the model fails.**
    * Each node moves; gravity loads the mesh; each soil needs $E$ and $\nu$. Soil reaching the envelope yields and passes its excess to its neighbors.
    * Yielding is not moving: the slope fails when yielded soil links into a path.
    * A trial stands if displacements level off and fails if they keep growing. Bisection narrows $F$ to a tolerance.
    * The band of shear strain is the slip surface.
* **Compared with limit equilibrium.** For most slopes $F$ is about the same. They differ when a search looks in the wrong place or can't follow the surface's shape, such as a thin weak layer.
    * Worth it when the mechanism is unknown, as a check, and when soil and structures act together. Limit equilibrium is enough for simple surfaces.
* **Building a model.**
    * Quadratic elements. Linear ones lock and can overstate $F$ badly with no warning.
    * A fine enough mesh, with several rows of elements across a thin layer.
    * Stiffness barely changes $F$, but displacements scale with $1/E$: with an assumed $E$, only their pattern means anything.
    * No tensile strength, and boundaries far enough away not to change $F$.
* **Structures in the mesh.** Limit equilibrium enters a structure as a force chosen beforehand; the finite element model computes it from the deformation.
    * **Bars** (reinforcement): tension only, with a stiffness. Gives the force along each layer; what a layer keeps after it ruptures can change $F$.
    * **Beams** (piles, walls): moment and shear along the member. How the ends are held matters.
    * **Joints** (block walls, liners, rock): slip at the contact's own $c$ and $\phi$, and open in tension.
* **Choosing.**
    * Reinforcement and continuous walls: about the same $F$; the model adds the forces.
    * A row of separate piles: take $F$ from limit equilibrium, because a 2D mesh has no gaps for soil to flow through.
    * Block and gravity walls, sheets the fill can slide along, and jointed rock (including toppling): use strength reduction.

---

## 20 True/False Questions

1. **True or False:** A slope that has stood for decades can fail with no change in its shape or loads. **True** *(A rise in pore pressure lowers the effective stress and the strength.)*
2. **True or False:** In an undrained (φ = 0) analysis of a clay, the pore pressure from the water table should also be subtracted. **False** *(The undrained strength already includes the pore pressure response; subtracting it counts it twice.)*
3. **True or False:** For an excavation in clay, the factor of safety is usually lowest right after the cut is finished. **False** *(Unloading drops the pore pressure, which recovers over years, so the long term is critical.)*
4. **True or False:** In a uniform slope of clean sand, a deep circle has a higher factor of safety than a thin surface along the face. **True** *(With no cohesion, the shallowest surface governs.)*
5. **True or False:** Bishop's simplified method does not satisfy horizontal force equilibrium. **True** *(It satisfies moment equilibrium and vertical force equilibrium only.)*
6. **True or False:** On a circle in a φ = 0 clay, OMS and Bishop's method give the same factor of safety. **True** *(Both reduce to the φ = 0 circle, because the normal forces no longer affect the strength.)*
7. **True or False:** Spencer's method can be used only on circular surfaces. **False** *(It satisfies complete equilibrium on any surface.)*
8. **True or False:** A warning about tension between slices changes the factor of safety XSLOPE reports. **False** *(A warning never changes F; it says the forces behind F are questionable.)*
9. **True or False:** Soil below the water table should be given its buoyant unit weight in XSLOPE. **False** *(Use total unit weights. The pore pressures already take the water off.)*
10. **True or False:** A surcharge on a slope face should be entered as a pressure normal to the face. **False** *(A weight acts vertically. Entered normal, it pushes into the hill and wrongly raises F.)*
11. **True or False:** Reinforcement entered as Active (Method A) should be given allowable capacities, with the reinforcement's own factor of safety already on them. **True**
12. **True or False:** A row of stabilizing piles adds strength to a slip surface that passes beneath the pile tips. **False** *(A surface that doesn't cross the piles gets nothing from them.)*
13. **True or False:** The Ito and Matsui pile force depends on how stiff the piles are. **False** *(It assumes rigid piles; it depends on the soil strength and the pile diameter and spacing.)*
14. **True or False:** Where water flows upward through clay at the toe of a dam, a piezometric line at the ground surface gives pore pressures that are too low. **True** *(Upward flow carries the pore pressure above hydrostatic.)*
15. **True or False:** The upstream slope of a dam is rarely critical while the pool is full. **True** *(The water buoys up the sliding mass and pushes on the face.)*
16. **True or False:** In the three-stage rapid drawdown method, the factor of safety from stage 1 is the rapid drawdown factor of safety. **False** *(Stage 1 is used only for the stresses the soil consolidated under at full pool.)*
17. **True or False:** A pseudostatic factor of safety below 1 means the slope will fail in the earthquake. **False** *(Real shaking lasts a moment and reverses; the slope may only move a limited distance.)*
18. **True or False:** Two slopes with the same factor of safety can have very different probabilities of failure. **True** *(F says nothing about how well the inputs are known.)*
19. **True or False:** In a strength reduction run with an assumed Young's modulus, the computed displacements are good predictions of how far the slope will move. **False** *(Displacements scale with 1/E. F is reliable, but only the pattern of movement means anything.)*
20. **True or False:** Using linear elements in a strength reduction analysis can overstate the factor of safety by a large amount, with nothing in the output to warn you. **True** *(Linear elements lock: they can't form the shear band.)*

---

## 30 Multiple Choice Questions

1. A new embankment is built quickly on a saturated soft clay. Right after construction, the clay's shear strength is:

    > A) Much higher, because the embankment raised the total stress<br>
    > B) About the same as before construction<br>
    > C) Zero, because the pore pressure equals the added load<br>
    > D) Lower, because the clay is now overconsolidated<br>
    > **Answer: B) About the same as before construction.** Undrained, the pore water takes the added load, so the effective stress, and the strength, don't change until the clay drains.

2. A road crosses an old landslide in clay that moved 30 years ago and is creeping again. Which strength belongs on the old slide surface?

    > A) The peak drained strength<br>
    > B) The undrained strength from UU tests<br>
    > C) The residual strength<br>
    > D) The peak undrained strength<br>
    > **Answer: C) The residual strength.** Large past movement has lined up the clay particles along the surface, leaving only the residual strength, often half the peak or less.

3. In a CU test on a heavily overconsolidated clay, the pore pressure during shearing:

    > A) Rises, so the undrained strength is below the drained strength<br>
    > B) Stays at zero<br>
    > C) Rises, so the undrained strength equals the drained strength<br>
    > D) Falls, so the undrained strength is above the drained strength<br>
    > **Answer: D) Falls, so the undrained strength is above the drained strength.** The clay tries to dilate. That is why an excavation in stiff clay is most critical in the long term.

4. A circular search on a 2:1 slope in clean sand ends on a very thin surface running along the face. What does this mean?

    > A) The surface is shallow raveling of the face; to find the deep slide, set a minimum slip depth<br>
    > B) The search failed and the answer should be ignored<br>
    > C) The slope will fail as a deep rotational slide<br>
    > D) The sand needs a cohesion intercept<br>
    > **Answer: A).** With no cohesion, the shallowest surface has the lowest F. The answer is real, but it isn't the deep mechanism a design cares about.

5. Shallow slides in sand slopes are common during heavy rain. With the water table at the ground surface and seepage parallel to the slope, the factor of safety is about:

    > A) The same as when dry, because water doesn't change the friction angle<br>
    > B) Half the dry value<br>
    > C) Zero<br>
    > D) Twice the dry value<br>
    > **Answer: B) Half the dry value.** The pore pressure cuts the effective normal stress, and so the friction, while the driving stress still comes from the total weight.

6. Why is the Ordinary Method of Slices unreliable on a slope with high pore pressures?

    > A) Its iteration often fails to converge<br>
    > B) It ignores the weight of the slices<br>
    > C) Its effective normal forces can come out too small, or negative, so F is too low<br>
    > D) It works only when φ = 0<br>
    > **Answer: C).** OMS ignores the side forces and resolves the weight perpendicular to the base; where u is high, little or no effective normal force is left.

7. Why must every method of slices make assumptions about the side forces?

    > A) The side forces are always zero<br>
    > B) The program would run too slowly without them<br>
    > C) The weight of each slice is unknown<br>
    > D) The unknowns outnumber the equations of equilibrium<br>
    > **Answer: D) The unknowns outnumber the equations of equilibrium.** The problem is statically indeterminate, and each method closes the gap differently.

8. Simplified Janbu's factor of safety, before its correction factor, is typically:

    > A) Too low, because it leaves out the interslice shear and moment equilibrium<br>
    > B) Too high, because it ignores the pore pressures<br>
    > C) Exactly Spencer's value<br>
    > D) The same as the Swedish method when φ = 0<br>
    > **Answer: A).** The correction factor mimics the effect of the missing forces. It grows with the depth of the surface.

9. A slope has a thin weak seam, and the critical surface runs along it. Which method should you use for design?

    > A) Bishop's simplified method<br>
    > B) Spencer's method<br>
    > C) The Ordinary Method of Slices<br>
    > D) The Corps of Engineers' procedure<br>
    > **Answer: B) Spencer's method.** It satisfies complete equilibrium on a noncircular surface. Bishop and OMS need circles, and the Corps' procedure depends on its assumed side force angles.

10. On a circle, Bishop's method usually lands close to Spencer's, while the force equilibrium procedures scatter. Why?

    > A) Bishop's method satisfies complete equilibrium<br>
    > B) Force equilibrium procedures ignore the pore pressure<br>
    > C) Spencer's method assumes horizontal side forces<br>
    > D) The F from moment equilibrium barely changes with the side force angle, while the F from force equilibrium changes a lot<br>
    > **Answer: D).** Bishop assumes horizontal side forces but keeps moment equilibrium, which is insensitive to that assumption. A force method's answer rides on its assumed angles.

11. Morgenstern–Price is run on one circle with a constant side force function and then with a half-sine function. What changes most?

    > A) The factor of safety, by 10 to 20%<br>
    > B) The scaling factor λ, while F hardly changes<br>
    > C) Nothing at all<br>
    > D) Whether moment equilibrium is satisfied<br>
    > **Answer: B).** The two functions put the side forces at quite different angles, but F changes very little. That is why Spencer's simpler assumption is usually enough.

12. On a 20 ft clay slope with cohesion only, Spencer gives 1.276 with tension on the bases of the crest slices. An 8 ft dry tension crack gives 1.084. Why did F drop?

    > A) The crack adds weight to the slope<br>
    > B) The crack changes the friction angle<br>
    > C) The model no longer counts cohesion along soil that would have torn open<br>
    > D) The crack lets water into the slope<br>
    > **Answer: C).** Without the crack, the solution had the top of the slope hanging from the soil behind it. Real soil cracks instead.

13. A wet slope is analyzed with $c'$ and $\phi'$, but every material's pore pressure source is set to none. The factor of safety will be:

    > A) Too high, because the friction uses the total normal stress<br>
    > B) Correct, because unit weights include the water<br>
    > C) Too low, because the water is counted twice<br>
    > D) Undefined; the run will not start<br>
    > **Answer: A) Too high.** It is a dry analysis of a wet slope. The pore pressure should carry part of the normal force and add nothing to friction.

14. A model has two starting circles, one in a sand embankment and one deep in the clay foundation, and one search reports only the deep circle. What should you do to check the other mechanism?

    > A) Nothing; the search tried both circles and the deep one is the minimum<br>
    > B) Increase the number of slices<br>
    > C) Switch to Bishop's method<br>
    > D) Run a separate search from each starting circle, or a grid search over the whole model<br>
    > **Answer: D).** A search refines the neighborhood it starts in and reports one surface. Several starting circles improve the odds but don't guarantee the global minimum.

15. Six geogrid layers are cut to 10 ft, and F rises only from 1.17 to 1.27. The most likely reason is:

    > A) The critical surface passes behind the short layers<br>
    > B) The layers ruptured<br>
    > C) The layers were entered as Passive<br>
    > D) Geogrid can't reinforce sand<br>
    > **Answer: A).** A surface that goes around the reinforcement gets nothing from it. Longer layers force the surface deeper, until it crosses every layer far enough from its ends.

16. A designer enters unfactored, long-term geogrid capacities as Active (Method A). The result is:

    > A) Correct, because XSLOPE applies the factor itself<br>
    > B) Conservative, because the reinforcement is factored twice<br>
    > C) Too high, because no factor of safety is ever put on the reinforcement<br>
    > D) Too low, because Active ignores pullout<br>
    > **Answer: C).** Active forces are not divided by F, so they must already be allowable values.

17. Two rows of drilled shafts are added to a slope. A search from a deep starting circle gives 1.845; a grid search gives 1.703 on a surface that leaves the face at the head of the upper row. What does this tell you?

    > A) The piles made deep surfaces stronger, so a shallow surface over the pile heads now governs<br>
    > B) The grid search is wrong, because it missed the piles<br>
    > C) The piles are too stiff<br>
    > D) The deep circle governs, because it crosses both rows<br>
    > **Answer: A).** A surface over the heads gets almost nothing from the piles. Raise the heads, extend the row, or add one near the crest, and search again.

18. A segmental block wall is analyzed by limit equilibrium with the blocks entered as an elastic material that can't fail. The factor of safety will be:

    > A) Correct<br>
    > B) Too low, because surfaces cut through the blocks<br>
    > C) Unaffected by the blocks<br>
    > D) Too high, because every surface must pass under the wall<br>
    > **Answer: D).** The wall really fails by slipping at its contacts, which limit equilibrium can't represent. A finite element model with joints can.

19. A dam on a clay layer over a permeable sand is analyzed with a piezometric line, and again with a seepage solution. The line gives a factor of safety 15% higher. Why?

    > A) The line includes suction in the clay<br>
    > B) The seepage solution uses a buoyant unit weight<br>
    > C) The line misses the upward flow through the clay at the toe, which raises the pore pressure<br>
    > D) The seepage solution is less accurate<br>
    > **Answer: C).** Water passes under the dam in the sand and comes up through the clay. No single line can show pore pressures above hydrostatic there.

20. In a seepage solution, the pore pressures above the phreatic surface are negative. For the stability analysis, XSLOPE by default:

    > A) Sets them to zero, because suction can't be relied on over the life of a slope<br>
    > B) Uses them, adding strength<br>
    > C) Doubles them as a safety margin<br>
    > D) Stops with an error<br>
    > **Answer: A).** Suction does add strength, but it can disappear when the soil wets up.

21. A zoned dam has a fine sand shell and a compacted clay core. For a 50-day drawdown, the time factor is 10 for the shell and 0.5 for the core. How are they analyzed?

    > A) Both drained<br>
    > B) The shell drained, the core undrained<br>
    > C) The shell undrained, the core drained<br>
    > D) Both undrained<br>
    > **Answer: B).** Above about 3, a zone drains as the pool drops; below it, the zone keeps its pore pressure. The test is made zone by zone.

22. In stage 3 of the rapid drawdown method, the drained strength replaces the undrained strength on some slices. Why?

    > A) The pool rose again<br>
    > B) Those slices failed in stage 1<br>
    > C) The undrained strength there came from UU tests<br>
    > D) A dilating fill's undrained strength relies on negative pore pressure that can't be counted on<br>
    > **Answer: D).** Given time, water flows in and the negative pore pressure goes away, so the drained strength caps the undrained strength.

23. The same dam is analyzed for rapid drawdown with two steady seepage solutions and with a transient run. The transient run gives a much lower factor of safety. The likely reason is:

    > A) A zone with drained strengths is still draining at the end of the drawdown<br>
    > B) The transient run uses different strengths for the core<br>
    > C) Transient runs always give lower answers<br>
    > D) The steady solutions forgot the pool load<br>
    > **Answer: A).** The second steady solution assumes the dam has already drained to the lowered pool. The transient run follows the drainage, so a slow zone still holds water.

24. Why is the seismic coefficient in a screening analysis usually less than the peak ground acceleration (as a fraction of g)?

    > A) Soil always amplifies the shaking<br>
    > B) The peak lasts only an instant, and a slope pushed past F = 1 briefly moves only a little<br>
    > C) The vertical acceleration cancels part of it<br>
    > D) The strength reduction factor already covers it<br>
    > **Answer: B).** Each method's multiplier was set together with the displacement it tolerates.

25. The earthquake record for a Newmark analysis is scaled up by a factor of 2. The computed displacement:

    > A) Doubles<br>
    > B) Stays the same, because k_y is unchanged<br>
    > C) Grows many times over<br>
    > D) Halves<br>
    > **Answer: C) Grows many times over.** Only the part of each peak above $k_y g$ moves the block. Scaled up, more peaks pass it, by more, and for longer.

26. The pseudostatic factor of safety of a dam was 2.0 to 2.5, yet its crest moved about 5 ft in the earthquake. The best explanation is:

    > A) The seismic coefficient was too small<br>
    > B) The wrong limit equilibrium method was used<br>
    > C) The record was scaled incorrectly<br>
    > D) The soil lost strength during shaking, which a pseudostatic analysis can't see<br>
    > **Answer: D).** A pseudostatic analysis, and Newmark's block, hold the strength fixed. For soils that weaken, the first question is whether they will lose strength.

27. A Taylor series analysis finds that the cohesion carries three quarters of the variance in F. The standard deviation of the cohesion is then cut in half. What happens?

    > A) F stays the same, and the probability of failure drops sharply<br>
    > B) F rises, and the probability of failure stays the same<br>
    > C) Both F and the probability of failure fall<br>
    > D) Nothing changes<br>
    > **Answer: A).** F uses only the most likely values. The probability of failure depends on the spread.

28. An engineer estimates a friction angle's highest and lowest conceivable values and divides the range by 6 to get its standard deviation. What is the concern?

    > A) None; dividing by 6 is always correct<br>
    > B) The standard deviation will be too large<br>
    > C) People guess ranges too narrow, so the standard deviation will be too small, which is unconservative<br>
    > D) Friction angles have no uncertainty<br>
    > **Answer: C).** The Nσ rule divides by about 4 instead, because an experienced engineer's range usually covers about four standard deviations, not six.

29. A strength reduction model of a slope on a 2 ft weak clay layer has only one row of elements across the layer. Compared with a properly meshed model, F will likely be:

    > A) Too low, because the layer is too weak<br>
    > B) Too high, because the shear band can't form inside the layer<br>
    > C) The same, because the mesh doesn't matter<br>
    > D) Zero<br>
    > **Answer: B).** A thin layer needs several rows of elements across it for the band to form there. Otherwise the model finds no mechanism through it.

30. A 2D strength reduction model of a slope with a row of separate drilled shafts gives an F that barely changes as the spacing grows, while limit equilibrium's drops. Why?

    > A) The shafts were entered as Passive<br>
    > B) The mesh is too fine<br>
    > C) Strength reduction ignores the shafts<br>
    > D) A 2D mesh treats the row as a continuous wall, with no gaps for soil to flow through<br>
    > **Answer: D).** For a row of separate piles, take F from limit equilibrium, and use the model for the forces in the shafts.

---

## 20 Short Answer Questions

1. **Name two ways a stable slope can become unstable, with an example of each.**
   The strength can decrease, for example when rain raises the pore pressure. The driving stress can increase, for example when the toe is excavated or a load is placed at the crest.

2. **Why is the end of construction usually the critical time for an embankment on soft clay?**
   The clay is loaded undrained, so its strength hasn't grown while the load has. As the clay drains, its effective stress and strength increase, and the embankment gets safer.

3. **Why describe the undrained strength of a normally consolidated clay as a value at the top plus a rate of increase, rather than one average?**
   An average is too high near the surface and too low at depth. Describing the real profile lets the search find the surface the real clay would fail on.

4. **What does a factor of safety of 1.5 mean in terms of the soil's strength?**
   The slope needs only two thirds of its strength for equilibrium. It should still stand if the strength were a third lower, with everything else as assumed.

5. **Why does the method of slices need slices once φ > 0, when the φ = 0 circle did not?**
   With friction, the strength depends on the normal stress, which varies along the surface and is unknown. Cutting the mass into slices lets each method estimate the normal force on each base.

6. **What is the line of thrust, and what does it mean if it drops out of the sliding mass near the crest?**
   It is the line through the points where the side forces act. If it leaves the mass near a cohesive crest, the solution has tension there, which real soil can't carry; a tension crack is the usual remedy.

7. **Which method would you use for design, and which would you run beside it as a check, on a circle and on a noncircular surface?**
   Spencer's method for design on either. On a circle, compare with Bishop's method; on a noncircular surface, with a force equilibrium procedure.

8. **Why should you enter total unit weights, never buoyant ones, in XSLOPE?**
   The program takes the water off through the pore pressures, so a buoyant weight would remove it twice. The buoyant shortcut also works only for still water and leaves out seepage forces.

9. **What is the difference between a piezometric line and a phreatic surface in a stability model?**
   Both use the same line. As a piezometric line, the pore pressure comes from the full depth below it (vertical equipotentials). As a phreatic surface, the flow runs along the line, which lowers the pore pressure where the line slopes.

10. **Why run a noncircular search on a slope with a thin weak layer?**
    A circle can't follow a thin flat layer; it spends most of its length in stronger soil. A noncircular surface can run along the layer and usually gives a lower F.

11. **What are the three ways a reinforced slope can fail?**
    The reinforcement ruptures, it pulls out because too little length is buried beyond the surface, or the surface passes behind or under the reinforcement.

12. **What is the difference between Method A (Active) and Method B (Passive) reinforcement?**
    In Method A the reinforcement forces are allowable values and are not divided by F. In Method B they are unfactored long-term capacities, divided by F along with the soil strength.

13. **Why does an entered pile force H need checking against the critical surface, when an Ito and Matsui force does not?**
    An entered H is the same on every trial surface, deep or shallow, so it is right only for the surface it was worked out for. Ito and Matsui's force is recomputed for each surface.

14. **Why does water flowing upward under the toe of a slope lower its stability?**
    Upward flow carries the pore pressure above hydrostatic, so the effective stress and the shear strength are lower than the depth below the water table would suggest.

15. **Why can't rapid drawdown be analyzed as an ordinary drained analysis at the lowered pool?**
    A drained analysis assumes the pore pressures have already come down with the pool. A low-permeability soil keeps its pore pressure and is sheared undrained before it can drain.

16. **In the three-stage method, why does the full pool set the strength and the lowered pool set the load?**
    The soil consolidated under the full-pool stresses, which fix its undrained strength. When the pool drops, the buoyancy and the water on the face are gone, and that new loading drives failure.

17. **What is the yield coefficient, and how is it found?**
    It is the seismic coefficient at which the factor of safety of a surface is exactly 1. It is found by solving the slope at a series of seismic coefficients until F crosses 1.

18. **What does the reliability index β measure?**
    How many standard deviations the most likely factor of safety sits above failure, F = 1. The larger β, the smaller the probability of failure.

19. **Why can Monte Carlo be run when the Taylor series can't, for an input whose standard deviation is larger than its most likely value?**
    The Taylor series needs a solve at the most likely value minus one standard deviation, which is then not a physical value. Monte Carlo only draws values from the distribution.

20. **In a strength reduction analysis, how does the model decide that a trial F fails?**
    The solver passes the stress that yielded soil can't carry to its neighbors. If the displacements level off, the trial stands; if they keep growing, no arrangement of stress carries the weight, and the trial fails.

---

## 15 Open Response (Essay) Questions

1. **Explain how water can cause a slope to fail, using both lists of causes (strength decreases and stress increases), and give a case history for each.**
   On the strength side, rain, snowmelt, or a rising water table raise the pore pressure, which lowers the effective stress and so the strength. At Thistle, a wet fall and a fast snowmelt raised the groundwater in an old slide already at residual strength. Water also swells clays, and fresh groundwater slowly leaches marine clays into quick clays, as at Rissa. On the stress side, water in a crack pushes on the sliding mass, a falling pool removes the support it gave the face, and soil gets heavier as it wets. At Oso, weeks of rain raised the groundwater while the river eroded the toe: one cause on each list. Water is behind most failures, which is why stability analyses need good pore pressures.

2. **Explain why an embankment on soft clay is most critical at the end of construction, while an excavation in clay is most critical in the long term. Which strength does each analysis use?**
   As an embankment goes up, the clay is loaded undrained: the pore pressure rises with the load, so the effective stress and strength barely change while the stress needed for equilibrium grows. F is lowest at the end of construction and rises as the clay drains. That analysis uses the undrained strength, from UU tests, with the pore pressure inside it. An excavation unloads the clay, and the pore pressure drops, often below its long-term value. Over time water flows back in, the effective stress and strength fall, and F keeps dropping for years. That analysis uses drained effective stress parameters with long-term pore pressures from steady seepage. The rule: if effective stresses will rise with time, the short term governs; if they will fall, the long term does.

3. **Explain why the limit equilibrium problem is statically indeterminate, and compare how OMS, Bishop, Spencer, and the force equilibrium procedures deal with it.**
   For n slices, the unknowns are F, the normal force on each base and where it acts, and the two side forces and their location on each boundary. Equilibrium gives three equations per slice, fewer than the unknowns, so every method assumes something. OMS ignores the side forces and resolves the weight perpendicular to the base; it satisfies only overall moment equilibrium and goes badly low with high pore pressures. Bishop assumes horizontal side forces and takes N from vertical equilibrium, satisfying moment and vertical force equilibrium; it is close to the complete methods on circles. The force equilibrium procedures assume the angle of every side force and satisfy force equilibrium slice by slice; their answer depends on those angles. Spencer assumes only that the side forces are parallel and solves for their angle along with F, satisfying complete equilibrium on any surface, which is why it is used for design.

4. **Explain the infinite slope for a sand: what controls F, why a search on a sand slope ends on the face, and what seepage parallel to the slope does.**
   In an infinite slope, the side forces on a block cancel, so the forces on the slip plane come from the block's weight alone. For a sand, F depends only on the friction angle and the slope angle; the depth drops out, so a dry sand slope stands at any angle up to φ. Any deeper surface, such as a circle, has a higher F, so a search keeps moving toward the face and ends on a thin sliver. That is real raveling, but not the deep slide a design is after, so a minimum slip depth keeps the search on the deep mechanism. With seepage parallel to the slope, the pore pressure lowers the effective normal stress while the driving stress still comes from the total weight. With the water table at the surface, F is about half the dry value, one reason shallow slides follow heavy rain.

5. **Describe how you would build and check a limit equilibrium model in XSLOPE, and the mistakes that give a reasonable-looking wrong answer.**
   Enter each material with total unit weights, a strength option, and a pore pressure source that matches it: an effective stress strength reads the water, while an undrained strength reads none. Draw the geometry, put the water in as a line or seepage solution and standing water as a load, and add loads in the right direction. Give a surface and search with Spencer, from more than one start or a grid search, and on a weak layer try a noncircular surface. Read the search and the solution: did the search stop in the open, is the surface a real mechanism, and what do the warnings say? Check with a hand calculation, a second method, or a chart. Classic mistakes: a wet slope with no pore pressure (F too high), an undrained strength that also reads the water line, buoyant unit weights, a surcharge entered normal to a slope face, a missing tension crack under a cohesive crest, and a local minimum taken for the global one.

6. **Explain how reinforcement enters a limit equilibrium analysis: where the force acts, how large it is, its direction, and whether it is divided by F.**
   Each layer gives one known force where the slip surface crosses it, applied to the base of that slice. It adds no unknowns. Its size comes from the capacity envelope: the smallest of the member's strength and the pullout each end can develop, so a surface crossing near an end gets only part of the capacity. Its direction is tangent to the slip surface, suited to flexible sheets, or axial along the member, suited to stiff bars; in sand the choice hardly matters, but in φ = 0 clay tangent gives a higher F. In Method A (Active) the forces are allowable values with their own factor of safety and are not divided by F. In Method B (Passive) they are long-term capacities divided by F with the soil. The values entered must match the method, and the search must be free to try surfaces behind and under the reinforcement, the third way a reinforced slope fails.

7. **Explain how a row of stabilizing piles is modeled in limit equilibrium, what limits its force, and how to search a slope that has one.**
   The row is one force per unit width of slope where a trial surface crosses the piles. You can enter that force from a lateral load analysis, but then it is the same on every surface, so check that the critical surface is the one it was meant for. Or XSLOPE computes it by Ito and Matsui, from the force of soil squeezing between the piles, recomputed for each surface; it assumes rigid vertical piles in level ground at about 2 to 8 diameters. The pile's shear and moment capacities cap the force, and bending usually governs. Closer spacing makes each pile take more and raises the force per foot. Because the piles strengthen the surfaces that cross them, the search must look for surfaces under the tips and over the heads, with a grid search across the whole slope.

8. **Compare the four ways of representing pore pressure in a stability analysis, and describe a case where the simple ones give the wrong answer.**
   A flow net gives accurate heads but is hard to use for every slice of every surface. A finite element seepage solution gives the pressure at every node, and XSLOPE reads it at the middle of each slice base. A piezometric line takes the pressure from the full depth below the line; a phreatic surface assumes flow along the line and gives less where it slopes. In a homogeneous slope with mostly horizontal flow, all of them agree. Under a dam on clay over a permeable sand, water flows under the dam in the sand and comes up through the clay at the toe. That upward flow raises the pore pressure well above hydrostatic and roughly halves the effective stress there. No line can show it, so both line representations overstate F, on the unsafe side; the seepage analysis is needed.

9. **Explain why rapid drawdown is dangerous, and describe the three stages of the Duncan, Wright, and Wong method.**
   The full pool pushes on the face and buoys the sliding mass. When it drops quickly, that support goes, the mass pushes with its full weight, and low-permeability soils keep the pore pressure the pool put into them. The time factor decides, zone by zone, which soils drain. Stage 1 is an effective stress analysis at full pool, kept for the stresses each slice consolidated under. Stage 2 turns those stresses into an undrained strength for each low-permeability slice, interpolating between two envelopes from CU tests on the slice's stress ratio, then computes F after drawdown with those strengths and drained strengths in free-draining zones. Stage 3 replaces the undrained strength with the drained one wherever the drained is lower, since a dilating fill's negative pore pressure can't be counted on, and recomputes F. The lower F governs. Shallow parts of a surface tend to be drained-critical and deep parts undrained-critical.

10. **Explain why undrained strengths are used for low-permeability zones in rapid drawdown, rather than an effective stress analysis with predicted pore pressures.**
    An effective stress analysis needs the pore pressures during drawdown. Part of that comes from the changing water loads, which can be estimated, but part comes from how the soil responds as it is sheared: dense fill dilates and loose fill contracts. No seepage analysis, steady or transient, contains that second part. The common simplifying assumption treats loose and dense fill alike and can err on the unsafe side; one dam it called safe had slid. An undrained strength is measured in tests in which the soil makes its own pore pressure as it is sheared, so it carries that response. That is why the three-stage method uses undrained strengths, set by the consolidation stresses at full pool.

11. **Walk through how a slope is evaluated for an earthquake: the questions in order, and what each kind of analysis can and can't tell you.**
    First, will the soils lose much strength? If so, as with loose saturated sand, the analysis is the comprehensive approach and stability after the earthquake with reduced strengths, since methods that hold strength fixed can't see the loss. If not, screen with a pseudostatic analysis: a seismic coefficient from a reference peak acceleration and a multiplier, a strength reduction, and a minimum F, all set together for a tolerable displacement. Strengths are undrained, since shaking lasts seconds. If F meets the minimum, the displacement should be tolerable. If not, Newmark's sliding block estimates the displacement: find the yield coefficient on a surface, and integrate the record, adding a slip whenever the shaking exceeds it. A pseudostatic F below 1 doesn't mean failure, because real shaking reverses. The sliding block assumes a rigid mass and a fixed strength.

12. **Explain what a factor of safety does not tell you, and how a reliability analysis fills the gap. Use the LASH trench.**
    F compares strength with stress using the most likely values, but every input is uncertain, the strength most of all, so F has a spread. Two slopes with the same F can have probabilities of failure that differ by thousands of times. A reliability analysis estimates the standard deviation of each input, from data, published COVs, or the highest and lowest conceivable values, and carries it to F by the Taylor series, Monte Carlo, or a response surface. The reliability index says how many standard deviations F sits above 1, and the probability of failure follows. The LASH trench was designed at F = 1.17 with careful strength data, and failed. A Taylor series analysis gives a probability of failure of about 18%; Duncan wrote that knowing it would likely have shown the slope was less stable than they thought. Conventional designs land near 1%, and the decision weighs the probability against the cost of a failure.

13. **Compare the Taylor series, Monte Carlo, and response surface methods: what each assumes, what it costs, and when you would use it.**
    The Taylor series moves each input one standard deviation up and down, a handful of solves, and combines the swings in F into its standard deviation. It assumes F changes linearly and assumes a shape (normal or lognormal) for its distribution; its swings also rank the inputs. It can't run when the most likely value minus a standard deviation isn't physical. Monte Carlo draws inputs, solves thousands of times, and counts failures; it assumes no shape and is the reference answer, but rare failures take very many solves. A response surface fits a formula to a few solves, checks the fit against more, and samples the fit cheaply; it is for probabilities too small to count. On a typical slope the three agree closely, and the standard deviations chosen matter more than the method.

14. **Explain how the strength reduction method finds a factor of safety and a slip surface, and when it is worth using instead of limit equilibrium.**
    Every soil's c and tan φ are divided by a trial F, and the slope is solved under its own weight. Soil whose stresses reach the strength envelope yields and passes its excess to its neighbors. When yielded soil links into a path from toe to crest, no arrangement of stress carries the weight, and displacements keep growing: the trial fails. Bisection narrows F to a tolerance, and the band of shear strain shows the slip surface, which no one chose. For most slopes, F is about the same as limit equilibrium's. Strength reduction is worth it when the mechanism is unknown, when a search might look in the wrong place or can't follow a thin weak layer, as a check, and when soil and structures act together. It costs a mesh, stiffness values, and more time, and the model must use quadratic elements, a fine enough mesh, no tensile strength, and distant boundaries.

15. **Compare how limit equilibrium and the finite element method represent structures in a slope, and say which method you would use for reinforcement, a sheet pile wall, a row of separate piles, a block wall, and a jointed rock face.**
    In limit equilibrium, a structure is a force chosen before the analysis and applied where the surface crosses it, and it gives no forces in the structure. In the finite element model the structure is in the mesh with a stiffness, and the model computes its forces from the deformation: bars for reinforcement, beams for piles and walls, and joints for contacts. For reinforcement and a continuous sheet pile wall, both give about the same F, and the model adds the force along each layer or the moment and shear in the wall. For a row of separate piles, take F from limit equilibrium, because a 2D mesh has no gaps for soil to flow through, and use the model for the shaft forces. A block wall fails at its contacts, and jointed rock can topple, which limit equilibrium can't represent, so use strength reduction with joints. Where design criteria were written for limit equilibrium, run it as well.

---

## Glossary of Key Terms

| Term | Definition |
|:-----|:-----------|
| **Active (Method A)** | Reinforcement or pile forces entered as allowable values and not divided by F. |
| **Bar Element** | A finite element that carries axial tension only, used for reinforcement. |
| **Beam Element** | A finite element with axial and bending stiffness that carries moment and shear, used for piles and walls. |
| **Bishop's Simplified Method** | A circular method that assumes horizontal side forces and takes each normal force from vertical equilibrium. |
| **Capacity Envelope** | The tension a reinforcement line can carry at each point: the smallest of its strength and the pullout from each end. |
| **Coefficient of Variation (COV)** | The standard deviation divided by the mean: a dimensionless measure of uncertainty. |
| **Complete-Equilibrium Method** | A method that satisfies force equilibrium in both directions and moment equilibrium, such as Spencer's. |
| **Critical Surface** | The trial surface with the lowest factor of safety. |
| **Developed (Mobilized) Strength** | The part of the strength a slope uses for equilibrium: c and tan φ divided by F. |
| **Drained Loading** | Loading slow enough for excess pore pressure to dissipate as it is applied. |
| **Effective Stress** | Total stress minus pore pressure; the stress that controls soil strength. |
| **Factor of Safety (F)** | Shear strength divided by the shear stress needed for equilibrium. |
| **Force Equilibrium Procedure** | A method that assumes the side force angles and satisfies force equilibrium on every slice (Corps of Engineers, Lowe and Karafiath). |
| **Infinite Slope** | A long, uniform slope with a slip plane parallel to the surface, where the side forces cancel. |
| **Ito and Matsui Method** | A method for the force a sliding soil puts on a row of piles as it squeezes between them. |
| **Joint Element** | A finite element at a contact that slips when its shear strength is reached and opens in tension. |
| **Line of Thrust** | The line through the points where the side forces act; it should stay inside the sliding mass. |
| **Liquefaction** | Loss of nearly all strength when shaking raises the pore pressure in a loose saturated sand. |
| **Locking** | The stiffening of linear elements that keeps a shear band from forming and overstates F. |
| **Method of Slices** | Cutting the sliding mass into vertical slices to estimate the normal force on each part of the surface. |
| **Monte Carlo Simulation** | Drawing input values from their distributions, solving each set, and counting the share that fails. |
| **Morgenstern–Price Method** | A complete-equilibrium method in which the side force angle varies along the surface by an assumed function. |
| **Newmark Sliding Block** | A rigid block that slips whenever the shaking exceeds its yield acceleration; the slips sum to a permanent displacement. |
| **Ordinary Method of Slices (OMS)** | A circular method that ignores the side forces; it needs no iteration and runs low with high pore pressures. |
| **Passive (Method B)** | Reinforcement or pile forces entered as unfactored capacities and divided by F with the soil strength. |
| **Phreatic Surface** | The line of zero pore pressure. As a stability input, the flow is taken to run along it, so where it slopes the pore pressure is less than the full depth below it. |
| **Piezometric Line** | A water line whose elevation gives the head straight below it, so the pore pressure is the unit weight of water times the depth below it. |
| **Probability of Failure ($P_f$)** | The chance that the factor of safety is below 1. |
| **Progressive Failure** | Failure in a softening soil that passes its peak at the most stressed point first and sheds load to its neighbors. |
| **Pseudostatic Analysis** | A limit equilibrium analysis with the earthquake replaced by a static horizontal force, $k_h W$. |
| **Pullout** | Failure of reinforcement by slipping out of the soil because too little length is buried beyond the slip surface. |
| **Quick Clay** | A leached marine clay that stands undisturbed but flows once remolded. |
| **R Envelope** | The total stress envelope drawn from CU tests, used for undrained strength in a single-stage seismic analysis. |
| **Rapid Drawdown** | A drop in the water against a slope too fast for low-permeability soils to drain. |
| **Reliability Index ($\beta$)** | The number of standard deviations between the most likely factor of safety and 1. |
| **Residual Strength** | The low strength left on a clay surface after large displacement lines up its particles. |
| **Response Surface** | A formula fitted to a few solves and checked, then sampled in place of the full analysis. |
| **Seismic Coefficient ($k_h$)** | The horizontal force in a pseudostatic analysis as a fraction of the weight. |
| **Spencer's Method** | A complete-equilibrium method that assumes all side forces are parallel and solves for their angle along with F. |
| **Strength Reduction (SSRM)** | Finding F by dividing every soil's strength by a trial factor until the slope can no longer stand. |
| **Swedish Method** | The φ = 0 circle: resisting moment of the cohesion over the driving moment of the weight. |
| **Taylor Series Method** | Estimating the spread of F by moving each input one standard deviation up and down. |
| **Tension Crack** | A vertical crack near the crest where cohesive soil can't carry tension; it has no strength and may hold water. |
| **Three-Stage Method** | The rapid drawdown method: full-pool stresses, undrained strengths after drawdown, then a drained check. |
| **Time Factor** | A measure of how fully a zone drains during a drawdown; above about 3, it is treated as drained. |
| **Undrained Loading** | Loading too fast for the water to flow, so the pore pressure change remains. |
| **Undrained Strength ($s_u$)** | The strength of a saturated soil sheared without drainage, used with φ = 0 in total stress. |
| **Yield Coefficient ($k_y$)** | The seismic coefficient at which a surface's factor of safety is exactly 1. |
