# Chapter 5 数值积分和微分 Numerical Integration and Differential

## 5.3 Romberg 积分

### 5.3.1 Richardson 外推法

利用 $T_n$ 和 $T_{2n}$ 的线性组合, 可以使误差从 $O(h^2)$ 提高到 $O(h^4)$。

假设 $F(h)$ 逼近 $F^*$ ($F^*$ 与 $h$ 无关) 的余项为：
$$
F^*-F(h)=\sum_{k=1}^{\infty}\alpha_kh^{p_k}
$$
其中 $p_k,\alpha_k$ 为与 $h$ 无关的常数，$\alpha_k\ne0,k>0$。定义：
$$
F_1(h)=F(h)\\
F_{m+1}(h)=\frac{F_m(qh)-q^{p_m}F_m(h)}{1-q^{p_m}}
$$

> $$
> F^*-F(h)=\sum_{k=1}^{\infty}\alpha_kh^{p_k}
> $$
>
> 步长减半：
> $$
> F^*-F\left(\frac{h}{2}\right)=\sum_{k=1}^{\infty}\alpha_k\left(\frac{h}{2}\right)^{p_k}
> $$
> 则：
> $$
> 2^{p_1}F^*-2^{p_1}F\left(\frac{h}{2}\right)=\alpha_1h^{p_1}+\sum_{k=2}^{\infty}\alpha_k\frac{h^{p_k}}{2^{p_k-p_1}}=\alpha_1h^{p_1}+\sum_{k=2}^{\infty}\frac{\alpha_k}{2^{p_k-p_1}}h^{p_k}
> $$
> 减去最上面的式子：
> $$
> \begin{gather*}
> (2^{p_1}-1)F^*-\left[2^{p_1}F\left(\frac{h}{2}\right)-F(h)\right]=\sum_{k=2}^{\infty}\frac{\alpha_k}{2^{p_k-p_1}}h^{p_k}\\
> F^*-\frac{2^{p_1}F\left(\frac{h}{2}\right)-F(h)}{(2^{p_1}-1)}=\sum_{k=1}^{\infty}\beta_kh^{p_k}\\
> F^*-\frac{F\left(\frac{h}{2}\right)-\left(\frac{1}{2}\right)^{p_1}F(h)}{(1-\left(\frac{1}{2}\right)^{p_1})}=\sum_{k=1}^{\infty}\beta_kh^{p_k}\\
> \end{gather*}
> $$
> 型式保持。
>

<blockquote style="border-left: 5px solid #b94263; border-radius: 3px 0 0 3px; padding: 10px 15px; background-color: rgba(185, 66, 110, 0.1)">
    例题
</blockquote>

设 $I(h)$ 逼近 $I$ 的余项为:
$$
I-I(h)=\alpha_1h^2+\alpha_2h^4+\cdots
$$
其中 $\alpha_k$ 为与 $h$ 无关的常数，且 $I(0.1)=0.99,I(0.04)=1.20$，在此基础上用外推法得到 $I$ 的更高精度的近似值为多少？

> $$
> \begin{gather*}
> I-I(0.1)=\alpha_10.1^2+\alpha_20.1^4+\cdots\\
> I-I(0.04)=\alpha_10.04^2+\alpha_20.04^4+\cdots\\
> \end{gather*}
> $$
> 消去 $\alpha_1$:
> $$
> \begin{gather*}
> 5.25I-6.25I(0.04)+I(0.1)=0.1^2(0.1^2-0.04^2)\alpha_2+\cdots\\
> \frac{6.25I(0.04)-I(0.1)}{5.25}=1.19238
> \end{gather*}
> $$
> 

### 5.3.2 Romberg 积分

将 Richardson 外推和复合梯形公式结合

<blockquote style="border-left: 5px solid #4545aa; border-radius: 3px 0 0 3px; padding: 10px 15px; background-color: rgba(70, 70, 188, 0.1)">
    Romberg 积分
</blockquote>

设 $f(x)\in C^{2m+2}[a,b]$，则复合梯形公式：
$$
T(h)=I(f)+\sum_{k=1}^{n}d_kh^{2k}+d_{n+1}(h)h^{2n+2}
$$
其中：$T(h)=T_n$，$I(f)=\int_a^bf(x)\mathrm{d}x,d_j(j\in\{1,\dots,n\})$ 为与 $h$ 无关的常数，$d_{n+1}(h)$ 为 $h$ 的函数。

> 证明略。

记：
$$
T_i^0=T\left(\frac{h}{2^i}\right)
$$
则：
$$
T_i^0=I(f)+\sum_{k=1}^{n}d_k\left(\frac{h}{2^i}\right)^{2k}+d_{n+1}\left(\frac{h}{2^i}\right)\left(\frac{h}{2^i}\right)^{2n+2}
$$
此时就可以外推了：
$$
T_i^1=\frac{4T_i^0-T_{i-1}^0}{4-1}
$$
Romberg 算法的递推表：
$$
\begin{gather*}
T_0^0=[f(a)+f(b)]\frac{h}{2}\quad h=b-a\\
T_i^0=\frac{1}{2}T_{i-1}^0+\frac{h}{2^i}\sum_{k=0}^{i-1}f(x_{k+\frac{1}{2}})\\
T_i^j=\frac{4^jT_{i}^{j-1}-T_{i-1}^{j-1}}{4^j-1}
\end{gather*}
$$

## 5.5 Gauss 积分

<blockquote style="border-left: 5px solid #4545aa; border-radius: 3px 0 0 3px; padding: 10px 15px; background-color: rgba(70, 70, 188, 0.1)">
    Gauss 点
</blockquote>

含有 $n+1$ 个求积点 $x_0,\dots,x_n$，而代数精度为 $2n+1$ 的求积公式称为 Gauss 型求积公式，$x_0,\dots,x_n$ 为 Gauss 点。由于上式为非线性方程组，实际计算非常困难。

<blockquote style="border-left: 5px solid #b94263; border-radius: 3px 0 0 3px; padding: 10px 15px; background-color: rgba(185, 66, 110, 0.1)">
    例题
</blockquote>

$$
\int_{-1}^1f(x)\mathrm{d}x=Af\left(-\frac{\sqrt{3}}{3}\right)+Bf\left(\frac{\sqrt{3}}{3}\right)
$$

> $$
> \begin{bmatrix}
> 1&1\\
> -\frac{\sqrt{3}}{3}&\frac{\sqrt{3}}{3}\\
> \end{bmatrix}
> \begin{bmatrix}
> A\\B
> \end{bmatrix}=
> \begin{bmatrix}
> 2\\0\\
> \end{bmatrix}
> $$
>
> 得到 $A=B=1$。且代数精度为 3。则是 Gauss 型求积公式。
>

<blockquote style="border-left: 5px solid #4545aa; border-radius: 3px 0 0 3px; padding: 10px 15px; background-color: rgba(70, 70, 188, 0.1)">
    Gauss 型求积公式的充要条件
</blockquote>

设以 $x_0,\dots,x_n$ 为节点的插值型求积公式
$$
\int_a^b\rho(x)f(x)\mathrm{d}x=\sum_{k=0}^nA_kf(x_k)
$$
是 Gauss 型求积公式的充要条件为：
$$
\omega_{n+1}(x)=(x-x_0)\cdots(x-x_n)
$$
与任意次数不超过 $n$ 次多项式 $P_{n}(x)$ 在区间 $[a,b]$ 上带权 $\rho(x)$ 正交，即：
$$
\int_a^b\rho(x)P_n(x)\omega_{n+1}(x)\mathrm{d}x=0
$$

> 将 $f(x)$ 分解为 $P_n(x)\omega_{n+1}(x)+R_n(x)$，其中 $P_n(x)$ 和 $R_n(x)$ 为不超过 $n$ 次的多项式。则：
> $$
> \begin{align*}
> \int_a^b\rho(x)f(x)\mathrm{d}x&=\int_a^b\rho(x)P_n(x)\omega_{n+1}(x)\mathrm{d}x+\int_a^b\rho(x)R_n(x)\mathrm{d}x\\
> &=0+\int_a^b\rho(x)R_n(x)\mathrm{d}x
> \end{align*}
> $$
> 由于 $n+1$ 个节点的插值型求积公式，所以对 $R_n(x)$ 的求积是精确的。

<blockquote style="border-left: 5px solid #b94263; border-radius: 3px 0 0 3px; padding: 10px 15px; background-color: rgba(185, 66, 110, 0.1)">
    例题
</blockquote>

构造 Gauss 型求积公式
$$
\int_0^1xf(x)\mathrm{d}x=Af(x_0)+Bf(x_1)
$$

> 设 $[0,1]$ 上带权 $\rho(x)=x$ 正交，且首系数为 $1$ 的多项式系为 $\{P_n(x)\}_0^{\infty}$。设 $P_2(x)=x^2+ax+b$，则 $P_2(x)$ 由下式可得：
> $$
> \begin{gather*}
> \int_0^1x\cdot 1\cdot P_2(x)\mathrm{d}x=0\\
> \int_0^1x\cdot x\cdot P_2(x)\mathrm{d}x=0
> \end{gather*}
> $$
> 得到 $a=-6/5,b=3/10$。则两根为：
> $$
> \frac{6\pm\sqrt{6}}{10}
> $$

### 5.5.2 Gauss 求积法的稳定性和收敛性

<blockquote style="border-left: 5px solid #4545aa; border-radius: 3px 0 0 3px; padding: 10px 15px; background-color: rgba(70, 70, 188, 0.1)">
    Gauss 求积法的稳定性和收敛性
</blockquote>

Gauss 求积公式中的求积系数全大于零，即 $A_k>0$。

> 设 $l_j(x)$ 是以 Gauss 点为插值点的拉格朗日插值基函数, 由于 Gauss 求积公式的代数精度为 $2n+1$，从而：
> $$
> 0<\int_a^b\rho(x)l^2_j(x)\mathrm{d}x=\sum_{k=0}^{n}A_kl_j^2(x_k)=A_j
> $$

这表明 Gauss 求积方法的数值计算是稳定。

<blockquote style="border-left: 5px solid #4545aa; border-radius: 3px 0 0 3px; padding: 10px 15px; background-color: rgba(70, 70, 188, 0.1)">
    Gauss 型求积公式余项
</blockquote>

若 $f\in C^{2n+2}[a,b]$，则 Gauss 求积公式具有余项：
$$
\int_a^b\rho(x)f(x)\mathrm{d}x-\sum_{k=0}^nA_kf(x_k)=\frac{f^{(2n+2)}(\xi)}{(2n+2)!}\int_a^b\rho(x)\omega^2_{n+1}(x)\mathrm{d}x
$$

> 构造 Hermite 插值多项式 $H_{2n+1}(x)$：
> $$
> f(x)-H_{2n+1}(x)=\frac{f^{(2n+2)}(\xi)}{(2n+2)!}\omega^2_{n+1}(x)
> $$
> 则得到余项。

### 5.5.3 Gauss-Legendre 求积公式

若 $\rho(x)=1$，$[a,b]=[-1,1]$，则求积点可取为 Legendre 多项式的零点。

对于一般区间 $[a,b]\ne[-1,1]$ 的情形，可通过坐标变换
$$
x=\frac{b+a}{2}+\frac{b-a}{2}t
$$
将积分 $\int_a^bf(x)\mathrm{d}x$ 变换为：
$$
\frac{b-a}{2}\int_{-1}^1f\left(\frac{b+a}{2}+\frac{b-a}{2}t\right)\mathrm{d}t
$$

### 5.5.4 Gauss-Chebyshev 求积公式

若 $\rho(x)=1/\sqrt{1-x^2}$，$[a,b]=[-1,1]$，则求积点可取为 Chebyshev 多项式的零点：
$$
x_k=\cos\frac{2k+1}{2(n+1)}\pi
$$
求积系数为：
$$
A_k=\frac{\pi}{n+1}
$$
