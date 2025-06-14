# example
## 1
Gamma $f(x)=\frac{\lambda^a}{P(a)}x^{a-1}e^{-\lambda x},x>0$
$\mathbb{E}(x)=\int_0^\infty x\frac{\lambda^a}{P(a)}x^{a+1-1}e^{-\lambda x}dx$
$=\int\frac{\lambda^{a+1}}{P(a+1)}x^{a+1-1}e^{-\lambda x}\frac{P(a+1)}{\lambda P(a)}dx=\frac{a}{\lambda}$
$var(x)=\mathbb{E}X^2-(\mathbb{E}X)^2=\frac{a}{\lambda^2}$
## 2
Poisson($\lambda$)

## Law of total variance
$VarX_1=Var\{E[X_1|X_2]\}+E\{Var[X_1|X_2]\}$
$g(X_2)=E[X_1|X_2],h(X_2)=Var[X_1|X_2]$

## e.g.
N claims in a year. $N\sim Poisson(\lambda)$
Given Nm claim size$\sim$ Gamma(9,0.06) independent

$X_i|N\sim(iid)Gamma(9,0.06)$, $N\sim Poisson(\lambda)$

$E\sum_{i=1}^NX_i=E[E(\sum_{i=1}^N X_i|N)]=E[\frac{9}{0.06}N]=\frac{9}{0.06}\lambda$

$Var(\sum_{i=1}^N)=Var[E(\sum_{i=1}^NX_i|N)]+E[Var(\sum_{i=1}^NX_i|N)]$
$=Var[\frac{9}{0.06}N]+E[\sum_{i=1}^NVar(X_i)+\sum_{i\ne j}cov(X_i,X_j)]$
$=Var[\frac{9}{0.06}N]+E[\frac{9}{0.06^2}N]$
$=(\frac{9}{0.06})^2\lambda+\frac{9}{0.06^2}\lambda$

## Probability inequality
### Markov inequality
If $x\ge 0$, r.v. $a>0$(constant)
$P(X>a)\le \frac{EX}{a}$  $(EX<\infty)$

Proof:
$a1_{X\ge a}=\begin{cases}a,X\ge a\\0,X<a\end{cases}\le X$
左右求期望
$ap(X\ge a)\le EX$

### Chebyshev’s inequality
X r.v. $EX=\mu$, $VarX=\sigma^2$ 
$P(|X-\mu|\ge a)\le\frac{\sigma^2}{a^2}$

Proof:
$a^21_{|X-\mu|\ge a}=\begin{cases}a^2,|X-\mu|\ge a\\0,|X-\mu|<a\end{cases}\le|X-\mu|^2$
左右取期望
$a^2P(|X-\mu|\ge a)\le E|X-\mu|^2-VarX=\sigma^2$ (a的系数可以换成任意k次)

$P(|X-\mu|\ge a)\le\frac{E|X-\mu|^k}{a^k}$

### (Chernoff Bounds)
$X$  $MGF=\varphi(t)=Ee^{tx}<\infty$
$\begin{cases}P(X\ge a)\le e^{-at}\varphi(t),t>0\\P(X>a)\le e^{-at}\varphi(t),t<0\end{cases}$
$P(X\ge a)=P(e^{tx}\ge e^{ta})\le\frac{Ee^{tx}}{e^{ta}}=e^{-ta}\varphi(t),t>0$
$P(X< a)=P(e^{tx}> e^{ta})=e^{-ta}\varphi(t),t<0$


# Limit theory(r.v.)(Probability a.s. Distribution $L_p$)
## convergence in probability
$X_n\underrightarrow{n\rightarrow\infty}x$
(对$\forall\epsilon>0,\exists N>0,s.t.n>N,|X_n-x|\le\epsilon$)
$X\quad \underrightarrow{p}\quad x$
def $p(\omega:|X_n(\omega)-X(\omega)|\ge\epsilon)\underrightarrow{n\rightarrow\infty}\quad 0$
1. If n large, $X_n(\omega)\sim X(\omega)$
2. $|X_n-X|\ge\epsilon$可以发生，概率小

## convergence in distribution(weak)
$X_n\underrightarrow{D(d)}X$
$F_n:$ cdf of $X_n$   $F:X$ 的cdf
$F_n(x)\underrightarrow{n\rightarrow\infty}F(x)$ x是$F(x)$的连续点
(Weak convergence)
$F_n(x)=p(X_n\ge x)$ constant

E.g. $X\sim N(0,1)$ $Y=-X$, $X(\omega)=-Y(\omega)$, $X(\omega)=Y(\omega)$ 分布一样，每一个点的取值不一样

依概率比依分布强。依概率可以推出依分布。

$X_n\underrightarrow{p}X\Rightarrow X_n\underrightarrow{d}X$ ($\lim_{n\rightarrow\infty}F_n(x)=F(x)$ x continuous point)
$F_n(t)=P(X_n\le t)\ge P(X_n\le t,X\le t-\epsilon)=P(X\le t-\epsilon)-P(X\le t-\epsilon,X_n>t=F(t-\epsilon)\ge F(t-\epsilon)-P(|X_n-X|\ge\epsilon)$
$n\rightarrow\infty:\lim_{n\rightarrow\infty}F_n(t)\ge F(t-\epsilon)-0,\forall\epsilon>0$
$\epsilon\rightarrow 0:\lim_{n\rightarrow 0}F_n(t)\ge F(t)$(1)
$F(t+\epsilon)=P(X\le t+\epsilon)\ge P(X\le t+\epsilon,X_n\le t)=P(X_n\le t)-P(X_n\le,X>t+\epsilon)\ge F_n(t)-P(|X_n-X|\ge \epsilon)$
$n\rightarrow\infty:F(t+\epsilon)\ge\lim_{n\rightarrow\infty}F_n(t)-0$
$\epsilon\rightarrow 0:F(t)\ge\lim_{n\rightarrow\infty}F_n(t)$(2)

(1)+(2)$\Rightarrow\lim_{n\rightarrow\infty}F_n(t)=F(t)$

2.$X_n\underrightarrow{d}X\&X=constant\Rightarrow X_n\underrightarrow{p}X$
$X\equiv c$
$P(|X_n-X|\ge \epsilon)\underrightarrow{n\rightarrow\infty}0$
$=P(X_n\ge c+\epsilon)+P(X_n\le c-\epsilon)$
$=1-F_n(c+\epsilon)+F_n(c-\epsilon)$=1-1+0=0

$F_n(t)\underrightarrow{n\rightarrow\infty}F(t)=P(X\le t)=\begin{cases}0,c>t\\1,c\le t\end{cases}$
$X\equiv c$,$p\Leftrightarrow d$
## almost sure convergence
$X_n\underrightarrow{a.s.}X$
$\Omega_0\in\Omega$ and $P(\Omega_0)=0$
取$\omega$ $X_n(\omega),X(\omega)$已给定，没有随机性
$\forall\omega\in\Omega-\Omega_0$, $X_n(\omega)\underrightarrow{n\rightarrow\infty}X(\omega)$
a.s.充要条件$\forall\epsilon>0,\lim_{N\rightarrow\infty}P(\cup_{n=N}^\infty|X_n-X|\ge\epsilon)=0$(1)
充分条件$\sum_{n=1}^\infty P(|X_n-X|\ge\epsilon)<\infty$(2)
Assume (1) is correct
(2)$\lim_{N\rightarrow\infty}\sum_{n=N}^\infty P(|X_n-X|\ge \epsilon)=0$
$\lim_{N\rightarrow\infty}P(\cup_{n=N}^\infty|X_n-X|\ge \epsilon)\le\lim_{N\rightarrow\infty}\sum_{n=N}^\infty P(|X_n-X|\ge \epsilon)=0$

Proof for (1)
$\forall\epsilon>0,\exists N>0,s.t.n>N,|X_n-X|\le\epsilon$（收敛）
$\cap_{\epsilon>0}\cup_{N>0}\cap_{n>N}|X_n(\omega)-X(\omega)|\le\epsilon$
$P(\cup_{\epsilon>0}\cap_{N>0}\cup_{n>N}|X_n(\omega)-X(\omega)\ge\epsilon)|=0\Leftrightarrow a.s.$
第一层cup是$A_N(\epsilon)$，第二层cap是$B(\epsilon)$
$P(\cup_{\epsilon>0}B(\epsilon))=0$, $B(\epsilon)$单调
$\Rightarrow$对每一个$\epsilon>0,P(B(\epsilon))=0\Leftrightarrow P(\cap_{N>0}A_N(\epsilon))=0\Rightarrow\lim_{N\rightarrow\infty }P(A_N(\epsilon))=0$
取$n=N$，(1)$\Rightarrow \lim_{N\rightarrow\infty}P(|X_n-X|\ge\epsilon)=0$


## $X_n\underrightarrow{L_p}X$
$E|X_n-X|^p\underrightarrow{n\rightarrow\infty}0$ 可推依概率收敛
$L_p\Rightarrow X_n\underrightarrow{p}X\Rightarrow P(|X_n-X|\ge\epsilon)\le\frac{E|X_n-X|^p}{\epsilon^p}\underrightarrow{n\rightarrow\infty}0$

# LLN(Law of Large Numbers)
## Bernoulli
$X_i=\begin{cases}1,Head(p)\\0,Tail(1-p)\end{cases},S_n=\sum_{i=1}^nX_i\sim B(n,p)$, $(X_i)\sim iid$
$\frac{S_n}{n}(r.v.)\rightarrow p$
(P弱大数律)（a.s.强大数律）
$P(|\frac{S_n}{n}-p|\ge\epsilon)\underrightarrow{n\rightarrow\infty}0$
$=P(|\frac{\sum(X_i-p)}{n}|\ge\epsilon)\le\frac{E|\sum(X_i-p)|^2}{\epsilon^2n^2}$
上方$=E\sum_{i,j}(X_i-p)(X_j-p)=\sum_iE(X_i-p)^2=\sum_iVarX_i$
因此上式$=\frac{kn}{\epsilon^2n^2}=\frac{k}{\epsilon^2n}$
（放2阶做不出强大数律，因为放太松，要到4阶）

$E\sum_{i,j,k,l}(X_i-p)(X_j-p)(X_k-p)(X_l-p)$
（4，0）是O(n)的，（1，3）都是0，（2，2）是$O(n^2)$的
（证不出收敛时可尝试用更高阶矩）