# Exercise - Analytical Solutions

## Part 1 - Dupuit Problem

Consider the following profile representing the classic Dupuit problem with a rectangular cross-section:

![rect_section.png](rect_section.png){width=700px}

The flow through the section is given by:

$$Q = K \frac{\left(H_o^2 - H_D^2\right)}{2D}$$

And the head (h) as a function of x is given by:

$$h = \sqrt{\frac{\left(H_o^2 - H_D^2\right)}{2D} x + H_o^2}$$


Assume following parameters:

<div style="width: 30%;" markdown="1">

| Parameter | Value | Units |
|-----------|-------|-------|
| K         | 0.001 | cm/s  |
| D         | 100   | m     |
| \(H_o\)   | 5     | m     |
| \(H_D\)   | 1     | m     |

</div>



Calculate the flow rate (Q) and generated a plot of the head (h) as a function of x for the parameter values given above.

### Excel Solution

Excel starter file: [dupuit.xlsx](dupuit.xlsx)

Excel solution: [dupuit_KEY.xlsx](dupuit_KEY.xlsx)

### Python Solution

Python starter file: <a href="https://colab.research.google.com/github/njones61/ce544/blob/main/docs/unit1/07_analytical/dupuit.ipynb" target="_blank"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

Python solution: <a href="https://colab.research.google.com/github/njones61/ce544/blob/main/docs/unit1/07_analytical/dupuit_KEY.ipynb" target="_blank"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>
 
## Part 2 - Flow Through an Earth Dam

Consider the following profile representing the flow through an earth dam:

![earthdam.png](earthdam.png){width=700px}

The flow through the section is given by:

$$
q = k L \tan(\alpha) \sin(\alpha)
$$

where:

$$L = \frac{d}{cos(\alpha)}-\sqrt{\frac{d^2}{cos^2(\alpha)}-\frac{H^2}{sin^2(\alpha)}}$$

Solve for the flow rate (q) using the set of parameters contained in the following Excel file.

Excel starter file: [earthdam.xlsx](earthdam.xlsx)

Excel solution: [earthdam_KEY.xlsx](earthdam_KEY.xlsx)
