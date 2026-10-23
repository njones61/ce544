# Exercise - Construction Dewatering

In this exercise, we will use the **Dewater** web app to design a well-based dewatering system for a construction site. The app calculates the drawdown from a set of wells and the pumping rate required to lower the water table to a desired level. We will assume unconfined conditions and apply the superposition principle to calculate the water level using the following equation:

![unconfined.png](../06_wells/images/unconfined.png)

>>$h = \sqrt{H^{2} - \dfrac{1}{\pi k} \sum_{i=1}^n q_{i}\ln\left(R/r_i\right)}$

Where:

>>$h$ = water level at a given location (m)<br>
$H$ = initial water table elevation (m)<br>
$k$ = hydraulic conductivity of the aquifer (m/s)<br>
$q_{i}$ = pumping rate of well $i$ (m³/s)<br>
$R$ = radius of influence (m)<br>
$r_i$ = distance from well $i$ to the point in question (m)<br>
$n$ = number of wells

This assumes we have a simple, uniform isotropic aquifer underlain by a low K unit. The heads are measured from the top of the low K unit.

When dealing with an excavation, we create a grid of points that covers the excavation and calculate the water level at each point resulting from a set of dewatering wells that surround the excavation. At each point, we calculate the distance ($r_i$) from each well to the point and apply the equation above. The well spacing and pumping rate can be adjusted until the water level at all points inside the excavation is below the target depth of the excavation.

Open the app here:

<a href="https://jonesgeo.com/dewater/" target="_blank"><b>Dewater: https://jonesgeo.com/dewater/</b></a>

It runs in your browser; there is nothing to install. The **How it works** button at the top of the app summarizes the equations and the steps. The app keeps your work if you reload the page, and **Save project** writes it to a file you can open later.

## Part 1 - Define the Excavation Site

The excavation size and location are defined by a polygon. You can draw it directly on the map (zoom to the site, click **Draw outline**, and click the corners), or load it from a GeoJSON file. For this problem, we will use the following GeoJSON file:

GEOJSON File: [byu_brewster.geojson](files/byu_brewster.geojson) (right-click and select "Save Link As")

This file contains the coordinates of a polygon that represents an excavation site. For this problem we will assume that BYU intends to build a new building to replace the Clyde Building and has decided to build the new building at the location of the current Brewster Building on the east side of campus. The GeoJSON file contains the coordinates of a rectangular excavation site that represents the footprint of the new building.

!!! Note
    An excavation at this location would not likely require dewatering as the water table is well below the
    elevation of the site. This is for illustrative purposes only.

Click **Load GeoJSON** in step 1 and select the file. (The same polygon also loads with the **Load the class example (BYU)** link.) The app zooms to the site and outlines the excavation in orange:

![dewater_app_excavation.jpg](images/dewater_app_excavation.jpg)

Then enter the following parameters in step 2:

| Parameter | Value | units |
|----------|-------|-------|
| Depth to the water table | 5  | m |
| Depth to the bottom of the aquifer | 55 | m |
| Excavation depth | 20 | m |
| Water required below the bottom | 0 | m |
| $k$      | 5e-4  | cm/s  |
| $R$      | 500   | m     |

The app converts the depths to the quantities in the equation and shows them under the inputs: the initial saturated thickness, $H$ = 55 − 5 = 50 m, and the target head inside the excavation, 55 − 20 = 35 m above the bottom of the aquifer. (You can also enter $H$ and the target head directly with **Heads above the low-k layer**.)

## Part 2 - Drawdown Calculations

In step 3, click **Click to add wells** and click the map to place wells around the excavation. They should be outside of the footprint of the excavation. Drag a well to move it, and right-click a well to delete it. Click the button again when you are done.

In step 4, enter a total pumping rate of $Q$ = 0.015 m³/s. The total pumping rate is divided equally among the wells. The app computes the water level on a grid surrounding the excavation and draws contours on the map as soon as anything changes:

![dewater_app_manual.jpg](images/dewater_app_manual.jpg)

The orange contour is the required water level (here, the excavation bottom). The area where the water is below the target is shaded green, and the panel reports the highest water level inside the excavation and whether the excavation is dewatered. If it isn't, a red circle marks the point where the water is highest. In step 5 you can switch the contours to the depth to water, drawdown, or the water below the required level, which is negative where the excavation is still wet. In step 6, **East–west** and **North–south** draw cross sections through the excavation showing the ground, the excavation, and the water table.

Play with the pumping rate and the well locations to determine when the water level is below the target at all points in the excavation.

## Part 3 - Rectangular Well System Design

Next, use **Generate a ring of wells** in step 3 to automatically place wells around the excavation, based on an offset distance from the excavation boundary and a number of wells. The wells are spaced evenly along a line offset from the edge of the excavation.

Use an offset of 15 m and 16 wells. Play with the number of wells, the offset distance, and the pumping rate. Compare your results to the previous section where you manually placed the wells.

## Part 4 - Pumping Rate Optimization

Click **Find the least Q that works** in step 4. The app finds the minimum total pumping rate that puts the water level inside the excavation just at the target at all points. With 16 wells at a 15 m offset, the result should look like this:

![dewater_app_ring.jpg](images/dewater_app_ring.jpg)

Because the wells share the pumping equally, this minimum rate can be computed directly rather than by trial and error: the highest water is always at the point in the excavation where the wells have the least combined effect, and the rate is the one that brings that point exactly to the target. The app also checks that the rate doesn't pump any of the wells dry. If it does, you need more wells, or wells farther from the excavation.

What is the total pumping rate in gpm?

## Part 5 - Q vs NumWells Design Curve

In step 7, with **Number of wells** selected, enter a range for the number of wells (for example, 4 to 40) and click **Compute the design curve**. For each number of wells, the app generates a ring of wells at the offset distance from step 3 and finds the minimum pumping rate. The results are presented in a curve of optimal pumping rate vs number of wells:

![dewater_app_curve.jpg](images/dewater_app_curve.jpg)

The design curve will help you determine the optimal number of wells and pumping rate required to dewater the excavation. In other words, at some point, adding more wells will not significantly reduce the pumping rate required to dewater the excavation. Use **Download CSV** to save the curve.

Try a few different offset distances. How does the offset affect the required pumping rate?

## Part 6 - The Radius of Influence

So far we have entered the radius of influence, $R$ = 500 m. In practice, $R$ is usually estimated with an empirical formula such as Sichardt's, $R = 3000\,s\sqrt{k}$ (with $s$, the drawdown, in m and $k$ in m/s). In step 2, change **Radius of influence, R** from **Entered** to **Sichardt**, and click **Find the least Q that works** again. Sichardt's formula needs the drawdown at the wells, $s_w$, which itself depends on the pumping rate, so the app solves the two together and reports $R$ and $s_w$. How does $R$ from Sichardt compare to 500 m, and how much does it change the pumping rate?

Then, in step 7, select **Hydraulic conductivity, k** and compute the design curve for $k$ from 1e-4 to 1e-2 cm/s. The plot shows the least pumping rate with $R$ from Sichardt and with $R$ fixed. With a fixed $R$, the pumping rate is simply proportional to $k$. Why is the curve with $R$ from Sichardt different, and what does that tell you about how much the choice of $R$ matters?

!!! Note "In practice"
    When a pumping test is available, $R$ comes from it: the drawdowns at the observation wells are
    plotted against the log of distance, and the line is extended to zero drawdown. Without a test, an
    empirical formula such as Sichardt's gives an estimate, usually computed once from the drawdown the
    design calls for. Because the pumping rate depends on $R$ only through $\ln(R/r)$, designers often
    run the design for a range of $R$. $R$ also grows the longer the wells pump, so a steady-state $R$
    stands for some period of pumping. Around a compact excavation, a ring of wells behaves much like
    one large well with a radius of $\sqrt{A/\pi}$, which is why the least total rate for a small site
    barely changes with the number of wells.
