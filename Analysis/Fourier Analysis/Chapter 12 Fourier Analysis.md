# Chapter 12 Fourier Analysis

Fourier 级数的来源为一维杆状物体的温度分布问题，可由下列方程描述：
$$
\begin{cases}
\dfrac{\partial^2T}{\partial x^2}=\dfrac{\partial T}{\partial t}&T=T(x,t)\\
T(0,t)=T(l,t)=0&t>0\\
T(x,0)=f(x)&0<x<l
\end{cases}
$$
即在一段长度为 $l$ 的长杆上，两端保持 $0$ 度，初始的温度分布为 $f(x)$。

Fourier 采取了分离变量法，令解具有如下形式
$$
T(x,t)=\phi(x)\psi(t)
$$
代入方程可得
$$
\begin{align*}
\phi''(x)\psi(t)&=\phi(x)\psi'(t)\\
\frac{\phi''(x)}{\phi(x)}&=\frac{\psi'(t)}{\psi(t)}
\end{align*}
$$
由于左边是关于 $x$ 的函数，右边是关于 $t$ 的函数，所以两端相等的唯一可能是等于某个常数
$$
\frac{\phi''(x)}{\phi(x)}=\frac{\psi'(t)}{\psi(t)}=-\lambda
$$
故方程组转化为
$$
\begin{cases}
\phi''(x)+\lambda\phi(x)=0\\
\psi'(t)+\lambda\psi(t)=0\\
\phi(0)=\phi(l)=0\\
T(x,0)=f(x)&0<x<l
\end{cases}
$$
方程的通解为
$$
\phi(x)=b\sin(\sqrt{\lambda}x+c)\\
\psi(t)=\exp(-\lambda t)
$$
条件 $\phi(0)=0\Longrightarrow c=0$，条件 $\phi(l)=0\Longrightarrow\sqrt{\lambda}l=n\pi$，故
$$
\lambda_n=(\frac{n\pi}{l})^2
$$
 对于每个 $\lambda_n$，对应一个 $\phi_n(x)$ 和 $\psi_n(t)$：
$$
\phi_n(x)=b_n\sin(\frac{n\pi}{l}x)\qquad\psi_n(t)=\exp\left[-\left(\frac{n\pi}{l}\right)^2t\right]
$$
故方程组通解为
$$
T(x,t)=\sum_{n=1}^{\infty}b_n\sin(\frac{n\pi}{l}x)\exp[-(\frac{n\pi}{l})^2t]
$$
初始条件为
$$
f(x)=T(x,0)=\sum_{n=1}^{\infty}b_n\sin(\frac{n\pi}{l}x)
$$
但是，如果是正确的，那么意味着，对于一个在 $[0,l]$ 上定义的函数，都能表示成上述三角函数的和，更一般的
$$
f(x)=\frac{a_0}{2}+\sum_{n=1}^{\infty}[a_n\cos(\frac{n\pi}{l}x)+b_n\sin(\frac{n\pi}{l}x)]
$$
对于大部分函数都是正确的。

## 12.1 函数的 Fourier 级数

尽管三角函数以 $2l$ 为公共周期，但是我们可以把定义在有限区间上的函数进行延拓，使之成为一个周期函数中的一段。

### 12.1.1 周期函数和三角函数的正交性

#### 1 周期函数的基本性质

周期函数在一个周期内的积分和起点无关
$$
\begin{align*}
\int_{a}^{a+T}f(x)dx&=\int_{a}^{0}f(x)dx+\int_{0}^{T}f(x)dx+\int_{T}^{a+T}f(x)dx\\
&=\int_{a}^{0}f(x)dx+\int_{0}^{T}f(x)dx+\int_{0}^{a}f(u+T)du\\
&=\int_{a}^{0}f(x)dx+\int_{0}^{T}f(x)dx+\int_{0}^{a}f(u)du\\
&=\int_{0}^{T}f(x)dx
\end{align*}
$$

#### 2 周期延拓

对于定义在 $[-l, l]$ 上的函数，可以通过复制产生定义在整个数组上的周期为 $2l$ 的函数
$$
F(x)=\begin{cases}
f(x-2nl)&(2n-1)l<x<(2n+1)l\\
\frac{f(l)+f(-l)}{2}&x=(2n+1)l
\end{cases}
$$

#### 3 奇延拓和偶延拓

对于定义在 $[0, l]$ 上的函数
$$
f_e(x)=\begin{cases}
f(x)&0\le x\le l\\
f(-x)&-l\le x\le 0
\end{cases}
$$

$$
f_o(x)=\begin{cases}
f(x)&0< x\le l\\
0&x=0\\
f(-x)&-l\le x< 0
\end{cases}
$$

#### 4 三角函数正交性

三角函数系
$$
1,\sin x,\cos x,\sin 2x,\cos2x,\dots
$$
的共同周期是 $2\pi$，积化和差可证明，在 $[-\pi,\pi]$ 上满足
$$
\begin{align*}
\int_{-\pi}^{\pi}\cos mx\cos nx&=\pi\delta_{mn}\\
\int_{-\pi}^{\pi}\sin mx\sin nx&=\pi\delta_{mn}\\
\int_{-\pi}^{\pi}\cos mx\sin nx&=0
\end{align*}
$$

### 12.1.2 Fourier 级数

假设对于可积且绝对可积的函数 $f(x)$ 
$$
a_m=\frac{1}{\pi}\int_{-\pi}^{\pi}f(x)\cos mx\ dx\\
b_m=\frac{1}{\pi}\int_{-\pi}^{\pi}f(x)\sin mx\ dx
$$
$a_m,b_m$ 为 $f(x)$ 的 Fourier 系数。记
$$
f(x)\thicksim\frac{a_0}{2}+\sum_{n=1}^{\infty}a_n\cos nx+b_n\sin nx
$$
后者为 $f(x)$ 的 Fourier 级数，这里尚不知这个级数收敛到 $f(x)$。

### 定理 12.1 Dirichlet 定理

设函数 $f(x)$ 以 $2\pi$ 为周期，可积且绝对可积。

1. 如果在任何有限区间上函数是逐段光滑的，那么它的 Fourier 级数在 $\mathbf R$ 上收敛，且
   $$
   \frac{a_0}{2}+\sum_{n=1}^{\infty}a_n\cos nx+b_n\sin nx=\frac{f(x+0)+f(x-0)}{2}
   $$

2. 如果函数处处连续且逐段光滑，那么它的 Fourier 级数在 $\mathbf R$ 上收敛到 $f(x)$。

------

一般的，$f(x)$ 定义在 $[-l,l]$ 上
$$
f(x)\thicksim\frac{a_0}{2}+\sum_{n=1}^{\infty}a_n\cos\frac{n\pi}{l}x+b_n\sin\frac{n\pi}{l}x\\
a_m=\frac{1}{l}\int_{-l}^{l}f(x)\cos \frac{n\pi}{l}x\ dx\\
b_m=\frac{1}{l}\int_{-l}^{l}f(x)\sin \frac{n\pi}{l}x\ dx
$$

### 12.1.3 有限区间上函数的 Fourier 级数

更一般的，$f(x)$ 定义在 $[a,b]$ 上
$$
f(x)\thicksim\frac{a_0}{2}+\sum_{n=1}^{\infty}a_n\cos\frac{2n\pi}{b-a}x+b_n\sin\frac{2n\pi}{b-a}x\\
a_m=\frac{2}{b-a}\int_{a}^{b}f(x)\cos \frac{2n\pi}{b-a}x\ dx\\
b_m=\frac{2}{b-a}\int_{a}^{b}f(x)\sin \frac{2n\pi}{b-a}x\ dx
$$

### 12.1.4 Fourier 级数的复数形式

$f(x)$ 定义在 $[-l,l]$ 上
$$
f(x)\thicksim\frac{a_0}{2}+\sum_{n=1}^{\infty}a_n\cos n\omega x+b_n\sin n\omega x\qquad\omega=\frac{\pi}{l}\\
a_m=\frac{1}{l}\int_{-l}^{l}f(x)\cos n\omega x\ dx\\
b_m=\frac{1}{l}\int_{-l}^{l}f(x)\sin n\omega x\ dx
$$
应用 Euler 公式
$$
\cos n\omega x=\frac{\exp(in\omega x)+\exp(-in\omega x)}{2}\\
\sin n\omega x=\frac{\exp(in\omega x)-\exp(-in\omega x)}{2i}
$$
得到
$$
\begin{align*}
f(x)&\thicksim\frac{a_0}{2}+\sum_{n=1}^{\infty}[a_n\frac{\exp(in\omega x)+\exp(-in\omega x)}{2}+ib_n\sin\frac{\exp(-in\omega x)-\exp(in\omega x)}{2}]\\
&\thicksim\frac{a_0}{2}+\sum_{n=1}^{\infty}[\frac{a_n-ib_n}{2}\exp(in\omega x)+\frac{a_n+ib_n}{2}\exp(-in\omega x)]\\
&\thicksim\frac{a_0}{2}+\sum_{n=1}^{\infty}[\frac{a_n-ib_n}{2}\exp(in\omega x)+\frac{a_n+ib_n}{2}\exp(-in\omega x)]\\
&\thicksim\sum_{n=-\infty}^{\infty}F_n\exp(in\omega x)\\
\end{align*}\\
$$
$$
F_0=\frac{a_0}{2}=\frac{1}{2l}\int_{-l}^{l}f(x)dx\\
F_{\pm n}=\frac{1}{2}(a_n\mp ib_n)=\frac{1}{2l}\int_{-l}^{l}f(x)[\cos n\omega x\mp i\sin n\omega x]dx\\
=\frac{1}{2l}\int_{-l}^{l}f(x)\exp(\mp in\omega x)dx\quad(n\in\mathbb N)\\
$$

满足 $F_{-n}=\bar{F_n}$。

## 12.2 平方平均收敛

### 12.2.1 平方平均收敛的基本概念

设 $L^2[a,b]$ 是 $[a,b]$ 上可积且平方可积的函数，不难验证，其在函数的加法和数乘运算下是个线性空间。定义内积，模长，距离
$$
<f,g>=\int_{a}^{b}f(x)g(x)dx\\
\|f\|\sqrt{<f,f>}=\sqrt{\int_{a}^{b}f^2(x)dx}\\
\|f-g\|\sqrt{<f-g,f-g>}=\sqrt{\int_{a}^{b}[f(x)-g(x)]^2dx}\\
$$
三角函数系
$$
\{\frac{1}{\sqrt{2\pi}},\frac{\cos mx}{\sqrt{\pi}},\frac{\sin mx}{\sqrt{\pi}},m\in\mathbb N\}
$$
是 $L^2[a,b]$ 上的标准正交系。

### 定义 12.3

对 $L^2[a,b]$ 中给定的函数 $f$，如果存在 $L^2[a,b]$ 中的一个函数列 $f_n$ 使得
$$
\lim_{n\to\infty}\|f_n-f\|^2=\lim_{n\to\infty}\int_{a}^{b}[f_n(x)-f(x)]^2dx=0
$$
则称 $f_n$ 平方平均收敛到 $f$。

### 12.2.2 Bessel 不等式

对于任何一组实数 $\alpha_0,\alpha_k,\beta_k$ 我们称
$$
g_n(x)=\frac{\alpha_0}{2}+\sum_{k=1}^{n}(\alpha_k\cos kx+\beta_k\sin kx)
$$
为 $n$ 次三角多项式
$$
\Delta_n=\|f-g_n\|^2=\int_{-\pi}^{\pi}[f(x)-g_n(x)]^2dx\\
=\int_{-\pi}^{\pi}f^2(x)dx-2\int_{-\pi}^{\pi}f(x)g_n(x)dx+\int_{-\pi}^{\pi}g_n^2(x)dx
$$
第二项，$a_0,a_k,b_k$ 为 $f(x)$ 的 Fourier 系数
$$
\begin{align*}
&\int_{-\pi}^{\pi}f(x)g_n(x)dx\\
=&\frac{\alpha_0}{2}\int_{-\pi}^{\pi}f(x)dx+\sum_{k=1}^{n}(\alpha_k\int_{-\pi}^{\pi}f(x)\cos kx\ dx+\beta_k\int_{-\pi}^{\pi}f(x)\sin kx\ dx)\\
=&\pi[\frac{\alpha_0a_0}{2}+\sum_{k=1}^{n}(\alpha_ka_k+\beta_kb_k)]
\end{align*}
$$
第三项
$$
\begin{align*}
&\int_{-\pi}^{\pi}g_n^2(x)dx\\
=&\int_{-\pi}^{\pi}[\frac{\alpha_0}{2}+\sum_{k=1}^{n}(\alpha_k\cos kx+\beta_k\sin kx)]^2dx\\
=&\int_{-\pi}^{\pi}[\frac{\alpha_0^2}{4}+\sum_{k=1}^{n}(\alpha_k^2\cos^2 kx+\beta_k^2\sin^2 kx)]dx\\
=&\pi[\frac{\alpha_0^2}{2}+\sum_{k=1}^{n}(\alpha_k^2+\beta_k^2)]\\
\end{align*}
$$
故
$$
\begin{align*}
\Delta_n&=\int_{-\pi}^{\pi}f^2(x)dx+\pi[-\alpha_0a_0-2\sum_{k=1}^{n}(\alpha_ka_k+\beta_kb_k)+\frac{\alpha_0^2}{2}+\sum_{k=1}^{n}(\alpha_k^2+\beta_k^2)]\\
&=\int_{-\pi}^{\pi}f^2(x)dx-\pi[\frac{a_0^2}{2}+\sum_{k=1}^{n}(a_k^2+b_k^2)]+\pi\{\frac{(\alpha_0-a_0)^2}{2}+\sum_{k=1}^{n}[(\alpha_k-a_k)^2+(\beta_k-b_k)^2]\}
\end{align*}
$$
故当 $\alpha_0=a_0,\alpha_k=a_k,\beta_k=b_k$ 时，$\Delta_n$ 最小。

### 定理 12.4

设 $f(x)\in L^2[-\pi,\pi]$，则在所有 $n$ 次三角多项式中，以 $f$ 的 Fourier 系数构成的三角多项式与 $f$ 的平方平均偏差 $\Delta_n$ 最小，最小值
$$
\Delta_n=\int_{-\pi}^{\pi}f^2(x)dx-\pi[\frac{a_0^2}{2}+\sum_{k=1}^{n}(a_k^2+b_k^2)]
$$

### 推论 12.5 Bessel 不等式

$$
\frac{a_0^2}{2}+\sum_{k=1}^{n}(a_k^2+b_k^2)\le\frac{1}{\pi}\int_{-\pi}^{\pi}f^2(x)dx
$$

### 推论 12.6

Fourier 系数极限为 0.

### 12.2.3 平方平均收敛

### 定理 12.7 Parseval 等式

设 $f(x)\in L^2[-\pi, \pi]$，则 $f(x)$ 的 Fourier 级数部分和 $S_n(x)$ 构成的三角多项式函数列平方平均收敛到 $f(x)$。
$$
\lim_{n\to\infty}\|f-S_n\|=\lim_{n\to\infty}\int_{-\pi}^{\pi}[f(x)-S_n(x)]^2dx=0
$$
上述结论等价于 Bessel 不等式取等号
$$
\frac{a_0^2}{2}+\sum_{k=1}^{n}(a_k^2+b_k^2)=\frac{1}{\pi}\int_{-\pi}^{\pi}f^2(x)dx
$$

### 推论 12.8

闭区间 $[-\pi,\pi]$ 上连续函数与三角函数系的标准正交基中的每一个都正交，则 $f(x)\equiv0$；如果两个连续函数 $f,g$ 的 Fourier 系数都相等，则 $f\equiv g$。

#### proof:

闭区间连续 $\Longrightarrow$ 有界 $\Longrightarrow$ 平方可积 $\Longrightarrow$ Fourier 展开。

### 推论 12.9

设 $f,g\in L^2[-\pi, \pi]$，$a_n,b_n,\tilde{a_n},\tilde{b_n}$ 是 $f,g$ 的 Fourier 系数，则
$$
\frac{1}{\pi}\int_{-\pi}^{\pi}f(x)g(x)dx=\frac{a_0\tilde{a_0}}{2}+\sum_{k=1}^{n}(a_k\tilde{a_k}+b_k\tilde{b_k})
$$

#### proof:

用 $f+g,f-g$ 的 Parseval 等式相减。

### 推论 12.10

设 $f(x)\in L^2[-\pi, \pi]$，对于 $[a,b]\sub[-\pi, \pi]$，有
$$
\int_{a}^{b}f(x)dx=\int_{a}^{b}\frac{a_0}{2}dx+\sum_{n=1}^{\infty}\int_{a}^{b}(a_n\cos nx+b_n\sin nx)dx
$$

#### proof:

取 
$$
g(x)=\begin{cases}
1&a\le x\le b\\
0&\text{otherwise}
\end{cases}
$$
运用 12.9 的结论。

### 12.2.4 广义 Fourier 级数

`pass`

## 12.3 收敛证明

### 12.3.1 Dirichlet 定理证明

设
$$
S(x)=\frac{f(x+0)+f(x-0)}{2}\\
S_n(x)=\frac{a_0}{2}+\sum_{k=1}^{n}(a_k\cos kx+b_k\sin kx)
$$
把
$$
a_k=\frac{1}{\pi}\int_{-\pi}^{\pi}f(t)\cos kt\ dt\qquad b_k=\frac{1}{\pi}\int_{-\pi}^{\pi}f(t)\sin kt\ dt
$$
代入部分和 $S_n(x)$
$$
\begin{align*}
S_n(x)&=\frac{1}{2\pi}\int_{-\pi}^{\pi}f(t)\ dt+\frac{1}{\pi}\sum_{k=1}^{n}(\cos kx\int_{-\pi}^{\pi}f(t)\cos kt\ dt+\sin kx\int_{-\pi}^{\pi}f(t)\sin kt\ dt)\\
&=\frac{1}{\pi}\int_{-\pi}^{\pi}[\frac{1}{2}+\sum_{k=1}^{n}\cos k(x-t)]f(t)\ dt\\
&=\frac{1}{\pi}\int_{-\pi}^{\pi}\frac{\sin(n+\frac{1}{2})(x-t)}{2\sin\frac{1}{2}(x-t)}f(t)\ dt\\
&=\frac{1}{2\pi}\int_{-\pi-x}^{\pi-x}\frac{\sin(n+\frac{1}{2})u}{\sin\frac{1}{2}u}f(x+u)\ du\\
&=\frac{1}{2\pi}\int_{-\pi}^{\pi}\frac{\sin(n+\frac{1}{2})u}{\sin\frac{1}{2}u}f(x+u)\ du\\
&=\frac{1}{2\pi}\int_{0}^{\pi}\frac{\sin(n+\frac{1}{2})u}{\sin\frac{1}{2}u}[f(x+u)+f(x-u)]\ du\tag{1}\\
\end{align*}
$$
其中，代入 $f(x)=1$
$$
S_n(x)=1=\frac{1}{\pi}\int_{0}^{\pi}\frac{\sin(n+\frac{1}{2})u}{\sin\frac{1}{2}u}du\tag{2}
$$
$(2)$ 是 Dirichlet 核。

对于一般函数
$$
\begin{align*}
S_n(x)-S(x)&=\frac{1}{2\pi}\int_{0}^{\pi}\frac{\sin(n+\frac{1}{2})u}{\sin\frac{1}{2}u}[f(x+u)+f(x-u)-2S(x)]\ du\\
&=\frac{1}{2\pi}\int_{0}^{\pi}\frac{\sin(n+\frac{1}{2})u}{\sin\frac{1}{2}u}\phi(x,u)\ du\\
\end{align*}
$$
欲证明 $\lim\limits_{n\to\infty}[S_n(x)-S(x)]=0$，要证明
$$
\lim_{n\to\infty}\int_{0}^{\pi}\frac{\sin(n+\frac{1}{2})u}{\sin\frac{1}{2}u}\phi(x,u)\ du\\
$$

------

### Riemann 引理

设函数 $\psi(x)$ 在 $[a,b]$ 上可积且绝对可积，则
$$
\lim_{n\to\infty}\int_{a}^{b}\psi(x)\sin nx\ dx=\lim_{n\to\infty}\int_{a}^{b}\psi(x)\cos nx\ dx=0
$$

#### proof:

考虑 $\psi(x)$ 有界

对 $[a,b]$ 进行分割
$$
a=x_0<x_1<\dots<x_n=b
$$
因为 $\psi(x)$ 有界故可积，$\forall\epsilon>0$，存在
$$
\sum_{i=1}^{n}\omega_i(x_i-x_{i-1})<\epsilon/2
$$
记 $m_i$ 为 $[x_{i-1},x_i]$ 的下确界，则 $\sum_{i=1}^{n}|m_i|$ 是常数，因此取 $N=\frac{4}{\epsilon}(\sum_{i=1}^{n}|m_i|)$，当 $ n>N$ 时有
$$
\frac{2}{n}(\sum_{i=1}^{t}|m_i|)<\frac{\epsilon}{2}
$$
故 $\forall\epsilon>0,\exist N>0:n>N$
$$
\begin{align*}
|\int_{a}^{b}\psi(x)\sin nx\ dx|&=|\sum_{i=1}^{n}\int_{x_{i-1}}^{x_i}\psi(x)\sin nx\ dx|\\
&=|\sum_{i=1}^{n}\int_{x_{i-1}}^{x_i}(\psi(x)-m_i)\sin nx\ dx+\sum_{i=1}^{n}\int_{x_{i-1}}^{x_i}m_i\sin nx\ dx|\\
&\le\sum_{i=1}^{n}\int_{x_{i-1}}^{x_i}|(\psi(x)-m_i)||\sin nx|\ dx+\sum_{i=1}^{n}|m_i|\int_{x_{i-1}}^{x_i}|\sin nx|\ dx\\
&\le\sum_{i=1}^{n}\int_{x_{i-1}}^{x_i}|(\psi(x)-m_i)|\ dx+\sum_{i=1}^{n}|m_i|(\frac{\cos nx_i-\cos nx_{i-1}}{n})\\
&\le\frac{\epsilon}{2}+\sum_{i=1}^{n}|m_i|(\frac{2}{n})\\
&\le\epsilon\\
\end{align*}
$$
考虑 $\psi(x)$ 无界且绝对可积

假设 $b$ 是唯一的瑕点，则 $\forall\epsilon>0,\exist\delta>0:\eta<\delta$
$$
\int_{b-\eta}^b|\psi(x)\sin nx|dx<\int_{b-\eta}^b|\psi(x)|dx<\epsilon/2
$$
对 $[a,b-\eta]$ 应用有界的情况，可得 $\forall\epsilon>0,\exist N>0:n>N$
$$
|\int_{a}^b\psi(x)\sin nxdx|<\epsilon
$$
故 Riemann 引理得证。

------

回到 Dirichlet:
$$
\begin{align*}
\lim_{n\to\infty}\int_{0}^{\pi}\frac{\sin(n+\frac{1}{2})u}{\sin\frac{1}{2}u}\phi(x,u)\ du=\lim_{n\to\infty}\int_{0}^{\pi}\frac{\phi(x,u)}{\sin\frac{1}{2}u}[\sin\frac{u}{2}\cos nu+\cos\frac{u}{2}\sin nu]\ du\\
\end{align*}
$$
如果 $\frac{\phi(x,u)}{\sin\frac{1}{2}u}$ 可积且绝对可积，那么上式极限为 0。
$$
\begin{align*}
\lim_{u\to0^+}\frac{\phi(x,u)}{\sin\frac{1}{2}u}&=\lim_{u\to0^+}\frac{f(x+u)+f(x-u)-f(x+0)-f(x-0)}{\sin\frac{1}{2}u}\\
&=\lim_{u\to0^+}[\frac{f(x+u)-f(x+0)}{u}+\frac{f(x-u)-f(x-0)}{u}]\frac{u}{\sin\frac{1}{2}u}\\
&=\lim_{u\to0^+}2(f'(x+0)-f'(x-0))
\end{align*}
$$
由于 $f(x)$ 分段光滑，所以 $f'(x)$ 分段连续。

## 12.4 Fourier 变换

### 12.4.1 Fourier 积分

$f(x)$ 定义在 $[-l,l]$，
$$
f(x)\thicksim\sum_{n=-\infty}^{\infty}F_{n}e^{in\omega x}\\
F_{\pm n}=\frac{1}{2l}\int_{-l}^{l}f(x)e^{\mp in\omega x}dx
$$
令 $\lambda_{n}=n\omega=\frac{n\pi}{l},\Delta\lambda_n=\lambda_{n}-\lambda_{n-1}$
$$
\begin{align*}
f(x)&\thicksim\sum_{n=-\infty}^{\infty}\frac{1}{2l}\int_{-l}^{l}f(\xi)e^{- in\omega(\xi-x)}d\xi\\
&=\sum_{n=-\infty}^{\infty}\frac{1}{2\pi}[\int_{-l}^{l}f(\xi)e^{- i\lambda_{n}(\xi-x)}d\xi]\Delta\lambda_n\\
&=\sum_{n=-\infty}^{\infty}\frac{1}{2\pi}[\int_{-l}^{l}f(\xi)e^{- i\lambda_{n}\xi}d\xi]e^{i\lambda_{n}x}\Delta\lambda_n\\
&=[\int_{-l}^{l}f(\xi)e^{- i\lambda_{n}\xi}d\xi]\sum_{n=-\infty}^{\infty}\frac{1}{2\pi}e^{i\lambda_{n}x}\Delta\lambda_n\\
&=\frac{1}{2\pi}\int_{-l}^{l}f(\xi)e^{- i\lambda_{n}\xi}d\xi\int_{-\infty}^{\infty}e^{i\lambda x}d\lambda\\
\end{align*}
$$

---

$$
\mathcal F[f(t)]=\int_{-\infty}^{\infty}f(t)e^{-j\omega t}dt=F(\omega)\\
\mathcal F^{-1}[F(\omega)]=\frac{1}{2\pi}\int_{-\infty}^{\infty}F(\omega)e^{j\omega t}d\omega=f(t)\\
$$

Duality:
$$
\begin{align*}
2\pi f(\omega)&=\int_{-\infty}^{\infty}F(t)e^{j\omega t}dt\\
2\pi f(-\omega)&=\int_{-\infty}^{\infty}F(t)e^{-j\omega t}dt\\
&=\mathcal F[F(t)]
\end{align*}
$$
Scaling:
$$
\begin{align*}
\mathcal F[f(at)]&=\int_{-\infty}^{\infty}f(at)e^{-j\omega t}dt\\
&=\begin{cases}
\frac{1}{a}\int_{-\infty}^{\infty}f(\tau)e^{-j\frac{\omega}{a}\tau}d\tau&a>0\\
-\frac{1}{a}\int_{-\infty}^{\infty}f(\tau)e^{-j\frac{\omega}{a}\tau}d\tau&a<0\\
\end{cases}\\
&=\frac{1}{|a|}F(\frac{\omega}{a})
\end{align*}
$$
Time shifting:
$$
\begin{align*}
\mathcal F[f(t-t_0)]&=\int_{-\infty}^{\infty}f(t-t_0)e^{-j\omega t}dt\\
&=\int_{-\infty}^{\infty}f(\tau)e^{-j\omega(\tau+t_0)}d\tau\\
&=e^{-j\omega t_0}\int_{-\infty}^{\infty}f(\tau)e^{-j\omega\tau}d\tau\\
&=e^{-j\omega t_0}F(\omega)
\end{align*}
$$
Frequency shifting:
$$
\begin{align*}
\mathcal F[f(t)e^{\pm j\omega_0 t}]&=\int_{-\infty}^{\infty}f(t)e^{\pm j\omega_0 t}e^{-j\omega t}dt\\
&=\int_{-\infty}^{\infty}f(t)e^{-j(\omega\mp \omega_0)t}dt\\
&=F(\omega\mp \omega_0)
\end{align*}
$$
Conjugation Symmetry:
$$
\begin{align*}
\mathcal F[f^*(t)]&=\int_{-\infty}^{\infty}f^*(t)e^{-j\omega t}dt\\
&=[\int_{-\infty}^{\infty}f(t)e^{j\omega t}dt]^*\\
&=F^*(-\omega)
\end{align*}
$$
Convolution:
$$
\begin{align*}
\mathcal F[f_1(t)*f_2(t)]&=\int_{-\infty}^{\infty}e^{-j\omega t}\int_{-\infty}^{\infty}f_1(\tau)f_2(t-\tau)d\tau dt\\
&=\int_{-\infty}^{\infty}f_1(\tau)\int_{-\infty}^{\infty}f_2(t-\tau)e^{-j\omega t}dtd\tau \\
&=F_2(\omega)\int_{-\infty}^{\infty}f_1(\tau)e^{-j\omega\tau}d\tau \\
&=F_1(\omega)F_2(\omega)
\end{align*}
$$
Multiplication:
$$
\begin{align*}
f(t)=f_1(t)f_2(t)&=\frac{1}{2\pi}\int_{-\infty}^{\infty}F_1(\omega_1)e^{j\omega_1 t}d\omega_1\frac{1}{2\pi}\int_{-\infty}^{\infty}F_2(\omega_2)e^{j\omega_2 t}d\omega_2\\
&=\frac{1}{2\pi}\int_{-\infty}^{\infty}\frac{1}{2\pi}\int_{-\infty}^{\infty}F_1(\omega_1)F_2(\omega_2)e^{j(\omega_1+\omega_2)t}d\omega_1d\omega_2\\
&=\frac{1}{2\pi}\int_{-\infty}^{\infty}e^{j\omega t}\frac{1}{2\pi}\int_{-\infty}^{\infty}F_1(\omega_1)F_2(\omega-\omega_1)d\omega_1d\omega\\
&=\frac{1}{2\pi}\int_{-\infty}^{\infty}[\frac{1}{2\pi}F_1(\omega)*F_2(\omega)]e^{j\omega t}d\omega\\
&=\frac{1}{2\pi}\int_{-\infty}^{\infty}[\frac{1}{2\pi}F(\omega)]e^{j\omega t}d\omega\\
\end{align*}
$$
Differential:
$$
\begin{align*}
\frac{d}{dt}f(t)&=\frac{d}{dt}\int_{-\infty}^{\infty}F(\omega)e^{j\omega t}dt\\
&=\int_{-\infty}^{\infty}F(\omega)\frac{d}{dt}e^{j\omega t}d\tau\\
&=\int_{-\infty}^{\infty}j\omega F(\omega)e^{j\omega t}d\tau\\
\mathcal{F}\{\frac{d}{dt}f(t)\}&=j\omega F(\omega)
\end{align*}
$$
