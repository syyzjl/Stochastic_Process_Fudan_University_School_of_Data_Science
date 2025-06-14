# e.g. 
$[0,t]$ $N(t)$: #{撞击}~poisson process$(\lambda)$ $\lambda$越大撞击越频繁
$\xi(i)\sim(iid)\exp(\beta)\bot N(t)$
累积磨损量>$\alpha$
平均寿命$(\eta)$
$$E\eta=\int_0^\infty P(\beta>t)dt=\int_0^\infty P(\sum_{i=1}^{N(t)}\xi_i\le\alpha)dt$$
$$=\int_0^\infty\sum_{n=0}^\infty P(\sum_{i=1}^n\xi_i\le\alpha)P(N(t)=n)dt$$
$$\{\eta>t\}\Leftrightarrow\{\sum_{i=1}^{N(t)}\xi_i\le\alpha\}$$


$$S_n=\sum_{i=1}^n\xi_i\sim\Gamma(n,\beta)\Rightarrow\tilde{N}(t)=\{n:S_n\le t<S_{n+1}\}\sim poisson(\beta)$$
$$P(N(t)=n)dt=\int_0^\infty\sum_{n=0}^\infty P(\tilde{N}(\alpha)=k)=\frac{(\lambda t)^ne^{-\lambda t}}{n!}dt$$
$$=\sum_{n=0}^\infty\sum_{k=n}^\infty\frac{(\alpha\beta)^ke^{-\alpha\beta}}{\lambda k!}\int_0^\infty\frac{\lambda^{n+1}t^ne^{-\lambda t}}{\Gamma(n+1)}dt$$
$$=\sum_{k=0}^\infty(k+1)\frac{(\alpha\beta)^ke^{-\alpha\beta}}{\lambda k!}$$
$$=\sum_{k=1}^\infty\frac{(\alpha\beta)^ke^{-\alpha\beta}}{\lambda (k-1)!}+\sum_{k=0}^\infty\frac{(\alpha\beta)^ke^{-\alpha\beta}}{\lambda k!}$$
$$=\sum_{k=0}^\infty\frac{(\alpha\beta)^ke^{-\alpha\beta}}{k!}\frac{\alpha\beta+1}{\lambda}$$
$$=\frac{1+\alpha\beta}\lambda$$


# superposition
$poisson(\lambda_1)$ $poisson(\lambda_2)$
两个流合到一起$\Rightarrow$ $N(t)=N_1(t)+N_2(t)$, Then $N(t)$ is a $poisson(\lambda_1+\lambda_2)$
$N_1(t)|_{N(t)}$ $=B(n,\frac{\lambda_1}{\lambda_1+\lambda_2})$$(*)$
## 1
$N(0)=0$
## 2
Distribution 
$$P(N(t)=k)=\frac{[(\lambda_1+\lambda_2)t]^ke^{-(\lambda_1+\lambda_2)t}}{k!}$$
Proof:
$$P(N(t)=k)=P(N_1(t)+N_2(t)=k)=\sum_{m=0}^kP(N_1(t)+N_2(t)=k|N_1(t)=m)P(N_1(t)=m)$$
$$=\sum_{m=0}^kP(N_2(t)=k-m)P(N_1=m)$$
$$=\sum_{m=0}^k\frac{(\lambda_2t)^{k-m}e^{-\lambda_2t}}{(k-m)!}\frac{(\lambda_1t)^me^{-\lambda_1t}}{m!}$$
$$=e^{-(\lambda_1+\lambda_2)t}\frac{(\lambda_2t)^k}{k!}\sum_{m=0}^k(\frac{\lambda_1}{\lambda_2})^m{k\choose m}$$
$$=\frac{e^{-(\lambda_1+\lambda_2)t}}{k!}(\lambda_1t+\lambda_2t)^k$$
## independent
$s<t$
$N(t)<N(s)\bot N(s)$
$LHS=N_1(t)+N_2(t)-N_1(s)-N_2(s)=N_1(t)-N_1(s)+N_2(t)-N_2(s)$
MGF:$$ Ee^{a(N(t)-N(s))+bN(s)}?=Ee^{a(N(t)-N(s))}Ee^{b(N(s))}$$
Proof:
$$LHS=Ee^{a(N_1(t)-N_1(s)+N_2(t)-N_2(s))+b(N_1(s)+N_2(s)}$$
$$=Ee^{a(N_1(t)-N_1(s))}e^{a(N_2(t)-N_2(s))}e^{bN_1(s)}e^{bN_2(s)}$$
$$=E[e^{a(N_1(t)-N_1(s))}e^{bN_1(s)}]E[e^{a(N_2(t)-N_2(s))}e^{bN_2(s)}]$$
$$=Ee^{a(N_1(t)-N_1(s))}Ee^{a(N_2(t)-N_2(s))}Ee^{bN_1(s)}Ee^{bN_2(s)}$$
$$=Ee^{a(N_1(t)-N_1(s))}e^{a(N_2(t)-N_2(s))}Ee^{bN_1(s)}e^{bN_2(s)}$$
$$=Ee^{a(N(t)-N(s))}Ee^{b(N(s))}$$

## stationary
$s<t$
$$N(t)-N(s)=N(t-s)?$$
$$LHS=N_1(t)-N_1(s)+N_2(t)-N_2(s)=\xi+\eta$$
$$RHS=N_1(t-s)+N_2(t-s)$$
利用全概率公式，对 $\xi+\eta$ 的 $\xi$ 取条件


## $(*)$
$$P(N_1(t)=k|N(t)=n)=\frac{P(N_1(t)=k,N_1(t)+N_2(t)=n)}{P(N(t)=n)}$$
$$=\frac{P(N_1(t)=k)P(k+N_2(t)=n)}{P(N(t)=n)}$$
$$={n\choose k}(\frac{\lambda_1}{\lambda_1+\lambda_2})^k(\frac{\lambda_1}{\lambda_1+\lambda_2})^{n-k}$$


$\{N_i(t)\}_{i=1}^k$  $N_i(t)\sim poisson(\lambda_i)$
Def. $$N(t)=\sum_{i=1}^kN_i(t)$$
$$\Rightarrow\begin{cases}N(t)\sim poisson(\sum_{i=1^k\lambda_i})\\N_i(t)|_{N(t)=n}\sim B(n,\frac{\lambda_i}{\sum_{i=1}^k\lambda_i})\end{cases}$$

# Decomposition
$N(t)\sim Poisson(\lambda)$
Type1. $P_1$ $N_1(t)$
Type2. $P_2$ $N_2(t)$
Then, $N_1(t)\sim poisson(\lambda P_1)$, $N_2(t)\sim poisson(\lambda P_2)$, $N_1(t)\bot N_2(t)$
## 1
$N(0)=0$
## 2
$P(N_1(t)=k)=\frac{(\lambda P_1t)^ke^{-\lambda P_1t}}{k!}$
Proof:$$LHS=\sum_{m=k}^\infty P(N_1(t)=k|N(t)=m)$$
$$=\sum_{m=k}^\infty{m\choose k}p_1^k(1-p_1)^{m-k}\frac{(\lambda t)^me^{-\lambda t}}{m!}$$
$$=\frac{P_1^k(\lambda t)^k}{k!}e^{-\lambda t}\sum_{m^*=0}^\infty\frac{(1-P_1)^{m^*}{\lambda t}^{m^*}}{m^*}$$
$$=\frac{(\lambda P_1t)^ke^{-\lambda P_1t}}{k!}$$


## independent
## stationary
$N_1(t)-N_1(s)=N_1(t-s)$
$RHS\sim poisson(\lambda P_1(t-s))$
$$LHS=P(N_1(s,t)=k)=\sum_{m=k}^\infty P(N_1(s,t)=k|N(s,t)=m)P(N(s,t)=m)$$
$$=\sum_{m=k}^\infty{m\choose k}P_1^k(1-P_1)^{m-k}(\lambda(t-s))^m\frac{e^{-\lambda(t-s)}}{m!}$$
## $N_1(t)\bot N_2(t)?$
$$P(N_1(t)=m,N_2(t)=k)=P(N_1(t)=m,N(t)=m+k)$$
$$=P(N_1(t)=m|N(t)=m+k)P(N(t)=m+k)$$
$$={m+k\choose m}P_1^m(1-P_1)^k\frac{(\lambda t)^{m+k}e^{-\lambda t}}{(m+k)!}$$
$$=\frac{e^{-\lambda tP_1}(\lambda tP_1)^m(\lambda t(1-P_1))^ke^{-\lambda t(1-P_1)}}{m!k!}$$
$$=P(N_1(t)=m)P(N_2(t)=k)$$

N(t):poisson
Type1:$P_1$
Type2:$P_2$
$\dots$
Type k:$P_k$

Then $$N_i(t)\sim poisson(\lambda P_i)$$
# compound poisson
Rare不需要满足
$(\xi_i)\sim(iid)(\xi)$    $N(t)\sim$ poisson process $(\lambda)$
$Z(t)=\sum_{i=1}^{N(t)}\xi_i$    $(\xi_i)\bot N(t)$   $Z(0)\equiv 0$ 

## eg1
$\xi_i\sim(iid)Bernoulli(p)$   $\xi_i=\begin{cases}1,p\\0,1-p\end{cases}$  Type1 and Type2
$Z(t)=\sum_{i=1}^{N(t)}\xi_i\sim N_1(t)$  (Type1)


## independent/stationary
## independent
$s<t$   $Z(t)-Z(s)\bot Z(s)??$
$$Ee^{a[Z(t)-Z(s)]+bZ(s)}=Ee^{a[Z(t)-Z(s)]}Ee^{bZ(s)}??$$
$$LHS=Ee^{a\sum_{i=N(s)+1}^{N(t)}\xi_i+b\sum_{i=1}^{N(s)}\xi_i}$$
$$=E\{Ee^{a\sum_{i=N(s)+1}^{N(t)}+b\sum_{i=1}^{N(s)}\xi_i}|N\}$$
$$=EEe^{a\sum_{i=N(s)+1}^{N(t)}\xi_i}Ee^{b\sum_{i=1}^{N(s)}\xi_i}$$
分别对$N,(\xi_i),(\xi_i)$
$$=Ee^{a\sum_{i=N(s)+1}^{N(t)}\xi_i}Ee^{b\sum_{i=1}^{N(s)}\xi_i}$$


## stationary
$s<t$    $Z(t)-Z(s)=Z(t-s)$
$\Leftrightarrow Ee^{a[Z(t)-Z(s)]}=Ee^{aZ(t-s)}??$
$$LHS=E\{Ee^{a\sum_{i=N(s)+1}^{N(t)}\xi_i}|N\}$$
$$=E[Ee^{a\xi_i}]^{N(t)-N(s)}$$
$$=Ee^{a\sum_{i=1}^{N(t)-N(s)}\xi_i}=Ee^{a\sum_{i=1}^{N(t-s)}\xi_i}=Ee^{aZ(t-s)}$$
## $EZ(t)$    $VarZ(t)$
$$EZ(t)=E\sum_{i=1}^{N(t)}\xi_i=E\{E\sum_{i=1}^{N(t)}\xi_i|N(t)\}=E\sum_{i=1}^{N(t)}E\xi_i=E\mu N(t)$$
$$=\mu \lambda t$$
$$VarZ(t)=Var\{E\sum_{i=1}^{N(t)}\xi_i|N(t)\}+E\{Var\sum_{i=1}^{N(t)}\xi_i|N(t)\}$$
$$=Var(\mu N(t))+EN(t)\sigma^2$$
$$=\mu^2\lambda t+\sigma^2\lambda t$$
