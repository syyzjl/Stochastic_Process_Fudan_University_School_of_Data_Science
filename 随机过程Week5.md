# Poisson proceess
$k=1$ $$P(N(t)=1)=nP(N(t_0,t_1)=1,N(t_1,t_2)=\dots=N(t_{n-1},t_n)=0)$$$$=nP(N(t/n)=1)\Pi_{i=1}^{n-1}P(N(t_i,t_{i+1})=0)$$$$=n[\lambda \frac tan+o(1/n)](1-\frac{\lambda t}n+o(1/n))^{n-1}$$
$$=\lambda te^{-\lambda t}$$
$k=2$ $P(N(t)=2)$
$$nP(N(t_0,t_1)=2)P(N(t_1,t_2)=\dots=N(t_{n-1},t_n)=0)=no(t/n)o(1)=o(1)$$
$${n\choose 2}P(N(t_0,t_1)=N(t_1,t_2)=1)P(N(t_2,t_3)=\dots=N(t_{n-1},t_n)=0)$$
$$=\frac{n(n-1)}2[\lambda\frac to+o(1/n)]^2(1-\lambda\frac to+o(1/n))^{n-2}$$
$$=\frac 12(\lambda t)^2e^{-\lambda t}$$
生成函数 $\xi$ r.v.  $Ez^\xi=\phi(z)$ $(\xi=0,1,\dots)$
$$\phi(z)=\sum_{k=0}^{\infty}z^kp(\xi=k)=p(\xi=0)+zp(\xi=1)+\dots$$
$$\phi(0)=p(\xi=0),\phi’(0)=p(\xi=1),\frac{\phi’’(0)}{2!}=p(\xi=2)$$
$$Ez^{poisson(\lambda t)}=\sum_{k=0}^{\infty}z^kp(\xi=k)=\sum_{k=0}^\infty z^k\frac{(\lambda t)^ke^{-\lambda t}}{k!}$$
$$=\sum_{k=0}^\infty\frac{(z\lambda t)^ke^{-z\lambda t}}{k!}e^{z\lambda t-\lambda t}$$
$$=e^{\lambda t(z-1)}$$
$??Ez^{N(t)}=e^{\lambda t(z-1)}$

$Ez^{N(t)}=\sum_{k=0}^\infty z^kP(N(t)=k)=f_k(t)=\varphi_z(t)$
$$f_k(t+\Delta t)=P(N(t+\Delta t)=k)$$
$k=0$
$$f_0(t+\Delta t)=P(N(t)=N(t+\Delta t)=0)=P(N(t)=0)[1-\lambda\Delta t+o(\Delta t)]$$
$$=f_0(t)[1-\lambda\Delta t+o(\Delta t)]$$
$$\lim_{\Delta t\rightarrow 0}(f_0(t+\Delta t)-f_0(t))/\Delta t=-\lambda f_0(t)$$
$$\Rightarrow f’_0(t)=-\lambda f_0(t)$$
$$\Rightarrow f_0(t)=ce^{-\lambda t}(c=1)$$

$f_k(t+\Delta t)=P(N(t+\Delta t)=k)$  (k 0(1),k-1 1(2),k-l l(3))
$$(1)P(N(t)=k)P(N(t,t+\Delta t)=0)=f_k(t)[1-\lambda t+o(\Delta t)]$$
$$(2)P(N(t)=k-1)P(N(t,t+\Delta t))f_{k-1}(t)[\lambda\Delta t+o(\Delta t)]$$
$$(3)P(N(t)=k-l)0(\Delta t)\rightarrow 0$$

$$f_k(t+\Delta t)=P(N(t+\Delta t)=k)=f_k(t)[1-\lambda \Delta t]+f_{k-1}(t)\lambda\Delta t+o(t)$$
$$\lim_{\Delta t\rightarrow 0}\frac{f_k(t+\Delta t)-f_k(t)}{\Delta t}=-f_k(t)\lambda+f_{k-1}(t)\lambda$$
$$\Rightarrow \sum f’_k(t)z^K=\sum -f_k(t)\lambda z^k+\sum f_{k-1}(t)\lambda z^k$$
$$\frac{\partial}{\partial t}[\sum_{k=0}^\infty z^kf_k(t)]-f’_0(t)=-[\sum_{k=0}^\infty f_k(t)\lambda z^k-f_0(t)\lambda]+\lambda z\sum_{k=0}^\infty f_k(t)z^k$$
$$\frac\partial{\partial t}\varphi_z(t)-f’_0(t)=-\lambda\varphi_z(t)+f_0(t)\lambda+\lambda z\varphi_z(t)$$
$$\frac\partial{\partial t}\varphi_z(t)=\varphi_z(t)[\lambda z-\lambda]$$
$$\varphi_z(t)=ce^{\lambda(z-1)t}$$
Since $\varphi_0(0)=P(N(0)=0)=1$, $c=1$
$$\varphi_z(t)=e^{\lambda(z-1)t}$$
## Poisson process Def2
$N(t)$: Stochastic process. $E=\{0,1,2,\dots\}$
$N(t)$ satisfies:
	1. $N(0)\equiv 0$
	2. Stationary
	3. Independent
	4. $N(t)\sim poisson(\lambda t)$
$EN(t)=\lambda t\Rightarrow E\frac{N(t)}{t}=\lambda$  $Var N(t)=\lambda t$
$$EN(t)N(s)=E[N(s)+N(t)-N(s)]N(s)=EN^2(s)+E(N(t)-N(s))N(s)$$
$$=\lambda s+(\lambda s)^2+\lambda(t-s)\lambda s=\lambda t\lambda s+\lambda s$$
$$Cov(N(t),N(s))$$
## Distribution $\forall$ 有限维joint
### 1 D.
$N(t)\sim poisson(\lambda t)$
### 2 D. 
$\begin{pmatrix}N(t_1)\\N(t_2)\end{pmatrix}\quad p(N(t_1)=m_1,N(t_2)=m_2)=p(N(t_1)=m_1)p(N(t_2-t_1)=m_2-m_1)$
$$=\frac{(\lambda t_1)^{m_1}e^{-\lambda t_1}}{m_1!}\frac{(\lambda(t_2-t_1))^{m_2-m_1}}{(m_2-m_1)!}$$
### multiple D. 
$\begin{pmatrix}N(t_1)\\\dots\\N(t_k)\end{pmatrix}$
$$P(N(t_1)=m_1,\dots,N(t_k)=m_k)$$
$$=P(N(t_1)=m_1,N(t_2)-N(t_1)=m_2-m_1,\dots)$$
$$=\frac{(\lambda t_1)^{m_1}e^{-\lambda t_1}}{m_1!}\dots\frac{(\lambda(t_k-t_{k-1}))^{m_k-m_{k-1}}}{(m_K-m_{k-1})!}$$
## sample path

	1 Arrival time
	2 waiting time

## Arrival time
## $S_1$ 
$cdf$  $P(S_1>t)=P(N(t)=0)=\frac{(\lambda t)^0e^{-\lambda t}}{0!}=e^{-\lambda t}$
Cdf of $S_1$ $$F(t)=1-e^{-\lambda t}$$
pdf $$f(t)=\lambda e^{-\lambda t}\sim \exp(\lambda)=\Gamma(1,\lambda)$$
### $S_2$
$$P(S_2>t)=P(N(t)=0)+P(N(t)=1)=e^{-\lambda t}+\frac{(\lambda t)^1e^{-\lambda t}}{1!}$$
Cdf$$F(t)=1-e^{-\lambda t}-\lambda te^{-\lambda t}$$
Pdf$$f(t)=\lambda e^{-\lambda t}-\lambda e^{-\lambda t}+\lambda^2te^{-\lambda t}=\lambda^2te^{-\lambda t}\sim\Gamma(2,\lambda)$$
### $S_k$
$$P(S_k>t)=\sum_{m=0}^{k-1}P(N(t)=m)=\sum_{m=0}^{k-1}\frac{(\lambda t)^me^{-\lambda t}}{m!}$$
$$F(t)=1-\sum_{m=0}^{k-1}\frac{(\lambda t)^me^{-\lambda t}}{m!}$$
$$f(t)=-\sum_{m=0}^{k-1}[\frac{m(\lambda t)^{m-1}\lambda e^{-\lambda t}}{m!}-\frac{(\lambda t)^,e^{-\lambda t}\lambda}{m!}]$$
$$=-\sum_{m=0}^{k-2}\frac{(\lambda t)^m\lambda e^{-\lambda t}}{m!}+\sum_{m=0}^{k-1}\frac{(\lambda t)^me^{-\lambda t}\lambda}{m!}$$
$$=\frac{\lambda^kt^{k-1}e^{-\lambda t}}{\Gamma(k)}\sim \Gamma(k,\lambda)$$


$$(S_k)_k\sim\Gamma(k,\lambda)$$


### Waiting time
$$X_1=S_1\sim\Gamma(1,\lambda)=\exp(\lambda)$$
$$X_k=S_{k}-S_{k-1}$$

$$P(X_2>t)=P(S_2-S_1>t)=\int P(S_2-S_1>t|S_1=m)P(S_1=m)dm=\int_0^\infty e^{-\lambda t}\lambda e^{-\lambda m}dm$$
$$P(S_2-S_1>t|S_1=m)=P(N(t)=0)=e^{-\lambda t}$$
Cdf$$1-e^{-\lambda t}$$
Pdf$$\lambda e^{-\lambda t}$$
#### 1
$S_2-S_1\bot S_1$  $X_2\bot X_1$  $X_2\sim \exp(\lambda)$


$$P(X_k>t)=P(S_k-S_{k-1}>t)=\int_0^\infty P(S_k-S_{k-1}>t|S_{k-1}=m)P(S_{k-1}=m)dm$$
$$=\frac{(\lambda t)^0e^{-\lambda t}}{0!}=e^{-\lambda t}$$


$$(X_k)_k\sim\exp(\lambda)$$


### Def3
$(X_k)(iid)\sim\exp(\lambda)\Rightarrow S_n=\sum_{k=1}^n X_k\sim\Gamma(n,\lambda)$    $(S_n)$
$$N(t)=\begin{cases}0,S_0\le t<S_1\\1,S_1\le t<S_2\\\dots\\k,S_k\le t<S_{k+1}\end{cases}$$
Then,$$N(t)\sim Poisson(\lambda t)$$
Def$$N(t)=\{n:S_n\le t<S_{n+1}\}$$
Satisfies
	1. Stationary
	2. Independent
	3. $N(t)\sim poisson(\lambda t)$

Pf:(1)
$$p(N(t)=k)=\frac{(\lambda t)^ke^{-\lambda t}}{k!},k=0,1,2,\dots$$
$$p(N(t)=0)=p(S_0\le t<S_1)=P(t<X_1)=e^{-\lambda t}$$
$$p(N(t)=k)=p(S_k\le t<S_{k+1})=\int_0^t P(S_k\le t<S_k+X_{k+1}|S_k=m)P(S_k=m)dm$$
$$=\int_0^tP(x_{k+1}>t-m)P(s_k=m)dm$$
$$=\int_0^te^{-\lambda(t-m)}\frac{\lambda^Km^{k-1}e^{-\lambda m}}{\Gamma(k)}$$
$$=\int_0^te^{-\lambda t}\frac{\lambda^km^{k-1}}{(k-1)!}dm$$
$$=\frac{(\lambda t)^ke^{-\lambda t}}{k!}$$

(2)
$N(t)-N(s)=N(t-s)$ stationary and independent
$$P(N(t)-N(s)=k|N(s)=m)=\frac{(\lambda(t-s)^k)e^{-\lambda(t-s)}}{k!},s<t$$
1)$k=0$
$$LHS=\frac{P(N(t)-N(s)=0,N(s)=m)}{P(N(s)=m)}=\frac{P(N(s)=N(t)=m)}{\frac{(\lambda s)^me^{-\lambda s}}{m!}}$$
分子$$=P(S_m\le s <t<S_{m+1})=\int_0^\infty P(S_m\le s <t<S_m+X_{m+1}|S_m=u)P(S_m=u)du$$
$$=\int_0^s P(X_{m+1}>t-u)P(S_m=u)du$$
$$=\int_0^se^{-t\lambda}\frac{\lambda^mu^{m-1}}{\Gamma(m)}du=\frac{e^{-\lambda t}\lambda^m}{(m-1)!}\frac 1m s^m$$
因此上式$$=e^{-\lambda(t-s)}$$
If $k\ge 1$
$$P(N(s)=m,N(t)=m+k)=P(S_m\le s<S_{m+1}<S_{m+k}\le t<S_{m+k+1})$$
