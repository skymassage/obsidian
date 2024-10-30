The ideal two-qubit Hamiltonian in the basis of $\ket{\uparrow, \uparrow}, \ket{\uparrow, \downarrow}, \ket{\downarrow, \uparrow}, \ket{\downarrow, \downarrow}, S(0, 2)$:
$$H_I / \hbar = 2 \pi \begin{pmatrix}
\overline{E}_z & \frac{1}{2}E_x(t) & \frac{1}{2}E_x(t) & 0 & 0\\
\frac{1}{2}E_x(t) & \frac{1}{2}\delta E_z & 0 & \frac{1}{2} E_x(t) & t_0\\
\frac{1}{2}E_x(t) & 0 & -\frac{1}{2}\delta E_z & \frac{1}{2}E_x(t) & -t_0\\
0 & \frac{1}{2}E_x(t) & \frac{1}{2}E_x(t) & -\overline{E}_z & 0\\
0 & t_0 & -t_0 & 0 & U-\epsilon
\end{pmatrix} \tag{1}$$
, where $\overline{E}_z=39.16 \mathrm{GHz}$, $\delta E_z = -40\mathrm{MHz}$, $t_0 = 900 \mathrm{MHz}$, $U-\epsilon=276.71 \mathrm{GHz}$ and
$$E_x(t) = \frac{g\mu_B}{h} B_x(t) = \overline{\Omega}_x(t) \cos(\overline{E}_z \cdot 2\pi t) + \overline{\Omega}_y(t) \cos(\overline{E}_z \cdot 2\pi t + \frac{\pi}{2}).$$
For CNOT, $\overline{\Omega}_x,\overline{\Omega}_y \sim 28\mathrm{MHz}$, $T=500 \mathrm{ns}$.
From $(1)$ , use SWA and RWA to obtain $\tilde{H}_{I,4\times4}^{SW,RWA}$ for optimization:
$$\tilde{H}_{I,4\times4}^{SWA,RWA}/\hbar = 2 \pi \begin{pmatrix}
0 & \frac{1}{4} \left(\overline{\Omega}_x(t) - i \overline{\Omega}_y(t)\right) & \frac{1}{4} \left(\overline{\Omega}_x(t) - i \overline{\Omega}_y(t)\right) & 0\\
\frac{1}{4} \left(\overline{\Omega}_x(t) + i \overline{\Omega}_y(t)\right) & \frac{1}{2} \delta E_z - J_m & \frac{1}{2}(J_p + J_m) & \frac{1}{4} \left(\overline{\Omega}_x(t) - i \overline{\Omega}_y(t)\right)\\
\frac{1}{4} \left(\overline{\Omega}_x(t) + i \overline{\Omega}_y(t)\right) & \frac{1}{2}(J_p + J_m) & -\frac{1}{2} \delta E_z - J_p & \frac{1}{4} \left(\overline{\Omega}_x(t) - i \overline{\Omega}_y(t)\right)\\
0 & \frac{1}{4} \left(\overline{\Omega}_x(t) + i \overline{\Omega}_y(t)\right) & \frac{1}{4} \left(\overline{\Omega}_x(t) + i \overline{\Omega}_y(t)\right) & 0
\end{pmatrix}$$, where

$$J_p = \frac{{t_0}^2}{U-\epsilon + \delta E_z/2} \enspace, \quad J_m = \frac{{t_0}^2}{U-\epsilon - \delta E_z/2}$$
Obtain $\tilde{U}_{I,4\times4}^{SWA}(T)$ of $\tilde{H}_{I,4\times4}^{SWA,RWA}/\hbar$ by the Schrödinger equation. Then transforming $\tilde{U}_{I,4\times4}^{SWA}(T)$ from the rotating frame back to the frame transformed by the SW transformation and combining it with the propagator in the subspace $\ket{0,2}$ in the same frame:

$$\tilde{U}_{I,4\times4}^{SWA}(T) = {U_0}^\dagger(T) \tilde{U}_{I,4\times4}^{SWA,RWA}(T) \enspace, \quad {U_0}(T)=\begin{pmatrix} e^{-i\overline{E}_z\cdot2\pi T} & & &\\ &1&&\\ &&1&\\ &&& e^{i\overline{E}_z\cdot2\pi T} \end{pmatrix}$$
$$\tilde{U}_I^{SWA}(T) = \begin{pmatrix} 
&\begin{matrix} \\ \\ \tilde{U}_{I,4\times4}^{SWA}(T) \\ \\ \begin{matrix}0&0&0&0\end{matrix} \end{matrix} 
& \begin{matrix} 0\\0\\0\\0\\ e^{-i(U-\epsilon+J_p+J_m)\cdot 2 \pi T} \end{matrix} 
\end{pmatrix}$$
Finally, the ideal system propagator:
$$U_I(T) \simeq e^{-S} \tilde{U}_I^{SWA}(T) e^{S}  \enspace,\quad S = \begin{pmatrix} \begin{matrix}\\ \\ \begin{matrix}0\end{matrix} \\ \\ \begin{matrix}0&\gamma(-\delta E_z)&-\gamma(\delta E_z)&0\end{matrix}\end{matrix} & \begin{matrix}0\\-\gamma(-\delta E_z)\\\gamma(\delta E_z)\\0\\0\end{matrix}\end{pmatrix} \enspace,\quad \gamma(\delta E_z)=\frac{t_0}{U-\epsilon+\delta E_z/2}$$, where
$$e^{\pm S} \simeq 1\pm S +\frac{S^2}{2} = \begin{pmatrix}1&0&0&0&0\\ 0& 1-\frac{1}{2}\gamma(-\delta E_z)^2 & \frac{1}{2}\gamma(-\delta E_z)\gamma(\delta E_z) &0 &\mp\gamma(-\delta E_z)\\ 0& \frac{1}{2}\gamma(-\delta E_z)\gamma(\delta E_z) & 1-\frac{1}{2}\gamma(\delta E_z)^2 &0 &\pm\gamma(\delta E_z)\\ 0&0&0&1&0\\ 0& \pm\gamma (-\delta E_z) & \mp\gamma(\delta E_z) & 0 & 1-\frac{1}{2}\left(\gamma(-\delta E_z)^2 + \gamma(\delta E_z)^2 \right) \end{pmatrix}$$
