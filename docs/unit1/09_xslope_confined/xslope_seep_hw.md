# Homework - Finite Element Seepage Analysis, Confined Conditions

For this assignment, you will build two finite element seepage models of sites with confined (fully saturated) conditions in XSLOPE Studio. Start each with **File → New** in **Seepage** mode, and save each as a separate file with **File → Save As**. Build the mesh with linear triangles (tri3).

(1) Redo the double sheetpile problem using XSLOPE:

![sheetpile_dual.gif](images/sheetpile_dual.gif)

Extend your mesh 40 ft both upstream and downstream from the sheetpiles (solve the entire problem, not just one half).

(2) Consider the following problem involving a permeable foundation below a relatively impermeable levee. Build a 
mesh of just the foundation, including the grout curtain, and perform a seepage anlysis. Extend your problem domain 
35 m beyond the toe of the levee in both directions. Assume that the levee is relatively impermeable (do not include 
it in your problem domain). Assume that the grout curtain extends all the way to bedrock and that the grout curtain 
is permeable but has a different (lower) K than the foundation.

![levee.png](images/levee.png)

Set up the problem in XSLOPE Studio and find the total flow rate for each of these values of K for the grout curtain. Make a table showing the total flow rate vs. k for the grout curtain where the k values varies as follows:

>>k = 2 m/d (same as no grout curtain)<br>
k = 1 m/d<br>
k = .5 m/d<br>
k = .2 m/d<br>
k = .1 m/d<br>
k = .01 m/d<br>
k = .001 m/d<br>

For each k value, show two flowrates: one for a unit width and one for the total levee section (assume that the 
levee is **300** m long in the transverse direction). The total flow rate is shown in the title of the solution plot. Write a paragraph summarizing your observations from the exercise. Put your solution in a word document.

## Submission

Put the following files in a zip archive:

- XSLOPE input file and a PNG of the solution for part 1
- XSLOPE input file and a PNG of the solution for part 2 (for the K = 0.2 m/d solution only)
- Word document with analyis of flow vs K for part 2

Upload the zip archive via Learning Suite.

!!! note "Do not put your name or NetID in the file"
    Learning Suite records who submitted each file, so your name is not needed
    inside the file itself. Leaving it out means your work can be graded
    anonymously, which keeps grading fair. This applies to scans and photos
    too — please don't write your name on the page.

## Grading Rubric

| Criteria                                                                             | Points |
|--------------------------------------------------------------------------------------|:------:|
| **Part 1: Double Sheetpile Problem**                                                 |        |
| XSLOPE seepage model set up correctly with proper geometry and mesh                  |   4    |
| Mesh extends 40 ft upstream and downstream from sheetpiles (entire problem solved)   |   2    |
| Boundary conditions correctly applied                                                |   3    |
| **Part 2: Grout Curtain Problem**                                                    |        |
| XSLOPE seepage model set up with domain extending 35 m beyond toe in both directions |   3    |
| Grout curtain extends to bedrock with lower K than foundation                        |   2    |
| Levee modeled as relatively impermeable                                              |   1    |
| Table includes all 7 K values (2, 1, 0.5, 0.2, 0.1, 0.01, 0.001 m/d)                 |   4    |
| Flow rates computed correctly for both unit width and total levee section (300 m)    |   5    |
| Total flow rates extracted from XSLOPE output correctly                              |   3    |
| Paragraph summarizing observations from the exercise                                 |   3    |
| **Total**                                                                            | **30** |
