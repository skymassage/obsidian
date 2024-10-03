$$B_1 = 2B \cos (\omega_{MV}t - \phi_1)\hat{x}$$
$$\tilde{H}^{SWA} = \begin{pmatrix}
-\overline{E_z} & \frac{\hbar}{2}\omega_{1_{0}}\eta & \frac{\hbar}{2}\omega_{1_{1}}\eta & 0\\
\frac{\hbar}{2}\omega_{1_{0}}\eta & -\frac{\delta E_z}{2} - \alpha(-\delta E_z) & \beta(\delta E_z) & \frac{\hbar}{2}\omega_{1_{1}}\eta\\
\frac{\hbar}{2}\omega_{1_{1}}\eta & \beta({\delta E_z}) & \frac{\delta E_z}{2} - \alpha(\delta E_z) &  \frac{\hbar}{2}\omega_{1_{0}}\eta\\
0 & \frac{\hbar}{2}\omega_{1_{1}}\eta & \frac{\hbar}{2}\omega_{1_{0}}\eta & \overline{E_z}
\end{pmatrix}$$
where
$$\eta = (e^{i\omega_{MV}t}e^{-i\phi_1} + e^{-i\omega_{MV}t}e^{i\phi_1}) \quad\quad\mathrm{and}\quad\quad \omega_{1_{i} = -\gamma_i B_1}$$
$\gamma_i = -\frac{g\mu_B}{\hbar}$ is the Rabi frequency of $q_i$.
Rotating frame:
$$U_{RF}  = \begin{pmatrix} e^{-i \frac{\omega_{0_1}}{2}t} & 0 \\ 0 & e^{i \frac{\omega_{0_1}}{2}t} \end{pmatrix} \bigotimes \begin{pmatrix} e^{-i \frac{\omega_{0_0}}{2}t} & 0 \\ 0 & e^{i \frac{\omega_{0_0}}{2}t} \end{pmatrix}$$
$$\tilde{H}^{SWA, RW} = U_{RF} \tilde{H}^{SWA} U_{RF}^{\dagger} - i\hbar U_{RF} \frac{d U_{RF}^{\dagger}}{dt}$$
$$\tilde{H}^{SWA, RW} = \begin{pmatrix}
0 & \frac{\hbar}{2}\omega_{1_{0}}\eta e^{-i\omega_{0_0} t} & \frac{\hbar}{2}\omega_{1_{1}}\eta e^{-i\omega_{0_1} t} & 0\\
\frac{\hbar}{2}\omega_{1_{0}}\eta e^{i\omega_{0_0} t} & - \alpha(-\delta E_z) & \beta(\delta E_z) e^{i\Delta \omega_{0} t} & \frac{\hbar}{2}\omega_{1_{1}}\eta e^{-i\omega_{0_1} t}\\
\frac{\hbar}{2}\omega_{1_{1}}\eta e^{i\omega_{0_1} t} & \beta({\delta E_z}) e^{i\Delta\omega_{0} t} & -\alpha(\delta E_z) &  \frac{\hbar}{2}\omega_{1_{0}}\eta e^{-i\omega_{0_0} t}\\
0 & \frac{\hbar}{2}\omega_{1_{1}}\eta e^{i\omega_{0_1} t} & \frac{\hbar}{2}\omega_{1_{0}}\eta e^{i\omega_{0_0} t} & 0
\end{pmatrix}$$
where $\Delta \omega_0 = \omega_{0_{0}} - \omega_{0_{1}}$

$$\tilde{H}^{SWA, RWA} = \begin{pmatrix}
0 & \frac{\hbar}{2}\omega_{1_{0}}\eta e^{-i\omega_{0_0} t} & \frac{\hbar}{2}\omega_{1_{1}}\eta e^{-i\omega_{0_1} t} & 0\\
\frac{\hbar}{2}\omega_{1_{0}}\eta e^{i\omega_{0_0} t} & 0 & 0 & \frac{\hbar}{2}\omega_{1_{1}}\eta e^{-i\omega_{0_1} t}\\
\frac{\hbar}{2}\omega_{1_{1}}\eta e^{i\omega_{0_1} t} & 0 & 0 &  \frac{\hbar}{2}\omega_{1_{0}}\eta e^{-i\omega_{0_0} t}\\
0 & \frac{\hbar}{2}\omega_{1_{1}}\eta e^{i\omega_{0_1} t} & \frac{\hbar}{2}\omega_{1_{0}}\eta e^{i\omega_{0_0} t} & 0
\end{pmatrix}$$



