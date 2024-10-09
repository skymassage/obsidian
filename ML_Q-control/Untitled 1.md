
$H=H_I(t) + H_N$

$$H_I(t)/\hbar = 2\pi
\begin{pmatrix}
\overline{E}_z  & \frac{1}{2} E_x(t) & \frac{1}{2} E_x(t) & 0 & 0 & 0 \\
\frac{1}{2} E_x(t) & \frac{1}{2} \delta E_z & 0 & \frac{1}{2} E_x(t) & t_0 & t_0\\
\frac{1}{2} E_x(t) & 0 & -\frac{1}{2} \delta E_z & \frac{1}{2} E_x(t) & -t_0 & -t_0\\
0 & \frac{1}{2} E_x(t) & \frac{1}{2} E_x(t) & -\overline{E}_z & 0 & 0 \\
0 & t_0 & -t_0 & 0 & U-\epsilon & 0\\
0 & t_0 & -t_0 & 0 & 0 & U+\epsilon\\
\end{pmatrix}$$
$$H_N/\hbar = 2\pi
\begin{pmatrix}
\frac{\beta_{E_{z_1}}+\beta_{E_{z_2}}}{2}  & 0 & 0 & 0 & 0 & 0 \\
0 & \frac{\beta_{E_{z_1}}-\beta_{E_{z_2}}}{2} & 0 & 0 & 0 & 0\\
0 & 0 & -\frac{\beta_{E_{z_1}}-\beta_{E_{z_2}}}{2}  & 0 & 0 & 0\\
0 & 0 & 0 & -\frac{(\beta_{E_{z_1}}+\beta_{E_{z_2}})}{2} & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 0\\
0 & 0 & 0 & 0 & 0 & 0\\
\end{pmatrix}
=2\pi \cdot \frac{1}{2}(\beta_{E_{z_1}}(Z \otimes I) + \beta_{E_{z_2}}(I \times Z))
=2\pi \cdot \frac{1}{2}(\beta_{E_{z_1}}H_{E_{z_1}}+\beta_{E_{z_1}}H_{E_{z_2}})$$
$$<J_2>=\frac{1}{2}\sum_{jk}\int_{0}^{t_f}dt_1\int_{0}^{t_1}dt_2 C_{jk}(t_1,t_2) \mathrm{Tr}[(R_j(t_1)R_k(t_2))_{4\times 4}] - \frac{1}{16}\sum_{jk}\int_{0}^{t_f}dt_1\int_{0}^{t_1}dt_2 C_{jk}(t_1,t_2)\mathrm{Tr}[R_{j,4\times 4}(t_1)]\mathrm{Tr}[R_{k,4\times 4}(t_2)],$$
where $R_j(t)=U_I^{\dagger}(t)H_{N_j} U_I(t)$, $C_{jk}(t_1,t_2)=<\beta_{j}(t_1)\beta_{k}(t_2)>$, and $j = E_{z_1}, E_{z_2}$.

The depahsing is quast-static so $C_{jk}(t_1,t_2)=<\beta_j\beta_k>$, and leave out the second term because $H_N$ is traceless
$$\begin{align*}<J_2> = \frac{1}{2} &\left( \beta_{E_{z_1}}\beta_{E_{z_1}} \int_{0}^{t_f}dt_1 \int_0^{t_1}dt_2\mathrm{Tr}[(R_1(t_1)R_1(t_1))_{4 \times 4}] + \beta_{E_{z_2}}\beta_{E_{z_2}} \int_{0}^{t_f}dt_1 \int_0^{t_1}dt_2\mathrm{Tr}[(R_2(t_1)R_2(t_1))_{4 \times 4}] \right.\\
&\left. \quad + \enspace \beta_{E_{z_1}}\beta_{E_{z_2}} \int_{0}^{t_f}dt_1 \int_0^{t_1}dt_2\mathrm{Tr}[(R_1(t_1)R_2(t_1))_{4 \times 4}] + \beta_{E_{z_1}}\beta_{E_{z_2}} \int_{0}^{t_f}dt_1 \int_0^{t_1}dt_2\mathrm{Tr}[(R_2(t_1)R_1(t_2))_{4 \times 4}] \right)\end{align*},$$
where $R_1(t)=U_I(t) (Z \otimes I) U_I(t)$, $R_2(t)=U_I(t) (I \otimes Z) U_I(t)$.