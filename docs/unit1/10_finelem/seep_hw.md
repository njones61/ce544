# Homework - Finite Element Seepage Analysis, Unconfined Conditions

For this exercise, you will build a finite element seepage model of the **Lost Lake** dam. Start with the base XSLOPE template and modify it to fit the cross section shown below.

[input_template.xlsx](https://xslope.readthedocs.io/en/latest/inputs/input_template.xlsx)

Once the input file is complete, upload the file and solve the problem using XSLOPE using the seepage colab notebook:

<a href="https://colab.research.google.com/github/njones61/xslope/blob/main/notebooks/xslope_seep.ipynb" target="_"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

The Lost Lake Dam includes a grout curtain, core, 
shell, riprap, filter, and a drain as shown below.

![lost_lake.png](images/lost_lake.png){width="1400"}

The water is impounded on the left side of the cross section at **H = 225 ft**. Water seeping out of the right side drains freely.

The material properties are as follows:

| Material        | kx [ft/yr] | Ky [ft/yr] | 
|-----------------|------------|-----------|
| Core            | 0.1        | 0.1       |
| Glacial Till    | 4000       | 2000      |
| Bedrock         | 2000       | 1000      |
| Rip Rap         | 100,000    | 100,000   |
| Shell           | 250        | 50        |
| Grouted Bedrock | 250        | 250        |
| Filter   | 1000       | 1000      |
| Drain    | 10,000     | 10,000    |

For each material, use:

>>$\alpha = 0.0$<br>$k_{r0} = 0.0001$<br>$h_0 = -1$

Use elements that are sufficiently small to capture the details in the thin zones. Select appropriate boundary conditions for the model.

You will need to create your profile lines carefully to ensure that the model is well-posed. 

## Problem Geometry

The coordinates of the points making up the center part of the cross section are shown below.

![lost_lake_coords_main.png](images/lost_lake_coords_main.png)

The coordinates of the left and right sides of the cross section are shown below:

![lost_lake_coords_sides.png](images/lost_lake_coords_sides.png)

## Tips

Here are some tips for setting up the problem:

1. You only need 8 materials. Use the 8 materials from the list above.
2. You will need 12 profile lines. Sometimes multiple profile lines link to the same material. Just enter the material ID at the top of the profile. The name will then appear.
3. Make sure you enter the coordinates in the correct order (left to right).
4. Profile lines should always be listed from top to bottom. Each line projects down to lower lines to define the regions to be filled in as it creates the polygons. Each line is strictly above all of the subsequent (or at least - not below).
5. When you define the profile lines, you only include the line segments on top of the zone. You should not include vertical edges on the left and right ends of the lines. For example, the profile line for the grouted bedrock (blue zone) is only two points. However, you can have vertical lines in the middle of a profile line if necessary - bedrock (orange zone at the bottom) for example.

## Submission

Create a PNG of the solution with 25 head contours and use base material = bedrock. Zip up your Excel file and a PNG of the solution plot and upload your zip archive via Learning Suite.

!!! Note
    You are allowed to work in pairs on this assignment if you wish. Just copy and upload the assignment when you are done and be sure to make a note who you worked with.

## Grading Rubric

| Criteria                                                                              | Points |
|---------------------------------------------------------------------------------------|:------:|
| XSLOPE Excel template modified correctly for Lost Lake dam geometry                  |   4    |
| 12 profile lines created in correct order (top to bottom)                            |   4    |
| Points on each profile line listed in correct order (left to right)                  |   2    |
| All 12 materials defined with correct hydraulic conductivity values (kx, ky)         |   5    |
| Material parameters (α, kr0, h0) set correctly for all materials                     |   2    |
| Boundary conditions appropriately selected (H=225 ft left, free drainage right)      |   3    |
| Element mesh sufficiently refined to capture details in thin zones                   |   3    |
| Model solves successfully without errors                                              |   2    |
| PNG output shows 25 head contours with base material = bedrock (12)                  |   3    |
| Proper file submission (zipped Excel file and PNG solution)                          |   2    |
| **Total**                                                                             | **30** |