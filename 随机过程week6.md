# conditional $(S_n)\sim \Gamma(n,\lambda)$
$(S_1,\dots,S_n)|_{N(t)=n}$
$S_k|_{N(t)=n}$
# ordered statistics
$(X_i)_{i=1}^n(iid)\sim X$
$f(x)$ : pdf of $X$ 
$F(x)$: cdf of X
$X_{(1)},\dots,X_{(n)}$
Joint:$$f(x_1\dots x_n)=n!f(X_1=x_1,\dots,X_n=x_n)$$
$$=n!f(x_1)\dots f(x_n)$$, $(x_1<\dots<x_n)$
$P(X_{(1)}=x_1,\dots,X_{(n)}=x_n)$,
$$f_{X_{(k)}}(x_k)=P(X_{(k)}=x_k)$$
$${n\choose k-1}P(X_1\le x_k\dots X_{k-1}\le x_k)P(X_k\le[x_k,x_{k+\Delta}])P(X_{k+1}\ge x_{k+\Delta},\dots,X_n\ge X_{k+\Delta})$$
$$={n-k+1\choose 1}{n\choose k-1}F^{k-1}(x_k)f(x_k)(1-F(x_k))^{n-k}$$

## $(S_1,\dots,S_n)|_{N(t)=n}$
$n=1$, $S_1|_{N(t)=1}$
$$P(S_1\ge m|N(t)=1)=\frac{P(S_1\ge m,N(t)=1)}{P(N(t)=1)}$$
$$=\frac{P(N(m)=0)P(N(t)=N(m)=1)}{P(n(t)=1)}$$
$$=\frac{t-m}t$$
Cdf:$$P(S_1\le m|N(t)=1)=\frac mt,m\in[0,t]$$
pdf:
$$\frac 1t$$
$m\in[0,t]\sim$ uniform distribution(0,t)

$n=2$  $(S_1,S_2)|_{N(t)=2}$
$$P(S_1=m_1,S_2=m_2|N(t)=2)=\frac{P(S_1=m_1,S_2=m_2,N(t)=2)}{P(N(t)=2)}$$
$$=\frac{P(N(m_1)=0,N(m_1,m_1+\Delta m_1)=1,N(m_1+\Delta m_2)=0,N(m_2,m_2+\Delta m_2)=1)}{p(N(t)=2)}$$
$$=\frac{2!\Delta m_1\Delta m_2}{t^2}$$
Conditional pdf
$$f_{(S_1,S_2)|N(t)=2}(m_1,m_2)=\frac{2!}{t^2}(0\le m_1<m_2\le t)$$

$$(S_1,\dots,S_n)|_{N(t)=n}=\frac{n!}{t^n}$$

$$f(x)=\frac 1t\Leftrightarrow (X_i)^n_{i=1}(iid)\sim uniform[0,t]$$
$$(S_1,\dots,S_n)|_{N(t)=n}=(u_{(1)}\dots u_{(n)})$$


## Back casting
$$P(N(s)=m|N(t)=n),s<t$$
$$=\frac{P(N(s)=m,N(t)=n)}{P(N(t)=n}$$
$$=\frac{P(N(s)=m,N(t)-N(s)=n-m)}{P(N(t)=n)}$$
$$={n\choose m}(\frac st)^m(\frac{t-s}t)^{n-m}$$
$$=P(B(n,\frac st)=m)$$
## $S_k|_{N(t)=n}$
Cdf:$$P(S_k\le m|N(t)=n)=\frac{P(S_k\le m,N(t)=n)}{P(N(t)=n)},N(m)=k+l$$
$$=\frac{P(N(m)=k+l,N(t)-N(m)=n-k-l,l\ge 0)}{P(N(t)=n)}$$
$$=\sum_{l=0}^{n-k}{n\choose k+l}(\frac mt)^{k+l}$$
$$=\sum_{l=0}^{n-k}P(B(n,\frac mt)=k+l)$$
$$=\sum_{l=0}^{n-k}P(N(m)=k+l|N(t)=n)$$


$$f_{s_k|N(t)=n}(m)=\frac \partial{\partial m}\sum_{t=0}^{n-k}{n\choose k+l}(\frac mt)^{k+l}(\frac{t-m}t)^{n-k-l}$$
$$=\frac{n!}{(k-1)!(n-k)!}(\frac mt)^{k-1}\frac 1t(\frac{t-m}t)^{n-k}$$
That is
$${n-k+1\choose 1}{n\choose k-1}F^{k-1}(x_k)f(x_k)(1-F(x_k))^{n-k}$$

## e.g.1
$N(t)\sim$ poisson process $(\lambda)$ $S_1,S_2$  Arrival time
$f:R_+\rightarrow k$ prove $E\sum_{i=1}^{N(t)}f(S_i)=\lambda\int0^tf(s)ds$

$$E(\sum_{i=1}^{N(t)})=\sum_{n=0}^\infty E(\sum_{i=1}^{N(t)}f(S_i|N(t)=n)P(N(t)=n)$$
$$=\sum_{n=0}^\infty E\sum_{i=1}^n f(u_{(i)})P(N(t)=n)$$
$$=\sum_{n=0}^\infty E\sum_{i=1}^n f(u_{i})P(N(t)=n)$$
$$=\sum_{n=0}^\infty n\int_0^tf(x)\frac 1t dxP(N(t)=n)$$
$$=EN(t)\frac 1t\int_0^tf(x)dx$$
$$v=\lambda\frac 1t\int_0^tf(x)dx$$


## e.g.2
$N(t)\sim$ poisson process$(\lambda)$,  $S_1,S_2\dots$ Arrival time
Suppose $N(t)=2$, $E(S_1S_2|N(t)=2)=?$

$$E(S_1S_2|N(t)=2)$$
$$(S_1S_2)|_{N(t)=2}=(u_{(1)}u_{(2)})$$
$$E(S_1S_2|N(t)=2)=Eu_{(1)}u_{(2)}=Eu_1u_2=Eu_1Eu_2$$
$$Eu_i=\int_0^tx\frac 1t dx=\frac 1t\frac{x^2}2|_0^t=\frac t2$$

