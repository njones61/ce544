# Homework - Finite Element Seepage Analysis, Confined Conditions

For this exercise, you will build two finite element seepage models of sites with confined (fully saturated) 
conditions. For each problem, start with the base XSLOPE template.

[input_template.xlsx](https://xslope.readthedocs.io/en/latest/inputs/input_template.xlsx)

Make a separate Excel file for each problem. After preparing the input file, upload the file and solve the problem using XSLOPE using the seepage colab notebook:

<a href="https://colab.research.google.com/github/njones61/xslope/blob/main/notebooks/xslope_seep.ipynb" target="_"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

(1) Redo the double sheetpile problem using XSLOPE:

![sheetpile_dual.gif](../10_finelem/images/sheetpile_dual.gif)

Extend your mesh 40 ft both upstream and downstream from the sheetpiles (solve the entire problem, not just one half).

(2) Redo the grout curtain problem we solved in the previous assignment. As before, extend your problem domain 35 m beyond the toe of the levee in both directions. Once again, assume that the levee is relatively impermeable. But this time, assume that the grout curtain extends all the way to bedrock and that the grout curtain is permeable but has a lower K than the foundation.

![levee.gif](../10_finelem/images/levee.gif)

Set up the problem using XSLOPE and analyze the flow rate (total) assuming various K values for the grout curtain. Make a table showing the total flow rate vs. k for the grout curtain where the k values varies as follows:

>>k = 2 m/d (same as no grout curtain)<br>
k = 1 m/d<br>
k = .5 m/d<br>
k = .2 m/d<br>
k = .1 m/d<br>
k = .01 m/d<br>
k = .001 m/d<br>

For each k value, show two flowrates: one for a unit width and one for the total levee section (once again, assume that the levee is **300** m long in the transverse direction). The total flowrate is displayed above the XSLOPE solution plot in the title. Write a paragraph summarizing your observations from the exercise.

## Submission

For part two, submit a copy of the k=0.2 m/d version of your Excel input template. Zip up the XSLOPE input templates and a PNG of the solution for parts 1 and 
2 along with your Word document for part 2 and upload the zip archive via Learning Suite.

## Grading Rubric

| Criteria                                                                             | Points |
|--------------------------------------------------------------------------------------|:------:|
| **Part 1: Double Sheetpile Problem**                                                 |        |
| XSLOPE seepage model set up correctly with proper geometry and mesh                  |   3    |
| Mesh extends 40 ft upstream and downstream from sheetpiles (entire problem solved)   |   2    |
| Boundary conditions correctly applied                                                |   2    |
| **Part 2: Grout Curtain Problem**                                                    |        |
| XSLOPE seepage model set up with domain extending 35 m beyond toe in both directions |   3    |
| Grout curtain extends to bedrock with lower K than foundation                        |   2    |
| Levee modeled as relatively impermeable                                              |   1    |
| Table includes all 7 K values (2, 1, 0.5, 0.2, 0.1, 0.01, 0.001 m/d)                 |   4    |
| Flow rates computed correctly for both unit width and total levee section (300 m)    |   5    |
| Total flow rates extracted from XSLOPE output correctly                              |   2    |
| Paragraph summarizing observations from the exercise                                 |   3    |
| Proper file submission (zipped Excel files and Word document)                        |   3    |
| **Total**                                                                            | **30** |