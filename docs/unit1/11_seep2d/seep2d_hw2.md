# Homework - SEEP2D Finite Element Model, Unconfined Conditions

For this exercise, you will build a SEEP2D finite element model of **Lost Lake**. It includes a grout curtain, core, 
shell, riprap, filter, and a drain as shown below. 

![lost_lake.png](lost_lake.png)

The material properties are as follows:

| Material        | kx [ft/yr] | Ky [ft/yr] |
|-----------------|------------|------------|
| Core            | 0.1        | 0.1        |
| Glacial Till    | 4000       | 2000       |
| Bedrock         | 2000       | 1000       |
| Rip Rap         | 100,000    | 100,0000   |
| Shell           | 250        | 50         |
| Grouted Bedrock | 250        | 50         |
| Filter   | 1000       | 1000       |
| Drain    | 10,000     | 10,000     |

Build a SEEP2D model of the system. Refine the mesh in the core, bedrock, drain, etc. so that you have small enough 
elements to sufficiently capture the flow in these regions. Select approriate boundary conditions for the model.

The following Excel file contains a set of XY coordinates of each of main features of the cross section above and a 
copy of the 
material properties. Create a SEEP2D coverage in GMS and paste in the XY coordinates as point features and then use 
these points to create your conceptual model and the SEEP2D mesh.

Excel File: [lost_lake_coords.xlsx](lost_lake_coords.xlsx)

## Submission

Zip up your GMS project files and upload. Upload your zip archive via Learning Suite.

!!! Note
    You are allowed to work in pairs on this assignment if you wish. Just copy and upload the assignment when you are done and be sure to make a note who you worked with.