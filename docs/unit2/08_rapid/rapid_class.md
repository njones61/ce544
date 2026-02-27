# Exercise - Rapid Drawdown Analysis with XSLOPE

In this exercise, we will perform a rapid drawdown analysis on the Johnson Reservoir dam using XSLOPE. Rapid drawdown analysis requires a three-stage process that accounts for the change in pore pressures and strengths when the water level in a reservoir is lowered rapidly. For details on the methodology, see:

[XSLOPE Rapid Drawdown Documentation](https://xslope.org/en/latest/lem/rapid/){:target="_blank"}

We will use the Johnson Reservoir dam for this exercise:

![johnson_res.png](../../unit1/10_finelem/images/johnson_res.png)

## Step 1 - Prepare the Input File

Start with the standard Excel input template:

[input_template.xlsx](https://xslope.org/en/latest/inputs/input_template.xlsx)

Set up the input file for the Johnson Reservoir dam using the following parameters.

### Profile Lines and Materials

The material properties are as follows. Note the addition of the $d$ and $\psi$ parameters for the shell and core materials. These are the undrained strength parameters used for the rapid drawdown analysis. The foundation material is assumed to be freely draining, so $d$ and $\psi$ are left blank.

| Material   | $\gamma$ (pcf) | Option | c' (psf) | $\phi'$ (deg) | d (psf) | $\psi$ (deg) |
|:----------:|:-------:|:------:|:-------:|:-------:|:-------:|:-------:|
| Shell      | 130     | mc     | 100     | 35      | 50      | 25      |
| Core       | 125     | mc     | 400     | 18      | 200     | 12      |
| Foundation | 127     | mc     | 100     | 27      |         |         |

Set the pore pressure option ($u$) for each material to `seep` since we will be using seepage-derived pore pressures.

### Seepage Boundary Conditions

On the **seep bc** sheet, set up **two** sets of seepage boundary conditions -- one for pre-drawdown (full pool) conditions and one for post-drawdown (lowered pool) conditions. XSLOPE supports two solutions on the seep bc sheet for this purpose.

**Solution 1 - Full Pool (Pre-Drawdown):**

- Upstream specified head: H = 302 ft (full pool level)
- Downstream specified head: H = 227 ft
- Exit face on downstream slope

**Solution 2 - Lowered Pool (Post-Drawdown):**

- Upstream specified head: H = 260 ft (lowered pool level)
- Downstream specified head: H = 227 ft
- Exit face on downstream slope

### Distributed Loads

On the **dloads** sheet, set up **two** sets of distributed loads corresponding to the two pool levels. The distributed loads represent the hydrostatic pressure from the water on the upstream face of the dam.

**Solution 1 - Full Pool:** Calculate the distributed load for water at the full pool level (El. 302 ft).

**Solution 2 - Lowered Pool:** Calculate the distributed load for water at the lowered pool level (El. 260 ft).

### Circles

Set up one or more starting circles for the upstream side of the dam (the side affected by rapid drawdown).

## Step 2 - Run the Seepage Analysis

Upload your Excel input file to the XSLOPE seepage notebook and run the analysis. The notebook will generate two seepage solutions -- one for each set of boundary conditions.

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
