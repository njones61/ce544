# Homework - Finite Difference Model of Dual Sheetpiles

(1) Write a spreadsheet to solve for the total head values for the problem shown below using the finite difference technique

![sheetpile_dual.gif](..%2F10_findiff%2Fsheetpile_dual.gif)

Use a 2.5 foot square grid. Extend the grid from the centerline of the cofferdam to 40 feet downstream from the 
outer edge of the cofferdam. This should give you 9 rows and 21 columns in your grid. Don't forget to add an extra grid node at the location of the sheet pile for the first four rows of nodes (21 columns on the bottom half - 22 on the top half). The grid looks like this:

![sheetpile_dual_grid.gif](..%2F10_findiff%2Fsheetpile_dual_grid.gif)

Lay out your spreadsheet so that you have a spreadsheet cell for each node of the grid (for each red dot). Enter an equation for the head at each node. Using the default approach in Excel, you may get an error message about a circular reference. To avoid this and to properly iterate to a solution, do the following:

!!! Note
    Before entering the equations in Excel, select the **Formulas** ribbon, and click on the **Calculation Options** button on the right end of the ribbon and select **Manual**. This will prevent Excel from automatically recalculating. You can select **Calculate Now** from the Formulas ribbon to recalculate the sheet or you can hit the **F9** button. Do this repeatedly until you converge.

(2) Add a section to your spreadsheet to compute the flow rate from your solution (assume a unit thickness in the transverse direction). To do this, compute the flux across the outgoing boundary. Using the head values at nodes on and adjacent to the nodes on the boundary to estimate the hydraulic gradient (dh/dx or dh/dy). Using this value, the appropriate contributing area, and Darcy's law, compute the flow rate. Remember to hit the F9 key to update your calculations.

## Submission

Upload your completed spreadsheet via Learning Suite after we grade it together in class.

## Grading Rubric

Self-grade your assignment using the following rubric. Enter your points in the "Submission notes" section for the assignment on Learning Suite when you upload your file. You can use fractional points if you like (e.g. 2.5).

| Criteria                                    | Points |
|---------------------------------------------|:------:|
| Completed on time and all or mostly correct |   3    |
| Completed more than half of assignment      |   2    |
| Made an effort                              |   1    |
| Did nothing                                 |   0    |