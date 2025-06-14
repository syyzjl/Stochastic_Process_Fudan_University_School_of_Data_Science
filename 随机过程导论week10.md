# $(X_0,X_1,\dots,X_m)$
$P(X_0=i_0,\dots,X_m=i_m)=P_0(i_0)P_{i_0i_1}\dots P_{i_{m-1}i_m}$
# $(X_0,X_2,X_5)$
$P(X_0=i_0,X_2=i_2,X_5=i_5)=P_0(i_0)P^{(2)}_{i_0i_2}P^{(3)}_{i_2i_5}$
# $X_m$
$P_m=(P_m(1)\dots P_m(N))$
$P_m=P_0P^{(m)}$

## simple random walk
$$X_n=\sum_{i=1}^n\xi_i,\xi_i=\begin{cases}1,1/2\\-1,1/2\end{cases}$$
$$P_{ij}=P(X_{n+1}=j|X_n=i)=\begin{cases}1/2,j=i+1\\1/2,j=i-1\\0,other\end{cases}$$
$$X_{n+1}=X_n+\xi_{n+1}=\begin{cases}X_n+1,1/2\\X_n-1,1/2\end{cases}$$
## eg2
$X_n:M-C$, $E=\{1,2,3\}$, $P(X_0=i)=1/3$, $i=1,2,3$
$P=\begin{pmatrix}1/2&1/2&0\\1/3&0&2/3\\1/2&0&1/2\end{pmatrix}$
$P^{(2)}=PP$
$P(X_0=3,X_2=1)=P_0(3)P^{(2)}_{31}=1/6$
$P(X_0=1|X_2=2)=\frac{P(X_2=2|X_0=1)P(X_0=1)}{P(X_2=2)}=\frac{P^{(2)}_{12}P_0(1)}{P_2(2)}=3/8$
## 吸收态
$$P(X_{n+1}=i|X_n=i)=1$$
$$P_{11}=1$$
## 可到达
$$i\rightarrow j$$
$$\exists m\ge 0,s.t.\quad P(X_{n+m}=j|X_n=i)>0$$
## 不可到达
$$\forall m\ge 1,P^{(m)}_{ij}=0$$
## 互通
$$i\leftrightarrow j$$
$$i\leftarrow j\&j\leftarrow i$$
## 不可约
$$\forall i,j\quad i\leftrightarrow j$$
## 闭集
C is a closed set. 不可约的状态空间里肯定没有闭集
## 周期
g(i)状态i的周期
$$g(i)=gcd\{m:P^m_{ii}>0\}$$
Gcd:最大公因子
若$d(i)>1$，有周期性，称$d(i)$为周期
若$d(i)=1$，称为非周期
## e.g.1
$E=\{1,2,3\},P=\begin{pmatrix}0&2/3&1/3\\1/2&0&1/2\\0&0&1\end{pmatrix}$
$\{1,2\}$互通，$\{3\}$闭集
1的周期$d(1)$
2$\{1\rightarrow 2\rightarrow 1\}$
4$\{1\rightarrow 2\rightarrow 1\rightarrow 2\rightarrow 1\}$
6
$d(2)=2$, $d(3)=1\Rightarrow 3$非周期

$i\leftrightarrow j\Rightarrow d(i)=d(j)$ $d(i)|d(j)\& d(j)|d(i)$
$i\rightarrow j:\exists m\ge 1,P^{(m)}_{ij}>0$
$j\rightarrow i:\exists k\ge 1,P^{(k)}_{ji}>0$
$\Rightarrow P^{(m+k)}_{jj}\ge P^{(k)}_{ji}P^{(m)}_{ij}>0\Rightarrow d(j)|m+k$
Assume $\exists\{S_n\}s.t.\quad P^{(S_n)}_{ii}>0\Rightarrow P^{(m+k+S_n)}_{jj}\ge P^{(k)}_{ji}P^{(S_n)}_{ii}P^{(m)}_{ij}>0\Rightarrow d(j)|m+k+S_n$
$\Rightarrow d(j)|S_n\Rightarrow d(j)$是$\{S_n\}$的因子
$d(i)$是$\{S_n\}$的最大公因子$\Rightarrow d(j)|d(i),d(i)|d(j)$
# 常返(recurrent)&瞬时
状态i是recurrent $T_i=min\{m:X_m=i\}$
Given $X_0=i$ 在有限步回到i $(T_i<\infty)$
$$P(T_i<\infty|X_0=i)=1\Leftrightarrow$$
$i$ 是常返的
$$P(T_i<\infty|X_0=i)<1\Leftrightarrow$$
$i$ 是瞬时的

## (i)
$$\sum_{k=1}^\infty f^{(k)}_{ii}=1\Leftrightarrow$$
$i$ 是常返
$$\sum_{k=1}^\infty f^{(k)}_{ii}<1\Leftrightarrow$$
$i$ 是瞬时
## (ii)
$$\sum_{k=1}^\infty P_{ii}^{(k)}=\infty\Leftrightarrow$$
$i$ 是常返
$$\sum_{k=1}^\infty P_{ii}^{(k)}<\infty\Leftrightarrow$$
$i$ 是瞬时
### (i)$\Leftrightarrow$(ii)
$$P_{ii}^{(k)}=P(X_k=i|X_0=i)$$
$$=\sum_{m=1}^\infty P(X_k=i|X_0=i,T_i=m)P(T_i=m|X_0=i)$$
$$=\sum_{m=1}^\infty(P_{ii}^{k-m}f_{ii}^{(m)})(*)$$
$$\sum_{k=1}^\infty P_{ii}^{(k)}=\sum_{k=1}^\infty\sum_{m=1}^k P_{ii}^{(k-m)}f_{ii}^{(m)}$$
$$=\sum_{m=1}^\infty(\sum_{k=m}^\infty P_{ii}^{(k-m)})f_{ii}^{(m)}$$
$$=(1+\sum_{s=1}^\infty P_{ii}^{(s)})\sum_{m=1}^\infty f_{ii}^{(m)}\quad s=k-m$$
$$(*)\Leftrightarrow\sum_{m=1}^\infty f_{ii}^{(m)}=\frac{\sum_{k=1}^\infty P_{ii}^{(k)}}{1+\sum_{k=1}^\infty P_{ii}^{(k)}}$$
## (ii):$i\leftrightarrow j$
$i$ 和 $j$ 具有相同的常返性（if i 是常返$\Rightarrow$ j是常返）
$i\rightarrow j,\exists m\ge 1,P_{ij}^{(m)}>0$
$j\rightarrow,\exists k\ge 1,P_{ji}^{(k)}>0$
$\Rightarrow \sum_{s=1}^\infty P_{jj}^{(m+k+s)}\ge P_{ji}^{(k)}\sum_{s=1}^\infty P_{ii}^{(s)}P_{ij}^{(m)}=\infty$
## (iii)
$M_i=\#\{m:X_m=i\}$（碰到i的次数）
Given $X_0=i$, $M_i=\infty$
i常返$\Leftrightarrow P(M_i=\infty|X_0=i)=1$
i瞬时$\Leftrightarrow P(M_i=\infty|X_0=i)=0$
$$P(M_i=\infty|X_0=i)=\lim_{k\rightarrow\infty}P(M_1\ge k|X_0=i)$$
$$=\lim_{k\rightarrow \infty}\sum_{m=1}^\infty f_{ii}^{(m)}P(M_i\ge k-1|X_0=i)$$
$$=\lim_{k\rightarrow\infty}(\sum_{m=1}^\infty f_{ii}^{(m)})^k$$
## (ii)
$$E(T_i|X_0=i)=\sum_{k=1}^\infty kP(T_i=k|X_0=i)$$
$$=\sum_{k=1}^\infty kf_{ii}^{(k)}$$
### 正常返
$E(T_i|X_0=i)<\infty$
### 零常返
$E(T_i|X_0=i)=\infty$
## e.g.1
$P=\begin{pmatrix}1/3&2/3&0\\1/2&0&1/2\\1/3&0&2/3\end{pmatrix}$
$$\sum_{k=1}^\infty f_{11}^{(k)}=2/3+\sum_{k=3}^\infty \frac 19(\frac 23)^{k-3}=1$$
常返
$$E(T_i|X_0=i)=\sum_{k=1}^{(k)}k=1/3+2\frac 13+\sum_{k=3}^\infty\frac 19(\frac 23)^{k-3}k$$
## e.g.2
$P=\begin{pmatrix}1-p&p\\q&1-q\end{pmatrix}$
$$\sum_{k=1}^\infty f_{11}^{(k)}=p+1-p=1$$
1是常返
$$E(T_1|X_0=1)=\sum_{k=1}^\infty f_{11}^{(k)}k=\frac{p+q}q<\infty$$
正常返
$$E(T_2|X_0=2)=\frac{p+q}p<\infty$$
正常返
# simple random walk
$\{0\}$常返性
$$\sum_{k=1}^\infty P_{00}^{(k)}=\sum_{k=1}^\infty P_{00}^{(2k)}=\sum_{k=1}^\infty\frac{(2k)!}{k!k!2^{2k}}=\sum_{k=1}^\infty\frac{\sqrt{2\pi 2k}e^{-2k}(2k)^{2k}}{2\pi ke^{-2k}(k^k)^22^{2k}}=\sum_{k=1}^\infty\frac{O(1)}{\sqrt{k}}=\infty$$
$$E(T_0|X_0=0)=\sum_{k=1}^\infty f_{00}^{(2k)}(2k)$$
$$P_{00}^{(2k)}={2k\choose k}(\frac 12)^k(\frac 12)^k=\frac{{2k\choose k}}{2^{2k}}$$

