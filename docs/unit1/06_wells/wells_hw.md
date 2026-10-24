# Homework - Well Equations

These problems use the steady well equations and the Theis equation for transient flow. $W(u)$, the Theis well function, is the exponential integral: `scipy.special.exp1(u)` in Python. In Excel, use this formula, with your own cell for `X1` (the starter files also give it):

`=IF(X1>10,0,IF(X1<0.01,-0.5772-LN(X1)+X1-X1^2/4,-0.5772-LN(X1)-SUMPRODUCT((-X1)^ROW($1:$40)/(ROW($1:$40)*FACT(ROW($1:$40))))))`

**1. Pumping test.** A well fully penetrating a confined aquifer **15** m thick is pumped at a constant **12** L/s for one day. The drawdown is recorded at two observation wells, **15** m and **60** m from the pumping well:

| Time since pumping began (min) | s at 15 m (m) | s at 60 m (m) |
|------:|------:|------:|
| 1 | 1.03 | 0.03 |
| 2 | 1.44 | 0.14 |
| 3 | 1.68 | 0.25 |
| 5 | 2.00 | 0.45 |
| 7 | 2.21 | 0.60 |
| 10 | 2.43 | 0.78 |
| 15 | 2.69 | 1.00 |
| 20 | 2.87 | 1.16 |
| 30 | 3.12 | 1.40 |
| 45 | 3.38 | 1.64 |
| 60 | 3.56 | 1.82 |
| 90 | 3.82 | 2.07 |
| 120 | 4.00 | 2.25 |
| 180 | 4.26 | 2.50 |
| 240 | 4.45 | 2.69 |
| 360 | 4.70 | 2.94 |
| 480 | 4.89 | 3.12 |
| 720 | 5.14 | 3.38 |
| 1,000 | 5.35 | 3.59 |
| 1,440 | 5.59 | 3.82 |

a. Plot the drawdown at both observation wells against time, with a log scale for time. Which points don't fall on a straight line, and why?

b. Use the Cooper–Jacob method on each observation well. Fit a straight line through the later points, find $\Delta s$ (the change in drawdown over one log cycle) and $t_0$ (where the line crosses s = 0), and calculate the transmissivity and storativity:

>>$T = \dfrac{2.3\,q}{4\pi\,\Delta s}, \qquad S = \dfrac{2.25\,T t_0}{r^2}$

Check that $u = r^2S/(4Tt)$ is less than 0.05 for the earliest point you used. Do the two wells agree?

c. Now treat the end of the test (1,440 min) as steady and use the Thiem equation with the two observation wells:

>>$T = \dfrac{q\ln\left(r_2/r_1\right)}{2\pi\left(s_1 - s_2\right)}$

Calculate $T$ and $k$ [cm/s]. Then find the radius of influence, $R$, where the drawdown from the Thiem equation reaches zero, and compare it with $R = 1.5\sqrt{Tt/S}$ at the end of the test. What does this tell you about the $R$ you get from a pumping test?

Excel starter file: [pumping_test.xlsx](files/pumping_test.xlsx)

Python starter file: <a href="https://colab.research.google.com/github/njones61/ce544/blob/main/docs/unit1/06_wells/files/pumping_test.ipynb" target="_blank"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

**2. Two wells.** Two wells are installed **60** ft apart in an unconfined aquifer **40** ft thick. The water table is **5** ft below the top of the aquifer, so the saturated thickness is $H$ = 35 ft. The hydraulic conductivity is **0.02** ft/min, and each well (**6** inches in diameter) pumps **35** gallons per minute.

a. Use a radius of influence of **3,000** ft and compute the steady water table along a cross section through both wells. Let x range from −250 to +250 ft in steps of 10 ft, with x = 0 halfway between the wells. At each x, calculate the distance to each well ($r_1$ and $r_2$), the head from each well alone ($h_1$ and $h_2$), and the head with both pumping ($h_{comb}$):

>>$h = \sqrt{H^2 - \dfrac{q \ln\left(R/r\right)}{\pi k}}, \qquad h_{comb} = \sqrt{H^2 - \dfrac{1}{\pi k}\sum_{i=1}^n{q_i \ln\left(R/r_i\right)}}$

Plot $H$, $h_1$, $h_2$, and $h_{comb}$ together. If you have done it correctly, it should look something like this:

![plot.png](images/plot.png)

b. The wells start pumping at the same time. With a specific yield of $S_y$ = **0.15**, compute $h_{comb}$ after **1** day and after **30** days of pumping, using the Theis equation in the same form (the wells still add in $H^2 - h^2$):

>>$h_{comb} = \sqrt{H^2 - \dfrac{1}{2\pi k}\sum_{i=1}^n{q_i W(u_i)}}, \qquad u_i = \dfrac{r_i^2 S_y}{4kHt}$

Plot both with the steady $h_{comb}$ from part a.

c. How long would the wells have to pump for the steady solution with $R$ = 3,000 ft to apply? Use $R = 1.5\sqrt{kHt/S_y}$. Is the steady solution a good model for a project that pumps for a month?

Excel starter file: [two_wells.xlsx](files/two_wells.xlsx)

Python starter file: <a href="https://colab.research.google.com/github/njones61/ce544/blob/main/docs/unit1/06_wells/files/two_wells.ipynb" target="_blank"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

**3. Pump failure.** A single well, **0.3** m in diameter, dewaters a small pit **10** m away in an unconfined aquifer with $H$ = **20** m, $k$ = **2e-4** m/s, and $S_y$ = **0.15**. It pumps **30** L/s. The pit needs the water table at least **3** m below its static level: $h \le$ 17 m at the pit.

a. How long after the pump starts is the pit dewatered? Use the Theis equation in the $H^2 - h^2$ form from Problem 2.

b. What are the heads at the pit and at the well after **3** days of pumping?

c. After 3 days, the power fails and the pump stops. Superposition works in time as well as in space: after the pump stops at $t_p$, the head is the same as if the well kept pumping $q$ and a second well at the same spot started pumping $-q$ at $t_p$:

>>$H^2 - h^2 = \dfrac{q}{2\pi k}\left[W(u) - W(u')\right], \qquad u' = \dfrac{r^2 S_y}{4kH\left(t - t_p\right)}$

Plot the head at the pit from 0 to 6 days. How long after the failure does the water rise back above the required level? What does this mean for the design of a dewatering system?

Excel starter file: [recovery.xlsx](files/recovery.xlsx)

Python starter file: <a href="https://colab.research.google.com/github/njones61/ce544/blob/main/docs/unit1/06_wells/files/recovery.ipynb" target="_blank"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

## Submission

If you completed any of the problems using Google Colab, use the "File|Download|Download .ipynb" command to download your notebook as an .ipynb file.

Combine your PDFs, spreadsheets, and *.ipynb notebook files into a single zip archive and upload it on Learning Suite.

!!! note "Do not put your name or NetID in the file"
    Learning Suite records who submitted each file, so your name is not needed
    inside the file itself. Leaving it out means your work can be graded
    anonymously, which keeps grading fair. This applies to scans and photos
    too — please don't write your name on the page.

## Grading Rubric

**Total: 30 points**

| Criteria | Points |
|----------|:------:|
| Problem 1a: Drawdown vs. log time plot | 2 |
| Problem 1b: T and S by Cooper–Jacob from both wells, with the u check | 5 |
| Problem 1c: T and k by Thiem; R compared with 1.5√(Tt/S) | 4 |
| Problem 2a: Steady two-well cross section | 4 |
| Problem 2b: Transient cross sections at 1 and 30 days | 3 |
| Problem 2c: Pumping time for R = 3,000 ft | 2 |
| Problem 3a: Time to dewater the pit | 2 |
| Problem 3b: Heads at 3 days | 1 |
| Problem 3c: Recovery plot, time to rise above the required level, and its meaning | 5 |
| Documentation and work shown clearly | 2 |
