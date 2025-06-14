# Distribution
## Exponential
$f(x)=\lambda e^{-\lambda x}$ ($x\ge 0$)
$P(X\ge t$)$=\int_t^\infty \lambda e^{-\lambda x}dx$=$-e^{-\lambda x}|_t^\infty$
无记忆性 $X\sim exp(\lambda)\rightarrow e^{-\lambda t}$$\Rightarrow P(X\ge t+s|X\ge t)=P(X\ge s)$
## Gamma
$f(x)=\frac{\lambda^a}{P(a)}x^{a-1}e^{-\lambda x}$, $x\ge 0$.
Pamma$(\lambda,a)$ $P(a)=(a-1)!$
取$a=1$, $f(x)=\lambda e^{\lambda x}$, $x\ge 0$
$X_1,\dots,X_\alpha{i.i.d\atop\sim}exp(\lambda)$
$\sum_{i=1}^\alpha X_i{d\atop\sim}Pamma(\lambda,\alpha)$
# Expectation
$\mathbb{E}g(x){\Delta\atop=}\begin{cases}\sum_x g(x)p(x)\quad 离散\\ \int_x g(x)f(x)dx\quad 连续\end{cases}$
# Variance
$VarX{\Delta\atop=}\mathbb{E}(X-\mathbb{E}X)^2=\mathbb{E}X^2-(\mathbb{E}X)^2$
# Moment
$\mathbb{E}(X-\mathbb{E}X)^k$
# MGF
$M_X(t){\Delta\atop=}\mathbb{E}e^{tX}$
$\frac{\partial}{\partial t}M_X(t)|_{t=0}=\mathbb{E}e^{tX}X=\mathbb{E}X$
$\frac{\partial}{\partial t^2}M_X(t)|_{t=0}=\mathbb{E}e^{tX}X^2|_{t=0}=\mathbb{E}X^2$
If $M_X(t)\exists$, determines the dissemination of $X$.
$X{d\atop=}Y$, $M_X(t)=M_Y(t)$
# Random vector
$X(\omega)$ $r.v.$ $\Omega\rightarrow \mathbb{R}$
$X{\Delta\atop=}\begin{pmatrix}X_1\\\dots\\X_m\end{pmatrix}$ Random vector
$X:\mathbb{R}\rightarrow\mathbb{R}^m$ $X(\omega)=\begin{pmatrix}X_1(\omega)\\\dots\\X_m(\omega)\end{pmatrix}$
## Distribution
### cdf(joint)
$F(x)=F(x_1\dots x_m)=P(X_1(\omega)\le x_1\dots X_m(\omega)\le x_m)$
### 离散 pmf(joint)
$p(x)=p(x_1\dots x_m)=p(X_1(\omega)=x_1,\dots,X_m(\omega)=x_m)$
### 连续 pdf(joint)
$f(x)=f(x_1\dots x_m)=\frac{\partial}{\partial x_1}\dots\frac{\partial}{\partial x_m}F(x_1\dots x_m)$
### (marginal) pmf
$p_{x_1}(x_1)=\sum_{x_2\dots x_m}p(x_1\dots x_m)$
Proof:(With Law of Total Probability)
$p_{x_1}=p(X_1(\omega)=x_1)=\sum_{x_2\dots x_m}p(X_1(\omega)=x_1|X_2(\omega)=x_2\dots X_m(\omega)=x_m)p(X_2=x_2,\dots,X_m=x_m)$
$=\sum_{x_2\dots x_m}p(X_1=x_1,\dots,X_m=x_m)$
### (marginal) PDF
$f_{X_1}(x_1)=\int_{X_2}\int_{X_m}f(x_1,\dots,x_m)dx_2\dots dx_m$
### conditional pmf
$p_{X_1(\omega)|X_2(\omega)}(x_1|x_2){\Delta \atop= }\frac{p(x_1 x_2)}{p_{X_2(\omega)}(x_2)}=\frac{p(x_1x_2)}{\sum_{x_1}p(x_1x_2)}$
### conditional pdf
$f_{X_1(\omega)|X_2(\omega)}(x_1|x_2)=\frac{f(x_1x_2)}{f_{X_2}(x_2)}=\frac{f(x_1x_2)}{\int f(x_1x_2)dx}$
$X=\begin{pmatrix}X_1\\X_2\end{pmatrix}$
### Expectation
#### 1
$\mathbb{E}X=\begin{pmatrix}\mathbb{E}X_1(\omega)\\\dots\\\mathbb{E}X_m(\omega)\end{pmatrix}$
#### 2
$\parallel X\parallel_2^2=X_1^2+\dots+X_m^2$
$\mathbb{E}g(x)=\begin{cases}\sum_{x_1,\dots,x_m}g(X)p(x_1,\dots,x_m)\quad 离散\\\int g(X)f(x_1,\dots,x_m)dx_1\dots dx_m\quad 连续\end{cases}$
#### 3
$\mathbb{E}[g(X_1)|X_2]=\begin{cases}\sum_{x_1}g(X_1)p_{X_1|X_2}(x_1|x_2)\quad 离散\\\int_{X_1}g(X_1)f_{X_1|X_2}(x_1|x_2)dx_1\quad 连续\end{cases}$
#### Law of total expectation
$$\mathbb{E}(X_1)=\mathbb{E}\{\mathbb{E}(X_1|X_2)\}$$
Proof:（离散）
$RHS=\mathbb{E}m(x_2)=\sum_{X_2}m(X_2)p_{X_2}(x_2)=\sum_{x_1}X_1p_{X_1|X_2}(x_1|x_2)$
$=\sum_{X_2}\sum_{X_1}X_1p_{X_1|X_2}(x_1|x_2)p_{X_2}(x_2)$
$=\sum_{X_2}\sum_{X_1}X_1\frac{p(X_1X_2)}{p_{X_2}(x_2)}p_{X_2}(x_2)$
$=\sum_{X_1}X_1\sum_{X_2}p(X_1X_2)=\sum_{X_1}X_1p_{X_1}(x_1)$
$=\mathbb{E}X_1=LHS$
Proof2:
$X_1=\begin{cases}1\quad A发生\\0\quad A不发生\end{cases}$

$X_2=\begin{cases}1\quad B发生\\0\quad B不发生\end{cases}$
$\mathbb{E}(X_1|X_2)=m(X_2)$
$LHS=\mathbb{E}m(X_2)=m(1)P(X_2=1)+m(0)P(X_2=0)$
$=m(1)p(B)+m(0)P(B^C)=P(A|B)P(B)+P(A|B^C)P(B^C)=P(A)$
$RHS=\sum_{x_1}x_1P(X_1=x_1)=P(X_1=1)=P(A)$
### Covariance/variance
$X\rightarrow \mathbb{R}^{m\times 1}$
$cov(X)=\begin{pmatrix}\quad&\quad\\\quad&\quad\end{pmatrix}$
$(i,i):VarX_i$ $(i,j)=cov(X_i,X_j){\Delta\atop=}\mathbb{E}(X_1-\mathbb{E}X_i)(X_j-\mathbb{E}X_j)=\mathbb{E}X_iX_j-\mathbb{E}X_i\mathbb{E}X_j$
If $cov(X_i,X_j)=0\Rightarrow X_,X_j$ uncorrelated.
### MGF
$M_X(t)=\mathbb{E}e^{<t,X>}=\mathbb{E}e^{t^TX}$ (joint MGF)
$=\mathbb{E}e^{t_1X_1+\dots+t_mX_m}=\begin{cases}\sum_{X_1,\dots,X_m}e^{t_1X_1+\dots+t_mX_m}p(X_1\dots X_m)\\\int\end{cases}$
### Marginal MGF
$M_{(X_1X_2)}(t_1,t_2)=\mathbb{E}e^{t_1X_1+t_2X_2}$
$=\begin{cases}\sum_{x_1,x_2}e^{t_1X_1+t_2X_2}p_{(X_1,X_2)}(x_1,x_2)\\\int\end{cases}$
### Independence
$X_1\bot X_2$
#### 1
$p(x_1x_2)=p_{X_1}(x_1)p_{X_2}(x_2)$ 离散
$f(x_1x_2)=f_{X_1}(x_1)f_{X_2}(x_2)$ 连续
#### 2
$\mathbb{E}e^{t_1X_1+t_2X_2}=\mathbb{E}e^{t_1X_1}\mathbb{E}e^{t_2X_2}$
#### 3
If $cov(X_i,X_j)=0$, $X_i,X_j$不相交。反过来不成立。
#### 4
$\{X_i\}$, $i=1,2,\dots,m$
$X_1,\dots,X_k$ is independent($k\le m$)
$p(X_1\dots X_k=P_{X_1}(x_1)\dots P_{X_k}(x_k)$
$LHS=p_{X_1\dots X_k}(x_1\dots x_k)=\sum_{x_{k+1}\dots x_m}p(x_1\dots x_m)$
$=\sum_{x_{k+1}\dots x_m}p_{X_1}(x_1)\dots p_{X_m}(x_m)$
$=p_{X_1}\dots p_{X_k}(x_k)\sum_{x_{k+1}}p_{X_{k+1}}(x_{k+1})\dots\sum_{x_m}p_{X_m}(x_m)$
$=RHS$
#### 5
$f(X_1\dots X_k)\bot g(X_{k+1}\dots X_m)$
Joint MGF $=\mathbb{E}e^{tf(X_1\dots X_k)+sg(X_{k+1}\dots X_m)}$
Proof:
$=\sum_{x_1\dots x_m}e^{tf(X_1\dots X_k)}e^{sg(X_{k+1}\dots X_m}p_{X_1}(X_1)\dots p_{X_m}(X_m)$
$=\sum_{X_1\dots X_k}e^{tf(X_1\dots X_k)}p_{X_1}(X_1)\dots p_{X_k}(X_k)\sum_{X_{k+1}\dots X_m}e^{sg(X_{k+1}\dots X_m)}p_{X_{k+1}}(X_{k+1})p_{X_m}(X_m)$
$=0$
