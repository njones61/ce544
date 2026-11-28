# Equation Sheet

## Hydraulic Head

**Pore Pressure (Static Water Table):**  

>$u = \gamma_w h_w \qquad \gamma_w = \rho g$

$h_w$ = depth below the water table; $\gamma_w$ = 9.81 kN/m³ = 62.4 lb/ft³

**Total Head:**  

>$h = z + \dfrac{v^2}{2g} + \dfrac{u}{\gamma_w} \qquad h_{el} = z \qquad h_{vel} = \dfrac{v^2}{2g} \qquad h_p = \dfrac{u}{\gamma_w}$

$z$ = elevation above the datum (the vertical coordinate is $y$ in the 2D equations below)

**Total Head for Groundwater:**  

>$h = z + \dfrac{u}{\gamma_w}$

## Darcy's Law

**Darcy's Law:**  

>$q = k\,A\,\dfrac{h_2 - h_1}{L} = k\,i\,A \qquad i = \dfrac{\Delta h}{L} \qquad i = -\dfrac{dh}{ds}$

$h_2$ = total head at the inflow end; $h_1$ = total head at the outflow end; $A$ = gross area of flow; $L$ = length of the flow path; $s$ = distance along the flow path

**Discharge and Seepage Velocity:**  

>$v_d = \dfrac{q}{A} = k\,i \qquad v_s = \dfrac{k\,i}{n_e} \qquad n_e = \dfrac{A_f}{A} = \lambda\,n$

$n_e$ = effective porosity ($n_e \approx n$ in sands and gravels); $A_f$ = area that carries flow; $\lambda$ = effective porosity factor

**Travel Time:**  

>$t = \dfrac{L}{v_s} = \dfrac{L\,n_e}{k\,i}$

**Reynolds Number (Darcy valid for Re below about 1 to 10):**  

>$\mathrm{Re} = \dfrac{\rho\,v_d\,d}{\mu}$

$\rho$ = 1000 kg/m³; $\mu \approx 1.0 \times 10^{-3}$ Pa·s; $d \approx d_{10}$

**Equivalent k, Flow Parallel to Layers:**  

>$k_{eq} = \dfrac{\sum_{i=1}^{n} k_i H_i}{\sum_{i=1}^{n} H_i}$

**Equivalent k, Flow Perpendicular to Layers:**  

>$k_{eq} = \dfrac{\sum_{i=1}^{n} H_i}{\sum_{i=1}^{n} H_i/k_i}$

$k_i$, $H_i$ = conductivity and thickness of layer $i$

## Darcy's Law in 2D

**Isotropic Soil:**  

>$v_x = -k\,\dfrac{\partial h}{\partial x} \qquad v_y = -k\,\dfrac{\partial h}{\partial y}$

**Anisotropic Soil:**  

>$v_x = -k_{xx}\,\dfrac{\partial h}{\partial x} - k_{xy}\,\dfrac{\partial h}{\partial y} \qquad v_y = -k_{yx}\,\dfrac{\partial h}{\partial x} - k_{yy}\,\dfrac{\partial h}{\partial y}$

>$k_{xx} = k_r \cos^2\alpha + k_s \sin^2\alpha \qquad k_{yy} = k_r \sin^2\alpha + k_s \cos^2\alpha$

>$k_{xy} = k_{yx} = \dfrac{1}{2}(k_r - k_s)\sin(2\alpha)$

$k_r$ = larger principal conductivity; $k_s$ = smaller principal conductivity, at right angles to it; $\alpha$ = angle of the $k_r$ direction, counterclockwise from $x$

## Flow Nets

**Flow Rate:**  

>$\Delta h = \dfrac{h}{n_e} \qquad q = k\,\dfrac{n_f}{n_e}\,\dfrac{b}{l}\,h$

>$q = k\,\dfrac{n_f}{n_e}\,h \quad (\text{square cells})$

$n_f$ = number of flow channels; $n_e$ = number of equipotential drops (not effective porosity); $h$ = total head lost across the net (not the total head at a point); $\Delta h$ = head lost in one drop; $b$, $l$ = width and length of a cell

**Pore Pressure from a Flow Net:**  

>$h_p = h - h_{el} \qquad u = h_p\,\gamma_w$

Here $h$ = total head at the point (count drops from the upstream side); $h_{el}$ = elevation of the point

**Anisotropic Soil (Transformed Section):**  

>$\underline{x} = x\sqrt{\dfrac{k_y}{k_x}} \qquad \underline{k} = \sqrt{k_x k_y} \qquad q = \underline{k}\,\dfrac{n_f}{n_e}\,h$

$n_f$ and $n_e$ counted on the transformed net; $h$ = total head lost

## Analytical Solutions

**Rectangular Section, Unconfined:**  

>$h = \sqrt{\dfrac{H_D^2 - H_o^2}{D}\,x + H_o^2}$

>$q = k\,\dfrac{H_o^2 - H_D^2}{2D}$

$H_o$, $H_D$ = water depths above the impervious base at $x = 0$ and $x = D$; $D$ = length of the section; $h$ = saturated thickness at $x$; $q$ per unit width

**Rectangular Section with Infiltration:**  

>$h^2 = -\dfrac{e}{k}\,x^2 + C_1 x + C_2 \qquad C_1 = \dfrac{H_D^2 - H_o^2}{D} + \dfrac{e\,D}{k} \qquad C_2 = H_o^2$

>$q_x = \dfrac{k\left(H_o^2 - H_D^2\right)}{2D} - e\left(\dfrac{D}{2} - x\right)$

$e$ = infiltration rate per unit length of the section (negative for evaporation)

**Rectangular Section, Confined:**  

>$q = k\,B\,\dfrac{H_o - H_D}{D}$

$B$ = thickness of the confined layer; $H_o$, $H_D$ = heads at $x = 0$ and $x = D$

**Seepage Through an Earth Dam:**  

>Step 1: $L = \dfrac{d}{\cos(\alpha)} - \sqrt{\dfrac{d^2}{\cos^2(\alpha)} - \dfrac{H^2}{\sin^2(\alpha)}}$

>Step 2: $q = k\,L\tan(\alpha)\sin(\alpha)$

$H$ = depth of the pool; $\Delta$ = horizontal length of the upstream face under water; $a$ = where the pool meets the upstream face; $a'$ = a point $0.3\Delta$ upstream of $a$; $d$ = horizontal distance from $a'$ to the downstream toe; $\alpha$ = angle of the downstream face from horizontal; $L$ = distance up the downstream face from the toe to the exit point

## Wells

**Thiem Equation (Confined Aquifer):**  

>$q = 2\pi kD\,\dfrac{H - H_w}{\ln(R/r_w)}$

>$h = H_w + \dfrac{q}{2\pi kD}\ln(r/r_w) \qquad h = H + \dfrac{q}{2\pi kD}\ln(r/R)$

$D$ = aquifer thickness; $H$ = head before pumping; $H_w$ = head at the well; $r_w$ = well radius; $h$ = head at distance $r$; $R$ = radius of influence

**Drawdown and Transmissivity:**  

>$s = H - h \qquad s_w = H - H_w \qquad T = kD \qquad q = 2\pi T\,\dfrac{s_w}{\ln(R/r_w)}$

$s$ = drawdown at distance $r$; $s_w$ = drawdown at the well

**Confined, Two Observation Wells:**  

>$k = \dfrac{q}{2\pi D\left(h_1 - h_2\right)}\ln(r_1/r_2) \qquad T = \dfrac{q\ln(r_2/r_1)}{2\pi\left(s_1 - s_2\right)}$

$h_1$, $s_1$ = head and drawdown at distance $r_1$; $h_2$, $s_2$ at $r_2$

**Confined, Multiple Wells:**  

>$s = \dfrac{1}{2\pi kD}\sum_{i=1}^{n} q_i \ln(R/r_i) \qquad h = H - \dfrac{1}{2\pi kD}\sum_{i=1}^{n} q_i \ln(R/r_i)$

$q_i$ = pumping rate of well $i$; $r_i$ = distance from well $i$ to the point

**Radius of Influence:**  

>Sichardt (empirical, widely used): $R = 3000\,s_w\,k^{0.5}$

>Kusakin (empirical): $R = 575\,s_w\,(Hk)^{0.5}$

>Lembke (semi-empirical): $R = H\,(k/2N)^{0.5}$

>Weber (semi-empirical): $R = 2.45\,(Hkt/n_e)^{0.5}$

>Kusakin (semi-empirical): $R = 1.9\,(Hkt/n_e)^{0.5}$

$H$ = initial saturated thickness (the aquifer thickness, $D$, if confined), m; $s_w$ = drawdown at the well, m; $k$ = hydraulic conductivity, m/s; $N$ = recharge from rainfall, m/s; $t$ = time since pumping began, s; $n_e$ = effective porosity (storativity, $S$, if confined)

**Unconfined Aquifer:**  

>$q = \dfrac{\pi k\left(H^2 - H_w^2\right)}{\ln(R/r_w)}$

>$h^2 = H^2 - \dfrac{q\ln(R/r)}{\pi k}$

>$k = \dfrac{q\ln(R/r_w)}{\pi\left(H^2 - H_w^2\right)} \qquad k = \dfrac{q\ln(r_2/r_1)}{\pi\left(h_2^2 - h_1^2\right)}$

Heads are measured up from the base of the aquifer, so $h$ = saturated thickness; $H$ = saturated thickness before pumping

**Unconfined, Multiple Wells:**  

>$h^2 = H^2 - \dfrac{1}{\pi k}\sum_{i=1}^{n} q_i \ln(R/r_i)$

**Theis Equation (Confined, Transient):**  

>$s = \dfrac{q}{4\pi T}\,W(u) \qquad u = \dfrac{r^2 S}{4Tt}$

>$W(u) = -0.5772 - \ln u + u - \dfrac{u^2}{2\cdot 2!} + \dfrac{u^3}{3\cdot 3!} - \cdots$

$S$ = storativity; $t$ = time since pumping began; $r$ = distance from the well

**Cooper–Jacob Approximation ($u < 0.05$):**  

>$W(u) \approx -0.5772 - \ln u \qquad s = \dfrac{q}{4\pi T}\ln\left(\dfrac{2.25\,Tt}{r^2 S}\right) \qquad R = 1.5\sqrt{Tt/S}$

**Unconfined, Transient:**  

>$H^2 - h^2 = \dfrac{q}{2\pi k}\,W(u) \qquad u = \dfrac{r^2 S_y}{4kHt} \qquad R = 1.5\sqrt{kHt/S_y}$

$S_y$ = specific yield; good while the drawdown is small compared with $H$

**Several Wells and Rate Changes, Transient:**  

>Confined: $s = \sum_{i,\,j}\dfrac{\Delta q_{ij}}{4\pi T}W\left(u_{ij}\right) \qquad u_{ij} = \dfrac{r_i^2 S}{4T\left(t - t_{ij}\right)}$

>Unconfined: $H^2 - h^2 = \sum_{i,\,j}\dfrac{\Delta q_{ij}}{2\pi k}W\left(u_{ij}\right) \qquad u_{ij} = \dfrac{r_i^2 S_y}{4kH\left(t - t_{ij}\right)}$

$i$ = each well, at distance $r_i$ from the point; $j$ = each change in that well's rate: $\Delta q_{ij}$ is the change, at time $t_{ij}$ (the start of pumping is the first change). A rate change acts as a new well at the same spot pumping the change from $t_{ij}$ on; when a pump stops, add a well pumping $-q$. Include only terms with $t > t_{ij}$.

**Pumping Test over Time, Confined:**  

>$s = \dfrac{2.3\,q}{4\pi T}\log\left(\dfrac{2.25\,Tt}{r^2 S}\right) \qquad T = \dfrac{2.3\,q}{4\pi\,\Delta s} \qquad S = \dfrac{2.25\,T t_0}{r^2}$

**Pumping Test over Time, Unconfined:**  

>$H^2 - h^2 = \dfrac{2.3\,q}{2\pi k}\log\left(\dfrac{2.25\,kHt}{r^2 S_y}\right) \qquad k = \dfrac{2.3\,q}{2\pi\,\Delta\left(H^2 - h^2\right)} \qquad S_y = \dfrac{2.25\,kH t_0}{r^2}$

Plot against the log of time and fit the later points. $\Delta s$ or $\Delta(H^2 - h^2)$ = change over one log cycle; $t_0$ = time where the line crosses zero; $r$ = distance to the observation well

## Construction Dewatering

**Flow to a Trench:** use the Rectangular Section, Unconfined $q$, per unit length of trench ($D$ = distance from the source to the trench).

**Heads Measured from the Low-k Layer:**  

>$H = d_{base} - d_{wt} \qquad h_t = d_{base} - \left(d_{exc} + d_m\right)$

Depths below the ground: $d_{base}$ to the top of the low-k layer (the bottom of the aquifer); $d_{wt}$ to the water table; $d_{exc}$ of the excavation; $d_m$ = extra depth wanted below the bottom of the excavation. $H$ = initial saturated thickness; $h_t$ = target head

**Drainage Time, Anisotropic Soil:**  

>$t_d = \dfrac{4 S_y H}{k_v}$

$k_v$ = vertical conductivity; $t_d$ = about the time for the water table to catch up with the heads at the well screens

**Leakage Through a Cutoff Wall:**  

>$q = k_w\,\dfrac{H^2 - h_t^2}{2b_w} \qquad Q = P\,q$

$k_w$ = conductivity of the wall; $b_w$ = wall thickness; $P$ = length of the wall around the site; $q$ per unit length of wall

## Transient Seepage

**Storativity of a Layer:**  

>$S = S_s\,b$

$S_s$ = specific storage (1/length); $b$ = layer thickness

**Drainage Rate of a Zone:**  

>$\mathrm{rate} \approx \dfrac{k_v}{S_y}$

$k_v$ = vertical conductivity; the rate is how fast the water table can fall through the zone. Compare it with how fast the pool falls.

## Constants and Unit Conversions

- $\gamma_w$ = 9.81 kN/m³ = 62.4 lb/ft³
- $g$ = 9.81 m/s² = 32.2 ft/s²
- 1 m = 3.28 ft
- 1 ft = 12 in
- 1 in = 2.54 cm
- 1 mi = 5280 ft
- 1 kg (mass) = 2.2 lb
- 1 psi = 144 lb/ft²
- 1 cm/s ≈ 2835 ft/day
- 1 day = 86,400 s
- 1 yr = 365 days
- 1 L = 0.001 m³
- 1 ft³ = 7.48 gal
- 1 acre = 43,560 ft²
- 1 acre-ft = 43,560 ft³
