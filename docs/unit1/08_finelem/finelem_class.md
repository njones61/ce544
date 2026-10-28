# Exercise - The Finite Element Method by Hand

In this exercise you will carry out the finite element method by hand on two small problems: a one-dimensional problem with three elements, solved all the way to the heads and the flow, and a single linear triangle, whose element matrix you will build from its coordinates. Work the problems on paper or in Excel.

## Part 1 - Three Layers in Series

Water flows horizontally through three soil layers in series, each 1 m² in cross section. The head is held at 12 m at the left end and at 3 m at the right end.

| Element | Nodes | Length L (m) | k (m/day) |
|:---:|:---:|:---:|:---:|
| a | 1–2 | 2 | 4 |
| b | 2–3 | 1 | 0.5 |
| c | 3–4 | 3 | 6 |

1. Compute the conductance of each element, $C = kA/L$.
2. Write each element's 2 × 2 matrix,

    >>$\begin{Bmatrix} q_1 \\ q_2 \end{Bmatrix} = \begin{bmatrix} C & -C \\ -C & C \end{bmatrix} \begin{Bmatrix} h_1 \\ h_2 \end{Bmatrix}$

    and assemble the three into the 4 × 4 global matrix $[T]$, element by element.

3. Apply the boundary conditions: replace the rows for nodes 1 and 4 with $h_1 = 12$ and $h_4 = 3$, and move the known heads to the right-hand side of the rows for nodes 2 and 3.
4. Solve the two remaining equations for $h_2$ and $h_3$.
5. Compute the flow at nodes 1 and 4 from the original rows of $[T]$. What do their signs mean?

## Part 2 - Checks

1. Check your flow against the layered systems lecture. For flow across layers, the equivalent conductivity is $k_{eq} = L / \sum (L_i/k_i)$, where $L$ is the total length, and the flow is $q = k_{eq} A \Delta h / L$.
2. Split element b into two elements, each 0.5 m long, and solve again (five nodes). Do the heads at the original nodes change? Why would that be true for any one-dimensional problem with linear elements?

## Part 3 - One Linear Triangle

A linear triangle has its nodes at $i$ = (0, 0), $j$ = (4, 0), and $k$ = (0, 2), in meters. The soil is isotropic, $k$ = 2 m/day, and the element is 1 m thick.

1. Compute the area $\Delta$ and the $[B]$ matrix:

    >>$\left[B\right] = \dfrac{1}{2\Delta}\begin{bmatrix} y_j - y_k & y_k - y_i & y_i - y_j \\ x_k - x_j & x_i - x_k & x_j - x_i \end{bmatrix}$

2. Compute the element transmissibility matrix, $[T] = \Delta [B]^T [K] [B]$. Check that it is symmetric and that each row adds to zero. Why must the rows add to zero?
3. With heads $h_i$ = 10 m, $h_j$ = 10 m, and $h_k$ = 6 m, compute the nodal flows $\{Q\} = [T]\{h\}$. Which way is the water flowing through the element, and why is the flow at node $j$ zero?
