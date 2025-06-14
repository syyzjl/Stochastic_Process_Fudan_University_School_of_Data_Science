# 反射Brownian Motion
$X_t=|B_t|$
$X_t$不是正态过程
$$EX_t=E|B_t|=\int_{-\infty}^\infty |x|\frac 1{\sqrt{2\pi t}}e^{-\frac {x^2}{2t}}dx=\sqrt{\frac {2t}\pi}$$
$$VarX_t=E|B_t|^2-\frac{2t}\pi=t-\frac{2t}\pi$$
distribution
$$P(X_t\le x)=\begin{cases}0,x\le 0\\P(|B_t|\le x),x\ge 0\end{cases}$$
$$P(|B_t|\le x)=P(\frac{-x}{\sqrt{t}}\le \frac {B_t}{\sqrt{t}}\le\frac x{\sqrt{t}})=\phi(\frac x{\sqrt{t}})-\phi(\frac{-x}{\sqrt{t}})$$
# 几何Brownian Motion
$$X_t=e^{\alpha B_t}$$
不是正态过程
$$EX_t=e^{\frac 12\alpha^2t}$$
$$VarX_t=e^{2\alpha^2t}-e^{\alpha^2t}$$
Distribution
$$P(X_t\le x)=\begin{cases}P(B_t\le \frac 1{\alpha}\ln x),\alpha < 0\\P(B_t\ge \frac 1\alpha\ln x),\alpha<0\end{cases}$$
上$=\phi(\frac{\ln x}{\alpha\sqrt{t}})$ 对数正态
# Brownian Bridge
$$X_t=B_t-tB_1,t\in[0,1],X_0=0=X_1$$
正态过程
$\begin{pmatrix}X_{t_1}\\\dots\\X_{t_k}\end{pmatrix}\sim$ Jointly Gaussian
$$\Leftrightarrow\sum_{i=1}^k\alpha_iX_{t_i}\sim N(*,*)$$
$$EX_t=0$$
$$cov(X_t,X_s)=cov(B_t-tB_1,B_s-sB_1)$$
$$=min(t,s)-st-ts+ts$$
$$=min(t,s)-st$$
$$\begin{pmatrix}X_{t_1}\\\dots\\X_{t_k}\end{pmatrix}\sim N((0)D),D_{ij}=min(t_i,t_j)-t_it_j$$
$$X_t\sim N(0,t-t^2)$$
$$B_t|B_1=0=N(0,t(1-t))$$
$$X_t=(d)(B_t|B_1=0)$$
# Integrated
$$X_t=\int_0^tB_sd_s=\lim_{\Delta_n\rightarrow 0}\sum_{i=1}^nB_{S_i}(S_i-S_{i-1})$$
正态过程
$$\begin{pmatrix}X_{t_1}\\\dots\\X_{t_k}\end{pmatrix}\sim N((0)D)$$
$$cov(X_t,X_s)=EX_tX_s=E\int_0^tB_udu\int_0^sB_vdv=\int_0^s\int_0^tmin(u,v)dudv$$
$$=\int_0^s(tv-\frac 12 v^2)dv=\frac 12 ts^2-\frac 16s^3$$
$$\int_0^tmin(u,v)du=\int_0^vudu+\int_v^tvdu=\frac 12 v^2+v(t-v)=tv-\frac 12 v^2$$
# Maximum & hitting time
$$M_t=\max_{s\in[0,t]} B_s,T_a=\inf\{t\ge 0:B_t=a\}$$
## $M_t$
### 1
$$M_t=|B_t|$$
$$P(M_t> x) =P(M_t>x,B_t>x)+P(M_t>x,B_t<x)$$
If $B_t>x\Rightarrow M_t>x$
$P(M_t>x,B_t>x=P(B_t>x)$
## stopping time(T)r.v.~($B_t$)
$\{T\le t\}$ 可由 $\{B_s,0\le s\le t\}$决定
## reflecting principle
If T is a stopping time, $\tilde{B}(t)=\begin{cases}B(t),t\le T\\2B(T_x)-B(t),t>T\end{cases}$
$$2B(T_x)=2x-B(t)$$
Then $\tilde{B}(t)$ is standard BM

$$P(M_t>x,B_t<x)=P(B_t<x,T_x<t)=P(\tilde{B}_t>x)=P(B_t>x)$$
$$\tilde{B}(t)=2x-B(t)>x$$
$$P(B_t>x)=P(B_t<-x)$$

### 2
$T_a$
$$P(T_a\le t)=P(M_t\ge a)=P(|B_t|\ge a)=P(B_t\ge a)+P(B_t\le -a)$$
$$=1-\phi(a/\sqrt{t})+\phi(-a/\sqrt{t})=2(1-\phi(a/\sqrt{t}))$$
$$\phi(a,t)$$
PDF
#### 1
$$P(T_a<\infty)=\lim P(T_a\le t)=\lim_{t\rightarrow\infty}2(1-\phi(a/\sqrt{t}))=1$$
#### 2
$ET_a=\infty$

### (1)
$$M^-(t)=\min_{s\in[0,t]}B_t=-\max_{s\in[0,t]}(-B_t)=-M_t$$
### (2)
$(B_t,M_t)$
$$P(B_t\le x,M_t\le y)=P(B_t\le x)-P(B_t\le x,M_t>y),x<y$$
$$P(B_t\le x, M_t>y)=P(B_t\ge x, T_y\le t)$$
$$\tilde{B}(t)=2B_(T_y)-B_t=2y-B_t=2y-x$$

# B-M with drift
从长时间看趋势往上或下，即均值不为0
$EB_t=0$
## 1
$X_0\equiv 0$
## 2
Independent $ stationary $(X_t-X_s)$
## 3
$X_t-X_s\sim N(\mu(t-s),\sigma^2(t-s))$
$$X_t=\mu t+\sigma B_t$$
$$\begin{pmatrix}X_{t_1}\\\dots\\X_{t_k}\end{pmatrix}\sim N(\begin{pmatrix}\mu t_1\\\dots\\\mu_{t_k}\end{pmatrix},())$$
$$cov(X_t,X_s)=cov(X_t-X_s+X_s,X_s)=VarX_s=s\sigma^2$$
$X_{t_1}|X_{t_2}=x_2,t_1<t_2$ 与$\mu$ 无关，取$\mu = 0$简化运算

# Ito Integral
$$\int f(x)dBx$$
$$\int_a^bf(x)dG(x)$$
$f$ 连续，$G(x)$ 有界变差
###  1分割
$$[a,b]=[t_0,t_1,\dots,t_n]=\Delta_n$$
### 2取点
$$[t_{i-1},t_i]$$
取点$\xi_i$

### 3
$$\sum_{i=1}^nf(\xi_i)(t_i-t_{i-1})=S_n$$
求和
### 4
limit 对$\forall \Delta_n,\forall \xi_i,\lim S_n=S$
$\sum_{i=1}^n|G(t_i)-G(t_{i-1})|<\infty$

## (1) $\int_0^tf(s)dBs$
Given 有界变差
($B_t$) 不是有界变差 $[0,t]=[t_0,t_1,\dots,t_{2^n}],t_i=\frac t{2^n}i$
找$\Delta_n$: 依概率
$$\sum_{i=1}^{2^n}|B(t_i)-B(t_{i-1})|=\infty$$
$$\lim_{M\rightarrow\infty}P(\sum_{i=1}^{2^n}|B(t_i)-B(t_{i-1})|\ge M)=1$$
$$E\sum_{i=1}^{2^n}|S_i|=\sum_{i=1}^{2^n}E|N(0,t_i-t_{i-1})|=\sum_{i=1}^{2^n}\sqrt{\frac {2t}{2^n\pi}}=k\sqrt{2^n}$$
$$Var\sum_{i=1}^{2^n}|S_i|=\sum_{i=1}^{2^n}E[N(0,t_i-t_{i-1})]^2$$
$$\sum_{i=1}^{2^n}(t_i-t_{i-1})<\infty$$

$$P(\xi\ge M)=P(\xi-E\xi\ge M-E\xi)\le -\frac 12 E\xi$$
$$\le P(|\xi-E\xi|\ge \frac 12E\xi)$$

### (1)
$$\int_0^tf(s)dB(s)$$
#### 1)
$$[0,t]=[t_0,t_1,\dots,t_n]=\Delta n$$
#### 2)
取 $\xi\in[t_{i-1},t_i]$
#### 3)
$$\sum_{i=1}^nf(\xi_i)(B_{t_i}-B_{t_{i-1}})=S_n$$
#### 4)
$$S_n=f(\xi_1)(B_{t_1}-B_{t_0})+f(\xi_0)(B_{t_2}-B_{t_1})+\dots+f(\xi_n)(B_{t_n}-B_{t_{n-1}})$$
$$=f(\xi_1)B_{t_1}-f(\xi_1)B_{t_0}+f(\xi_2)B_{t_2}-f(\xi_2)B_{t_1}+\dots+f(\xi_n)B_{t_n}-f(\xi_n)B_{t_{n-1}}$$
$$=B_{t_1}(f(\xi_1)-f(\xi_2))+B_{t_2}(f(\xi_2)-f(\xi_3))+\dots+B_{t_{n-1}}(f(\xi_{n-1})-f(\xi_n))+f(\xi_n)B_{t_n}$$

$$-\sum_{i=1}^{n-1}B_{t_i}(f(\xi_{i+1})-f(\xi_i))$$
$$\rightarrow -\int_0^tB_sdfs$$
### (1)
$$\int_0^tf(s)dBs=f(t)B_t-\int_0^tB_sdfs$$
$fs$ 有界， $f(s)$ 给定

## e.g.
$$\int_0^tB_sdB_s=$$
### 1
$$\Delta_n=[t_0,t_1,\dots,t_n],|||\Delta_n|||\rightarrow 0$$
### 2
$$\xi_i\in [t_{i-1},t_i],\forall$$
### 3
$$S_n=\sum_{i=1}^nB(\xi_i)[B(t_i)-B(t_{i-1})]$$
### 4
 取极限，$\forall\Delta n,\forall\xi_n,S_n\rightarrow S$
 取$\xi_i=t_{i-1},S=\frac {B_t^2-t}2$
 $\xi_i=t_i,S=\frac {B_t^2+t}2$
 $$E|S_n-S|^2\rightarrow(|||\Delta_n|||\rightarrow 0)0$$
