# Exercise - Stability Analysis with XSLOPE, Part 1

In this exercise, we will solve three slope stability problems using the XSLOPE python package. For each problem, start with the standard Excel input template:

[input_template.xlsx](https://xslope.readthedocs.io/en/latest/inputs/input_template.xlsx)

After preparing each set of inputs, launch the XSLOPE Google Colab notebook for stability analysis and upload your Excel input file and solve:

<a href="https://colab.research.google.com/github/njones61/xslope/blob/main/notebooks/xslope_lem.ipynb" target="_"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

For each problem, explore the results using the variations suggested below.

## Problem 1 - Simple Embankement

Solve the following problem using XSLOPE:

![part1a_fig.png](images/part1a_fig.png)

**Variations:**

a) Distributed load on top of slope. q = 750 psf<br>
b) Tension crack. Depth = 3 ft<br>
c) Submerged by 10 ft depth of water (use distributed load)

## Problem 2 - Simple Slope with Foundation

Solve the following problem using XSLOPE:

![part1b_fig.png](images/part1b_fig.png)

## Problem 3 - Slope with Multiple Layers

Solve the following problem using XSLOPE. Be careful to find the location of the critical circle (global minimum FS).

![part1c_fig.png](images/part1c_fig.png)

**Variations:**

a) Change the cohesion of the lower material to see the effect on the location of the critical circle (slope circle vs. deep circle)