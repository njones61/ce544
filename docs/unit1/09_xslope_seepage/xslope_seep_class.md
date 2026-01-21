# Exercise - XSLOPE Seepage Analysis

For this exercise, we will perform a seepage analysis using XSLOPE for problem with confined (fully-saturated) 
conditions. The problem corresponds to the clay-blanket sheetpile case that we analyzed in our flow net section:

![sheetpilefigure.png](images/sheetpilefigure.png)

We will first prepare the problem inputs in an XSLOPE Excel input file. Start with the standard template:

[input_template.xlsx](https://xslope.readthedocs.io/en/latest/inputs/input_template.xlsx)

Use the Excel file to specify the 
material properties, define the 
geometry using a profile line, and assign 
boundary 
conditions. As you set up the problem, you will need to define a local coordinate system. Set up your coordinate system as follows:

![sheetpilepoints.png](images/sheetpilepoints.png)

After preparing the input file, launch the following Google Colab notebook to upload the Excel input file and 
perform the seepage analysis:

<a href="https://colab.research.google.com/github/njones61/xslope/blob/main/notebooks/xslope_seep.ipynb" target="_"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

Solution: [xslope_clay_blanket.xlsx](https://xslope.readthedocs.io/en/latest/seep/files/xslope_clay_blanket.xlsx)