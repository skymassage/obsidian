# QD ($6 \times 6$)
The two-electron double dot Hamiltonian is given by the following:
$$H = H_\epsilon + H_t + H_U + H_Z$$
$H_\epsilon$: the detuning describes the gate-controlled energy shift of the dots with respect to each other.
$H_t$: the tunneling of the electrons from one dot to the other.
$H_U$: accounts for the on-site interaction (Coulomb interaction).
$H_Z$: the Zeeman coupling when external magnetic fields are introduced.

In the basis {$\ket{\uparrow, \uparrow}, \ket{\uparrow, \downarrow}, \ket{\downarrow, \uparrow}, \ket{\downarrow, \downarrow}, S(0, 2), S(2, 0)$}:
$$ 
H/\hbar = 2\pi
\begin{pmatrix}
\overline{E}_z  & 0 & 0 & 0 & 0 & 0 \\
0 & \frac{1}{2} \delta E_z & 0 & 0 & t_0 & t_0\\
0 & 0 & -\frac{1}{2} \delta E_z & 0 & -t_0 & -t_0\\
0 & 0 & 0 & -\overline{E}_z & 0 & 0 \\
0 & t_0 & -t_0 & 0 & U-\epsilon & 0\\
0 & t_0 & -t_0 & 0 & 0 & U+\epsilon\\
\end{pmatrix}
\tag{1}
$$
$U$: the Coulomb energy of the quantum dot (assumed equal for the two dots).
$\epsilon$: the energy detuning between the dots can be controlled through plunger gates.
$t_0$: the tunnel coupling can be controlled through barrier gates.
$\overline{E}_z = \frac{E_{z_1} + E_{z_2}}{2}$ and $\delta E_z = E_{z_1} - E_{z_2}$  are the average and the difference of the qubits Zeeman splittings, respectively.

$H = H_0 + V$ where $H_0$ is the diagonal part of $H$ and $V$ is the off-diagonal part of $H$. If $V$ is considered a perturbation of $H_0$, i.e. the strength of the interaction $V$ must be much smaller than $H_0$, then it is possible to use the Schrieffer-Wolff transformation (SWT):
$$H^{\mathrm{SW}} = e^S H e^{-S}=H_0+\frac{1}{2}[S,V]+O(V^3)$$
$$S =
\begin{pmatrix}
0 & 0 & 0 & 0 & 0 &0\\
0 & 0 & 0 & 0 & -\gamma(\delta E_z) & -\sigma(\delta E_z)\\
0 & 0 & 0 & 0 & \gamma(-\delta E_z) & \sigma(-\delta E_z)\\
0 & 0 & 0 & 0 & 0 &0\\
0 & \gamma(\delta E_z) & -\gamma(-\delta E_z) & 0 & 0 &0\\
0 & \sigma(\delta E_z) & -\sigma(-\delta E_z) & 0 & 0 &0\\
\end{pmatrix} \quad\quad\mathrm{and}\quad\quad
\begin{cases}\gamma(\delta E_z) = t_0 / (U-\epsilon-\delta E_z/2)\\
\sigma(\delta E_z) = t_0 /(U + \epsilon -\delta E_z/2)\end{cases}$$
where $S$ is the generator of the transformation which must make $V+[S, H_0]=0$.
## CZ
Expand $H^{\mathrm{SW}}$ to the second order of $S$ and omit $O(V^3)$ for Schrieffer-Wolff approximation (SWA), i.e. $\tilde{H}^{\mathrm{SWA}} = H_0+\frac{1}{2}[S,V]$:
$$\tilde{H}^{\mathrm{SWA}}/\hbar = 2\pi \begin{pmatrix}
\overline{E}_z  & 0 & 0 & 0 & 0 & 0\\
0 & \frac{1}{2}\delta E_z - \alpha(\delta E_z) & \beta(\delta E_z) & 0 & 0 & 0\\
0 & \beta(\delta E_z) & -\frac{1}{2} \delta E_z - \alpha(-\delta E_z) & 0 & 0 & 0\\
0 & 0 & 0 & -\overline{E}_z & 0 & 0\\
0&0&0&0 & (U-\epsilon) + t_0(\gamma(\delta E_z)+\gamma(-\delta E_z)) & \beta(\delta E_z)\\
0&0&0&0 & \beta(\delta E_z) & (U+\epsilon) + t_0(\sigma(\delta E_z)+\sigma(-\delta E_z))\\
\end{pmatrix}$$
where,
$$ 
\alpha (\delta E_z) = \frac{{t_0}^2}{U - \epsilon -\delta E_z/2} + \frac{{t_0}^2} {U + \epsilon - \delta E_z/2} \enspace
\quad\quad\mathrm{and}\quad\quad
\beta(\delta E_z) = \frac{\alpha(\delta E_z) + \alpha(-\delta E_z)}{2}
$$
Choose $\tilde{H}_{4 \times 4}^{\mathrm{SWA}}$:
$$
\tilde{H}_{4 \times 4}^{\mathrm{SWA}}/\hbar = 2\pi \begin{pmatrix}
\overline{E}_z  & 0 & 0 & 0\\
0 & \frac{1}{2}\delta E_z - \alpha(\delta E_z) & \beta(\delta E_z) & 0\\
0 & \beta(\delta E_z) & -\frac{1}{2} \delta E_z - \alpha(-\delta E_z) & 0 &\\
0 & 0 & 0 & -\overline{E}_z\\
\end{pmatrix}
$$
To obtain $\tilde{U}_{4\times 4}^{\mathrm{SWA}}(T)$:
$$\tilde{U}_{4\times 4}^{\mathrm{SWA}}(T) = \begin{pmatrix}
e^{-i\overline{E}_z \cdot 2\pi T}  & 0 & 0 & 0\\
0 & ae^{i\phi_1} & c & 0\\
0 & d & be^{i\phi_2} & 0 &\\
0 & 0 & 0 & e^{i\overline{E}_z \cdot 2\pi T}\\
\end{pmatrix}$$
Add $R_Z(\theta_1) \bigotimes R_Z(\theta_2)$ to implement the CZ gate:
$$\begin{aligned}&
\left(e^{-i\theta_1/2}\begin{pmatrix} 1&0\\0&e^{i\theta_1}\end{pmatrix}
\bigotimes
e^{-i\theta_2/2}\begin{pmatrix} 1&0\\0&e^{i\theta_2}\end{pmatrix}\right)
\begin{pmatrix}
e^{-i\overline{E}_z \cdot 2\pi T}  & 0 & 0 & 0\\
0 & ae^{i\phi_1} & b & 0\\
0 & c & de^{i\phi_2} & 0 &\\
0 & 0 & 0 & e^{i\overline{E}_z \cdot 2\pi T}\\
\end{pmatrix}\\
&= e^{-i(\theta_1/2+\theta_2/2+\overline{E}_z\cdot 2\pi T)}
\begin{pmatrix}
1&0&0&0\\
0 & ae^{i(\theta_2+\phi_1+\overline{E}_z \cdot 2\pi T)} & be^{i(\theta_2+\overline{E}_z \cdot 2\pi T)} &0\\
0 & ce^{i(\theta_1 + \overline{E}_z \cdot 2\pi T)} & de^{i(\theta_1 + \phi_2 + \overline{E}_z \cdot 2\pi T)} & 0\\
0&0&0&e^{i(\theta_1+\theta_2 + \overline{E}_z \cdot 4\pi T)}
\end{pmatrix}
\end{aligned}$$
Choose $\theta_1=-(\phi_2+\overline{E}_z\cdot 2\pi T)$ and $\theta_2=-(\phi_1+\overline{E}_z\cdot 2\pi T)$ and try to make $a,d=1$, $b,c=0$, and $\phi_1+\phi_2=(2p+1)\pi$ to obtain the CZ gate.
Consider $\tilde{H}_{4 \times 4}^{\mathrm{SWA}}(2,2)$, $\tilde{H}_{4 \times 4}^{\mathrm{SWA}}(2,3)$, $\tilde{H}_{4 \times 4}^{\mathrm{SWA}}(3,2)$, $\tilde{H}_{4 \times 4}^{\mathrm{SWA}}(3,3)$:
$${H}_{2 \times 2}^{\mathrm{SWA}}/\hbar = 2\pi \begin{pmatrix}
\frac{1}{2}\delta E_z - \alpha(\delta E_z) & \beta(\delta E_z)\\
\beta(\delta E_z) & -\frac{1}{2} \delta E_z - \alpha(-\delta E_z)\\
\end{pmatrix}
=2\pi\left[\left(\frac{1}{2}\delta E_z \cdot Z + \beta(\delta E_z) \cdot X \right) - \begin{pmatrix} \alpha(\delta E_z) & 0\\ 0 & \alpha(-\delta E_z) \end{pmatrix} \right]$$
If $U-\epsilon \gg \delta E_z$ and $U-\epsilon \gg t_0$, we can treat $\alpha(\delta E_z) \cong \alpha(-\delta E_z)$, so
$$\tilde{U}_{2\times 2}^{\mathrm{SWA}}(T) \simeq \left[\cos\left(\sqrt{\left(\frac{\delta E_z}{2}\right)^2 + \beta(\delta E_z)^2} \cdot 2\pi T \right) \cdot I -  i \sin\left(\sqrt{\left(\frac{\delta E_z}{2}\right)^2 + \beta(\delta E_z)^2} \cdot 2\pi T \right) \cdot \frac{\frac{1}{2}\delta E_z \cdot Z + \beta(\delta E_z) \cdot X}{\sqrt{\left(\frac{\delta E_z}{2}\right)^2 + \beta(\delta E_z)^2}} \right]
\begin{pmatrix}e^{i\alpha(\delta E_z) \cdot  2\pi T}&0\\0&e^{-i\alpha(\delta E_z) \cdot 2\pi T}\end{pmatrix}$$
Note that
$$\tilde{U}_{4\times 4}^{\mathrm{SWA}}(T) = \begin{pmatrix}
e^{-i\overline{E}_z \cdot 2\pi T} && 0 && 0 && 0\\
\begin{matrix}0\\0\end{matrix} &&& \tilde{U}_{2\times 2}^{SWA}(T) &&& \begin{matrix}0\\0\end{matrix} \\
0 && 0 && 0 && e^{i\overline{E}_z \cdot 2\pi T}
\end{pmatrix}$$
In order to make $a,d=1$, $b,c=0$, let $\sqrt{\left(\frac{\delta E_z}{2}\right)^2 + \beta(\delta E_z)^2} \cdot 2\pi T = 2n\pi$, then $\phi_1=\alpha(\delta E_z) \cdot 2\pi T$ and $\phi_2=\alpha(-\delta E_z) \cdot 2\pi T$. And from $\phi_1 + \phi_2 = (2p+1)\pi$, we have  $2 \beta(\delta E_z) \cdot 2\pi T = (2p+1)\pi$, so solve:
$$
\begin{cases}
\sqrt{\left(\frac{\delta E_z}{2}\right)^2 + \beta(\delta E_z)^2} \cdot T = n \\
\beta(\delta E_z) \cdot T = \frac{(2p+1)}{4}
\end{cases}
$$
then obtain
$$
\begin{cases}
T = \frac{1}{\delta E_z}\frac{\sqrt{16n^2-(2p+1)^2}}{2}\\
\beta(\delta E_z) = \frac{2p+1}{4T}
\end{cases}
$$
Solve $t_0$ from $T$ and $\beta(\delta E_z)$, and we have
$$t_0 = \sqrt{\frac{2p+1}{\sqrt{16n^2-(2p+1)^2}} \frac{\delta E_z}{\frac{1}{U-\epsilon-\delta E_z} + \frac{1}{U+\epsilon-\delta E_z} + \frac{1}{U-\epsilon+\delta E_z} + \frac{1}{U+\epsilon+\delta E_z}}} $$
Choose $n=1$ and $p=1$ to get the shortest $T$:
$$T = \frac{\sqrt{7}}{2} \frac{1}{\delta E_z} \tag{2}$$
$$t_0 = \sqrt{\frac{3}{\sqrt{7}} \frac{\delta E_z}{\frac{1}{U-\epsilon-\delta E_z} + \frac{1}{U+\epsilon-\delta E_z} + \frac{1}{U-\epsilon+\delta E_z} + \frac{1}{U+\epsilon+\delta E_z}}} \tag{3}$$
Here in the CZ gate, we use Eq. $(1)$ for sumulation and we can infer the range of $T$ and $t_0$ from $(2)$ and $(3)$. For $\overline{E}_z=39.16 \mathrm{GHz}$, $\delta E_z = -40 \mathrm{MHz}$, $U=6000 \mathrm{GHz}$, $\epsilon=0$, $t_0 \sim 10\mathrm{GHz}$ and the standard deviation of the quasi-static noise for the tunneling $t_0$ is $6.5\mathrm{MHz}$.

## CNOT
For CNOT, we intorduce the AC magnetic field $\overrightarrow{B}_x(t) = [\Omega_x(t) \cos(\overline{E}_z 2\pi t) + \Omega_y(t) \cos(\overline{E}_z 2 \pi t + \frac{\pi}{2})] \hat{x}$, so $H_m = - \overrightarrow{u}_s \cdot \overrightarrow{B_x}(t) = \frac{g \mu_B}{\hbar} (S_{1x} \bigotimes I + I \bigotimes S_{2x}) B_x(t) = \frac{g \mu_B}{2} \cdot B_x(t) (\sigma_x \bigotimes I + I \bigotimes \sigma_x)$. The ideal Hamiltonian for the CNOT gate is
$$H_I = H_\epsilon + H_t + H_U + H_Z + H_m$$
And
$$ 
H_I/\hbar = 2\pi
\begin{pmatrix}
\overline{E}_z  & \frac{1}{2} E_x(t) & \frac{1}{2} E_x(t) & 0 & 0 & 0 \\
\frac{1}{2} E_x(t) & \frac{1}{2} \delta E_z & 0 & \frac{1}{2} E_x(t) & t_0 & t_0\\
\frac{1}{2} E_x(t) & 0 & -\frac{1}{2} \delta E_z & \frac{1}{2} E_x(t) & -t_0 & -t_0\\
0 & \frac{1}{2} E_x(t) & \frac{1}{2} E_x(t) & -\overline{E}_z & 0 & 0 \\
0 & t_0 & -t_0 & 0 & U-\epsilon & 0\\
0 & t_0 & -t_0 & 0 & 0 & U+\epsilon\\
\end{pmatrix}
$$
where $E_x(t) = \frac{g \mu_B}{\hbar} B_x(t)$. Because $\cos(\overline{E}_z 2\pi t)$ is high-frequency, it will take much time for simulation. We need to do RWA to elminate the high-frequency terms. And we should do SWA first. 
By the SWT, expand $H_I^{SW}=e^{S}H_I e^{-S}$ to the second order of $S$ (check [Schreiff-Wolf Approximation](schrieff_wolf_approximation.md)), i.e.
$$H_I^{\mathrm{SW}} = H_0 + \frac{1}{2}[S,V] + H_m + [S,H_m] + O(V^3)$$
Omit $O(V^3)$, $\gamma(E_z)-\gamma(-\delta E_z)$, and $\sigma(E_z)-\sigma(-\delta E_z)$ (because of $U-\epsilon \gg \delta E_z$) terms, then
$$
\tilde{H_I}^{\mathrm{SWA}}/\hbar = 2\pi \begin{pmatrix}
\begin{matrix} \\ &&\tilde{H_I}_{4\times 4}^{SWA}& \\ \\ \\ 0&0&0&0 \\ 0&0&0&0 \end{matrix} &
\begin{matrix} 0&0 \\ 0&0 \\ 0&0 \\ 0&0 \\ (U-\epsilon) + t_0(\gamma(\delta E_z)+\gamma(-\delta E_z)) & \beta(\delta E_z) \\ \beta(\delta E_z) & (U+\epsilon) + t_0(\sigma(\delta E_z)+\sigma(-\delta E_z)) \end{matrix}
\end{pmatrix}
$$
where
$$
\tilde{H}_{I,4\times 4}^{\mathrm{SWA}}/\hbar = 2\pi \begin{pmatrix}
\overline{E}_z  & \frac{1}{2} E_x(t) & \frac{1}{2} E_x(t) & 0\\
\frac{1}{2} E_x(t) & \frac{1}{2}\delta E_z - \alpha(\delta E_z) & \beta(\delta E_z) & \frac{1}{2} E_x(t)\\
\frac{1}{2} E_x(t) & \beta(\delta E_z) & -\frac{1}{2} \delta E_z - \alpha(-\delta E_z) & \frac{1}{2} E_x(t) &\\
0 & \frac{1}{2} E_x(t) & \frac{1}{2} E_x(t) & -\overline{E}_z\\
\end{pmatrix}
$$
Apply the rotating wave transformation to the Hamiltonian to transform $\tilde{H}_{I,4\times 4}^{SWA}$ to the rotating frame (RF)
$$\tilde{H}_{I,4\times 4}^{\mathrm{SWA,\ RF}}=U_{0}^{\dagger}(t)\tilde{H}_{I,4\times 4}^{\mathrm{SWA}}U_{0}(t) - i\hbar U_{0}^{\dagger}(t) \dot{U}_{0}^(t)$$
where
$$U_{0}(t)=\begin{pmatrix}e^{-i\overline{E}_z 2\pi t} &0&0&0 \\ 0&1&0&0 \\ 0&0&1&0 \\ 0&0&0& e^{i\overline{E}_z 2\pi t} \end{pmatrix}$$
And dropping out the high frequency terms ($e^{\pm E_z \cdot 4\pi t}$) for approximation
$$\tilde{H}_{I,4\times4}^{\mathrm{SWA,\ RWA}}/\hbar = 2 \pi \begin{pmatrix}
0 & \frac{1}{4} \left(\overline{\Omega}_x(t) - i \overline{\Omega}_y(t)\right) & \frac{1}{4} \left(\overline{\Omega}_x(t) - i \overline{\Omega}_y(t)\right) & 0\\
\frac{1}{4} \left(\overline{\Omega}_x(t) + i \overline{\Omega}_y(t)\right) & \frac{1}{2} \delta E_z - \alpha(\delta E_z) & \beta(\delta E_z) & \frac{1}{4} \left(\overline{\Omega}_x(t) - i \overline{\Omega}_y(t)\right)\\
\frac{1}{4} \left(\overline{\Omega}_x(t) + i \overline{\Omega}_y(t)\right) & \beta(\delta E_z)  & -\frac{1}{2} \delta E_z - \alpha(-\delta E_z) & \frac{1}{4} \left(\overline{\Omega}_x(t) - i \overline{\Omega}_y(t)\right)\\
0 & \frac{1}{4} \left(\overline{\Omega}_x(t) + i \overline{\Omega}_y(t)\right) & \frac{1}{4} \left(\overline{\Omega}_x(t) + i \overline{\Omega}_y(t)\right) & 0
\end{pmatrix}$$
where $\overline{\Omega}_x=\frac{g\mu_B}{\hbar}\Omega_x$ and $\overline{\Omega}_y=\frac{g\mu_B}{\hbar}\Omega_y$.
So we can use this approximated Hamiltonian $\tilde{H}_{I,4\times4}^{\mathrm{SWA,\ RWA}}$ for propagating by the Schrödinger equation to get $\tilde{U}_{I,4\times4}^{\mathrm{SWA,\ RWA}}(T)$, and transform it back to $U_I(T)$.
First, transform it from the rotating frame back to the frame transformed by the SW transformation
$$\tilde{U}_{I,4\times4}^{\mathrm{SWA}}(T) = {U_0}^\dagger(T) \tilde{U}_{I,4\times4}^{\mathrm{SWA,\ RWA}}(T) \enspace$$
$$\tilde{U_I}^{\mathrm{SWA}}(T)
=\begin{pmatrix} \tilde{U}_{I,4\times4}^{\mathrm{SWA}}(T)\\ & 1 & 0 \\ & 0 & 1 \end{pmatrix}
\begin{pmatrix} 1&0&0&0&\\ 0&1&0&0&\\ 0&0&1&0&\\ 0&0&0&1&\\ &&&& e^{-i2\pi T \begin{pmatrix}(U-\epsilon) + t_0(\gamma(\delta E_z)+\gamma(-\delta E_z)) & \beta(\delta E_z) \\\\ \beta(\delta E_z) & (U+\epsilon) + t_0(\sigma(\delta E_z)+\sigma(-\delta E_z))\end{pmatrix}} \end{pmatrix}
=\begin{pmatrix}
\begin{matrix} \\ && \tilde{U}_{I,4\times4}^{\mathrm{SWA}}(T) & \\ \\ \\ 0&0&0&0 \\ 0&0&0&0 \end{matrix} &
\begin{matrix} 0\qquad\qquad\qquad\qquad\qquad0 \\ 0\qquad\qquad\qquad\qquad\qquad0 \\ 0\qquad\qquad\qquad\qquad\qquad0 \\ 0\qquad\qquad\qquad\qquad\qquad0 \\  e^{-i2\pi T \begin{pmatrix}(U-\epsilon) + t_0(\gamma(\delta E_z)+\gamma(-\delta E_z)) & \beta(\delta E_z) \\\\ \beta(\delta E_z) & (U+\epsilon) + t_0(\sigma(\delta E_z)+\sigma(-\delta E_z))\end{pmatrix}} \end{matrix}
\end{pmatrix}$$
Finally, expand the SW transformation $U_I = e^{-S} U_I^{\mathrm{SW}} e^S$ to the second order of $S$ to transform back the original frame
$$\begin{aligned}
U_I(T) &\simeq e^{-S} U_I^{\mathrm{SWA}}(T) e^S\\
&\simeq \tilde{U_I}^{\mathrm{SWA}}(T) + [-S, \tilde{U_I}^{\mathrm{SWA}}(T)]+\frac{1}{2}[-S, [-S, \tilde{U_I}^{\mathrm{SWA}}(T)]]\\
&\simeq U_I^{\mathrm{SWA}}(T) + U_I^{\mathrm{SWA}}(T)S-SU_I^{\mathrm{SWA}}(T) + \frac{1}{2}(S^2U_I^{\mathrm{SWA}}(T)-U_I^{\mathrm{SWA}}(T)S^2)
\end{aligned}$$
Here the gate time $T=100\mathrm{ns}$, $t_0=5000\mathrm{MHz}$, $U=6000\mathrm{GHz}$, $\epsilon=0$, $\overline{E}_z=39.16\mathrm{GHz}$, $\delta E_z = -40\mathrm{MHz}$, and the standard deviation of the quasi-static noise for the tunneling $t_0$ is $6.5\mathrm{MHz}$.

However, $\tilde{U}_{I,4\times4}^{\mathrm{SWA,\ RWA}}(T)$ can be accurately optimized to a CNOT gate with the infidelity $0$, the infidelity of $U_I(T)$ is still $\sim 10^{-6}$ due to SWA and RWA (let $\tilde{U}_{I,4\times4}^{\mathrm{SWA,\ RWA}}(T)$ as the CNOT matrix and transform it to back to $U_I(T)$ wiht RWA and SWA).
### Dephasing noise
Now consider the dephasing noise, we sample the quasi-static noise $\xi_{E_{z_1}}, \xi_{E_{z_2}}$ with the standard deviation $6.5\mathrm{MHz}$, so add $E_{z_1} \rightarrow E_{z_1} + \xi_{E_{z_1}}$ and $E_{z_2} \rightarrow E_{z_2} + \xi_{E_{z_2}}$ to the Hamiltonian:
$$H(t)=H_I(t)+H_N = H_\epsilon + H_t + H_U + H_Z + H_m(t)+H_N$$
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
\frac{\xi_{E_{z_1}}+\xi_{E_{z_2}}}{2}  & 0 & 0 & 0 & 0 & 0 \\
0 & \frac{\xi_{E_{z_1}}-\xi_{E_{z_2}}}{2} & 0 & 0 & 0 & 0\\
0 & 0 & -\frac{\xi_{E_{z_1}}-\xi_{E_{z_2}}}{2}  & 0 & 0 & 0\\
0 & 0 & 0 & -\frac{(\xi_{E_{z_1}}+\xi_{E_{z_2}})}{2} & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 0\\
0 & 0 & 0 & 0 & 0 & 0\\
\end{pmatrix}
=2\pi \cdot \frac{1}{2}(\xi_{E_{z_1}}(Z \otimes I) + \xi_{E_{z_2}}(I \otimes Z))
=2\pi \cdot \frac{1}{2}(\xi_{E_{z_1}}H_{E_{z_1}}+\xi_{E_{z_1}}H_{E_{z_2}})$$
With SWT (note that $H_{N}$ is diagonal so directly add it to $\tilde{H}_{I}^{SW}$):
$$\tilde{H}^{\mathrm{SWA}} = H_0 + \frac{1}{2}[S,V] + H_m + [S,H_m] + H_N = \tilde{H}_{I}^{SWA}+H_N$$
and RWA (neglect the high frequency terms $e^{\pm i(2\overline{E}_{z} + \xi_{avg}) 2\pi t}$ and $e^{\pm i(2\overline{E}_{z} + \xi_{avg}) 2\pi t + \frac{\pi}{2}}$):
$$\tilde{H}_{4\times 4}^{\mathrm{SWA,\ RF}}=U_{0}^{\dagger}(t)\tilde{H}_{4\times 4}^{\mathrm{SWA}}U_{0}(t) - i\hbar U_{0}^{\dagger}(t) \dot{U}_{0}^(t)$$
We have
$$\begin{align}
\tilde{H}_{4\times4}^{\mathrm{SWA,\ RWA}}/\hbar &= 2 \pi \begin{pmatrix}
\xi_{avg} & \frac{1}{4} \left(\overline{\Omega}_x(t) - i \overline{\Omega}_y(t)\right) & \frac{1}{4} \left(\overline{\Omega}_x(t) - i \overline{\Omega}_y(t)\right) & 0\\
\frac{1}{4} \left(\overline{\Omega}_x(t) + i \overline{\Omega}_y(t)\right) & \frac{1}{2} (\delta E_z + \xi_{sub}) - \alpha(\delta E_z) & \beta(\delta E_z) & \frac{1}{4}  \left(\overline{\Omega}_x(t) - i \overline{\Omega}_y(t)\right)\\
\frac{1}{4} \left(\overline{\Omega}_x(t) + i \overline{\Omega}_y(t)\right) & \beta(\delta E_z)  & -\frac{1}{2} (\delta E_z + \xi_{sub}) - \alpha(-\delta E_z) & \frac{1}{4} \left(\overline{\Omega}_x(t) - i \overline{\Omega}_y(t)\right)\\
0 & \frac{1}{4} \left(\overline{\Omega}_x(t) + i \overline{\Omega}_y(t)\right) & \frac{1}{4} \left(\overline{\Omega}_x(t) + i \overline{\Omega}_y(t)\right) & -\xi_{avg}
\end{pmatrix} \\
&= \tilde{H}_{I,4\times4}^{\mathrm{SWA,\ RWA}}/\hbar \enspace+ 2\pi \cdot \frac{1}{2}(\xi_{E_{z_1}}(Z \otimes I) + \xi_{E_{z_2}}(I \otimes Z)),
\end{align}$$
where $\xi_{avg} = \frac{\xi_{E_{z_1}} + \xi_{E_{z_1}}}{2}, \xi_{sub} = \xi_{E_{z_1}} - \xi_{E_{z_1}}$.
Transform it from the rotating frame back to the frame transformed by the SW transformation and expand the SW transformation $U = e^{-S} U^{\mathrm{SW}} e^S$ to the second order of $S$ to transform back the original frame
$$\tilde{U}_{4\times4}^{\mathrm{SWA}}(T) = {U_0}^\dagger(T) \tilde{U}_{4\times4}^{\mathrm{SWA,\ RWA}}(T) \enspace$$
$$\tilde{U}^{\mathrm{SWA}}(T)
=\begin{pmatrix}
\begin{matrix} \\ && \tilde{U}_{4\times4}^{\mathrm{SWA}}(T) & \\ \\ \\ 0&0&0&0 \\ 0&0&0&0 \end{matrix} &
\begin{matrix} 0\qquad\qquad\qquad\qquad\qquad0 \\ 0\qquad\qquad\qquad\qquad\qquad0 \\ 0\qquad\qquad\qquad\qquad\qquad0 \\ 0\qquad\qquad\qquad\qquad\qquad0 \\  e^{-i2\pi T \begin{pmatrix}(U-\epsilon) + t_0(\gamma(\delta E_z)+\gamma(-\delta E_z)) & \beta(\delta E_z) \\\\ \beta(\delta E_z) & (U+\epsilon) + t_0(\sigma(\delta E_z)+\sigma(-\delta E_z))\end{pmatrix}} \end{matrix}
\end{pmatrix}$$
$$\begin{aligned}
U(T) &\simeq e^{-S} U^{\mathrm{SWA}}(T) e^S\\
&\simeq \tilde{U}^{\mathrm{SWA}}(T) + [-S, \tilde{U}^{\mathrm{SWA}}(T)]+\frac{1}{2}[-S, [-S, \tilde{U}^{\mathrm{SWA}}(T)]]\\
&\simeq U^{\mathrm{SWA}}(T) + U^{\mathrm{SWA}}(T)S-SU^{\mathrm{SWA}}(T) + \frac{1}{2}(S^2U^{\mathrm{SWA}}(T)-U^{\mathrm{SWA}}(T)S^2)
\end{aligned}$$
Employ the robust control method to minimize the cost function:
$$\mathcal{L}=J_1+<J_2>$$
$$J_1=1-\frac{|\mathrm{Tr}[U_{T}^{{\dagger}}U_{I,4\times 4}(t_{f})|^2}{16}$$
$$<J_2>=\frac{1}{2}\sum_{jk}\int_{0}^{t_f}dt_1\int_{0}^{t_1}dt_2 C_{jk}(t_1,t_2) \mathrm{Tr}[(\mathbf{R}_j(t_1)\mathbf{R}_k(t_2))_{4\times 4}] - \frac{1}{16}\sum_{jk}\int_{0}^{t_f}dt_1\int_{0}^{t_1}dt_2 C_{jk}(t_1,t_2)\mathrm{Tr}[\mathbf{R}_{j,4\times 4}(t_1)]\mathrm{Tr}[\mathbf{R}_{k,4\times 4}(t_2)]$$
where $R_j(t)=U_I^{\dagger}(t)H_{N_j} U_I(t)$, $C_{jk}(t_1,t_2)=<\xi_{E_{z_1}}\xi_{E_{z_2}}>$, where $\mathbf{R}_1(t)=\pi \xi_{E_{z_1}} U_I^{\dagger}(t) (Z \otimes I) U_I(t)$, $\mathbf{R}_2(t)=\pi \xi_{E_{z_2}} U_I^{\dagger}(t) (I \otimes Z) U_I(t)$. Leave out the second term because $H_N$ is traceless, so $$\begin{aligned}<J_2> = \frac{\pi^2}{2} &\left( \xi_{E_{z_1}}^2 \int_{0}^{t_f}dt_1 \int_0^{t_1}dt_2\mathrm{Tr}[(R_1(t_1)R_1(t_2))_{4 \times 4}] + \xi_{E_{z_2}}^2 \int_{0}^{t_f}dt_1 \int_0^{t_1}dt_2\mathrm{Tr}[(R_2(t_1)R_2(t_2))_{4 \times 4}] 
\right.\\ &\left.
\quad + \enspace \xi_{E_{z_1}}\xi_{E_{z_2}} \int_{0}^{t_f}dt_1 \int_0^{t_1}dt_2\mathrm{Tr}[(R_1(t_1)R_2(t_2))_{4 \times 4}] + \xi_{E_{z_1}}\xi_{E_{z_2}} \int_{0}^{t_f}dt_1 \int_0^{t_1}dt_2\mathrm{Tr}[(R_2(t_1)R_1(t_2))_{4 \times 4}] \right)\end{aligned}$$
where $R_1(t)=U_I^{\dagger}(t) (Z \otimes I) U_I(t)$, $R_2(t)=U_I^{\dagger}(t) (I \otimes Z) U_I(t)$.
Use $\tilde{H}_{I, 4\times4}^{\mathrm{SWA,\ RWA}}$ to optimize $\mathcal{L}$ without transforming the propagator back to the original frame and then obtain the optimal pulse. Use $\tilde{H}_{4\times4}^{\mathrm{SWA,\ RWA}}$ for testing and the propagators should be transformed back to the original frame to get the average infidelity.
Because $H_{E_{z_1}}=Z\otimes I$ and $H_{E_{z_2}}=I\otimes Z$, so
$$R_{j}(t) =\begin{pmatrix}
r_{j,11}(t) & r_{j,12}(t) & r_{j,13}(t)& r_{j,14}(t) \\ 
r_{j,12}^{*}(t) & r_{j,22}(t) & r_{j,23}(t)& r_{j,24}(t) \\
r_{j,13}^{*}(t) & r_{j,23}^{*}(t) & r_{j,33}(t)& r_{j,34}(t) \\
r_{j,14}^{*}(t) & r_{j,24}^{*}(t) & r_{j,34}^{*}(t)& r_{j,44}(t)
\end{pmatrix}$$
Then,
$$\begin{aligned}\mathrm{Tr}[R_j(t_1)R_k(t_2)] &=
r_{j,11}(t_1)r_{k,11}(t_2)
+ r_{j,22}(t_1)r_{k,22}(t_2)
+ r_{j,33}(t_1)r_{k,33}(t_2)
+ r_{j,44}(t_1)r_{k,44}(t_2)\\
&\quad + \;2\: [r_{j,12}^{\mathrm{Re}}(t_1) r_{k,12}^{\mathrm{Re}}(t_2) + r_{j,12}^{\mathrm{Img}}(t_1) r_{k,12}^{\mathrm{Img}}(t_2)
+ r_{j,13}^{\mathrm{Re}}(t_1) r_{k,13}^{\mathrm{Re}}(t_2) + r_{j,13}^{\mathrm{Img}}(t_1) r_{k,13}^{\mathrm{Img}}(t_2)\\
&\qquad\quad + \enspace r_{j,14}^{\mathrm{Re}}(t_1) r_{k,14}^{\mathrm{Re}}(t_2) + r_{j,14}^{\mathrm{Img}}(t_1) r_{k,14}^{\mathrm{Img}}(t_2)
+ r_{j,23}^{\mathrm{Re}}(t_1) r_{k,23}^{\mathrm{Re}}(t_2) + r_{j,23}^{\mathrm{Img}}(t_1) r_{k,23}^{\mathrm{Img}}(t_2)\\
&\qquad\quad + \enspace r_{j,24}^{\mathrm{Re}}(t_1) r_{k,24}^{\mathrm{Re}}(t_2) + r_{j,24}^{\mathrm{Img}}(t_1) r_{k,24}^{\mathrm{Img}}(t_2)
+ r_{j,34}^{\mathrm{Re}}(t_1) r_{k,34}^{\mathrm{Re}}(t_2) + r_{j,34}^{\mathrm{Img}}(t_1) r_{k,34}^{\mathrm{Img}}(t_2)]
\end{aligned}$$
$$\begin{aligned}
&\int_{0}^{t_f}dt_1\int_{0}^{t_1}dt_2 \mathrm{Tr}[R_j(t_1)R_j(t_2)] \\
&= \frac{1}{2}\left[\left(\int_{0}^{t_f} r_{j,11}(t) dt \right)^2 + \left(\int_{0}^{t_f} r_{j,22}(t) dt \right)^2 + \left(\int_{0}^{t_f} r_{j,33}(t) dt \right)^2 + \left(\int_{0}^{t_f} r_{j,44}(t) dt \right)^2 \right] \\
&\quad\enspace +\: \left(\int_{0}^{t_f} r_{j,12}^{\mathrm{Re}}(t)dt \right)^2 + \left(\int_{0}^{t_f} r_{j,12}^{\mathrm{Img}}(t)dt \right)^2 + \left(\int_{0}^{t_f} r_{j,13}^{\mathrm{Re}}(t)dt \right)^2 + \left(\int_{0}^{t_f} r_{j,13}^{\mathrm{Img}}(t)dt \right)^2 \\
&\quad\enspace +\: \left(\int_{0}^{t_f} r_{j,14}^{\mathrm{Re}}(t)dt \right)^2 + \left(\int_{0}^{t_f} r_{j,14}^{\mathrm{Img}}(t)dt \right)^2 + \left(\int_{0}^{t_f} r_{j,23}^{\mathrm{Re}}(t)dt \right)^2 + \left(\int_{0}^{t_f} r_{j,23}^{\mathrm{Img}}(t)dt \right)^2 \\
&\quad\enspace +\: \left(\int_{0}^{t_f} r_{j,24}^{\mathrm{Re}}(t)dt \right)^2 + \left(\int_{0}^{t_f} r_{j,24}^{\mathrm{Img}}(t)dt \right)^2 + \left(\int_{0}^{t_f} r_{j,34}^{\mathrm{Re}}(t)dt \right)^2 + \left(\int_{0}^{t_f} r_{j,34}^{\mathrm{Img}}(t)dt \right)^2\\

&\simeq \left(\frac{t_f}{N}\right)^2 \left\{ \frac{1}{8} \Biggl[ \left( \sum_{n=0}^{N-1} r_{j,11}(t_n)+r_{j,11}(t_{n+1}) \right)^{\!2} + \left( \sum_{n=0}^{N-1} r_{j,22}(t_n)+r_{j,22}(t_{n+1}) \right)^{\!2}
\right. \\ &\left.
\hspace{7.5em} + \left( \sum_{n=0}^{N-1} r_{j,33}(t_n)+r_{j,33}(t_{n+1}) \right)^{\!2} + \left( \sum_{n=0}^{N-1} r_{j,44}(t_n)+r_{j,44}(t_{n+1}) \right)^{\!2} \Biggl]
\right. \\ &\left.

\hspace{5.5em} + \frac{1}{4} \Biggl[ \left( \sum_{n=0}^{N-1} r_{j,12}^{\mathrm{Re}}(t_n)+r_{j,12}^{\mathrm{Re}}(t_{n+1}) \right)^{\!2} + \left( \sum_{n=0}^{N-1} r_{j,12}^{\mathrm{Img}}(t_n)+r_{j,12}^{\mathrm{Img}}(t_{n+1}) \right)^{\!2}
\right. \\ &\left.
\hspace{8.5em} + \left( \sum_{n=0}^{N-1} r_{j,13}^{\mathrm{Re}}(t_n)+r_{j,13}^{\mathrm{Re}}(t_{n+1}) \right)^{\!2} + \left( \sum_{n=0}^{N-1} r_{j,13}^{\mathrm{Img}}(t_n)+r_{j,13}^{\mathrm{Img}}(t_{n+1}) \right)^{\!2}
\right. \\ &\left.
\hspace{8.5em} + \left( \sum_{n=0}^{N-1}  r_{j,14}^{\mathrm{Re}}(t_n)+r_{j,14}^{\mathrm{Re}}(t_{n+1}) \right)^{\!2} + \left( \sum_{n=0}^{N-1} r_{j,14}^{\mathrm{Img}}(t_n)+r_{j,14}^{\mathrm{Img}}(t_{n+1}) \right)^{\!2}
\right. \\ &\left.
\hspace{8.5em} + \left( \sum_{n=0}^{N-1} r_{j,23}^{\mathrm{Re}}(t_n)+r_{j,23}^{\mathrm{Re}}(t_{n+1}) \right)^{\!2} + \left( \sum_{n=0}^{N-1} r_{j,23}^{\mathrm{Img}}(t_n)+r_{j,23}^{\mathrm{Img}}(t_{n+1}) \right)^{\!2}
\right. \\ &\left.
\hspace{8.5em} + \left( \sum_{n=0}^{N-1} r_{j,24}^{\mathrm{Re}}(t_n)+r_{j,24}^{\mathrm{Re}}(t_{n+1}) \right)^{\!2} + \left( \sum_{n=0}^{N-1} r_{j,24}^{\mathrm{Img}}(t_n)+r_{j,24}^{\mathrm{Img}}(t_{n+1}) \right)^{\!2}
\right. \\ &\left.
\hspace{8.5em} + \left( \sum_{n=0}^{N-1} r_{j,34}^{\mathrm{Re}}(t_n)+r_{j,34}^{\mathrm{Re}}(t_{n+1}) \right)^{\!2} + \left( \sum_{n=0}^{N-1} r_{j,34}^{\mathrm{Img}}(t_n)+r_{j,34}^{\mathrm{Img}}(t_{n+1}) \right)^{\!2\;}
\Biggl]
\right\}
\end{aligned}$$
Let $I_{j,11} = \sum_{n=0}^{N-1}r_{j,11}(t_n)+r_{j,11}(t_{n+1})$, $I_{j,12}^{\mathrm{Re}} = \sum_{n=0}^{N-1}r_{j,11}^{\mathrm{Re}}(t_n)+r_{j,11}^{\mathrm{Re}}(t_{n+1})$, and $I_{j,12}^{\mathrm{Img}} = \sum_{n=0}^{N-1}r_{j,11}^{\mathrm{Img}}(t_n)+r_{j,11}^{\mathrm{Img}}(t_{n+1})$, $\dots$. So
$$\begin{aligned}&\int_{0}^{t_f}dt_1\int_{0}^{t_1}dt_2 \mathrm{Tr}[R_j(t_1)R_k(t_2)] + \mathrm{Tr}[R_k(t_1)R_j(t_2)] \\
&= \left(\int_{0}^{t_f}r_{j,11}(t)dt \right) \left(\int_{0}^{t_f}r_{k,11}(t)dt \right) + \left(\int_{0}^{t_f}r_{j,22}(t)dt \right)  \left(\int_{0}^{t_f}r_{k,22}(t)dt \right) \\
&\quad\enspace + \left(\int_{0}^{t_f}r_{j,33}(t)dt \right) \left(\int_{0}^{t_f}r_{k,33}(t)dt \right)
+ \left(\int_{0}^{t_f}r_{j,44}(t)dt \right)  \left(\int_{0}^{t_f}r_{k,44}(t)dt \right) \\
&\quad\enspace + \; 2\left[ \left(\int_{0}^{t_f} r_{j,12}^{\mathrm{Re}}(t)dt \right) \left(\int_{0}^{t_f} r_{k,12}^{\mathrm{Re}}(t)dt \right) + \left(\int_{0}^{t_f} r_{j,12}^{\mathrm{Img}}(t)dt \right) \left(\int_{0}^{t_f} r_{k,12}^{\mathrm{Img}}(t)dt \right) 
\right.\\ &\left. 
\qquad\qquad + \left(\int_{0}^{t_f} r_{j,13}^{\mathrm{Re}}(t)dt \right) \left(\int_{0}^{t_f} r_{k,13}^{\mathrm{Re}}(t)dt \right) + \left(\int_{0}^{t_f} r_{j,13}^{\mathrm{Img}}(t)dt \right) \left(\int_{0}^{t_f} r_{k,13}^{\mathrm{Img}}(t)dt \right)
\right.\\ &\left. 
\qquad\qquad + \left(\int_{0}^{t_f} r_{j,14}^{\mathrm{Re}}(t)dt \right) \left(\int_{0}^{t_f} r_{k,14}^{\mathrm{Re}}(t)dt \right) + \left(\int_{0}^{t_f} r_{j,14}^{\mathrm{Img}}(t)dt \right) \left(\int_{0}^{t_f} r_{k,14}^{\mathrm{Img}}(t)dt \right)
\right.\\ &\left. 
\qquad\qquad + \left(\int_{0}^{t_f} r_{j,23}^{\mathrm{Re}}(t)dt \right) \left(\int_{0}^{t_f} r_{k,23}^{\mathrm{Re}}(t)dt \right) + \left(\int_{0}^{t_f} r_{j,23}^{\mathrm{Img}}(t)dt \right) \left(\int_{0}^{t_f} r_{k,23}^{\mathrm{Img}}(t)dt \right)
\right.\\ &\left. 
\qquad\qquad + \left(\int_{0}^{t_f} r_{j,24}^{\mathrm{Re}}(t)dt \right) \left(\int_{0}^{t_f} r_{k,24}^{\mathrm{Re}}(t)dt \right) + \left(\int_{0}^{t_f} r_{j,24}^{\mathrm{Img}}(t)dt \right) \left(\int_{0}^{t_f} r_{k,24}^{\mathrm{Img}}(t)dt \right)
\right.\\ &\left. 
\qquad\qquad + \left(\int_{0}^{t_f} r_{j,34}^{\mathrm{Re}}(t)dt \right) \left(\int_{0}^{t_f} r_{k,34}^{\mathrm{Re}}(t)dt \right) + \left(\int_{0}^{t_f} r_{j,34}^{\mathrm{Img}}(t)dt \right) \left(\int_{0}^{t_f} r_{k,34}^{\mathrm{Img}}(t)dt \right)
\right] \\

&\simeq \left(\frac{t_f}{N}\right)^2 
\left[\frac{1}{4}\left( I_{j,11}I_{k,11} + I_{j,22}I_{k,22} + I_{j,33}I_{k,33} + I_{j,44}I_{k,44} \right) + \frac{1}{2}\Bigl( I_{j,12}^{\mathrm{Re}}I_{k,12}^{\mathrm{Re}} + I_{j,12}^{\mathrm{Img}}I_{k,12}^{\mathrm{Img}} + 
I_{j,13}^{\mathrm{Re}}I_{k,13}^{\mathrm{Re}} + I_{j,13}^{\mathrm{Img}}I_{k,13}^{\mathrm{Img}} 
\right.\\ &\left.
\hspace{5.5em} + I_{j,14}^{\mathrm{Re}}I_{k,14}^{\mathrm{Re}} + I_{j,14}^{\mathrm{Img}}I_{k,14}^{\mathrm{Img}} + 
I_{j,23}^{\mathrm{Re}}I_{k,23}^{\mathrm{Re}} + I_{j,23}^{\mathrm{Img}}I_{k,23}^{\mathrm{Img}}
+ I_{j,24}^{\mathrm{Re}}I_{k,24}^{\mathrm{Re}} + I_{j,24}^{\mathrm{Img}}I_{k,24}^{\mathrm{Img}} + 
I_{j,34}^{\mathrm{Re}}I_{k,34}^{\mathrm{Re}} + I_{j,34}^{\mathrm{Img}}I_{k,34}^{\mathrm{Img}}
\Bigl)
\right]
\end{aligned}$$
Finally,
$$\begin{aligned}<J_2> &\simeq 
\left(\frac{\pi t_f}{N}\right)^2 \bigg\{
\xi_{E_{z_1}}^2 \bigg[\frac{1}{16} (I_{z_1,11}^{2} + I_{z_1,22}^{2} + I_{z_1,33}^{2} + I_{z_1,44}^{2}) + \frac{1}{8}\Big( I_{z_1,12}^{\mathrm{Re}^2} + I_{z_1,12}^{\mathrm{Img^{2}}} + I_{z_1,13}^{\mathrm{Re}^2} + I_{z_1,13}^{\mathrm{Img^{2}}} \\
&\hspace{9.5em} +\: I_{z_1,14}^{\mathrm{Re}^2} + I_{z_1,14}^{\mathrm{Img^{2}}} + I_{z_1,23}^{\mathrm{Re}^2} + I_{z_1,23}^{\mathrm{Img^{2}}} + I_{z_1,24}^{\mathrm{Re}^2} + I_{z_1,24}^{\mathrm{Img^{2}}} + I_{z_1,34}^{\mathrm{Re}^2} + I_{z_1,34}^{\mathrm{Img^{2}}}
\Big)\bigg] \\

&\hspace{5.5em} + \: \xi_{E_{z_2}}^2 \bigg[\frac{1}{16} (I_{z_2,11}^{2} + I_{z_2,22}^{2} + I_{z_2,33}^{2} + I_{z_2,44}^{2}) + \frac{1}{8}\Big( I_{z_2,12}^{\mathrm{Re}^2} + I_{z_2,12}^{\mathrm{Img^{2}}} + I_{z_2,13}^{\mathrm{Re}^2} + I_{z_2,13}^{\mathrm{Img^{2}}} \\
&\hspace{10.5em} +\: I_{z_2,14}^{\mathrm{Re}^2} + I_{z_2,14}^{\mathrm{Img^{2}}} + I_{z_2,23}^{\mathrm{Re}^2} + I_{z_2,23}^{\mathrm{Img^{2}}} + I_{z_2,24}^{\mathrm{Re}^2} + I_{z_2,24}^{\mathrm{Img^{2}}} + I_{z_2,34}^{\mathrm{Re}^2} + I_{z_2,34}^{\mathrm{Img^{2}}} 
\Big)\bigg] \\

&\hspace{5.5em} +\: \xi_{E_{z_1}}\xi_{E_{z_2}} \bigg[\frac{1}{8}\left( I_{z_1,11}I_{z_2,11} + I_{z_1,22}I_{z_2,22} + I_{z_1,33}I_{z_2,33} + I_{j,44}I_{z_2,44} \right) \\
&\hspace{10.5em} + \frac{1}{4}\Bigl( I_{z_1,12}^{\mathrm{Re}}I_{z_2,12}^{\mathrm{Re}} + I_{z_1,12}^{\mathrm{Img}}I_{z_2,12}^{\mathrm{Img}} + 
I_{z_1,13}^{\mathrm{Re}}I_{z_2,13}^{\mathrm{Re}} + I_{z_1,13}^{\mathrm{Img}}I_{z_2,13}^{\mathrm{Img}}\\
&\hspace{13em} + I_{z_1,14}^{\mathrm{Re}}I_{z_2,14}^{\mathrm{Re}} + I_{z_1,14}^{\mathrm{Img}}I_{z_2,14}^{\mathrm{Img}} + 
I_{z_1,23}^{\mathrm{Re}}I_{z_2,23}^{\mathrm{Re}} + I_{z_1,23}^{\mathrm{Img}}I_{z_2,23}^{\mathrm{Img}} \\
&\hspace{13em} + I_{z_1,24}^{\mathrm{Re}}I_{z_2,24}^{\mathrm{Re}} + I_{z_1,24}^{\mathrm{Img}}I_{z_2,24}^{\mathrm{Img}} + 
I_{z_1,34}^{\mathrm{Re}}I_{z_2,34}^{\mathrm{Re}} + I_{z_1,34}^{\mathrm{Img}}I_{z_2,34}^{\mathrm{Img}}
\Bigl)
\bigg]
\bigg\}
\end{aligned}$$
It is simpler to compute $I_{j,pq}$ like this: $I_{j,11} = \sum_{n=0}^{N-1}r_{j,11}(t_n)+r_{j,11}(t_{n+1})=r_{j,11}(t_0) + r_{j,11}(t_N) + 2\sum_{n=1}^{N-1}r_{j,11}(t_n), \dots$. Compute $R_{j}(t_0) + R_{j}(t_N) + 2\sum_{n=1}^{N-1}R_{j}(t_n), \dots$, and then take out $I_{j,pq}$, $I_{j,pq}^{\mathrm{Re}}$, and $I_{j,pq}^{\mathrm{Img}}$ from it.
If the noises are independent (noises are sampled from Gaussian distribution respectively), we don't consider the cross term (the $\xi_{E_{z_1}}\xi_{E_{z_2}}$ term).
### Tunneling Noise

$$H(t)=H_I(t)+H_N = H_\epsilon + H_t + H_U + H_Z + H_m(t)+H_N$$
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
0  & 0 & 0 & 0 & 0 & 0 \\
0  & 0 & 0 & 0 & \xi_{t_0} & \xi_{t_0}\\
0  & 0 & 0 & 0 & -\xi_{t_0} & -\xi_{t_0}\\
0  & 0 & 0 & 0 & 0 & 0\\
0 & \xi_{t_0} & -\xi_{t_0} & 0 & 0 & 0\\
0 & \xi_{t_0} & -\xi_{t_0} & 0 & 0 & 0\\
\end{pmatrix}$$
With SWT (note that $H_{N}$ is off-diagonal check [Schreiff-Wolf Approximation](schrieff_wolf_approximation.md)):
$$\tilde{H}^{SWA} = H_0 + \frac{1}{2}[S,V] + H_m + [S,H_m] + H_N + [S, H_N] = \tilde{H}_{I}^{SWA} + H_N + [S, H_N]$$
$$
\tilde{H}^{\mathrm{SWA}}/\hbar = 2\pi \begin{pmatrix}
\begin{matrix} \\ &&\tilde{H}_{4\times 4}^{SWA}& \\ \\ \\ 0&\xi_{t_0}&-\xi_{t_0}&0 \\ 0&\xi_{t_0}&-\xi_{t_0}&0 \end{matrix} &
\begin{matrix} 0&0 \\ \xi_{t_0}&\xi_{t_0} \\ -\xi_{t_0}&-\xi_{t_0} \\ 0&0 \\ (U-\epsilon) + (t_0 + 2\xi_{t_0}) (\gamma(\delta E_z)+\gamma(-\delta E_z)) & (1+\frac{2\xi_{t_0}}{t_0}) \beta(\delta E_z)  \\ (1+\frac{2\xi_{t_0}}{t_0}) \beta(\delta E_z) & (U+\epsilon) + (t_0 + 2\xi_{t_0}) (\sigma(\delta E_z)+\sigma(-\delta E_z)) \end{matrix}
\end{pmatrix}
$$
where
$$
\tilde{H}_{4\times 4}^{\mathrm{SWA}}/\hbar = 2\pi \begin{pmatrix}
\overline{E}_z  & \frac{1}{2} E_x(t) & \frac{1}{2} E_x(t) & 0\\
\frac{1}{2} E_x(t) & \frac{1}{2}\delta E_z - (1+\frac{2\xi_{t_0}}{t_0}) \alpha(\delta E_z) & (1+\frac{4\xi_{t_0}}{t_0} ) \beta(\delta E_z) & \frac{1}{2} E_x(t)\\ \frac{1}{2} E_x(t) & (1+\frac{4\xi_{t_0}}{t_0}) \beta(\delta E_z) & -\frac{1}{2} \delta E_z - (1+\frac{2\xi_{t_0}}{t_0})\alpha(-\delta E_z) & \frac{1}{2} E_x(t) &\\ 0 & \frac{1}{2} E_x(t) & \frac{1}{2} E_x(t) & -\overline{E}_z\\
\end{pmatrix}
$$
