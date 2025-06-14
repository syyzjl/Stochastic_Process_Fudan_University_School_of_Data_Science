# compound poisson
## distribution
### 1
$$p(Z(t)\ge x)=P(\sum_{i=1}^{N(t)}\xi_i\ge x)=\sum_{n=0}^{\infty}P(\sum_{i=1}^{N(t)}\xi_i\ge x|N(t)=n)P(N(t)=n)$$
### 2 MGF
$$M_{Z(t)}(s)=Ee^{sz(t)}=Ee^{s\sum_{i=1}^{N(t)}\xi_i}=E\{Ee^{s\sum_{i=1}^{N(t)}\xi_i}|N(t)=n\}P(N(t)=n)=\sum_{n=0}^\infty M_{\xi}(s)\frac{(\lambda t)^ne^{-\lambda t}}{n!}$$
$$=e^{[M_{\xi}(s)-1]\lambda t}$$
# nonhomogeneous poisson
$$\tilde{N}(t)$$
1. $\tilde{N}(0)\equiv 0$
2. Independent $\tilde{N}(t)-\tilde{N}(s)\bot\tilde{N}(s)$
3. rare $P(\tilde{N}(t,t+\Delta t)=1)=\lambda(t)\Delta t+o(\Delta t)$, $P(\tilde{N}(t,t+\Delta t)\ge 2)=o(\Delta t)$

## pmf
$$m(t)=\int_0^t\lambda(u)du$$
$$m(s,t)=\int_s^t\lambda(u)du$$
$$P(\tilde{N}(t)=k)=\frac{m(t)^ke^{-m(t)}}{k!}$$
$$\Rightarrow P(\tilde{N}(s,t)=k)=\frac{m(s,t)^ke^{-m(s,t)}}{k!}$$
## pf 
$$G_{\tilde{N}(t)}(s)=Es^{\tilde{N}(t)}$$
$$G_{\tilde{N(t+\Delta t)}}(s)-G_{\tilde{N}(t)}(s)=Es^{\tilde{N}(t)}E[s^{\tilde{N}(t+\Delta t)-\tilde{N}(t)}-1]$$
$$=G_{\tilde{N}(t)}(s)[\sum_{k=0}^\infty s^kP(\tilde{N}(t+\Delta t)-\tilde{N}(t)=k)-1]$$
$$=G_{\tilde{N}(t)}(s)\lambda(t)(s-1)\Delta t$$

$$\int_0^u\frac{\frac\partial{\partial t}G_{\tilde{N}(t)}(s)}{G_{\tilde{N}(t)}(s)}=\int_0^u\lambda(t)(s-1)dt$$
$$G_{\tilde{N}(u)}(s)=e^{(s-1)m(u)}$$
## (2)
$$Eu^{\tilde{N}(t)}=Eu^{\tilde{N}(s)}u^{\tilde{N}(s,t)}$$
$$G_{\tilde{N}(t)}(u)=G_{\tilde{N}(s)}(u)Eu^{\tilde{N}(s,t)}$$
$$\Rightarrow Eu^{\tilde{N}(s,t)}=e^{(u-1)[m(t)-m(s)]}=e^{(u-1)\int_s^t\lambda(u)du}$$
## arrival time($S_n$)
$$P(S_1>t)=P(\tilde{N}(t)=0)=\frac{m(t)^0e^{-m(t)}}{0!}=e^{-m(t)}$$
$$F(t)=1-e^{-m(t)}$$
$$f(t)=e^{-m(t)}m’(t)=\lambda(t)e^{-m(t)}$$
$$P(S_2>t)=e^{-m(t)}+\frac{m(t)e^{-m(t)}}{1!}$$
Cdf of $S_2$ $$1-e^{-m(t)}-m(t)e^{-m(t)}$$
Pdf$$\lambda(t)e^{-m(t)}-\lambda(t)e^{-m(t)}+m(t)e^{-m(t)}\lambda(t)$$
### $S_n$
### $X_n$
$$X_1=S_1$$
pdf
$$\lambda(t)e^{-m(t)}\exp()$$
$$X_2=S_2-S_1$$
$$P(X_2>t)=\int_0^\infty P(X_2>t|X_1=s)P(X_1=s)ds$$
($X_1,X_2$不独立)
$$=\int_0^\infty e^{-m(s+t)}\lambda(s)ds$$
Cdf $$1-\int_0^\infty e^{-m(t+s)}\lambda(s)ds$$
pdf
$$\int_0^\infty e^{-m(t+s)}\lambda(s)\lambda(t+s)ds$$
$\tilde{N}(t)$非齐次 $m(t)=\int_0^t\lambda(u)du, m^{-1}(t)$
Define $N(t)=\tilde{N}(m^{-1}(t))$:齐次poisson
1. $N(0)=\tilde{N}(0)\equiv 0$
2. $P(N(t)=k)=P(\tilde{N}(m^{-1}(t))=k)=P(\tilde{N}(u)=k)=\frac{m(u)^ke^{-m(u)}}{k!}=\frac{t^ke^{-t}}{k!}$
3. Stationary: $$N(t)-N(s)=N(t-s):P(N(t)-N(s)=k)=P(\tilde{N}(m^{-1}(t))-\tilde{N}(m^{-1}(s))=k)=P(\tilde{N}(v,u)=k)$$
$$=\frac{m(v,u)^ke^{-m(v,u)}}{k!}=\frac{(t-s)^ke^{-(t-s)}}{k!}\sim poisson(\lambda(t-s))$$
4. Independent $N(t)-N(s)\bot N(s)$ $$Ee^{a[N(t)-N(s)]+bN(s)?=Ee^a[N(t)-N(s)]}Ee^{bN(s)}$$
$$LHS=Ee^{a[\tilde{N}(m^{-1}(t))-\tilde{N}(m^{-1}(s))]+b\tilde{N}(m^{-1}(s))}$$
$$=Ee^{a[\tilde{N}(u)-\tilde{N}(v)]+b\tilde{N}(v)}$$
$$=Ee^{a[\tilde{N}(u)-\tilde{N}(v)]}Ee^{b\tilde{N}(v)}$$
$$=Ee^{a[N(t)-N(s)]}Ee^{bN(s)}$$



# Markov Chain
$E=\{e_1,\dots,e_N\}=\{1,\dots,N\}(N=\infty or N<\infty)$
$T=\{0,1,2,\dots\}$
## Markov property
下个时间点取值只和这个时间点有关
$$S_{n+1}\sim F(S_n)$$$$P(X_{n+1}|X_n)=P(X_{n+1}|X_n,X_{n-1},\dots,X_0)$$
## $\{X_n\}$
$$P(X_{n+1}=j|X_n=i)=P(X_{n+1}=j|X_n=i,X_{n-1}=i_{n-1},\dots,X_0=i_0)$$
$$\forall i,j,i_0,i_1,\dots,i_{n-1}\in E$$
1. $X_0$（初始时间）$P_0(P_0(1),\dots,P_0(N))\sim$初始分布。$P_0(i)=P(X_0=i)$
Transition prob: $P_{ij}=P_{i,j:n}=P(X_{n+1}=j|X_n=i)$
2. $(X_0,X_1)$
$P(X_0=i_0,X_1=i_1)=P(X_1=i_1|X_0=i_0)P(X_0=i_0)=P_{i_0i_1}P_0(i_0)$
3. $(X_0,X_1,X_2)$
$$P(X_0=i_0,X_1=i_1,X_2=i_2)=P(X_0=i_0)P(X_1=i_1|X_0=i_0)P(X_2=i_2|X_1=i_1,X_0=i_0)$$
$$=P_0(i_0)P_{i_0i_1}P_{i_1i_2}$$
4. $(X_0,\dots,X_k)$
$$P(X_0=i_0,\dots,X_k=i_k)=P_0(i_0)P_{i_0i_1}\dots P_{i_{k-1}i_k}$$
## 1步transition prob
$$P=\begin{pmatrix}P_{11},\dots,P_{1N}\\\dots\\P_{N1},\dots,P_{NN}\end{pmatrix}$$
$$\sum_{j=1}^NP_{ij}=1$$
## m步transition prob
$$P_{ij}^{(m)}=P(X_{n+m}=j|X_n=i)$$
$$P^{(m)}=\begin{pmatrix}P_{11}^{(m)},\dots,P_{1N}^{(m)}\\\dots\\P_{N1}^{(m)},\dots,P_{NN}^{(m)}\end{pmatrix}$$


$$X_0\sim P_0$$
$$X_1\sim P_1=(P_1(1),\dots,P_1(N))$$
$$P_1(i)=P(X_1=i)$$
$$P_1(i)=P(X_1=i)=\sum_{k=1}^NP(X_1=1|X_0=k)P(X_0=k)=\sum_{k=1}^NP_0(k)P_{ki}$$
$$=P_0P[;i]=(P_0P)[;i]$$
$$\Rightarrow P_1=P_0P$$


$$X_2\sim P_2=(P_2(1),\dots,P_2(N))$$
$$P_2(i)=P(X_2=i)=\sum_{j=1}^N P(X_2=i|X_1=j)P(X_1=j)$$
$$=\sum_{j=1}^NP_1(j)P_{ji}=P_1P[;i]$$
$$P_2=P_1P$$
同理按$X_0$取条件$$P_2(i)=P_0P^{(2)}[;i]$$
$$P^{(2)}=PP$$
$$\Rightarrow P_n=P_0P^n=P_0P^{(n)}$$
## C—K方程
$$P^{(n+m)}=P^{(n)}P^{(m)}$$
## $(X_0,X_2)$
$$P(X_0=i_0,X_2=i_2)=\sum_{i_1=1}^NP(X_0=i_0,X_1=i_1,X_2=i_2)$$
$$=\sum_{i_1=1}^NP_0(i_0)P_{i_0i_1}P_{i_1i_2}$$
$$=P_0(i_0)(PP)[i_0,i_2]$$

$$P(X_0=i_0,X_2=i_2)=P(X_2=i_2|X_0=i_0)P(X_0=i_0)=P_{i_0i_2}^{(2)}P_0(i_0)$$

