# Homework - Analytical Solution to Profile Model

In class we discussed the Dupuit problem with an infiltration term (e):

![rect_section_e.gif](images/rect_section_e.gif)

The equation for the flow rate as a function of x is:

>>$Q = k\dfrac{\left(H_o^2-H_D^2\right)}{2D}-e\left(\dfrac{D}{2}-x\right)$

Derive an equation for h in terms of x. Start with:

>>$h^2 = -\dfrac{e}{k}x^2 + C1x + C2$

and insert the left and right boundary conditions and solve for C1 and C2. Solve the resulting equation for h.

Put your solution in a word document and show each of your steps. Or you can derive on paper and submit a scan or photo of your work.

Once you have found your equation for h, created a modified version of the solution to the Dupuit problem that we did in class that uses your new equation for h. You can do it in Python or Excel. 

Excel starter file: [dupuit_with_recharge.xlsx](files/dupuit_with_recharge.xlsx)

Python starter file: <a href="https://colab.research.google.
com/github/njones61/ce544/blob/main/docs/unit1/05_analytical/dupuit_with_recharge.ipynb" target="_blank"><img 
src="https://colab.
research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

## Submission

Submit your Word document with your derivation and your Excel file or a link to your Colab notebook in Learning Suite. Upload your files after.

## Grading Rubric

**Total: 30 points**

| Criteria | Points |
|----------|:------:|
| Derivation: Applying left boundary condition | 4 |
| Derivation: Applying right boundary condition | 4 |
| Derivation: Solving for C1 | 3 |
| Derivation: Solving for C2 | 3 |
| Derivation: Final equation for h(x) | 4 |
| Implementation: Excel or Python solution correctly set up | 6 |
| Implementation: Results plotted and verified | 4 |
| Documentation and clarity of work | 2 |