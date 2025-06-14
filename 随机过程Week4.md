# LLN
## (2)
$\{X_n,n\ge 1\}$   $EX_n^2<\infty$   $S_n=\sum_{i=1}^nX_i$  if. $\frac{VarS_n}{n^2}\rightarrow 0$
$\frac{S_n}n\underrightarrow{p}E\frac{S_n}n$   Chebyshev LLN. 去掉了i.i.d

Proof:
$P(|\frac{S_n}n-E\frac{S_n}n|\ge\epsilon)\underrightarrow{n\rightarrow\infty}0$??
$LHS\le\frac{E|\frac{S_n}n-E\frac{S_n}n|^2}{\epsilon^2}=\frac{\frac 1{n^2}VarS_n}{\epsilon^2}\underrightarrow{n\rightarrow\infty}0$   $cov(X_i,X_j)\sim O(1)$

## (3)Khinchine LLN
$(X_n,n\ge 1)$   I.i.d.  $EX_n=\mu$   $\bar{x}=S_n=\sum_{i=1}^nX_i$   $\frac{S_n}n\underrightarrow{p\&a.s.}\mu$
sample mean$\rightarrow$population mean

Proof(p):
$P(|\frac{S_n}n-\mu|\ge\epsilon)\underrightarrow{n\rightarrow\infty}0$
$\le\frac{E|\frac{S_n}n-\mu|^2}{\epsilon^2}$   But $EX_n^2$ may not exist

Need to prove $\frac{S_n}n\underrightarrow{d}\mu$   MGF  $M_X(t)=Ee^{itx}$
$Ee^{it\frac{S_n}n}\underrightarrow{n\rightarrow\infty}e^{it\mu}$
$LHS=Ee^{it\frac 1n\sum_{k=1}^nX_k}=E\Pi_{k=1}^ne^{it\frac 1nX_k}=\Pi_{k=1}^nEe^{it\frac 1nX_k}=\Pi_{k=1}^n[1+\mu\frac{it}n+O(\frac 1{n^2})]\underrightarrow{n\rightarrow\infty}e^{it\mu}$
$Ee^{sX_k}=\varphi(s)$
$\varphi(0)=1$
$\varphi’(0)=Ee^{sX_k}X_k|_{s=0}=EX_k=\mu$
$\varphi(s)=\varphi(0)+\varphi’(0)s=1+\mu s+o(s)$


# CLT
## (1)De Moivre-Laplace
$S_n\sim B(n,p)$
$\begin{pmatrix}S_n=\sum_{i=1}^nX_i\\X_i\sim(iid)\begin{cases}1,p\\0,1-p\end{cases}\end{pmatrix}$
$\frac{S_n}n\underrightarrow{p}$  $p$    $\frac{S_n}n-p$ $\underrightarrow{p}$  $0$
$P(|\frac{S_n}n-p|\ge\epsilon)\underrightarrow{n\rightarrow\infty}0$

$Var(\frac{S_n}n)=\frac 1{n^2}Var(\sum_{i=1}^nX_i)$
$=\frac 1{n^2}\sum_{i=1}^nVarX_i+\sum_{i\ne j}cov(X_i,X_j)$
$=\frac{1}n(p-p^2)$

$\frac{\frac{S_n}n-p}{\sqrt{\frac{p(1-p)}n}}\underrightarrow{d}N(0,1)$

## (2)Lery-Feller
$(X_n)_{n\ge 1}\sim(iid)EX_n=\mu<\infty$   $VarX_n=\sigma^2<\infty$   $S_n=\sum_{i=1}^n$ 
$\frac{S_n-n\mu}{\sqrt{n}\sigma}\underrightarrow{d}N(0,1)$

$M_X(t)=Ee^{tX}=(X\sim N(0,1))\int_{-\infty}^\infty e^{tx}\frac 1{\sqrt{2\pi}}e^{-\frac{x^2}2}dx=\int_{-\infty}^\infty\frac 1{\sqrt{2\pi}}e^{-\frac 12 (x-t)^2}e^{\frac{t^2}2}dx=e^{\frac 12 t^2}$
$\frac{S_n-n\mu}{\sqrt{n}\sigma}=\sum_{k=1}^{n}(\frac{X_k-\mu}\sigma)\frac 1{\sqrt{n}}=\frac{\sum_{k=1}^N\xi_k}{\sqrt{n}}$
$Ee^{t\frac{\sum_{k=1}^n\xi}{\sqrt{n}}}=\Pi_{k=1}^nEe^{\frac{t\xi_k}{\sqrt{n}}}=\Pi_{k=1}^n(1+\frac 12\frac{t^2}n+o(\frac 1n))\underrightarrow{n\rightarrow\infty}e^{\frac 12t^2}$
$Ee^{s\xi_k}=\varphi(s)=1+\frac 1{2!}s^2+0(s^2)$
$\varphi(0)=1$, $\varphi’(0)=E\xi_k=0$, $\varphi’’(0)=E\xi_k^2=Var\xi_k=1$


# Stochastic process
$\{X_t,t\in T\}$ $X_t$ is r.v.
T:时间 离散或连续
E：状态空间
$X_t:$ t fixed. $X_t$ is r.v.$\sim$ particular distribution
$X_\omega(t)$: $\omega$ fixed. Function on t
$X(t,\omega)$关于t的函数sample path

## eg1
$X_n$: 总点数（n次）
$T=\{1,2,\dots\}$ 时间离散
$E=\{1,2,\}$ 状态离散
$X_1=\begin{cases}1,1/6\\\dots\\6,1/6\end{cases}$
$X_2=\begin{cases}2,1/36\\\dots\\12,1/36\end{cases}$
$\dots$
$\omega_1=(1,1,\dots,1)$
$X_1=1,X_2=2,X_3=3\Rightarrow X_n=n$
$\omega_2=(2,\dots,2)$
$X_1=2,X_2=4,X_3=6\Rightarrow X_n=2n$  $(n,X_n)$的图线是sample path

## eg2 Random walk(simple symmetric) R
$S_n$: n时刻的位置（一维数轴上）
$T=\{0,1,2,3,\dots\}$离散的
$E=\{0,\pm 1,\pm 2,\dots\}$
$X_n=\begin{cases}+1,right\\-1,left\end{cases}$
$S_n=\sum_{k=1}^nX_k$
$S_0\equiv 0$
$S_1=\begin{cases}1,1/2\\-1,1/2\end{cases}$

$P(S_n=m)=P(\sum_{k=1}^nX_k=m)=P(\sum_{k=1}^n(2\xi_k-1)=m)=P(\sum_{k=1}^n\xi_k=\frac{m+n}2)={n\choose\frac{m+n}2}(\frac 12)^n$
$\frac{X_n+1}2 =\xi_n=\begin{cases}1,1/2\\-1,1/2\end{cases}$

$\omega$ given 
$\omega_1=(1,1,\dots)$
$S_0=0,S_1=1,S_3=3,\dots\Rightarrow S_n=n$
$\omega_2=(-1,-1,\dots)$
$S_0=0,S_1=-1,S_3=-3,\dots\Rightarrow S_n=-n$
$\omega_3=(1,-1,1,-1,\dots)$
$S_0=0,S_1=1,S_2=0,\dots$

## eg3
$S_n$: 到n时刻为止多少人去超市
$T\ge 0$: 连续
$S_n:\{0,1,2,\dots\}$离散
Given $n=t$ $S_n|_{n=t}\sim Poisson(\lambda t)$(r.v.)

# Poisson process
*流*  $N(t):(0,t]$ $N(0)\equiv 0$  $s<t$   $N(s)$
柏松流
	independent(increament)每个质点间独立$N(s)\bot N(t)-N(s)$
	Stationary每个相同长度时间段质点分布相同 $N(t)-N(s)=(d)N(t-s)$
	Rare足够短的时间内最多一个质点$\begin{cases}P(N(t+\Delta t)-N(t)=1)=\lambda\Delta t+o(\Delta t)\\P(N(t+\Delta t)-N(t)\ge 2)=o(\Delta t)\end{cases}\Rightarrow P(N(t+\Delta t)-N(t)=0)=1-\lambda\Delta t+o(\Delta t)$

Poisson process: $N(t):\#\{(0,t)\}$  $N(0)\equiv 0$: then $N(t)\sim poisson(\lambda t)$
$P(N(t)=k)=\frac{(\lambda t)^ke^{-\lambda t}}{k!}(k=0,1,2,\dots)$（用柏松流可推）

$k=0,P(N(t)=0)=e^{-\lambda t}$
$P(N(t)=0)=P(N(t_0,t_1)=N(t_1,t_2)=N(t_{n-1},t_n)=0)$
$=P(N(t_0,t_1)=0)P(N(t_1,t_2)=0)\dots P(N(t_{n-1},t_n)=0)$
$=[1-\lambda\frac tn+o(\frac 1n)]^n\underrightarrow{n\rightarrow\infty}e^{-\lambda t}$

	

