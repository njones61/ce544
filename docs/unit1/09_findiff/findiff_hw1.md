# Homework - Finite Difference Model of Dual Sheetpiles

(1) Write a spreadsheet to solve for the total head values for the problem shown below using the finite difference technique

![sheetpile_dual.gif](sheetpile_dual.gif)

Use a 2.5 foot square grid. Extend the grid from the centerline of the cofferdam to 40 feet downstream from the 
outer edge of the cofferdam. This should give you 9 rows and 21 columns in your grid. Don't forget to add an extra grid node at the location of the sheet pile for the first four rows of nodes (21 columns on the bottom half - 22 on the top half). The grid looks like this:

![sheetpile_dual_grid.gif](sheetpile_dual_grid.gif)

Lay out your spreadsheet so that you have a spreadsheet cell for each node of the grid (for each red dot). Enter an equation for the head at each node. Using the default approach in Excel, you may get an error message about a circular reference. To avoid this and to properly iterate to a solution, do the following:

!!! Note
    Before entering the equations in Excel, select the **Formulas** ribbon, and click on the **Calculation Options** button on the right end of the ribbon and select **Manual**. This will prevent Excel from automatically recalculating. You can select **Calculate Now** from the Formulas ribbon to recalculate the sheet or you can hit the **F9** button. Do this repeatedly until you converge.

(2) Add a section to your spreadsheet to compute the flow rate from your solution (assume a unit thickness in the transverse direction). To do this, compute the flux across the outgoing boundary. Using the head values at nodes on and adjacent to the nodes on the boundary to estimate the hydraulic gradient (dh/dx or dh/dy). Using this value, the appropriate contributing area, and Darcy's law, compute the flow rate. Remember to hit the F9 key to update your calculations.

## Submission

Upload your completed spreadsheet via Learning Suite after we grade it together in class.

## Grading Rubric

| Criteria                                                                              | Points |
|---------------------------------------------------------------------------------------|:------:|
| Grid layout correct (9 rows × 21/22 columns, 2.5 ft spacing, extra node at sheet pile) |   5    |
| Finite difference equations correctly entered at all interior nodes                   |   10   |
| Boundary conditions correctly applied at all boundary nodes                           |   5    |
| Excel calculation setup (manual calculation mode, iterative solution converges)      |   3    |
| Flow rate calculation section included with correct flux computation                  |   4    |
| Hydraulic gradient correctly estimated using adjacent node heads                      |   2    |
| Darcy's law correctly applied with appropriate contributing area                      |   1    |
| **Total**                                                                             | **30** |