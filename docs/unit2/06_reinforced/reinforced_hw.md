# Homework - Reinforced Slope Design

The following slope is similar to the geogrid problem we solved in class:

![hw_slope_fig.gif](images/hw_slope_fig.gif)

The objective of this assignment is to design a reinforced slope using geogrids that is both safe and economical. You 
will determine the number of geogrid layers, their elevations, and their lengths. Use XSLOPE to perform the slope stability analysis and to design the reinforcement.

The Excel input for this assignment has been prepared for you:

[xslope_reinforce_hw.xlsx](files/xslope_reinforce_hw.xlsx)

This file contains everything but the reinforcement table.

Use the following XSLOPE Google Colab notebook to perform the analysis and design:

<a href="https://colab.research.google.com/github/njones61/xslope/blob/main/notebooks/xslope_lem.ipynb" target="_"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

**(a) Slope analysis**

Solve the problem assuming the slope does not have any reinforcement. Compute the critical factor of safety using a circular failure surface.

**(b) Reinforcement design**

Design reinforcement for the slope using layers of geogrids. You can add as many layers as you need (up to the limit of 10) 
and you can put them at any combination of elevations. Design a length for the layers, but keep each layer the same length 
in order to simplify the problem. In summary, you will have three basic design parameters:

1. Number of layers
2. Elevations for the layers
3. Lateral length of the layers.

Assume the following parameters:

| Parameter        | Value      |
|------------------|------------|
| Tensile strength | 800 lbs/ft |
| Pullout length   | 4 ft       |
| Cost/ft          | $300       |

Your objective is to design a reinforcement that satisfies the following constraints:

* Minimize the total cost
* FS must be >= 1.5

The total cost is calculated as the sum of the unit cost multiplied by the number of layers and the layer length.



## Submission

Show all of your calculations inside the Excel input file on the "reinforce" sheet. Upload a copy of your Excel file 
to Learning Suite.

## Grading Rubric

**Total: 30 points**

| Criteria | Points |
|----------|:------:|
| Part A: Unreinforced slope FS calculation | 10 |
| Part B: Reinforcement design meets FS ≥ 1.5 | 8 |
| Part B: Design is economical (minimized cost) | 6 |
| Part B: Proper placement of geogrid layers | 3 |
| Documentation and justification of design | 3 |