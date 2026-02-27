# Homework - Seepage/Slope Stability Integration

In this assignment, you will redo the earth dam problem from the previous XSLOPE homework, but this time using a seepage analysis to define the pore pressures instead of a piezometric line.

![earthdamfig.gif](../05_xlope/images/earthdamfig.gif)

Start with your solution from the previous homework (XSLOPE LEM, Part 2). You will modify it to use seepage-derived pore pressures instead of the piezometric line.

Use the XSLOPE Google Colab seepage notebook for the seepage analysis:

<a href="https://colab.research.google.com/github/njones61/xslope/blob/main/notebooks/xslope_seep.ipynb" target="_"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

Use the XSLOPE Google Colab LEM notebook for the slope stability analysis:

<a href="https://colab.research.google.com/github/njones61/xslope/blob/main/notebooks/xslope_lem.ipynb" target="_"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

## Instructions

1. Open your Excel input file from the previous homework and change the pore pressure option for each material from `piezo` to `seep`.

2. Add the following seepage material properties to the **mat** sheet:

| Material | k1  | k2  | alpha | kr0  | h0 |
|:--------:|:---:|:---:|:-----:|:----:|:--:|
| Shell    | 1   | 1   | 0     | 0.01 | -1 |
| Core     | 0.001 | 0.001 | 0  | 0.01 | -1 |
| Clay     | 0.01 | 0.01 | 0   | 0.01 | -1 |
| Sand     | 1   | 1   | 0     | 0.01 | -1 |

3. Set up the seepage boundary conditions on the **seep bc** sheet. Use a specified head of H = 302 ft on the upstream boundary and H = 227 ft on the downstream boundary. Define an exit face on the downstream slope of the dam.

4. Upload the Excel file to the **seepage notebook** and run the seepage analysis. Download the zip archive.

5. Upload the zip archive to the **LEM notebook** and run the slope stability analysis using Spencer's method. Perform two sets of calculations: one for the upstream side and one for the downstream side.

## Submission

Save a copy of your Excel input file and a PNG of the solution plots for each side (upstream and downstream). Zip up your files into a single zip archive. Upload your zip archive via Learning Suite.

## Grading Rubric

| Criteria                                                                  | Points |
|---------------------------------------------------------------------------|:------:|
| Pore pressure option changed to `seep` for all materials                  |   3    |
| Seepage material properties entered correctly                             |   4    |
| Upstream specified head boundary condition (H = 302 ft) set up correctly  |   3    |
| Downstream specified head boundary condition (H = 227 ft) set up correctly|   3    |
| Exit face defined on downstream slope                                     |   3    |
| Seepage analysis runs successfully                                        |   3    |
| Spencer's method used for slope stability analysis                        |   2    |
| Upstream side analysis performed and minimum FOS identified               |   3    |
| Downstream side analysis performed and minimum FOS identified             |   3    |
| Excel input file and PNG solution plots properly submitted in zip archive |   3    |
| **Total**                                                                 | **30** |
