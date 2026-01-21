# Exercise - Unconfined Seepage Problems, Part 1

For this exercise, we will build an input file and perform a seepage analysis using XSLOPE for an site with unconfined (partially-saturated) conditions. The problem corresponds to the following cross section:

![earthdamfigure.png](images/earthdamfigure.png)

We will first prepare the problem inputs in an XSLOPE Excel input file. Start with the standard template:

[input_template.xlsx](https://xslope.readthedocs.io/en/latest/inputs/input_template.xlsx)

Use the Excel file to specify the 
material properties, define the 
geometry using a profile line, and assign 
boundary 
conditions. We will define a local coordinate system with the origin (x=0, y=0) at the toe of the dam on the left side of the figure. This results in the following set of points:

![earthdampts.png](images/earthdampts.png)

After preparing the input file, launch the following Google Colab notebook to upload the Excel input file and 
perform the seepage analysis:

<a href="https://colab.research.google.com/github/njones61/xslope/blob/main/notebooks/xslope_seep.ipynb" target="_"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

Solution: [xslope_earth_dam1.xlsx](https://xslope.readthedocs.io/en/latest/seep/files/xslope_earth_dam1.xlsx)