# Spherical Harmonics

## $\nabla^2u=0$

Laplace 方程在球坐标系中的表示为：
$$
\frac{1}{r^2}\frac{\part}{\part r}(r^2\frac{\part u}{\part r})+\frac{1}{r^2\sin\theta}\frac{\part}{\part\theta}(\sin\theta\frac{\part u}{\part\theta})+\frac{1}{r^2\sin^2\theta}\frac{\part^2u}{\part\phi^2}=0\tag{1.1}
$$
首先把表示距离的变量 $r$ 与表示角度的变量 $\theta,\phi$ 分离：
$$
u(r,\theta,\phi)=R(r)Y(\theta,\phi)
$$
带入 $(1.1)$ 式：
$$
\frac{Y}{r^2}\frac{d}{dr}(r^2\frac{dR}{dr})+\frac{R}{r^2\sin\theta}\frac{\part}{\part\theta}(\sin\theta\frac{\part Y}{\part\theta})+\frac{R}{r^2\sin^2\theta}\frac{\part^2Y}{\part\phi^2}=0
$$
两边同乘 $\dfrac{r^2}{RY}$ 并且移项后得到：
$$
\frac{1}{R}\frac{d}{dr}(r^2\frac{dR}{dr})+\frac{1}{Y\sin\theta}\frac{\part}{\part\theta}(\sin\theta\frac{\part Y}{\part\theta})+\frac{1}{Y\sin^2\theta}\frac{\part^2Y}{\part\phi^2}=0\\
\frac{1}{R}\frac{d}{dr}(r^2\frac{dR}{dr})=-\frac{1}{Y\sin\theta}\frac{\part}{\part\theta}(\sin\theta\frac{\part Y}{\part\theta})-\frac{1}{Y\sin^2\theta}\frac{\part^2Y}{\part\phi^2}
$$
左右两侧分别为关于 $r$ 的函数和关于 $\theta, \phi$ 的函数，二者只可能等于某个常数，令这个常数为 $l(l+1)$，因此：
$$
\frac{1}{R}\frac{d}{dr}(r^2\frac{dR}{dr})=l(l+1)\\
r^2\frac{d^2R}{dr^2}+2r\frac{dR}{dr}-l(l+1)R=0\tag{1.2}
$$

$$
\frac{1}{Y\sin\theta}\frac{\part}{\part\theta}(\sin\theta\frac{\part Y}{\part\theta})+\frac{1}{Y\sin^2\theta}\frac{\part^2Y}{\part\phi^2}=-l(l+1)\tag{1.3}\\
$$

$(1.2)$ 式为欧拉型常微分方程：

---

令 $r=e^t$，则：
$$
\begin{align*}
\frac{dR}{dr}&=\frac{dR}{dt}\frac{dt}{dx}=\frac{1}{r}\frac{dR}{dt}\\
\frac{d^2R}{dr^2}&=\frac{d}{dr}(\frac{dR}{dr})=\frac{d}{dr}(\frac{1}{r}\frac{dR}{dt})\\
&=-\frac{1}{r^2}\frac{dR}{dt}+\frac{1}{r}\frac{d}{dr}(\frac{dR}{dt})\\
&=-\frac{1}{r^2}\frac{dR}{dt}+\frac{1}{r}\frac{d}{dt}(\frac{dR}{dt})\frac{dt}{dr}\\
&=-\frac{1}{r^2}\frac{dR}{dt}+\frac{1}{r^2}\frac{d^2R}{dt^2}\\
&=\frac{1}{r^2}(\frac{d^2R}{dt^2}-\frac{dR}{dt})\\
\end{align*}
$$
带入 $(1.2)$ 式：

$$
\frac{d^2R}{dt^2}+\frac{dR}{dt}-l(l+1)R=0\\
$$
解得：
$$
\color{red}\begin{align*}
R&=Ae^{lt}+Be^{-(l+1)t}\\
&=Ar^l+B\frac{1}{r^{l+1}}
\end{align*}
$$

---

进一步分离变量
$$
Y(\theta,\phi)=\Theta(\theta)\Phi(\phi)
$$
$(1.3)$ 式左右两边同时乘以 $\sin^2\theta$，并且移项：
$$
\frac{\sin\theta}{\Theta}\frac{d}{d\theta}(\sin\theta\frac{d\Theta}{d\theta})+\frac{1}{\Phi}\frac{d^2\Phi}{d\phi^2}=-l(l+1)\sin^2\theta\\
\frac{\sin\theta}{\Theta}\frac{d}{d\theta}(\sin\theta\frac{d\Theta}{d\theta})+l(l+1)\sin^2\theta=-\frac{1}{\Phi}\frac{d^2\Phi}{d\phi^2}\\
$$
同理，方程左右必须等于某个常数，令这个常数为 $m^2$：
$$
\frac{\sin\theta}{\Theta}\frac{d}{d\theta}(\sin\theta\frac{d\Theta}{d\theta})+l(l+1)\sin^2\theta=m^2\\
\frac{\sin\theta}{\Theta}(\cos\theta\frac{d\Theta}{d\theta}+\sin\theta\frac{d^2\Theta}{d\theta^2})+l(l+1)\sin^2\theta=m^2\tag{1.4}
$$

$$
-\frac{1}{\Phi}\frac{d^2\Phi}{d\phi^2}=m^2\tag{1.5}
$$

$(1.5)$ 式的通解为：
$$
\color{red}\Phi(\phi)=C_1\cos m\phi+C_2\sin m\phi
$$
对于 $(1.4)$ 式，进行变量代换：
$$
x=\cos\theta,y=\Theta(\theta)
$$
可得：
$$
\begin{align*}
\frac{d\Theta}{d\theta}&=\frac{dy}{dx}\frac{dx}{d\theta}=-\frac{dy}{dx}\sin\theta\\
\frac{d^2\Theta}{d\theta^2}&=-\frac{d}{d\theta}(\frac{dy}{dx}\sin\theta)\\
&=-\frac{d}{d\theta}(\frac{dy}{dx})\sin\theta-\frac{dy}{dx}\cos\theta\\
&=-\frac{d}{dx}(\frac{dy}{dx})\frac{dx}{d\theta}\sin\theta-\frac{dy}{dx}\cos\theta\\
&=\frac{d^2y}{dx^2}\sin^2\theta-\frac{dy}{dx}\cos\theta\\
\end{align*}
$$
带入 $(1.4)$ 式：
$$
(1-x^2)\frac{d^2y}{dx^2}-2x\frac{dy}{dx}+\left[l(l+1)-\frac{m^2}{1-x^2}\right]y=0\tag{1.6}
$$
$(1.6)$ 式即为 $l$ 阶**连带 Legendre 方程**。$m=0$ 时，为 $l$ 阶 **Legendre 方程**。

## Legendre's Polynomial

先考虑 $m=0$ 的情况。改写 Legendre 方程为：
$$
\frac{d^2y}{dx^2}-\frac{2x}{1-x^2}\frac{dy}{dx}+\frac{l(l+1)}{1-x^2}y=0\tag{2.1}
$$

在 $x=0$ 处，
$$
P(x)=\frac{2x}{1-x^2}\to0\\
Q(x)=\frac{l(l+1)}{1-x^2}\to l(l+1)
$$
均为有限值，他们必然在 $x=0$ 处解析。可在这点有 Taylor 级数解，设解为：
$$
y=\sum_{k=0}^{\infty}C_kx^k
$$
带入 $(1.6)$​ 式：
$$
(1-x^2)\sum_{k=2}^{\infty}k(k-1)C_kx^{k-2}-2x\sum_{k=1}^{\infty}kC_kx^{k-1}+l(l+1)\sum_{k=0}^{\infty}C_kx^k=0\\
\sum_{k=0}^{\infty}(k+2)(k+1)C_{k+2}x^k-\sum_{k=2}^{\infty}k(k-1)C_kx^k-2\sum_{k=1}^{\infty}kC_kx^k+l(l+1)\sum_{k=0}^{\infty}C_kx^k=0\\
\left[\sum_{k=0}^{\infty}(k+2)(k+1)C_{k+2}-\sum_{k=\color{red}0}^{\infty}k(k-1)C_k-2\sum_{k=\color{red}0}^{\infty}kC_k+l(l+1)\sum_{k=0}^{\infty}C_k\right]x^k=0\\
\sum_{k=0}^{\infty}[(k+2)(k+1)C_{k+2}-(k-l)(k+l+1)C_k]x^k=0\\
$$
因此需要上述各项为 $0$，得到解的系数的递推公式：
$$
(k+2)(k+1)C_{k+2}-(k-l)(k+l+1)C_k=0\\
C_{k+2}=\frac{(k-l)(k+l+1)}{(k+2)(k+1)}C_k
$$
从 $C_0$ 开始递推偶数项：
$$
C_2=\frac{-l(l+1)}{2!}C_0\\
C_4=\frac{(2-l)(3+l)}{4\cdot3}C_2=\frac{(2-l)(0-l)(l+1)(3+l)}{4!}C_0\\
\cdots\\
C_{2k}=\frac{(2k-2-l)\cdots(0-l)(1+l)\cdots(2k-1+l)}{(2k)!}C_0
$$
从 $C_1$ 开始递推奇数项：

$$
C_3=\frac{(1-l)(2+l)}{3!}C_1\\
C_5=\frac{(3-l)(4+l)}{5\cdot4}C_3=\frac{(3-l)(1-l)(2+l)(4+l)}{5!}C_1\\
\cdots\\
C_{2k+1}=\frac{(2k-1-l)\cdots(1-l)(2+l)\cdots(2k+l)}{(2k+1)!}C_1
$$
因此得到 Legendre 方程的解：
$$
\color{red}\begin{align*}
y&=y_0(x)+y_1(x)\\
&=C_0\left[1+\sum_{k=1}^{\infty}\frac{(2k-2-l)\cdots(0-l)(1+l)\cdots(2k-1+l)}{(2k)!}x^{2k}\right]\\
&+C_1\left[x+\sum_{k=1}^{\infty}\frac{(2k-1-l)\cdots(1-l)(2+l)\cdots(2k+l)}{(2k+1)!}x^{2k+1}\right]
\end{align*}
$$
奇偶部分的级数是 Legendre 方程两个线性独立的解，称为 Legendre 函数。其中，$y_0(x)$ 是偶函数，$y_1(x)$ 是奇函数。

Legendre 函数收敛半径为：

$$
R=\lim_{k\to\infty}\left|\frac{C_k}{C_{k+2}}\right|=\lim_{k\to\infty}\left|\frac{(k+2)(k+1)}{(k-l)(k+l+1)}\right|=1
$$
因此 Legendre 函数收敛域为 $x\in(-1,1)$ ，对应 $\theta\ne0，\pi$。

---

$$
\begin{align*}
\lim_{k\to\infty}k\left(\frac{(2k+2)(2k+1)}{(2k-l)(2k+l+1)}-1\right)&=\lim_{k\to\infty}k\left(\frac{4k^2+6k+2}{4k^2+2k-l^2-l}-1\right)\\
&=\lim_{k\to\infty}\left(\frac{4k^2+(2+l^2+l)k}{k^2+k-l^2-l}\right)\\
&=4>1
\end{align*}
$$

因此由 Raabe 判别法可得，$y_0(x)$ 在 $x=1$ 处发散。同理 $y_1(x)$ 在 $x=-1$ 处发散。

---

观察可得，当某个因子出现在系数中时候，它会在之后的所有项中出现。特别是，当 $l$ 取整数时候，对于某个 $k$，$2k-l$ 或 $2k-1-l$ 会变成 $0$，即 $y_0(x)$ 或 $y_1(x)$ 会从无穷级数变为有限的级数，发散的问题就不存在了：

**如果 $l$ 是正偶数， $y_0(x)$ 变为 $l$ 次多项式；如果 $l$ 是正奇数， $y_1(x)$ 变为 $l$ 次多项式。$l$ 为负数时候可以得到类似结论。**

取
$$
C_l=\frac{(2l)!}{2^l(l!)^2}
$$
时候，可以使得各项的系数保持简洁：
$$
C_{l-2}=-\frac{l(l-1)}{2(2l-1)}C_l=-\frac{l(l-1)}{2(2l-1)}\frac{(2l)!}{2^l(l!)^2}=-\frac{(2l-2)!}{2^l(l-1)!(l-2)!}\\
C_{l-4}=-\frac{(l-2)(l-3)}{4(2l-3)}C_{l-2}=\frac{(l-2)(l-3)}{4(2l-3)}\frac{(2l-2)!}{2^l(l-1)!(l-2)!}=\frac{(2l-4)!}{2^l2!(l-2)!(l-4)!}\\
C_{l-2k}=(-1)^{k}\frac{(2l-2k)!}{2^lk!(l-k)!(l-2k)!}\quad k\in[0, l/2]
$$
因此，$l$ 次的 Legendre 多项式为：
$$
P_{l}(x)=\frac{1}{2^l}\sum_{k=0}^{K}(-1)^{k}\frac{(2l-2k)!}{k!(l-k)!(l-2k)!}x^{l-2k}
$$
其中，$l$ 为偶数时候 $K=l/2$，$l$ 为奇数时候 $K=(l-1)/2$。

以下是前几阶的 Legendre 多项式：
$$
\begin{align*}
P_0(x)&=1&P_1(x)&=x\\
P_2(x)&=\frac{1}{2}(3x^2-1)&P_3(x)&=\frac{1}{2}(5x^3-3x)\\
P_4(x)&=\frac{1}{8}(35x^4-30x^2+3)&P_5(x)&=\frac{1}{8}(63x^5-70x^3+15x)
\end{align*}
$$

以 $\theta$ 为变量：
$$
\begin{align*}
P_0(x)&=1&P_1(x)&=\cos\theta\\
P_2(x)&=\frac{1}{4}(3\cos2\theta+1)&P_3(x)&=\frac{1}{8}(5\cos3\theta+3\cos\theta)\\
P_4(x)&=\frac{1}{64}(35\cos4\theta+20\cos2\theta+9)&P_5(x)&=\frac{1}{128}(63\cos5\theta+35\cos3\theta+30\cos\theta)
\end{align*}
$$

## Basic Property of Legendre Polynomial

### Differential Representation

Rodriques 公式：
$$
P_l(x)=\frac{1}{2^ll!}\frac{d^l}{dx^l}(x^2-1)^l
$$

<blockquote style="border-left: 5px solid #4545aa; border-radius: 3px 0 0 3px; padding: 10px 15px; background-color: rgba(70, 70, 188, 0.1)">
    证明
</blockquote>

二项式定理展开：
$$
\begin{align*}
(x^2-1)^l&=\sum_{k=0}^{l}\binom{l}{k}x^{2l-2k}(-1)^{k}\\
&=\sum_{k=0}^{l}\frac{(-1)^{k}l!}{k!(l-k)!}x^{2l-2k}\\
\end{align*}
$$
因此：
$$
\begin{align*}
\frac{1}{2^ll!}\frac{d^l}{dx^l}(x^2-1)^l&=\frac{d^l}{dx^l}\sum_{k=0}^{l}\frac{(-1)^{k}}{k!(l-k)!}x^{2l-2k}\\
&=\frac{1}{2^l}\sum_{k=0}^{l}\frac{(-1)^{k}}{k!(l-k)!}\frac{d^l}{dx^l}x^{2l-2k}\\
&=\frac{1}{2^l}\sum_{k=0}^{K}\frac{(-1)^{k}}{k!(l-k)!}\frac{d^l}{dx^l}x^{2l-2k}\\
&=\frac{1}{2^l}\sum_{k=0}^{K}\frac{(-1)^{k}(2l-2k)!}{k!(l-k)!(l-2k)!}x^{l-2k}\\
&=P_l(x)
\end{align*}
$$

### Recurrent Formula

<blockquote style="border-left: 5px solid #42b983; border-radius: 3px 0 0 3px; padding: 10px 15px; background-color: rgba(66, 185, 131, 0.1)">
    1
</blockquote>

$$
(n+1)P_{n+1}(x)=(2n+1)xP_n(x)-nP_{n-1}(x)
$$

<blockquote style="border-left: 5px solid #4545aa; border-radius: 3px 0 0 3px; padding: 10px 15px; background-color: rgba(70, 70, 188, 0.1)">
    证明
</blockquote>

令 $u=x^2-1$​，则
$$
\frac{d}{dx}u^{n+1}=2(n+1)xu^{n}
$$

$$
\begin{align*}
\frac{d^2}{dx^2}u^{n+1}&=\frac{d}{dx}[2(n+1)xu^n]\\
&=2(n+1)[u^n+2nx^2u^{n-1}]\\
&=2(n+1)[u^n+2n(u+1)u^{n-1}]\\
&=2(n+1)[(2n+1)u^n+2nu^{n-1}]\\
\end{align*}
$$

因此先看作一阶导：
$$
\begin{align*}
P_{n+1}(x)&=\frac{1}{2^{n+1}(n+1)!}\frac{d^{n+1}}{dx^{n+1}}u^{n+1}\\
&=\frac{1}{2^nn!}\frac{d^n}{dx^n}[xu^{n}]\\
&=\frac{1}{2^nn!}\sum_{k=0}^{n}\binom{n}{k}\frac{d^kx}{dx^k}\frac{d^{n-k}u^{n}}{dx^{n-k}}\\
&=\frac{1}{2^nn!}[x\frac{d^n}{dx^n}u^{n}+n\frac{d^{n-1}}{dx^{n-1}}u^n]\\
&=xP_{n}(x)+\frac{n}{2^nn!}\frac{d^{n-1}}{dx^{n-1}}u^n
\end{align*}
$$
再看作二阶导：
$$
\begin{align*}
P_{n+1}(x)&=\frac{1}{2^{n+1}(n+1)!}\frac{d^{n+1}}{dx^{n+1}}u^{n+1}\\
&=\frac{1}{2^nn!}\frac{d^{n-1}}{dx^{n-1}}\left[(2n+1)u^n+2nu^{n-1}\right]\\
&=\frac{(2n+1)}{2^nn!}\frac{d^{n-1}}{dx^{n-1}}u^n+\frac{1}{2^{n-1}(n-1)!}\frac{d^{n-1}}{dx^{n-1}}u^{n-1}\\
&=\frac{(2n+1)}{2^nn!}\frac{d^{n-1}}{dx^{n-1}}u^n+P_{n-1}(x)\\
\end{align*}
$$
因此：
$$
\begin{align*}
P_{n+1}(x)&=\frac{(2n+1)}{2^nn!}\frac{d^{n-1}}{dx^{n-1}}u^n+P_{n-1}(x)\\
&=\frac{(2n+1)}{n}[P_{n+1}(x)-xP_n(x)]+P_{n-1}(x)\\
(n+1)P_{n+1}(x)&=(2n+1)xP_n(x)-nP_{n-1}(x)
\end{align*}
$$

## Associated Legendre functions

对于：
$$
(1-x^2)\frac{d^{2}P_{l}(x)}{dx^{2}}-2x\frac{dP_{l}(x)}{dx}+l(l+1)P_{l}(x)=0
$$
两边求一阶导到 $m$ 阶导：
$$
(1-x^2)\frac{d^{1+2}P_{l}(x)}{dx^{1+2}}-2(1+1)x\frac{d^{1+1}P_{l}(x)}{dx^{1+1}}+[l(l+1)-1\cdot2]\frac{d^{1}P_{l}(x)}{dx^{1}}=0\\
(1-x^2)\frac{d^{2+2}P_{l}(x)}{dx^{2+2}}-2(2+1)x\frac{d^{2+1}P_{l}(x)}{dx^{2+1}}+[l(l+1)-2\cdot3]\frac{d^{2}P_{1}(x)}{dx^{2}}=0\\
\vdots\\
(1-x^2)\frac{d^{m+2}P_{l}(x)}{dx^{m+2}}-2(m+1)x\frac{d^{m+1}P_{l}(x)}{dx^{m+1}}+[l(l+1)-m(m+1)]\frac{d^{m}P_{l}(x)}{dx^{m}}=0
$$

因为 $P_l(x)$ 是 $l$ 阶多项式，因此 $m\in[0,l]$ 以保证等式左边不为常数 $0$。
$$
(1-x^2)\frac{d^2y}{dx^2}-2x\frac{dy}{dx}+\left[l(l+1)-\frac{m^2}{1-x^2}\right]y=0\tag{4.1}
$$

连带 Legendre 函数是 Legendre 方程中 $m\ne0$ 时候的解。引入：

$$
\begin{align*}
w(x)&=(1-x^2)^{m/2}\frac{d^{m}P_{l}(x)}{dx^{m}}\\
\frac{dw}{dx}&=-mx(1-x^2)^{m/2-1}\frac{d^{m}P_{l}(x)}{dx^{m}}\\
&+(1-x^2)^{m/2}\frac{d^{m+1}P_{l}(x)}{dx^{m+1}}\\
\frac{d^2w}{dx^2}&=-m(1-x^2)^{m/2-1}\frac{d^{m}P_{l}(x)}{dx^{m}}\\
&+m(m-2)x^2(1-x^2)^{m/2-2}\frac{d^{m}P_{l}(x)}{dx^{m}}\\
&-2mx(1-x^2)^{m/2-1}\frac{d^{m+1}P_{l}(x)}{dx^{m+1}}\\
&+(1-x^2)^{m/2}\frac{d^{m+2}P_{l}(x)}{dx^{m+2}}\\
\end{align*}
$$
带入 $(4.1)$ 式：
$$
\begin{align*}
&\quad(1-x^2)\frac{d^{2}w(x)}{dx^{2}}-2x\frac{dw}{dx}+[l(l+1)-\frac{m^2}{1-x^2}]w\\
&=(1-x^2)\frac{d^{m+2}P_{l}(x)}{dx^{n+2}}-2(m+1)x\frac{d^{m+1}P_{l}(x)}{dx^{m+1}}+[l(l+1)-m(m+1)]\frac{d^{m}P_{l}(x)}{dx^{m}}\\
&=0
\end{align*}
$$
因此 $w(x)$ 就是 $(4.1)$ 式的解，记为：
$$
\color{red}P_{l}^{m}(x)=(1-x^2)^{m/2}\frac{d^{m}P_{l}(x)}{dx^{m}}
$$
称为 $m$ 阶**连带勒让德多项式**。

因此如果 $l\in[0,n]$，对于每一个 $l$，$m\in[0,l]$

## Sphere Harmonics

把角度函数 $Y(\theta,\phi)=\Theta(\theta)\Phi(\phi)$ 的两部分解拼起来：
$$
\begin{align*}
Y_{l}^{m}(\theta,\phi)&=\Theta_{l}^{m}(\theta)\Phi(\phi)\\
&=P_{l}^{m}(\cos\theta)\left\{\begin{matrix}\cos m\phi \\ \sin m\phi\end{matrix}\right\}\quad l\in\{0,\dots,n\},m\in\{0,\dots,l\}\\
&=P_{l}^{|m|}(\cos\theta)\exp(im\phi)\quad l\in\{0,\dots,n\},m\in\{-l,\dots,l\}\\
\end{align*}
$$
归一化后得到：
$$
Y_{l}^{m}(\theta,\phi)=\sqrt{\frac{(2l+1)(l-m)!}{4\pi(l+m)!}}P_{l}^{|m|}(\cos\theta)\exp(im\phi)\\
l\in\{0,\dots,n\},m\in\{-l,\dots,l\},\theta\in[0,\pi],\phi\in[0,2\pi]\\
$$
用三角函数来表示就是：
$$
Y_{l}^{m}(\theta,\phi)=\begin{cases}
(-1)^{m}\sqrt{2}\sqrt{\dfrac{2l+1}{4\pi}\dfrac{(l-|m|)!}{(l+|m|)!}}P_{l}^{|m|}(\cos\theta)\sin|m|\phi&m<0\\
\sqrt{\dfrac{2l+1}{4\pi}P_{l}}(\cos\theta)&m=0\\
(-1)^{m}\sqrt{2}\sqrt{\dfrac{2l+1}{4\pi}\dfrac{(l-m)!}{(l+m)!}}P_{l}^{m}(\cos\theta)\cos m\phi&m>0\\
\end{cases}
$$
