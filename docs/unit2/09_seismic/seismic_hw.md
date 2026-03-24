# Homework - Seismic Slope Stability with XSLOPE

In this assignment, you will use XSLOPE to perform seismic slope stability analyses a problem from an earlier exercise. 

![earthdamfig.gif](../05_xslope/images/earthdamfig.gif)

Solve using the XSLOPE Google Colab notebook for stability analysis:

<a href="https://colab.research.google.com/github/njones61/xslope/blob/main/notebooks/xslope_lem.ipynb" target="_"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

Note that we have analyzed this slope using both piezometric lines and full 2D finite element seepage analysis. For simplicity, we will use the piezometric line for this problem. You can download an Excel template for this problem here:

[earth_dam_seismic.xlsx](files/earth_dam_seismic.xlsx)

## Part 1 - Static Analysis

First, we will perform a static analysis of the slope to establish a baseline factor of safety.

a) Upload the Excel input file and run the static analysis using the Colab notebook.

b) Note the factor of safety for the downstream side.

c) Save a PNG of the solution plot.

## Part 2 - Site Analysis

Next, we will go through the process of establishing a site-specific seismic coefficient ($k_h$) for our site. 

a) Use the USGS Unified Hazard tool [USGS website](https://earthquake.usgs.gov/hazards/interactive/){:target="blank"}. Assume that the dam is located near Litle Rock, Arkansas (use the search tool). Obtain the PGA both of the following return periods:

| Return Period | Variable |
|:-------------:|:--------:|
| 2% in 50 years |  PGA_2   |
| 10% in 50 years |  PGA_10  |

b) Multiply both of PGA values by 0.5 to obtain the seismic coefficient ($k_h$) for both return periods.

## Part 3 - Seismic Analysis

a) Since this is a constructed slope, we will use shear strengths from R-envelopes as we did for the Johnson Reservoir problem in the in-class exercise. Update the material properties in your Excel input file to use the following R-envelope values:

| Material | $\gamma$ (pcf) | c$_R$ (psf) | $\phi_R$ (deg) |
|:--------:|:-------:|:-----------:|:--------------:|
| Shell    |   125   |    1200     |       22       |
| Core     |   122   |     600     |       16       |
| Clay     |   123   |     250     |       15       |
| Sand     |   127   |    1200     |       22       |

b) Enter the seismic coefficient ($k_h$) you found in Part 2 into the Excel input file for the PGA_2 return period. Save your Excel input file as **earth_dam_seismic_2.xlsx**.

c) Upload the Excel input file and run the seismic analysis using the Colab notebook. Save a PNG of the solution plot.

d) Change the seismic coefficient ($k_h$) to PGA_10 and re-run the analysis. Save a PNG of the solution plot.

## Submission

Combine the following files into a zip archive:

1. PNG of the solution plot for the static analysis (Part 1)
2. Excel input file with the R-envelope soil properties and seismic coefficient for PGA_2 (Part 3b)
3. PNG of the solution plot for the seismic analysis with PGA_2 (Part 3c)
4. PNG of the solution plot for the seismic analysis with PGA_10 (Part 3d)

Upload your zip archive via Learning Suite.

## Grading Rubric

**Total: 30 points**

| Criteria | Points |
|----------|:------:|
| Part 1: Static analysis FS and solution plot | 5 |
| Part 2: PGA values and seismic coefficients for both return periods | 5 |
| Part 3a-b: R-envelope properties applied, Excel file with PGA_2 | 8 |
| Part 3c-d: Seismic analysis solution plots for PGA_2 and PGA_10 | 7 |
| All files properly submitted in zip archive | 5 |
