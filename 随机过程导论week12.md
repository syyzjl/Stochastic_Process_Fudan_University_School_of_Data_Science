$$\phi_n(s)=E[Es^{\sum_{j=1}^{Z_{n-1}}\xi_{n-1,j}}|Z_{n-1}]=E[\phi(s)^{Z_{n-1}}=\phi_{n-1}(\phi(s))=\phi(\phi\dots\phi(s))$$
$$\frac{\phi_n^{(k)}(s)}{k!}|_{s=0}=P(Z_n=k)$$
## e.g.
$$P(\xi=k)=\frac 1{2^{k+1}},k=0,1,2,\dots P(Z_n=k)=?$$
$$\phi(s)Es^\xi=\sum_{k=0}^\infty s^k\frac 1{2^{k+1}}=\frac 12 \sum_{k=0}^\infty(\frac s2)^k=\frac 12\frac 1{1-\frac s2}=\frac 1{2-s}$$
$$\phi\phi(s) = \frac{2-s}{3-2s}$$
$$\phi_n(s) = \frac n{n+1}+\frac s{(n+1)^2}\frac 1{1-\frac {ns}{n+1}}=\frac{n}{n+1}+\frac s{(n+1)^2}\sum_{k=0}^\infty(\frac {ns}{n+1})^k$$
$$P(Z_n=k)=\frac{n^{k-1}}{(n+1)^{k+1}}$$
## branch
$$EZ_n=EE[\sum_{j=1}^{Z_{n-1}}\xi_{n-1,j}|Z_{n-1}]=E[\mu Z_{n-1}]=\mu EZ_{n-1}=\mu^2EZ_{n-2}=\dots=\mu^nEZ_{n-n}=\mu^n$$
## 最终灭绝概率$\tau$
$$\tau = \lim_{n\rightarrow\infty}P(Z_n=0=\lim_{n\rightarrow\infty}\phi_n(0)$$
存在$Z_n=0\Rightarrow$对$m>n,Z_m=0$
$$P(Z_n=0)\le P(Z_m=0)$$
$$\tau_n\le \tau_m$$
$\mu<1$一定灭绝
$$\tau=\lim_{n\rightarrow\infty}P(Z_n=0)=1-\lim_{n\rightarrow}P(Z_n\ge 1)\le\frac{EZ_n}1=\mu^n$$
$$\tau\ge 1-\lim_{n\rightarrow\infty}\mu^n=1$$
$$\tau =1$$
$\mu>1,P_0\in(0,1)$
$$ P_0=P(\xi = 0)\in[0,1]$$
$$P_0=\phi(0)=0\Rightarrow\phi_n(0)=0$$
$$\tau=\lim_{n\rightarrow\infty}\phi_n(0)=\lim_{n\rightarrow\infty}\phi(\phi_{n-1}(0))$$
$$\tau=\phi(\tau),\tau = 1$$
$$\phi(s)=Es^\xi=\sum_{k=0}^\infty s^kP(\xi=k)$$
$$\phi(1)=1$$
$$\phi’(s)|_{s=1}=E\xi s^{\xi-1}|_{s=1}=E\xi=\mu>1$$
$$\phi’’(s)>0$$
$$\phi(0)=P(\xi=0)=P_0$$
# Wiener Process/Brownian Motion
## Def1
### 1
$B_0\equiv 0$
###  2 增量独立 $t_1<\dots<t_n$
$\begin{pmatrix}B(t_2)-B(t_1)\\\dots\\B(t_n)-B(t_{n-1})\end{pmatrix}$ 独立
### 3 增量平稳
$$B(t)-B(s)\sim B(t-s)-B(0)=B(t-s)\sim N(0,t-s)$$
### 4
$$B(t)\sim N(0,t)$$
$$EB_t=0$$
$$VarB_t=t$$
$$cov(B_t,B_s)=EB_tB_s-0=E(B_t-B_s+B_s)B_s=EB_s^2=VarB_s=s=min(s,t)$$
## Distribution 任意有限维joint jointly normal Def2
$$B_t\sim N(0,t)(1D)$$
### 2D
$$\begin{pmatrix}B_t\\B_s\end{pmatrix}=\begin{pmatrix}1&1\\0&1\end{pmatrix}\begin{pmatrix}B_t-B_s\\B_s\end{pmatrix}\sim N(\begin{pmatrix}0\\0\end{pmatrix}\begin{pmatrix}t&min(t,s)\\min(t,s)&s\end{pmatrix})$$
$$\begin{pmatrix}B_{t_1}\\\dots\\B_{t_n}\end{pmatrix}=\begin{pmatrix}1,0,\dots,0\\\dots\\1,1,\dots,1\end{pmatrix}\begin{pmatrix}B_{t_1}\\\dots\\B_{t_n}-B_{t_{n-1}}\end{pmatrix}$$
$$X\sim N(\mu,\Sigma)\Rightarrow AX\sim N(A\mu,A\Sigma A^T)$$

## $\Leftarrow$
### 1
$$EB_0=0,VarB_0=0\Rightarrow B_0=EB_0=0$$
### 2
$$\begin{pmatrix}B_{t_1}\\\dots\\B_{t_n}\end{pmatrix}\sim N(\begin{pmatrix}0\\\dots\\0\end{pmatrix}\Sigma),\Sigma_{ij}=min(t_i,t_j)$$
$$\begin{pmatrix}B(t_2)-B(t_1)\\\dots\\B(t_n)-B(t_{n-1})\end{pmatrix}=\begin{pmatrix}-1&1&0&\dots&0&0\\\dots\\0&0&0&\dots&-1&1\end{pmatrix}\begin{pmatrix}B_{t_1}\\\dots\\B_{t_n}\end{pmatrix}\sim N(\begin{pmatrix}0\\\dots\\0\end{pmatrix}\Omega)$$
(Jointly normal $\Rightarrow$ independent 等价 uncorrelated)
$$\Rightarrow cov(B(t_i)-B(t_{i-1}),B(t_j)-B(t_{j-1}))$$
### 3
$$B(t)-B(s)\begin{pmatrix}1&-1\end{pmatrix}\begin{pmatrix}B_t\\B_s\end{pmatrix}\sim N(0,t-s)$$
$$Var(B_t-B_s)=VarB_t+VarB_s-2cov(B_t,B_s)=t+s-2s=t-s$$
### 4
取 $s=0$ 分布正态

## Def2 $(B_t)_{t\ge 0}$ Gaussian Process 任意有限维 jointly normal
$EB_t = 0$   $cov(B_t,B_s)=min(t,s)$   Then $(B_t)_{t\ge 0}$ is BM
### eg1
$X_t=B_{t+t_0}-B_{t_0}$ is BM
用Def1 
#### 1
$$X_0=B_{t_0}-B_{t_0}=0$$
#### 2
$$X_{t_2}-X_{t_1}=B_{t_2+t_0}-B_{t_1+t_0}$$
$$X_{t_3}-X_{t_2}=B_{t_3+t_0}-B_{t_2+t_0}$$
$$X_{t_n}-X_{t_{n-1}}=B_{t_n+t_0}-B_{t_{n-1}+t_0}$$
互相独立
#### 3
$s<t$   $$X_t-X_s=B_{t+t_0}-B_{s+t_0}\sim N(0,t-s)$$
#### 4
取$s=0$
### eg2
$$X_t=\frac 1{\sqrt{c}} B_{ct},c>0$$
$$EX_t=E\frac 1{\sqrt{c}} B_{ct}=0$$
$$cov(X_t,X_s)=cov(\frac 1{\sqrt{c}}B_{ct},\frac 1{\sqrt{c}}B_{cs})$$
$$=\frac 1c cov(B_{ct},B_{cs})=\frac{min(ct.cs)}{c}=min(t,s)$$
$\Rightarrow$ $X_t$ is B-M
## conditional $B_t$
### 1
$$f_{B_t|B_s}(y|x)=\frac{P(B_t=y,B_s=x)}{P(B_s=x)}=\frac{P(B_s=x)P(B_t-B_s=y-x)}{P(B_s=x)}=P(B_{t-s}=y-x)$$
$$=\frac 1{\sqrt{2\pi(t-s)}}c^{-\frac{(y-x)^2}{2(t-s)}}$$
$$\sim N(x,t-s)$$
### 2
$$f_{B_s|B_t}(y|x)$$
### 3
$$f_{B_s|B_{t_1},B_{t_2}}(y|x_1,x_2)$$
## Sample path
$$\xi=\begin{cases}\Delta,\frac 12\\-\Delta,\frac 12\end{cases}$$
$$S_t=\sum_{i=1}^n \xi_i\sim N(0,t)$$
$$E\xi_i=0$$
$$VarS_t=Var(\sum_{i=1}^n\xi_i)=\sum_{i=1}^n Var\xi_i=n\Delta^2=t$$
Let $\Delta = \sqrt{\frac tn}$
1. A.s.连续
2. 无处存在导数
A.s.$\exists \Omega_0,\rho(\Omega_0)=0,\omega\in\Omega_0$
$B_{\omega}(t)$ 不连续$\Leftrightarrow$ $P(\Omega:B_{\omega}(t)$不连续$)=0$
$$P(|B(t)-B(t_0)|\ge\epsilon)\rightarrow(t-t_0\rightarrow 0)0$$
$$LHS\le\frac{E|N(0,t-t_0)|^2}{\epsilon^2}=\frac{t-t_0}{\epsilon^2}\rightarrow(t\rightarrow t_0)0$$


$$\lim_{\Delta t\rightarrow 0}\frac{B(t+\Delta t)-B(t)}{\Delta t}\sim N(0,\frac 1{\Delta t})$$
若倒数存在，方差会无穷大（不严格说明）

