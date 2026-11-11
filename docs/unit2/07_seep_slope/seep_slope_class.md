# Exercise - Seepage/Slope Stability Integration

In this exercise you will go back to two slopes you have already solved with a piezometric line, take their pore pressures from a finite element seepage analysis instead, and compare the factors of safety. Both analyses run in one XSLOPE Studio file. In **Seepage** mode, you build the mesh and run the seepage analysis. Then you set **u** to `seep` for each material, and the stability analysis in **LEM** mode reads its pore pressures from the seepage solution.

## Problem 1 - The Spreadsheet Slope

This is the slope you solved by hand in the method of slices spreadsheets ([Ordinary Method of Slices](../02_limiteq1/limiteq1_class.md), [Janbu and Bishop](../03_limiteq2/limiteq2_class.md), and [Spencer](../03_limiteq2/limiteq2_hw.md)) and in XSLOPE in Problem 1 of [Stability Analysis with XSLOPE, Part 2](../04_xslope/xslope_class2.md), with the same soils and the same piezometric line.

![class_slope.png](../04_xslope/images/class_slope.png){width="950"}

Open this file in XSLOPE Studio with **File → Open**. It is the solution model from that XSLOPE exercise, with the piezometric line and the spreadsheet circle:

[xslope_spreadsheet_slope.xlsx](files/xslope_spreadsheet_slope.xlsx)

### Part a - Piezometric line

Run Spencer's method twice: once with **Analysis** set to **Single surface**, on the spreadsheet circle, and once with **Auto search**. Note both factors of safety and where the critical surface is.

### Part b - Seepage analysis

1. In **Global parameters**, set the time unit to `day`.

2. In the **Materials** editor, set **u** to `seep` for all three soils and enter their seepage properties:

    | Material | k1 = k2 (ft/day) | α | kr0 | h0 |
    |:--------:|:----------------:|:-:|:------:|:--:|
    | soil 1 | 0.5 | 0 | 0.0001 | −1 |
    | soil 2 | 1 | 0 | 0.0001 | −1 |
    | soil 3 | 0.01 | 0 | 0.0001 | −1 |

3. Switch to **Seepage** mode. In **Seep BC**, give the left edge, from (0, 0) to (0, 80), a specified head of 80 ft, where the piezometric line starts. Make the slope face and the ground beyond the toe an exit face, from (150, 84) through (174.7, 64) and (204.3, 40) to (320, 40). The right edge and the base carry no flow.

4. Build the mesh with the default settings, and run the seepage analysis. Where does the phreatic surface meet the slope face? The piezometric line meets it at el. 52.

5. Switch to **LEM** mode, and run the spreadsheet circle and the search again. How do the factors of safety compare with part a, and why?

Solution: [xslope_spreadsheet_slope_SEEP_solution.xlsx](files/xslope_spreadsheet_slope_SEEP_solution.xlsx). On the spreadsheet circle, F = 1.580 with the piezometric line and 1.726 with the seepage solution. The search finds 0.765 with the line, on the lower face, and 0.972 with the seepage, on a longer surface from just behind the crest (x = 146) to the toe. The seepage solution's phreatic surface meets the face at el. 46, 6 ft below the piezometric line, so the line was conservative here. Dry, the same search finds 1.133, so the water is what takes this slope below 1, and the higher water of the piezometric line takes it further.

## Problem 2 - The Earth Dam

This dam is Example 2 in Section 6.13.6 of the textbook (pp. 121–123, Figs. 6.41 to 6.43), the one you analyzed with a piezometric line in Problem 1 of the [XSLOPE LEM, Part 2](../04_xslope/xslope_hw2.md) homework. The book uses it because a piezometric line and a seepage analysis give very different answers for it.

![earth_dam.png](../04_xslope/images/earth_dam.png){width="950"}

Open this file, the model of the downstream side from that homework, with the piezometric line and two starting circles:

[xslope_earth_dam_down.xlsx](files/xslope_earth_dam_down.xlsx)

### Part a - Piezometric line

Run an **Auto search** by Spencer's method, and note the factor of safety and where the critical circle is.

### Part b - Seepage analysis

1. In **Global parameters**, set the time unit to `min`. The book gives the conductivities in ft/min.

2. In the **Materials** editor, set **u** to `seep` for all four materials and enter their seepage properties:

    | Material | k1 = k2 (ft/min) | α | kr0 | h0 |
    |:--------:|:----------------:|:-:|:-----:|:--:|
    | Shell | 1 × 10⁻² | 0 | 0.001 | −5 |
    | Core | 1 × 10⁻⁶ | 0 | 0.001 | −5 |
    | Clay | 1 × 10⁻⁵ | 0 | 0.001 | −5 |
    | Sand | 1 × 10⁻³ | 0 | 0.001 | −5 |

    h0 is −5 ft here instead of the −1 you have used before, because on a dam this size −1 is too sharp for the seepage solution to converge at the default mesh.

3. Switch to **Seepage** mode. In **Seep BC**, give the reservoir a specified head of 302 ft, on the upstream ground and face from (−150, 227) through (0, 227) to (225, 302). Give the ground beyond the downstream toe, from (590, 227) to (740, 227), a specified head of 227 ft, for tailwater at the ground surface. Make the downstream face, from (320, 317) to (590, 227), an exit face. Leave the two side edges and the base with no boundary condition, so no water crosses them.

4. Build the mesh with the default settings, and run the seepage analysis. Look at the head contours under the downstream toe. Is the head in the sand higher or lower than the ground surface there? Which way is the water flowing through the clay?

5. Switch to **LEM** mode, and run the **Auto search** by Spencer's method again. Where is the critical surface now, and why?

Solution: [xslope_earth_dam_down_SEEP_solution.xlsx](files/xslope_earth_dam_down_SEEP_solution.xlsx).

With the piezometric line, the search finds F = 1.558 on a deep circle that reaches the bottom of the clay. With the seepage solution, it goes straight to the downstream toe and finds F = 0.12: a blowout at the toe.

The seepage solution shows why. Water from the reservoir flows through the sand under the dam and has to come up through the clay at the toe. Under the toe, the head in the sand is about 240.6 ft, 13.6 ft above the ground, and at el. 208, in the clay, the pore pressure is 28 ft of water, against 19 ft below a piezometric line at the ground. At the surface, that upward flow leaves the soil with almost no effective stress. A piezometric line can't represent water flowing upward, so it misses the blowout. The book shows that the line overstates the factor of safety on deeper circles too: for circles that reach the bottom of the clay, it gets 1.57 with the line and 1.37 with the seepage.
