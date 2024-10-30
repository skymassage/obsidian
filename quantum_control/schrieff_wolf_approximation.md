Decompose a Hamiltonian into two parts
$$H=H_0+\epsilon V$$
where $H_0$ is a Hamiltonian with known eigenstates $\ket{n}$ and corresponding eigenvalues $E_n$, and where $V$ is a small perturbation which is sometimes taken to be time-dependent. And it is assumed without loss of generality that $V$ is purely off-diagonal in the eigenbasis of $H_0$, i.e., $\bra{n}V\ket{n}=0$for all $n$. The Schrieffer–Wolff transformation is a unitary transformation which expresses the Hamiltonian in a basis (the "dressed" basis) where it is diagonal to first order in the perturbation $V$. This unitary transformation is conventionally written as:
$$H'=e^S H e^{-S}$$
where $S$ is the generator of the transformation will likewise be small and $S^{\dagger} = -S$. By the Baker-Campbell-Hausdorff formula formula, we expand $H'$ to the second order of $S$
$$\begin{aligned}
H'&= H+\epsilon[S, H]+\frac{\epsilon^2}{2}[S, [S,H]]+ O(S^3) \\
&= H_0 + \epsilon V + \epsilon([S,H_0]+\epsilon[S,V]) + \frac{\epsilon^2}{2}[S, [S,H_0]+\epsilon[S,V]] + O(S^3)\\
&= H_0 + \epsilon(V+[S,H_0])+\epsilon^2([S,V] + \frac{1}{2}[S,[S,H_0]])+ \cancelto{O(V^3)}{\frac{\epsilon^3}{2}[S,[S,V]] + O(S^3)}
\end{aligned}$$
Choosing the generator$S$ such that $V+[S,H_0]=0$ and omit $O(V^3)$
$$H'\simeq H_0 + \frac{\epsilon^2}{2}[S,V]$$
If adding another small perturbation
$$H=H_0+\epsilon (V+W)$$, where $W$ is also off-diagonal. So
$$\begin{aligned}
H'&=e^S H e^{-S}\\
&= H+\epsilon[S, H]+\frac{\epsilon^2}{2}[S, [S,H]]+O(S^3) \\
&= H_0 + \epsilon (V+W) + \epsilon([S,H_0]+\epsilon[S,V+W]) + \frac{\epsilon^2}{2}[S, [S,H_0]+\epsilon[S,V+W]] + O(S^3)\\
&= H_0 + \epsilon(V+W+[S,H_0])+\epsilon^2([S,V+W]+\frac{1}{2}[S,[S,H_0]])+\cancelto{O(V^3)}{\frac{\epsilon^3}{2}[S,[S,V+W]] + O(S^3)}\\
&= H_0 + \epsilon(V+[S,H_0]) + \epsilon^2([S,V]+\frac{1}{2}[S,[S,H_0]]) +\epsilon W + \epsilon^2[S,W] + O(V^3)
\end{aligned}$$
Sinilarly, choosing the generator S such that $V+[S,H_0]=0$ and omit $O(V^3)$
$$H'\simeq H_ 0+ \frac{\epsilon^2}{2}[S,V] + \epsilon W + \epsilon^2[S,W]$$