# Homework - Bishop's Simplified Procedure

For this assignment, you will use the Bishop's Simplified Procedure to analyze the stability of a slope using Excel. You will be solving the same slope we analyzed as a class exercise using the Ordinary Method of Slices (OMS). The slope is partially saturated with a piezometric line.

![oms1.png](images/oms1.png)

The slice details are as follows:

![oms2.png](images/oms2.png)

The factor of safety for the Bishop's Simplified Procedure is calculated as follows:

>>$F = \dfrac{\sum {\left[\dfrac{c'\Delta l + \left(W cos\alpha - u \Delta l cos^2\alpha\right)\tan\phi'}{cos\alpha + \left(sin\alpha\tan\phi'\right)/F}\right]}}{\sum {W\sin\alpha}}$

Where:

>>$c'$ = the effective cohesion at the base of the slice<br>
$\phi'$ = the friction angle at the base of the slice<br>
$\Delta l$ = the length of the base of the slice<br>
$W$ = the weight of the slice<br>
$\alpha$ = the angle of the slope at the base of the slice<br>
$u$ = the pore water pressure at the base of the slice = $\gamma_w \cdot h_w$<br>
$\gamma_w$ = the unit weight of water<br>
$h_w$ = the height of the water above the base of the slice

Note that the factor of safety (F) is a function of the unknown factor of safety (F) itself. Therefore, the calculation must be done iteratively. You can start with an initial guess for F and then update it until the difference between the calculated F and the assumed F is less than a specified tolerance (e.g., 0.0001).

Download the Excel file below and use it to calculate the factor of safety for the slope.

Excel starter file: [bsp.xlsx](files/bsp.xlsx)

## Submission

Upload the completed Excel file to Learning Suite.

## Grading Rubric

**Total: 30 points**

| Criteria | Points |
|----------|:------:|
| Proper setup of iterative solution | 6 |
| Correct calculation of slice base lengths | 4 |
| Correct calculation of slice weights | 4 |
| Correct calculation of pore water pressures | 4 |
| Numerator term calculations | 5 |
| Denominator term calculations | 3 |
| Iterative solution converges to correct FS | 2 |
| Documentation and work shown clearly | 2 |