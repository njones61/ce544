# Exercise - Seismic Slope Stability Analysis

In this exercise we will calculate the factor of safety for slopes under seismic loading conditions. For the first problem, we will do an infinite slope analysis by hand. For the second problem, we will use XSLOPE with the seismic coefficient to analyze slopes from earlier exercises.

## Problem 1 - Infinite Slope Problem

A new subdivision is planned for bench to the east of Santaquin, Utah adjacent to Dry Mountain in Southern Utah
County, Utah. There is a slope at the base of the mountain that shows evidence of slippage during past seismic
events. Boring logs indicate that there is a layer of rock parallel to the slope at a depth of approximatley 25 ft. UU triaxial tests were conducted from samples taken from the site in a sandy clay layer near the bedrock. For
infinite slopes, the factor of safety is given by:

![infslope_fig.png](images/infslope_fig.png)

>>$FS = \dfrac{S_u}{\gamma z cos\beta sin\beta + k\gamma z cos^2\beta}$

where:

>>$S_u$ = undrained shear strength of the soil (psf)<br>
$\gamma$ = unit weight of the soil (pcf)<br>
$z$ = depth to the failure plane (ft)<br>
$\beta$ = slope angle (degrees)

Assume the following values for the slope:

|         Parameter         | Value | Units |
|:-------------------------:|:-----:|-------|
|          $\beta$          |  21   | degrees |
|            $z$            |  25   | ft |
|         $\gamma$          |  120  | pcf |
|           $S_u$           | 2000  | psf |

Consider the following three cases:

| Case                       | Peak Acceleration (g)  | Acceleration Multiplier |
|:---------------------------|:----------------------:|:-----------------------:|
| 10% Exceedance in 50 years | [find using USGS tool] |           0.5           |
| 2% Exceedance in 50 years  | [find using USGS tool] |           0.5           |
| Threshold Case             |        [solve]         |           0.5           |

Do the following:

a. Enter an appropriate strength reduction factor and adjust the undrained strength.

b.  Enter a set of formulas to compute the factor of safety against slope failure under seismic conditions. For the first two cases, find the peak accelerations from the [USGS website](https://earthquake.usgs.gov/hazards/interactive/){:target="blank"}.

c.  For the third case in the table, find the peak acceleration that results in a factor of safety = 1.0.

Use following Excel spreadsheet for your calculations:

Excel starter file: [seismic_infslope.xlsx](files/seismic_infslope.xlsx)<br>
Excel solution file: [seismic_infslope_KEY.xlsx](files/seismic_infslope_KEY.xlsx)

## Problem 2 - Seismic Analysis with XSLOPE

In this problem, we will use XSLOPE to perform seismic slope stability analyses. The seismic coefficient ($k_h$) is entered on the **main** sheet of the Excel input template. This applies a horizontal pseudo-static force to each slice during the limit equilibrium analysis.

Start with the standard Excel input template:

[input_template.xlsx](https://xslope.org/en/latest/inputs/input_template.xlsx)

After preparing each set of inputs, launch the XSLOPE Google Colab notebook for stability analysis and upload your Excel input file and solve:

<a href="https://colab.research.google.com/github/njones61/xslope/blob/main/notebooks/xslope_lem.ipynb" target="_"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

### Part a - Simple Embankment with Seismic Load

Revisit the simple embankment from the XSLOPE Part 1 exercise:

![part1a_fig.png](../05_xlope/images/part1a_fig.png)

1. Set up the problem in XSLOPE and solve for the static factor of safety (no seismic load, $k_h = 0$).
2. Now add a seismic coefficient of $k_h = 0.1$ on the **main** sheet and re-solve. Compare the factor of safety to the static case.
3. Increase the seismic coefficient to $k_h = 0.2$ and solve again. Note the change in factor of safety and the location of the critical circle.

### Part b - Method of Slices Problem with Seismic Load

Revisit the method of slices problem from the XSLOPE Part 2 exercise:

![part2a_fig.png](../05_xlope/images/part2a_fig.png)

Use the following spreadsheet to get the coordinates of the profile lines:

[method-of-slices-input.xlsx](../05_xlope/files/method-of-slices-input.xlsx)

1. Set up the problem in XSLOPE with the piezometric line and solve for the static factor of safety.
2. Add a seismic coefficient of $k_h = 0.15$ and re-solve. Compare to the static factor of safety.
3. Try to find the value of $k_h$ that results in a factor of safety of approximately 1.0. You can do this by adjusting $k_h$ on the main sheet and re-running the analysis.
