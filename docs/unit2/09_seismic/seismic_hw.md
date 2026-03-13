# Homework - Seismic Slope Stability with XSLOPE

In this assignment, you will use XSLOPE to perform seismic slope stability analyses a problem from an earlier exercises. The seismic coefficient ($k_h$) is entered on the **main** sheet of the Excel input template.

Solve using the XSLOPE Google Colab notebook for stability analysis:

<a href="https://colab.research.google.com/github/njones61/xslope/blob/main/notebooks/xslope_lem.ipynb" target="_"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

Use the Excel template you build for the earth dam problem from your previous XSLOPE homework:

![earthdamfig.gif](../05_xslope/images/earthdamfig.gif)

Start with your existing Excel input file from the XSLOPE LEM Part 2 homework (with the piezometric line).

a) Run the static analysis ($k_h = 0$) and record the factor of safety for the downstream side.

b) Add a seismic coefficient of $k_h = 0.1$ on the **main** sheet and re-run the analysis for the downstream side. Report the new factor of safety.

c) Find the value of $k_h$ that results in a factor of safety of approximately 1.0 for the downstream side (+/- 0.01). Do this by adjusting $k_h$ and re-running the analysis until you converge on the critical value. Report the critical $k_h$ value and corresponding factor of safety.

## Submission

Save a copy of your Excel input file and PNG of the solution plots for part c. Zip up your files into a single zip archive. Upload your zip archive via Learning Suite.

## Grading Rubric

**Total: 30 points**

| Criteria | Points |
|----------|:------:|
| Part a: Static analysis FS for downstream side | 5 |
| Part b: Seismic analysis with $k_h = 0.1$ | 8 |
| Part c: Critical $k_h$ for FS = 1.0 found and reported | 12 |
| Excel input file and PNG solution plot properly submitted in zip archive | 5 |
