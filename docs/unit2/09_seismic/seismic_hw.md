# Homework - Seismic Slope Stability with XSLOPE

In this assignment, you will use XSLOPE to perform seismic slope stability analyses on problems from earlier exercises. The seismic coefficient ($k_h$) is entered on the **main** sheet of the Excel input template.

Start with the standard Excel input template:

[input_template.xlsx](https://xslope.org/en/latest/inputs/input_template.xlsx)

Solve using the XSLOPE Google Colab notebook for stability analysis:

<a href="https://colab.research.google.com/github/njones61/xslope/blob/main/notebooks/xslope_lem.ipynb" target="_"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

## Problem 1 - Earth Dam with Seismic Loading

Use the earth dam problem from your previous XSLOPE homework:

![earthdamfig.gif](../05_xlope/images/earthdamfig.gif)

Start with your existing Excel input file from the XSLOPE LEM Part 2 homework (with the piezometric line).

a) Run the static analysis ($k_h = 0$) and record the factor of safety for the downstream side.

b) Add a seismic coefficient of $k_h = 0.1$ on the **main** sheet and re-run the analysis for the downstream side. Report the new factor of safety.

c) Find the value of $k_h$ that results in a factor of safety of approximately 1.0 for the downstream side. Do this by adjusting $k_h$ and re-running the analysis until you converge on the critical value. Report the critical $k_h$ value and corresponding factor of safety.

## Problem 2 - Reinforced Slope with Seismic Loading

Use the reinforced slope from the reinforced slopes exercise:

![geogrid_fig.png](../06_reinforced/images/geogrid_fig.png)

Start with your existing XSLOPE input file that includes the geogrid reinforcement.

a) Run the static analysis ($k_h = 0$) and record the factor of safety with reinforcement.

b) Add a seismic coefficient of $k_h = 0.15$ and re-run. Report the new factor of safety.

c) Compare how the seismic loading affects the reinforced slope vs. the unreinforced slope. Run the $k_h = 0.15$ case with the reinforcement removed and compare.

## Submission

Save a copy of your Excel input files and PNGs of the solution plots for each case. Zip up your files into a single zip archive. Upload your zip archive via Learning Suite.

## Grading Rubric

**Total: 30 points**

| Criteria | Points |
|----------|:------:|
| Problem 1a: Static analysis FS for downstream side | 3 |
| Problem 1b: Seismic analysis with $k_h = 0.1$ | 4 |
| Problem 1c: Critical $k_h$ for FS = 1.0 found and reported | 6 |
| Problem 2a: Static analysis FS with reinforcement | 3 |
| Problem 2b: Seismic analysis with $k_h = 0.15$ | 4 |
| Problem 2c: Comparison of reinforced vs. unreinforced under seismic loading | 5 |
| Excel input files and PNG solution plots properly submitted in zip archive | 5 |
