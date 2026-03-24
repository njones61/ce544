# Exercise - Rapid Drawdown Analysis with XSLOPE

In this exercise, we will perform a rapid drawdown analysis on the Johnson Reservoir dam using XSLOPE. Rapid drawdown analysis requires a three-stage process that accounts for the change in pore pressures and strengths when the water level in a reservoir is lowered rapidly. For details on the methodology, see:

[XSLOPE Rapid Drawdown Documentation](https://xslope.org/en/latest/lem/rapid/){:target="_blank"}

We will use the Johnson Reservoir dam for this exercise:

![johnson_res.png](../../unit1/10_finelem/images/johnson_res.png)

## Step 1 - Prepare the Input File

Start with the following Excel input template that has been set up for a normal LEM analysis of the Johnson Reservoir dam. You can download the template here:

[xslope_johnson_rapid_start.xlsx](files/xslope_johnson_rapid_start.xlsx)

The template includes the geometry of the dam, the profile lines, and the materials. It also includes a set of seepage boundary conditions for a normal LEM analysis (not rapid drawdown). We will modify the template to set up the rapid drawdown analysis.

### Materials

The material properties are as follows. Note the addition of the $d$ and $\psi$ parameters for the shell and core materials. These are the undrained strength parameters used for the rapid drawdown analysis. Enter the $d$ and $\psi$ parameters shown below for the Core and Foundation. The shell material is assumed to be freely draining, so $d$ and $\psi$ are left blank.

| Material   | $\gamma$ (pcf) | Option | c' (psf) | $\phi'$ (deg) | d (psf) | $\psi$ (deg) |
|:----------:|:-------:|:------:|:-------:|:-------:|:-------:|:-------:|
| Shell      | 130     | mc     | 100     | 35      |         |         |
| Core       | 125     | mc     | 400     | 18      | 500     | 12      |
| Foundation | 127     | mc     | 100     | 27      |  250       |    20     |

Make sure the pore pressure option ($u$) for each material is set to `seep` since we will be using seepage-derived pore pressures.

Verify that the seepage properties are set up for all 3 materials. They should match the following:

| Material   | k1  | k2  | alpha | kr0  | h0 |
|:----------:|:---:|:---:|:-----:|:----:|:--:|
| Shell      | 1   | 1   | 0     | 0.0001 | -1 |
| Core       | 0.001 | 0.001 | 0  | 0.0001 | -1 |
| Foundation | 0.1 | 0.1 | 0     | 0.0001 | -1 |


### Circles

Set up one or more starting circles for the upstream side of the dam (the side affected by rapid drawdown). The one in the starting template is a good option. 

### Distributed Loads

On the **dloads** sheet, set up **two** sets of distributed loads corresponding to the two pool levels. The distributed loads represent the hydrostatic pressure from the water on the upstream face of the dam.

**Solution 1 - Full Pool:** Calculate the distributed load for water at the full pool level (El. 160 ft). (This should already be set up for you.
)

**Solution 2 - Lowered Pool:** Calculate the distributed load for water at the lowered pool level (El. 110 ft).

### Seepage Boundary Conditions

On the **seep bc** sheet, set up **two** sets of seepage boundary conditions -- one for pre-drawdown (full pool) conditions and one for post-drawdown (lowered pool) conditions. XSLOPE supports two solutions on the seep bc sheet for this purpose.

**Solution 1 - Full Pool (Pre-Drawdown):**

- Upstream specified head: H = 160 ft (full pool level)
- Downstream specified head: H = 100 ft (free drainage at the downstream toe)
- Exit face on downstream slope

This should already be set up for you.

**Solution 2 - Lowered Pool (Post-Drawdown):**

- Upstream specified head: H = 110 ft (lowered pool level)
- Downstream specified head: H = 100 ft (free drainage at the downstream toe)
- Exit face on downstream slope

## Step 2 - Run the Seepage Analysis

Upload your Excel input file to the XSLOPE seepage notebook and run the analysis. The notebook will generate two seepage solutions -- one for each set of boundary conditions. Use base_mat=3 when plotting the seepage solutions to focus the flow net cells on the foundation material. 

<a href="https://colab.research.google.com/github/njones61/xslope/blob/main/notebooks/xslope_seep.ipynb" target="_"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

After the seepage analysis completes, download the resulting zip archive. The archive contains the Excel input file, the mesh file, and both seepage solutions.

## Step 3 - Run the Rapid Drawdown Analysis

Upload the zip archive from Step 2 to the XSLOPE LEM notebook. The notebook will automatically detect the two seepage solutions and use them for the three-stage rapid drawdown analysis.

<a href="https://colab.research.google.com/github/njones61/xslope/blob/main/notebooks/xslope_lem.ipynb" target="_"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

Review the results. The notebook will report factors of safety for each stage of the rapid drawdown analysis:

- **Stage 1:** Pre-drawdown stability using drained strengths and full pool pore pressures
- **Stage 2:** Post-drawdown stability using interpolated undrained strengths
- **Stage 3:** Post-drawdown stability check using drained strengths

The critical factor of safety for rapid drawdown is the minimum of Stages 2 and 3.

Solution: [xslope_johnson_rapid_KEY.zip](files/xslope_johnson_rapid_KEY.zip)