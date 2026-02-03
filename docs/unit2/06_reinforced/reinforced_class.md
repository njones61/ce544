# Exercise - Reinforced Slopes

In this exercise, we will explore how to simulate soil reinforcement from layers of geogrid material built into an 
embankement. This problem was featured in the user manual for the UTEXASED slope stability analysis software 
developed by Stephen G. Wright at the University of Texas at Austin.

![geogrid_fig.png](images/geogrid_fig.png)

(1) Set up the problem and solve for the factor of safety using XSLOPE without the reinforcement. Note the factor of 
safety. The toe of the slope corresponds to (0, 0) and the top of the slope corresponds to (30, 24). Extend the 
problem to the left to x = -30 ft and to the right to x = 100 ft. Compute the factor of safety for the slope with no reinforcement.

(2) Solve again but include the impact of the geogrid layers. Assume that each layer of geogrid is 20 ft long and the full 
tensile force in the geogrids develops over a length of 4 ft. Set up your reinforcement table with formulas such 
that the length of the reinforcement, tensile strength, and slope angle are all variables. Compare the factor of 
safety and the location of the critical circle to the solution without the reinforcement.

(3) Experiment with following parameters to determine the impact of each on the factor of safety:

>(a) Change the tensile strength to 1200 lbs/ft.<br> 
>(b) Change the length of the geogrid layers to 30 ft.<br>
>(c) Experiment with different values of the slope angle. 

Start with the standard Excel input template:

[input_template.xlsx](https://xslope.readthedocs.io/en/latest/inputs/input_template.xlsx)

After the input file, launch the XSLOPE Google Colab notebook for stability analysis and upload your Excel input file 
and solve:

<a href="https://colab.research.google.com/github/njones61/xslope/blob/main/notebooks/xslope_lem.ipynb" target="_"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

Solution: [xslope_reinforce.xlsx](https://xslope.readthedocs.io/en/latest/lem/samples/files/xslope_reinforce.xlsx)