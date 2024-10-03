$$H=\omega(t)X + \omega_0 Z = \sqrt{\omega(t)^2+{\omega_0}^2} \frac{\omega(t)X + \omega_0 Z}{\sqrt{\omega(t)^2+{\omega_0}^2}}$$
$$U(t)=e^{-iHt}=e^{-i \left(\sqrt{\omega(t)^2+{\omega_0}^2} \cdot t\right) \left(\frac{\omega(t)X + \omega_0 Z}{\sqrt{\omega(t)^2+{\omega_0}^2}}\right)}=\cos\left( \sqrt{\omega(t)^2+{\omega_0}^2} \cdot t\right) I - i\sin \left( \sqrt{\omega(t)^2+{\omega_0}^2} \cdot t \right) \frac{\omega(t)X + \omega_0 Z}{\sqrt{\omega(t)^2+{\omega_0}^2}}$$
If $\sqrt{\omega(t)^2+{\omega_0}^2} \cdot t = \frac{\pi}{2}$ and $\omega(t) = \omega_0$:
$$U=-i\frac{1}{\sqrt{2}}(X+Z)=-i\cdot\frac{1}{\sqrt{2}}\begin{pmatrix}1&1\\1&-1\end{pmatrix}$$
is $-i$ times the Hadamard gate.