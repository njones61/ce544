# Homework - Rapid Drawdown Analysis

In this assignment, you will perform a rapid drawdown analysis on the earth dam from the previous homework using XSLOPE. This builds on your seepage/slope stability homework by adding a second set of boundary conditions to model the post-drawdown water level.

![earthdamfig.gif](../05_xslope/images/earthdamfig.gif)

For background on the three-stage rapid drawdown methodology, see:

[XSLOPE Rapid Drawdown Documentation](https://xslope.org/en/latest/lem/rapid/){:target="_blank"}

Use the XSLOPE Google Colab seepage notebook for the seepage analysis:

<a href="https://colab.research.google.com/github/njones61/xslope/blob/main/notebooks/xslope_seep.ipynb" target="_"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

Use the XSLOPE Google Colab LEM notebook for the slope stability analysis:

<a href="https://colab.research.google.com/github/njones61/xslope/blob/main/notebooks/xslope_lem.ipynb" target="_"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

## Instructions

Start with your Excel input file from the seepage/slope stability homework. You will modify it to support the two-stage seepage analysis required for rapid drawdown.

### 1. Add Undrained Strength Parameters

Add $d$ and $\psi$ parameters to the **mat** sheet for each material with poor drainage. Leave these blank for freely draining materials (Sand).

| Material | c' (psf) | $\phi'$ (deg) | $\gamma$ (pcf) | d (psf) | $\psi$ (deg) |
|:--------:|:--------:|:--------------:|:-------:|:-------:|:-------:|
| Shell    |    0     |       34       |   125   |        |       |
| Core     |   100    |       26       |   122   |   300    |   20    |
| Clay     |    0     |       24       |   123   |   100      |     18    |
| Sand     |    0     |       32       |   127   |         |         |

For the pore pressure option ($u$), set it to `seep` for all materials since we will be using seepage-derived pore pressures in the slope stability analysis.

Verify that the seepage properties are set up for all 4 materials. They should match the following:

| Material | k1  | k2  | alpha | kr0  | h0 |
|:--------:|:---:|:---:|:-----:|:----:|:--:|
| Shell    | 864   | 864   | 0     | 0.0001 | -1 |
| Core     | 0.0864 | 0.0864 | 0  | 0.0001 | -1 |
| Clay     | 0.864 | 0.864 | 0   | 0.0001 | -1 |
| Sand     | 86.4   | 86.4   | 0     | 0.0001 | -1 |

### 2. Set Up Two Sets of Distributed Loads

On the **dloads** sheet, set up two sets of distributed loads corresponding to the two pool levels:

**Solution 1 - Full Pool:** Distributed load for water at the full pool level (El. 302 ft) on the upstream face. This is already in the input file.

**Solution 2 - Lowered Pool:** Distributed load for water at the lowered pool level (El. 250 ft) on the upstream face. You will need to calculate the (x,y) coordinates where the water intersects the upstream face for both pool levels to set up the distributed loads correctly.

### 3. Set Up Two Sets of Seepage Boundary Conditions

On the **seep bc** sheet, set up two sets of boundary conditions:

**Solution 1 - Full Pool (Pre-Drawdown):**

- Upstream specified head: H = 302 ft
- Exit face on downstream slope and tail

This is already in the input file.

**Solution 2 - Lowered Pool (Post-Drawdown):**

- Upstream specified head: H = 250 ft (lowered pool level)
- Exit face on downstream slope and tail

Use the (x,y) coordinates where the water intersects the upstream face that you calculated for the distributed loads to set up the specified head boundary condition for Solution 2.

### 4. Run the Seepage Analysis

Upload your Excel file to the **seepage notebook** and run the analysis. The notebook will generate two seepage solutions. Download the resulting zip archive.

### 5. Run the Rapid Drawdown Analysis

Upload the zip archive to the **LEM notebook**. Run the rapid drawdown analysis using Spencer's method.

Review the three-stage results and report the critical factor of safety.

## Submission

Save a copy of your Excel input file, the mesh file, the two seepage solution files, and a PNG of the rapid drawdown solution plot. Zip up your files into a single zip archive. Upload your zip archive via Learning Suite.

## Grading Rubric

**Total: 30 points**

| Criteria | Points |
|----------|:------:|
| Undrained strength parameters (d, $\psi$) entered correctly for appropriate materials | 4 |
| Solution 1 seepage BCs set up correctly (full pool H = 302 ft) | 3 |
| Solution 2 seepage BCs set up correctly (lowered pool H = 250 ft) | 3 |
| Exit face defined on downstream slope for both solutions | 2 |
| Solution 1 distributed loads calculated correctly (full pool) | 3 |
| Solution 2 distributed loads calculated correctly (lowered pool) | 3 |
| Seepage analysis runs successfully with two solutions | 3 |
| Spencer's method used for rapid drawdown analysis on upstream side | 3 |
| Three-stage results reviewed and critical FS reported | 3 |
| Input fies and PNG solution plot properly submitted in zip archive | 3 |
