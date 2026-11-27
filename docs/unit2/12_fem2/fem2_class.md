# Exercise - Strength Reduction with Structures

In this exercise you will run strength reduction in XSLOPE Studio on two slopes with structures in them, a geogrid-reinforced slope and a sheet pile wall, and read the forces in the structures. [Tutorial FEM-2](https://xslope.org/en/latest/tutorials/fem02_reinforcement/){:target="_blank"} and [Tutorial FEM-4](https://xslope.org/en/latest/tutorials/fem04_piles/){:target="_blank"} show each step.

## Problem 1 - A Geogrid-Reinforced Slope

The reinforced slope from the Soil Reinforcement lecture: a 24 ft sand fill at 1.25:1 with six geogrid layers, each with a tensile capacity of 800 lb/ft and a residual capacity of 600 lb/ft.

![geogrid_slope.png](images/geogrid_slope.png){width="971"}

Open this file in XSLOPE Studio: [xslope_reinforced_slope.xlsx](files/xslope_reinforced_slope.xlsx)

1. In **LEM**, click **Run → Run LEM…** with Spencer and **Auto search**. What is F?

2. Switch the mode strip to **FEM**. Click **Run → Build Mesh…**, untick **Auto-size from geometry**, set **Target element size** to 2, untick **Refine thin zones**, and click **Build**. Click **Run → Run FEM…** and **Run** (a few minutes). What is F? Compare it with step 1.

3. Click **1D Details…**, set **Field state** to **Last converged**, and select **Line 5**. What is the largest force in the layer, and how far from the face is it?

4. Open **Reinforcement** and set **Tres** to 0 on all six lines, so that a layer carries nothing once it reaches its capacity. Run FEM again. What is F, and why is it lower than in step 2?

Solution:

**1.** F = 1.589.

**2.** F = 1.535, 3% below Spencer. With the geogrid in the slope, the two methods give about the same F.

**3.** About 764 lb/ft, 11 ft from the face. The force is small at the face, largest near the middle of the layer, and small again at the buried end. Limit equilibrium applies one force at the point where the circle crosses the layer.

**4.** F = 1.457. A layer that reaches its capacity now drops to zero instead of to 600 lb/ft, and its load passes to the other layers and the soil.

## Problem 2 - A Sheet Pile Wall

A 20 ft clay slope at 1:1 with a PZ-27 steel sheet pile wall at mid-slope, its tip fixed in the rigid base.

![sheet_pile_wall.png](images/sheet_pile_wall.png){width="971"}

Open this file in XSLOPE Studio: [xslope_pile_wall.xlsx](files/xslope_pile_wall.xlsx)

1. Switch to **FEM**. Click **Run → Build Mesh…**, untick **Auto-size from geometry**, set **Target element size** to 2, and click **Build**. Run FEM. What is F, and where does the shear strain band go?

2. With the wall's resistance H entered (49,000 lb/ft, the passive resistance of the soil below the slip surface), Spencer's method gives F = 1.704. Compare it with step 1. Where does the critical circle go?

3. Click **1D Details…**, set **Field state** to **Last converged**, and select the wall. What is the largest bending moment, and where is it? What fraction of the wall's moment capacity, 152,000 lb·ft/ft, is it?

Solution:

**1.** F = 1.730. The band runs from the head of the wall up to the crest: the soil above the wall slides out over its head.

**2.** The two methods agree within 2%. Spencer's critical circle also passes over the head of the wall.

**3.** About 84,000 lb·ft/ft, at the tip, which is fixed; the moment is zero at the free head. That is 55% of the capacity, so the soil above the wall fails before the wall does. Limit equilibrium gives no moment in the wall; only strength reduction does.
