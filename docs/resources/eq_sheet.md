# Equation Sheet

## Hydraulic Head

**Pore Pressure (Static Water Table):**  

>$u = \gamma_w h_w \qquad \gamma_w = \rho g$

**Total Head:**  

>$h = z + \dfrac{v^2}{2g} + \dfrac{u}{\gamma_w} \qquad h_{el} = z \qquad h_{vel} = \dfrac{v^2}{2g} \qquad h_p = \dfrac{u}{\gamma_w}$

**Total Head for Groundwater:**  

>$h = z + \dfrac{u}{\gamma_w}$

## Darcy's Law

**Darcy's Law:**  

>$q = k\,A\,\dfrac{h_2 - h_1}{L} = k\,i\,A \qquad i = \dfrac{\Delta h}{L}$

>$i = -\dfrac{dh}{ds} \qquad q = -k\,A\,\dfrac{dh}{ds}$

**Discharge and Seepage Velocity:**  

>$v_d = \dfrac{q}{A} = k\,i$

>$v_s = \dfrac{v_d}{n} = \dfrac{k\,i}{n} \qquad v_s = \dfrac{k\,i}{n_e} \qquad n_e = \dfrac{A_f}{A} = \lambda\,n$

**Travel Time:**  

>$t = \dfrac{L}{v_s} = \dfrac{L\,n_e}{k\,i}$

**Reynolds Number (Darcy valid for Re below about 1 to 10):**  

>$\mathrm{Re} = \dfrac{\rho\,v_d\,d}{\mu}$

**Equivalent k, Flow Parallel to Layers:**  

>$k_{eq} = \dfrac{\sum_{i=1}^{n} k_i H_i}{\sum_{i=1}^{n} H_i}$

**Equivalent k, Flow Perpendicular to Layers:**  

>$k_{eq} = \dfrac{\sum_{i=1}^{n} H_i}{\sum_{i=1}^{n} H_i/k_i}$

## Governing Equations

**Darcy's Law in 2D (Isotropic):**  

>$v_x = -k\,\dfrac{\partial h}{\partial x} \qquad v_y = -k\,\dfrac{\partial h}{\partial y}$

**Anisotropic Conductivity ($k_r$ at angle $\alpha$ counterclockwise from $x$):**  

>$v_x = -k_{xx}\,\dfrac{\partial h}{\partial x} - k_{xy}\,\dfrac{\partial h}{\partial y} \qquad v_y = -k_{yx}\,\dfrac{\partial h}{\partial x} - k_{yy}\,\dfrac{\partial h}{\partial y}$

>$k_{xx} = k_r \cos^2\alpha + k_s \sin^2\alpha \qquad k_{yy} = k_r \sin^2\alpha + k_s \cos^2\alpha$

>$k_{xy} = k_{yx} = \dfrac{1}{2}(k_r - k_s)\sin(2\alpha)$

**Conservation of Mass:**  

>$\mathrm{inflow} - \mathrm{outflow} = \dfrac{\Delta\,\mathrm{storage}}{\Delta t} + \mathrm{sources},\ \mathrm{sinks}$

**Steady Saturated Flow (Principal Axes):**  

>$k_x\dfrac{\partial^2 h}{\partial x^2} + k_y\dfrac{\partial^2 h}{\partial y^2} + k_z\dfrac{\partial^2 h}{\partial z^2} = 0$

**Laplace Equation:**  

>$\dfrac{\partial^2 h}{\partial x^2} + \dfrac{\partial^2 h}{\partial y^2} = 0$

## Flow Nets

**Flow Rate:**  

>$\Delta h = \dfrac{h}{n_e} \qquad q = k\,\dfrac{n_f}{n_e}\,\dfrac{b}{l}\,h$

>$q = k\,\dfrac{n_f}{n_e}\,h \quad (\text{square cells})$

**Pore Pressure from a Flow Net:**  

>$h_p = h - h_{el} \qquad u = h_p\,\gamma_w$

**Anisotropic Soil (Transformed Section):**  

>$\underline{x} = x\sqrt{\dfrac{k_y}{k_x}} \qquad \underline{k} = \sqrt{k_x k_y} \qquad q = \underline{k}\,\dfrac{n_f}{n_e}\,h$

## Analytical Solutions

**Dupuit–Forchheimer Equation:**  

>$\dfrac{\partial^2 (h^2)}{\partial x^2} = 0$

**Rectangular Section, Unconfined:**  

>$h = \sqrt{\dfrac{H_D^2 - H_o^2}{D}\,x + H_o^2}$

>$q = k\,\dfrac{H_o^2 - H_D^2}{2D}$

**Rectangular Section with Infiltration:**  

>$h^2 = -\dfrac{e}{k}\,x^2 + C_1 x + C_2$

>$q_x = \dfrac{k\left(H_o^2 - H_D^2\right)}{2D} - e\left(\dfrac{D}{2} - x\right)$

**Rectangular Section, Confined:**  

>$q = k\,B\,\dfrac{H_o - H_D}{D}$

**Seepage Through an Earth Dam ($a'$ at $0.3\Delta$ upstream of $a$):**  

>$q = k\,L\tan(\alpha)\sin(\alpha) \quad (\text{equation 1})$

>$L = \dfrac{d}{\cos(\alpha)} - \sqrt{\dfrac{d^2}{\cos^2(\alpha)} - \dfrac{H^2}{\sin^2(\alpha)}} \quad (\text{equation 2})$

## Wells

**Thiem Equation (Confined Aquifer):**  

>$q = 2\pi kD\,\dfrac{H - H_w}{\ln(R/r_w)}$

>$h = H_w + \dfrac{q}{2\pi kD}\ln(r/r_w) \qquad h = H + \dfrac{q}{2\pi kD}\ln(r/R)$

**Drawdown and Transmissivity:**  

>$s = H - h \qquad s_w = H - H_w \qquad T = kD \qquad q = 2\pi T\,\dfrac{s_w}{\ln(R/r_w)}$

**Confined, k from Observation Wells:**  

>$k = \dfrac{q}{2\pi D\left(h_1 - h_2\right)}\ln(r_1/r_2)$

**Confined, Multiple Wells:**  

>$s = \dfrac{1}{2\pi kD}\sum_{i=1}^{n} q_i \ln(R/r_i) \qquad h = H - \dfrac{1}{2\pi kD}\sum_{i=1}^{n} q_i \ln(R/r_i)$

**Radius of Influence ($H$ and $s_w$ in m; $k$ and $N$ in m/s; $B$ for $H$ and $S$ for $n_e$ if confined):**  

>Sichardt (empirical, widely used): $R = 3000\,s_w\,k^{0.5}$

>Kusakin (empirical): $R = 575\,s_w\,(Hk)^{0.5}$

>Lembke (semi-empirical): $R = H\,(k/2N)^{0.5}$

>Weber (semi-empirical): $R = 2.45\,(Hkt/n_e)^{0.5}$

>Kusakin (semi-empirical): $R = 1.9\,(Hkt/n_e)^{0.5}$

**Unconfined Aquifer:**  

>$q = \dfrac{\pi k\left(H^2 - H_w^2\right)}{\ln(R/r_w)}$

>$h^2 = H^2 - \dfrac{q\ln(R/r)}{\pi k}$

>$k = \dfrac{q\ln(R/r_w)}{\pi\left(H^2 - H_w^2\right)} \qquad k = \dfrac{q\ln(r_2/r_1)}{\pi\left(h_2^2 - h_1^2\right)}$

**Unconfined, Multiple Wells:**  

>$h^2 = H^2 - \dfrac{1}{\pi k}\sum_{i=1}^{n} q_i \ln(R/r_i)$

**Theis Equation (Confined, Transient):**  

>$s = \dfrac{q}{4\pi T}\,W(u) \qquad u = \dfrac{r^2 S}{4Tt}$

>$W(u) = -0.5772 - \ln u + u - \dfrac{u^2}{2\cdot 2!} + \dfrac{u^3}{3\cdot 3!} - \cdots$

**Cooper–Jacob Approximation ($u < 0.05$):**  

>$W(u) \approx -0.5772 - \ln u \qquad s = \dfrac{q}{4\pi T}\ln\left(\dfrac{2.25\,Tt}{r^2 S}\right) \qquad R = 1.5\sqrt{Tt/S}$

**Unconfined, Transient:**  

>$H^2 - h^2 = \dfrac{q}{2\pi k}\,W(u) \qquad u = \dfrac{r^2 S_y}{4kHt} \qquad R = 1.5\sqrt{kHt/S_y}$

**Pumping Test over Time, Confined:**  

>$s = \dfrac{2.3\,q}{4\pi T}\log\left(\dfrac{2.25\,Tt}{r^2 S}\right) \qquad T = \dfrac{2.3\,q}{4\pi\,\Delta s} \qquad S = \dfrac{2.25\,T t_0}{r^2}$

**Pumping Test over Time, Unconfined:**  

>$H^2 - h^2 = \dfrac{2.3\,q}{2\pi k}\log\left(\dfrac{2.25\,kHt}{r^2 S_y}\right) \qquad k = \dfrac{2.3\,q}{2\pi\,\Delta\left(H^2 - h^2\right)} \qquad S_y = \dfrac{2.25\,kH t_0}{r^2}$

## Construction Dewatering

**Flow to a Trench, Unconfined:**  

>$q = k\,\dfrac{H_o^2 - H_D^2}{2D}$

**Heads Measured from the Low-k Layer:**  

>$H = d_{base} - d_{wt} \qquad h_t = d_{base} - \left(d_{exc} + d_m\right)$

**Drainage Time, Anisotropic Soil:**  

>$t_d = \dfrac{4 S_y H}{k_v}$

**Leakage Through a Cutoff Wall:**  

>$q = k_w\,\dfrac{H^2 - h_t^2}{2t} \qquad Q = P\,q$

## Finite Element Method

**Governing Equation (2D Steady):**  

>$\dfrac{\partial}{\partial x}\left(k_x\dfrac{\partial h}{\partial x}\right) + \dfrac{\partial}{\partial y}\left(k_y\dfrac{\partial h}{\partial y}\right) = 0$

**Global System:**  

>$[T]\{h\} = \{q\}$

**1D Element:**  

>$C = \dfrac{kA}{L} \qquad q_1 = C\,(h_1 - h_2) \qquad q_2 = C\,(h_2 - h_1)$

**Linear Triangle:**  

>$h = a_1 + a_2 x + a_3 y$

>$\{i\} = [B]\{h\} \qquad \{v\} = -[K]\{i\} \qquad \{Q\} = -\Delta[B]^T\{v\}$

>$[T] = \Delta[B]^T[K][B]$

>$[B] = \dfrac{1}{2\Delta}\begin{bmatrix} y_j - y_k & y_k - y_i & y_i - y_j \\ x_k - x_j & x_i - x_k & x_j - x_i \end{bmatrix}$

>$\Delta = \dfrac{1}{2}\left[\left(x_j - x_i\right)\left(y_k - y_i\right) - \left(x_k - x_i\right)\left(y_j - y_i\right)\right]$

## Transient Seepage

**Storativity of a Layer $b$ Thick:**  

>$S = S_s\,b$

**Drainage Rate of a Zone:**  

>$\mathrm{rate} \approx \dfrac{k_2}{S_y}$

## Unit Conversions:
- 1 m = 3.28 ft
- 1 ft = 12 in 
- 1 in = 2.54 cm 
- 1 lb = 2.2 kg 
- 1 mi = 5280 ft 
- 1 acre = 43,560 ft² 
- 1 acre-ft = 43,560 ft³ 