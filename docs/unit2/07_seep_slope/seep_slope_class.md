# Exercise - Seepage/Slope Stability Integration

In this exercise, we will combine seepage and slope stability analyses using XSLOPE. We will first run a seepage analysis to compute pore pressures and then use those pore pressures in a slope stability analysis. Start with the standard Excel input template:

[input_template.xlsx](https://xslope.org/en/latest/inputs/input_template.xlsx)

Use the XSLOPE Google Colab seepage notebook for the seepage analysis:

<a href="https://colab.research.google.com/github/njones61/xslope/blob/main/notebooks/xslope_seep.ipynb" target="_"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

Use the XSLOPE Google Colab LEM notebook for the slope stability analysis:

<a href="https://colab.research.google.com/github/njones61/xslope/blob/main/notebooks/xslope_lem.ipynb" target="_"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

## Problem 1 - Johnson Reservoir

This problem corresponds to the Johnson Reservoir example from the XSLOPE documentation:

![johnson_res.png](../../unit1/10_finelem/images/johnson_res.png)

The strength parameters for the three materials are:

| Material   | γ (pcf) | Option | c (psf) | φ (deg) |
|:----------:|:-------:|:------:|:-------:|:-------:|
| Shell      | 130     | mc     | 100     | 35      |
| Core       | 125     | mc     | 400     | 18      |
| Foundation | 127     | mc     | 100     | 27      |

Download the following Excel input file:

[xslope_johnson_res.xlsx](https://xslope.org/en/latest/seep/files/xslope_johnson_res.xlsx) 

Use the following steps to solve the problem:

1. Upload the Excel file to the **seepage notebook** and run the seepage analysis. After the analysis is complete, download the zip archive that the notebook generates. The archive contains the Excel input file, the mesh file, and the seepage solution.

2. Upload the zip archive to the **LEM notebook** and run the slope stability analysis. The pore pressures from the seepage solution will automatically be used in the stability analysis.

3. Review the results. Note how the pore pressures from the seepage analysis affect the factor of safety.

## Problem 2 - Method of Slices Problem with Seepage

This is the same problem we solved earlier in the XSLOPE exercises.

![part2a_fig.png](../05_xlope/images/part2a_fig.png)

Use the following spreadsheet to get the coordinates of the profile lines:

[method-of-slices-input.xlsx](../05_xlope/files/method-of-slices-input.xlsx)

Add the following seepage properties for the three materials:

| Material | k1  | k2  | alpha | kr0    | h0 |
|:--------:|:---:|:---:|:-----:|:------:|:--:|
| Silt     | 0.5 | 0.5 | 0     | 0.0001 | -1 |
| Sand     | 1   | 1   | 0     | 0.0001 | -1 |
| Clay     | 0.01| 0.01| 0     | 0.0001 | -1 |

### Part a - Piezometric Line

First, solve the problem using a piezometric line to define the pore pressures. Set the pore pressure option for each material to `piezo`. Enter the following piezometric line coordinates on the **piezo** sheet:

|   x   |  y  |
|:-----:|:---:|
|   0   | 40  |
| 115.7 | 40  |
| 130.5 | 52  |
|  150  | 61  |
|  180  | 70  |
|  208  | 76  |
|  245  | 79  |
|  320  | 80  |

Use a single starting circle to find the factor of safety.

### Part b - Seepage Analysis

Now solve the same problem using a seepage analysis.

1. Change the pore pressure option for each material to `seep`.
2. Set up the seepage boundary conditions on the **seep bc** sheet using a specified head of H = 80 ft on the upstream boundary.
3. Run the seepage analysis using the **seepage notebook** and download the zip archive.
4. Upload the zip archive to the **LEM notebook** and run the slope stability analysis. Use a single starting circle.
5. Compare the factor of safety to the piezometric line solution from Part a.

Solution: [TODO](TODO)
