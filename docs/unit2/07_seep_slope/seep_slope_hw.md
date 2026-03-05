# Homework - Seepage/Slope Stability Integration

This problem corresponds to the Johnson Reservoir example from the XSLOPE documentation:

![johnson_res.png](../../unit1/10_finelem/images/johnson_res.png)

we will combine seepage and slope stability analyses using XSLOPE. We will first run a seepage analysis to compute pore pressures and then use those pore pressures in a slope stability analysis. 

Use the XSLOPE Google Colab seepage notebook for the seepage analysis:

<a href="https://colab.research.google.com/github/njones61/xslope/blob/main/notebooks/xslope_seep.ipynb" target="_"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

Use the XSLOPE Google Colab LEM notebook for the slope stability analysis:

<a href="https://colab.research.google.com/github/njones61/xslope/blob/main/notebooks/xslope_lem.ipynb" target="_"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

## Instructions

1. Download the following Excel input file:

[xslope_johnson_res.xlsx](./files/xslope_johnson_res.xlsx)

2. The strength parameters for the three materials are:

| Material   | γ (pcf) | Option | c (psf) | φ (deg) |
|:----------:|:-------:|:------:|:-------:|:-------:|
| Shell      | 130     | mc     | 100     | 35      |
| Core       | 125     | mc     | 400     | 18      |
| Foundation | 127     | mc     | 100     | 27      |

Enter the material properties into the **mat** sheet of the Excel input file. Set the pore pressure option for each material to `seep`.

3. Upload the Excel file to the **seepage notebook** and run the seepage analysis. After the analysis is complete, download the zip archive that the notebook generates. The archive contains the Excel input file, the mesh file, and the seepage solution. Also download the PNG of the seepage solution plot.

4. Upload the zip archive to the **LEM notebook** and run the slope stability analysis. The pore pressures from the seepage solution will automatically be used in the stability analysis. Download the PNG of the slope stability solution plot.

## Submission

Save a copy of your Excel input file and a PNG of the solution plots (both seepage and slope stability). Zip up your files into a single zip archive. Upload your zip archive via Learning Suite.

## Grading Rubric

| Criteria                                                                  | Points |
|---------------------------------------------------------------------------|:------:|
| Material properties (γ, c, φ) entered correctly for all three materials   |   8    |
| Pore pressure option set to `seep` for all materials                      |   4    |
| Seepage analysis runs successfully and solution is reasonable             |   6    |
| Slope stability analysis runs successfully using seepage pore pressures   |   6    |
| Seepage and slope stability solution plots saved as PNGs                  |   3    |
| Excel input file and PNG solution plots properly submitted in zip archive |   3    |
| **Total**                                                                 | **30** |
