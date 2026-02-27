# Homework - Reliability Analysis

Consider the following slope:

![hw_fig.png](images/hw_fig.png)

Each of the non-zero parameters have been anayzed and a standard deviation has been estimated for each as follows:

| Parameter  | MLV | $\sigma$ |
|:----------:|:---:|:--------:|
|  $\phi_1$  | 30  |   4.5    |
|   $c_1$    | 100 |    20    |
| $\gamma_1$ | 125 |   9.1    |
|   $Su_2$   | 700 |   150    |
| $\gamma_2$ | 115 |   7.2    |

Perform a reliability analysis on the slope to find both the reliability (R) and probability of failure (Pf). Use the Taylor Series Method to find $COV_F$.

Start with the standard Excel input template:

[input_template.xlsx](https://xslope.org/en/latest/inputs/input_template.xlsx)

Perform your slope stability calculations using the XSLOPE Google Colab notebook:

<a href="https://colab.research.google.com/github/njones61/xslope/blob/main/notebooks/xslope_lem.ipynb" target="_"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

Summarize all of your calculations in a spreadsheet.

## Submission

Zip up a copy of your XSLOPE Excel input file (with MLV parameters) and the spreadsheet into a single zip archive. Upload your zip archive via Learning Suite.

## Grading Rubric

**Total: 30 points**

| Criteria | Points |
|----------|:------:|
| XSLOPE model setup with MLV parameters | 5 |
| FS calculation with MLV parameters | 4 |
| Partial derivatives for each parameter | 6 |
| COV_F calculation using Taylor Series Method | 5 |
| Standard deviation of F calculation | 3 |
| Reliability (R) calculation | 3 |
| Probability of failure (Pf) calculation | 3 |
| Documentation in spreadsheet | 1 |
