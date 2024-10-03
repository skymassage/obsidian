Krotov, GRAPE, CRAB, Goat, drag
qiskit跑x-gate
RL中的action用truncated normal distbution抽樣

$I_{mean} = (I_{ideal} + I_{n1} + I_{n2}) / 3$
Use $I_{noisy} = I_{mean} - I_{ideal}$ ,instead of $I_{noisy} = (n \cdot I_{mean} - I_{ideal}) / (n-1)$, beacause you don't know how many uncertainties in the real world.
$I_{weighted}=w_{ideal} \cdot I_{ideal} + w_{noisy} \cdot I_{noisy}$
$r = -\log_{10}I_{weighted}$

- 與學長討論QD的J1+J2如何做

3. 確認是否為切不夠細: QD CNOT關掉coupling(t_0)target=$\sigma_x \otimes I=\begin{pmatrix}0&1\\1&0\end{pmatrix}\otimes\begin{pmatrix}1&0\\0&1\end{pmatrix}$，可以的話在打開t0做這個target，記得用4x4去做但不要用RW與SW轉回去，N切細去試試
5. 擾動在noise free得到的pulse在放到noise做opimize
7. dephasing noise與inf是否有second order的關係，畫關係圖看看

擾動在noise free優化得到的pulse，放到noise去優化
target=$\sigma_x \otimes I$用Noise優化
$[-22.5*1e3, 0, 22.5*1e3]$試試3組而不是27組
initial bound=$\pm28 \times 10^6$; search bound=$\pm2800 \times 10^6$, $\pm28 \times 10^6$ too small


1. noise free情況下4x4的InF=10^-16，轉到6x6的InF=10^-6，也就是leakage差不多10^-6。
   noise情況下4x4的avg InF=10^-6，轉到6x6的avg InF=10^-5，也就是leakage差不多10^-5。
   用qutip算所有uncertainty的點，看平均inf也為1e-5的order，若是，則leakage會因為加noise，從1e-6升到1e-5
   若不是，則轉換有誤差
   對比較大noise，不管4x4或6x6，inf都1e-5~1e-4，但在較小noise情況下4x4的inf會比1e-6小，但4x4的inf最低為1e-6，所以4x4的平均inf會較小(1e-6)，6x6的平均inf比較大(1e-5)
2. 整理之前數據成表格

1. 這次只有改$\tilde{H}_{4\times4}^{\mathrm{SWA,\ RWA}}$，後面transformation也要改一下(control Hamiltonian不加入dephasing noise)


----
CNOT的action之std用神經網路學試試
QD(CNOT)的U=6000GHZ, epsilon=0,在NM多一個t_0控制參數去找最佳值，原本參數有2(x,y) X step個，現在為2 X step+1(t_0)
QD(CZ): T=50ns <-> t_0~10GHZ; T=250 <-> 1GHZ



1. noise_std = $k\sigma$, $k=\sqrt{3/2}$怎麼推導
2. the policy network outputs are then fed into a network, called normal projection network, to generate $\mu_a$ , $\sigma_a$ ( (layer number ? structure)
3. set the initial network parameters of normal projection network to be zeros such that it gives a flat pulse right at the zero line at the beginning
6. 直接初始化policy network參數，不用projection network
7. X-gate的noise case只用noise_std=0.1訓練，可以noise_std再調小訓練讓fig 5.1-8之X軸的1e-4到1e-2與4th order重合，還是這樣做會偏離4th order，那可以透過調大$w_{noisy}$來解決嗎? 可以
9. 用noise_std=0.1訓練，當noisy InF約1e-4時，就可以開始漸漸降低$w_{noisy}$比重，調降方式是根據InF大小嗎? 另外每個stage的iteration次數都不是100或1000的倍數，是怎麼決定到下個stage? 用看的







