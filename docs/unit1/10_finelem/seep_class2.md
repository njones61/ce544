# Exercise - Unconfined Seepage Problems, Part 2

In this exercise, we will solve two additional unconfined seepage problems using XSLOPE. The first problem corresponds to a simple earth dam with a low-permeability core and the second problem corresponds to a dam with a core, filter, and drain.

## Problem 1 - Johnson Reservoir

The Johnson Reservoir problem corresponds to the following cross section:

![johnson_res.png](images/johnson_res.png)

We will first prepare the problem inputs in an XSLOPE Excel input file. Start with the standard template:

[input_template.xlsx](https://xslope.readthedocs.io/en/latest/inputs/input_template.xlsx)

Use the Excel file to specify the 
material properties, define the 
geometry using a profile line, and assign 
boundary 
conditions. 

After preparing the input file, launch the following Google Colab notebook to upload the Excel input file and 
perform the seepage analysis:

<a href="https://colab.research.google.com/github/njones61/xslope/blob/main/notebooks/xslope_seep.ipynb" target="_"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

Solution: [xslope_johnson_res.xlsx](https://xslope.readthedocs.io/en/latest/seep/files/xslope_johnson_res.xlsx)

## Problem 2 - Earth Dam with Core, Filter, and Drain

The Earth Dam with Core, Filter, and Drain problem corresponds to the following cross section:

![damwithfilterdrain.png](images/damwithfilterdrain.png)

In this case, we will go through the process of deriving the geometry (point coordinates) of the cross section from 
the image. Enter the resulting profile lines, material properties, etc. in the XSLOPE Excel input file.

[input_template.xlsx](https://xslope.readthedocs.io/en/latest/inputs/input_template.xlsx)

After preparing the input file, launch the following Google Colab notebook to upload the Excel input file and 
perform the seepage analysis:

<a href="https://colab.research.google.com/github/njones61/xslope/blob/main/notebooks/xslope_seep.ipynb" target="_"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

Solution: [xslope_earthdam2.xlsx](https://xslope.readthedocs.io/en/latest/seep/files/xslope_earth_dam2.xlsx). 
