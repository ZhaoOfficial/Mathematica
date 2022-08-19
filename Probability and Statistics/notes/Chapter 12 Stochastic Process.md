# 第十二章 随机过程及其统计描述
# Chapter 12 Stochastic Process

## 12.1 随机过程的概念

它的研究对象是随时间演变的随机现象，需要用无限多个随机变量来进行描述。

设 $T$ 是一无限实数集，我们把依赖于参数 $t\in T$ 的一族随机变量成为*随机过程*，记为 $\{X(t),t\in T\}$，$T$ 称为*参数集*。

我们称 $X(t)$ 为时刻 $t$ 时候过程的*状态*，而 $X(t_1)=x$ 称为 $t=t_1$ 时候过程处于状态 $x$。对于 $\{X(t)\}$ 的所有可能取值的全体称为随机过程的*状态空间*。

对于随机过程进行一次实验的结果记为 $x(t),t\in T$，成为随机过程的一个*样本函数*或者样本曲线。

> Example 1:
>
> 抛一次硬币，定义
> $$
> X(t)=\begin{cases}\cos\pi t&\text{it is head}\\t&\text{it is tail}\end{cases}
> $$
> 一次试验是抛一次硬币，当得到 head 时，样本函数是 $\cos\pi t$；当得到 tail 时，样本函数是 $t$。则状态空间是 $(-\infty, +\infty)$。
>


> Example 2:
>
> 考虑随机相位正弦波
> $$
> X(t)=a\cos(\omega t+\Theta)
> $$
> $a,\omega>0$ 为常数，$\Theta\thicksim\text{Unif}(0, 2\pi)$。
>
> 一次试验是从 $\Theta$ 中得到一个值 $\theta$，对应的样本函数为 $a\cos(\omega t+\theta)$。则状态空间是 $[-a,a]$。
>
> Example 3:
>
> 考虑抛一颗骰子，$X(n)$ 是第 $n$ 次抛掷的点数，$Y(n)$ 是前 $n$ 次抛掷的点数的最大值。
>
> 对于$X(n)$，一次试验是抛这个骰子，样本函数是这一次实验的点数序列。则状态空间是 $\{1,2,3,4,5,6\}$。
>
> 对于$Y(n)$，一次试验是抛这个骰子，样本函数是这一次实验的点数的最大值序列。则状态空间是 $\{1,2,3,4,5,6\}$。

根据任一时刻的**状态**为连续性随机变量或离散型随机变量分为连续型随机过程和离散型随机过程。

根据**参数**的连续或离散分为连续参数随机过程和离散参数随机过程。

## 12.2 随机过程的统计描述

### 12.2.1 随机过程的分布函数族

给定随机过程 $\{X(t),t\in T\}$，对于每个固定的参数 $t$，随机变量 $X(t)$ 的分布函数与 $t$ 有关，记为
$$
F_X(x,t)=P\{X(t)\le x\},x\in\mathbb R
$$
称它为随机过程 $\{X(t),t\in T\}$ 的*一维分布函数*，$F_X(x,t)$ 称为*一维分布函数族*。

为了描述随机过程在不同时刻状态之间的统计联系，对任意 $n$ 个**不同**的时刻 $t_1,t_2,\dots,t_n\in T$，引入 $n$ 个随机变量 $(X(t_1),\dots,X(t_n))$，它们的分布函数记为
$$
F_X(x_1,\dots,x_n;t_1,\dots,t_n)=P\{X(t_1)\le x_1,\dots,X(t_n)\le x_n\},x_i\in\mathbb R
$$
对于固定的 $n$，我们称 $F_X(x_1,\dots,x_n;t_1,\dots,t_n)$ 为随机过程 $\{X(t),t\in T\}$ 的 *$n$ 维分布函数族*。

$n$ 越大，$n$ 维分布函数族对于随机过程的描述也越完善。

### 12.2.2 随机过程的数字特征

给定随机过程 $\{X(t),t\in T\}$，对于每个固定的参数 $t$，$X(t)$ 是一个随机变量，它的均值与 $t$ 有关，记为
$$
\mu_X(t)=\text{E}[X(t)]
$$
则称 $\mu_X(t)$ 为随机过程 $\{X(t),t\in T\}$ 的*均值函数*，也称集平均或者统计评价。

我们把随机过程 $\{X(t),t\in T\}$ 的二阶原点矩和二阶中心矩记作
$$
\Psi_X^2(t)=\text{E}[X^2(t)]\\
\sigma_X^2(t)=D_X(t)=\text{Var}[X(t)]=\text{E}[(X(t)-\mu_X(t))^2]
$$
并分别称它们为随机过程 $\{X(t),t\in T\}$ 的*均方值函数*和*方差函数*。$\sigma_X(t)$ 为*标准差函数*。

设任意 $t_1,t_2\in T$，把随机变量 $X(t_1),X(t_2)$ 的二阶原点混合矩，二阶中心混合矩记作
$$
R_{XX}(t_1,t_2)=\text{E}[X(t_1)X(t_2)]\\
C_{XX}(t_1,t_2)=\text{Cov}[X(t_1),X(t_2)]=\text{E}[(X(t_1)-\mu_X(t_1))(X(t_2)-\mu_X(t_2))]
$$
并分别称它们为随机过程 $\{X(t),t\in T\}$ 的*自相关函数*和*自协方差函数*。

如果对于每一个参数 $t$，随机过程 $\{X(t),t\in T\}$ 的二阶矩都存在，则称它为*二阶矩过程*。

特殊的二阶矩过程：*正态过程*，即对于任意 $n\ge1$ 和任意 $t_1,t_2,\dots,t_n\in T$，$(X(t_1),\dots,X(t_n))$ 服从 $n$ 维正态分布。正态过程的统计特性完全由均值函数和自协方差函数决定。

> Example 1:
>
> 设 $A,B$ 是两个随机变量，求随机过程 $X(t)=At+B,t\in(-\infty, +\infty)$ 的数字特征。如果 $A,B$ 相互独立且 $A\thicksim\mathcal{N}(0,1),B\thicksim\text{U}(0,2)$，则 $X(t)$ 的数字特征又是怎么样的？
> $$
> \begin{align*}
> \mu_X(t)&=\text{E}[X(t)]\\
> &=\text{E}[At+B]\\
> &=t\text{E}[A]+\text{E}[B]\\
> \Psi_X(t)&=\text{E}[X^2(t)]\\
> &=\text{E}[t^2A^2+2tAB+B^2]\\
> &=t^2\text{E}[A^2]+2t\text{E}[AB]+\text{E}[B^2]\\
> \sigma_X^2(t)&=\text{E}[(X(t)-\mu_X(t))^2]\\
> &=\text{E}[(At+B-t\text{E}[A]-\text{E}[B])^2]\\
> &=\text{E}[A^2t^2+B^2+t^2\text{E}^2[A]+\text{E}^2[B]\\
> &\quad+2tAB-2t^2\text{E}[A]A-2t\text{E}[B]A\\
> &\quad-2t\text{E}[A]B-2\text{E}[B]B+2t\text{E}[A]\text{E}[B]]\\
> &=t^2\text{E}[A^2]+\text{E}[B^2]-t^2\text{E}^2[A]+2t\text{E}[AB]\\
> &\quad-2t\text{E}[A]\text{E}[B]-\text{E}^2[B]\\
> R_{XX}(t_1,t_2)&=\text{E}[X(t_1)X(t_2)]\\
> &=\text{E}[(At_1+B)(At_2+B)]\\
> &=t_1t_2\text{E}[A^2]+(t_1+t_2)\text{E}[AB]+\text{E}[B^2]\\
> C_{XX}(t_1,t_2)&=\text{E}[X(t_1)-\mu_X(t_1)]\text{E}[X(t_2)-\mu_X(t_2)]\\
> &=\text{E}[(At_1+B-t_1\text{E}[A]-\text{E}[B])(At_2+B-t_2\text{E}[A]-\text{E}[B])]\\
> &=\text{E}[t_1t_2A^2+t_1AB-t_1t_2\text{E}[A]A-t_1\text{E}[B]A\\
> &\quad+t_2AB+B^2-t_2\text{E}[A]B-\text{E}[B]B\\
> &\quad-t_1t_2\text{E}[A]A-t_1\text{E}[A]B+t_1t_2\text{E}^2[A]+t_1\text{E}[A]\text{E}[B]\\
> &\quad-t_2\text{E}[B]A-\text{E}[B]B+t_2\text{E}[A]\text{E}[B]+\text{E}^2[B]\\
> &=t_1t_2\text{E}[A^2]+t_1\text{E}[AB]+t_2\text{E}[AB]+\text{E}[B^2]\\
> &\quad-t_2\text{E}[A]\text{E}[B]-\text{E}^2[B]-t_1t_2\text{E}^2[A]-t_1\text{E}[A]\text{E}[B]\\
> \end{align*}
> $$
>
> $$
> \begin{align*}
> \text{E}(A)&=0\\
> \text{E}(A^2)&=\text{Var}(A)+\text{E}^2(A)=1\\
> \text{E}(B)&=1\\
> \text{E}(B^2)&=4/3\\
> \mu_X(t)&=1\\
> \Psi_X(t)&=t^2+4/3\\
> \sigma_X^2(t)&=t^2+1/3\\
> R_{XX}(t_1,t_2)&=t_1t_2+4/3\\
> C_{XX}(t_1,t_2)&=t_1t_2+1/3\\
> \end{align*}
> $$
>


> Example 2:
>
> 设 $X(t)=A\cos\omega t+B\sin\omega t,t\in(-\infty,+\infty)$，其中 $A,B\sim\mathcal{N}(0,\sigma^2)$ 且相互独立，$\omega$ 为常数。证明 $X(t)$ 是正态过程且求出其均值函数和自相关函数。
>
> 对于任意 $n\ge1$ 和任意 $t_1,t_2,\dots,t_n\in T$，
> $$
> X(t_i)=A\cos\omega t_i+B\sin\omega t_i
> $$
> 故 $X(t_i)$ 是 $A,B$ 的线性组合，由于 $A,B\sim\mathcal{N}(0,\sigma^2)$ 且相互独立，因此 $(X(t_1),\dots,X(t_n))$ 是多维正态分布，因此 $X(t)$ 是正态过程。
> $$
> \begin{align*}
> \mu_X(t)&=\text{E}[A\cos\omega t+B\sin\omega t]\\
> &=\text{E}[A]\cos\omega t+\text{E}[B]\sin\omega t)\\
> &=0\\
> R_{XX}(t_1,t_2)&=\text{E}[(A\cos\omega t_1+B\sin\omega t_1)(A\cos\omega t_2+B\sin\omega t_2)]\\
> &=\sigma^2\cos\omega(t_2-t_1)
> \end{align*}
> $$

### 12.2.3 二维随机过程的分布函数和数字特征

设 $X(t),Y(t)$ 是依赖于同一参数 $t\in T$ 的随机过程，对于不同的 $t\in T$，$X(t),Y(t)$ 是不同的二维随机变量，因此称 $\{(X(t),Y(t)),t\in T\}$ 是*二维随机过程*。

对于给定的二维随机过程 $\{(X(t),Y(t)),t\in T\}$，$t_1,\dots,t_n;t_1',\dots,t_m'\in T$，我们称 $n+m$ 维随机变量
$$
(X(t_1),\dots,X(t_n);Y(t_1'),\dots,Y(t_m'))
$$
 的分布函数
$$
F(x_1,\dots,x_n;t_1,\dots,t_n;y_1,\dots,y_m;t_1',\dots,t_m')
$$
为这个二维随机过程的 *$n+m$ 维分布函数*。

如果对于任意 $n,m\in\mathbb N$ 和任意 $t_1,t_2,\dots,t_n\in T,t_1',t_2',\dots,t_m'\in T$，$(X(t_1),\dots,X(t_n))$ 与 $(Y(t_1'),\dots,Y(t_m'))$ 相互独立，则称随机过程 $X(t)$ 和 $Y(t)$ 是*相互独立*的。

记 $X(t)$ 和 $Y(t)$ 的二阶混合原点矩
$$
R_{XY}(t_1,t_2)=\text{E}[X(t_1)Y(t_2)]
$$
为随机过程 $X(t)$ 和 $Y(t)$ 的*互相关函数*。同理还有 $X(t)$ 和 $Y(t)$ 的*互协方差函数*
$$
\begin{align*}
C_{XY}(t_1,t_2)&=\text{E}[(X(t_1)-\mu_X(t_1))(Y(t_2)-\mu_Y(t_2))]\\
&=R_{XY}(t_1,t_2)-\mu_X(t_1)\mu_Y(t_2)
\end{align*}
$$
如果二维随机过程 $\{(X(t),Y(t)),t\in T\}$ 对于任意的 $t_1,t_2\in T$ 都有 $C_{XY}(t_1,t_2)=0$，则称随机过程 $X(t)$ 和 $Y(t)$ 是*不相关*的。（独立一定不相关，不相关不一定独立）

同理可以引入多维随机过程以及各自的均值函数和两两之间的互相关、互协方差函数。

## 12.3 泊松过程和维纳过程

二者都属于*独立增量过程*：给定二阶矩过程 $\{X(t),t\in T\}$，称随机变量 $X(t)-X(s),0\le s<t$ 为随机过程在区间 $(s,t]$ 上的增量。

如果对于任意 $n\in\mathbb N$ 和任意 $0\le t_0<\dots<t_n$，$n$ 个增量 $X(t_i)-X(t_{i-1})$ 相互独立，则称 $\{X(t),t\in T\}$ 是独立增量过程。

**在互不重叠的区域上，状态的增量是相互独立的。**

对于任意 $h\in\mathbb R$ 和任意 $0\le s+h<t+h$，若 $X(t+h)-X(s+h)$ 与 $X(t)-X(s)$ 的分布相同，则称增量具有*平稳性*。因此增量此时只依赖于 $t-s$ 而与初末状态无关，对应的独立增量过程是*齐次的*或者*时齐的*。

若 $X(0)=0$​​ 且方差函数已知，则独立增量过程 $\{X(t),t\ge0\}$​​​ 的协方差函数：

首先记 $Y(t)=X(t)-\mu_X(t)$，若 $X(t)$ 是独立增量过程，那么 $Y(t)$ 也是独立增量过程且 $Y(0)=0,\ \text{E}[Y(t)]=0,\ \text{E}[Y^2(t)]=\text{E}[(X(t)-\mu_X(t))^2]=D_X(t)$。
$$
\begin{align*}
C_{XX}(s,t)&=\text{E}[(X(s)-\mu_X(s))(X(t)-\mu_X(t))]\\
&=\text{E}[Y(s)Y(t)]\\
&=\text{E}[Y(s)Y(t)-Y^2(s)+Y^2(s)]\\
&=\text{E}[Y(s)(Y(t)-Y(s))]+\text{E}[Y^2(s)]\quad(0\le s<t)\\
&=\text{E}[Y(s)]\text{E}[(Y(t)-Y(s))]+\text{E}[Y^2(s)]\\
&=\text{E}[Y^2(s)]\\
&=D_X(s)
\end{align*}
$$

因此 $C_{XX}(s,t)=D_X(\min(s, t))$。​

### 12.3.1 泊松过程

研究排队理论，散粒噪声。

#### 12.3.1.1 推导

以 $N(t),\ge0$ 表示在时间间隔 $(0,t]$ 内出现的事件（质点）数，因此对于 $\{N(t),t\ge0\}$ 来说，一次试验是观察事件数，样本函数是直线或阶梯函数，状态空间是全体自然数的连续参数离散型随机变量。称此过程为*计数过程*。

记 $N(t)-N(t_0)\equiv N(t_0, t)$，表示 $(t_0,t]$ 之间出现的事件数。若出现 $k$ 个事件，即 $\{N(t_0,t)=k\}$ 也是一个事件，其概率记为
$$
P_k(t_0,t)=P\{N(t_0,t)=k\}
$$
假设 $N(t)$ 满足以下条件：

1. $N(t)$ 是独立增量过程。

2. $$
   \forall\epsilon>0\\
   P_1(t,t+\Delta t)=P\{N(t,t+\Delta t)=1\}=\lambda\Delta t+o(\Delta t)
   $$

   $\lambda>0$ 称为过程 $N(t)$ 的强度。

3. $$
   \sum_{j=2}^{\infty}P_j(t,t+\Delta t)=\sum_{j=2}^{\infty}P\{N(t,t+\Delta t)=j\}=o(\Delta t)
   $$

   即在该时间间隔内出现多次事件的概率与出现一次事件的概率相比可以忽略不计。

4. $N(0)=0$，即初始时候不发生事件。

则满足以上条件的 $N(t)$ 称为*强度为 $\lambda$ 的泊松过程*，把事件出现的时刻 $t_1,\dots$ 称为*强度为 $\lambda$ 的泊松流*。

---

以下求出泊松过程的增量的分布律：

首先，$\sum_{k=0}^{\infty}P_k(t_0,t)=1$，即一段时间内发生的事件数的可能性之和必为 $1$。

计算 $0$ 次在 $\Delta t$ 时间内发生的概率
$$
\begin{align*}
P_0(t,t+\Delta t)&=1-P_1(t,t+\Delta t)-\sum_{k=2}^{\infty}P_k(t,t+\Delta t)\\
&=1-\lambda\Delta t+o(\Delta t)
\end{align*}
$$
再确定 $P_0(t_0,t)$ 的概率，先看其很短时间内的增量和
$$
\begin{align*}
P_0(t_0,t+\Delta t)&=P\{N(t_0,t+\Delta t)=0\}\\
&=P\{N(t_0,t)+N(t,t+\Delta t)=0\}\\
&=P\{N(t_0,t)=0,N(t,t+\Delta t)=0\}\\
&=P\{N(t_0,t)=0\}P\{N(t,t+\Delta t)=0\}\qquad(\text{independence})\\
&=P\{N(t_0,t)=0\}(1-\lambda\Delta t+o(\Delta t))\\
&=P_0(t_0,t)(1-\lambda\Delta t+o(\Delta t))
\end{align*}\\
$$
因此确定方程
$$
P_0(t_0,t+\Delta t)-P_0(t_0,t)=-\lambda P_0(t_0,t)\Delta t+o(\Delta t))
$$
两边除以 $\Delta t$ 并且令 $\Delta t\to0$
$$
\frac{dP_0(t_0,t)}{dt}=-\lambda P_0(t_0,t)
$$
解得
$$
\ln\frac{P_0(t_0,t)}{P_0(t_0,t_0)}=-\lambda(t-t_0)
$$
因为 $N(t_0,t_0)=0$，所以 $P_0(t_0,t_0)=1$。代入得到
$$
P_0(t_0,t)=e^{-\lambda(t-t_0)}
$$
对于 $P_k(t_0,t)$ 的概率，也是看其很短时间内的增量和
$$
\begin{align*}
P_k(t_0,t+\Delta t)&=P\{N(t_0,t+\Delta t)=k\}\\
&=P\{N(t_0,t)+N(t,t+\Delta t)=k\}\\
&=\sum_{j=0}^{k}P\{N(t_0,t)=j,N(t,t+\Delta t)=k-j\}\\
&=\sum_{j=0}^{k}P\{N(t_0,t)=j\}P\{N(t,t+\Delta t)=k-j\}\\
&=P\{N(t_0,t)=k-1\}P\{N(t,t+\Delta t)=1\}\\
&\quad+P\{N(t_0,t)=j\}P\{N(t,t+\Delta t)=0\}\\
&=P\{N(t_0,t)=k-1\}[\lambda\Delta t+o(\Delta t)]\\
&\quad+P\{N(t_0,t)=k\}[1-\lambda\Delta t+o(\Delta t)]\\
&=P_{k-1}(t_0,t)[\lambda\Delta t+o(\Delta t)]+P_{k}(t_0,t)[1-\lambda\Delta t+o(\Delta t)]
\end{align*}\\
$$
整理可得微分方程
$$
\frac{dP_{k}(t_0,t)}{dt}+\lambda P_{k}(t_0,t)=\lambda P_{k-1}(t_0,t)
$$
令 $k=1$，加上条件 $P\{N(t_0,t_0)=k\}=0$ 可得到 $P_1(t_0,t)$
$$
\begin{align*}
\frac{dP_{1}(t_0,t)}{dt}&=\lambda[P_{0}(t_0,t)-P_{1}(t_0,t)]\\
\frac{dP_{1}(t_0,t)}{dt}+\lambda P_{1}(t_0,t)&=\lambda e^{-\lambda(t-t_0)}\\
[e^{\lambda t}P_{1}(t_0,t)]'&=e^{\lambda t_0}\\
e^{\lambda t}P_{1}(t_0,t)&=e^{\lambda t_0}(t-t_0)\\
P_{1}(t_0,t)&=(t-t_0)e^{-\lambda(t-t_0)}
\end{align*}
$$
对于一般形式，整理可得
$$
\begin{align*}
[e^{\lambda t}P_{k}(t_0, t)]'&=\lambda e^{\lambda t}P_{k-1}(t_0, t)\\
e^{\lambda t}P_{k}(t_0, t)&=\int_{t_0}^{t}\lambda e^{\lambda t}P_{k-1}(t_0, t)dt
\end{align*}
$$
由归纳法可得
$$
P_{k}(t_0,t)=\frac{[\lambda(t-t_0)]^k}{k!}e^{-\lambda(t-t_0)}
$$

---

因此增量 $N(t_0,t)$ 的概率分布是参数为 $\lambda(t-t_0)$ 的泊松分布。

以下为泊松分布的另一种定义：

1. $N(t)$ 是独立增量过程。
2. $N(t)-N(t_0)\sim\text{Pois}(\lambda(t-t_0)),0\le t_0<t$。
3. $N(0)=0$​。



#### 12.3.1.2 数字特征

$$
\begin{align*}
\mu_N(t)&=\text{E[N(t)]}=\text{E(N(0,t)})=\lambda t\\
\sigma^2_N(t)&=\text{Var}[N(t)]=\text{Var}[N(0,t)]=\lambda t\\
C_{NN}(s,t)&=\lambda\min(s, t)\\
R_{NN}(s,t)&=C_{NN}(s,t)+\mu_N(s)\mu_N(t)=\lambda^2st+\lambda\min(s, t)\\
\end{align*}
$$

如果泊松过程的强度不是一个常数而是随时间的一个函数 $\lambda=\lambda(t),t\ge0$​​，则称泊松过程为**非齐次的**，可得：
$$
P\{N(t)-N(t_0)=k\}=\frac{[\int_{t_0}^{t}\lambda(\tau)d\tau]^ke^{-\int_{t_0}^{t}\lambda(\tau)d\tau}}{k!}\\
\text{E}[N(t)]=\int_{0}^{t}\lambda(\tau)d\tau\\
R_{NN}(s,t)=\int_{0}^{\min(s, t)}\lambda(\tau)d\tau[1+\int_{0}^{\min(s, t)}\lambda(\tau)d\tau]
$$

#### 12.3.1.3 等待时间和点间间距

设质点依次重复出现的时刻为：
$$
\mathbf t_1,\dots,\mathbf t_n,\dots
$$
是一个强度为 $\lambda$​​ 的泊松流。记 $W_n=\mathbf t_n$​​​ ​是一随机变量，表示事件第 $n$ 次出现的等待时间。 注意到事件 $\{W_n>t\}=\{N(t)<n\}$，因此
$$
\begin{align*}
F_{W_n}(t)&=P(W_n\le t)\\
&=1-P(W_n>t)\\
&=1-P(N(t)<n)\\
&=P(N(t)\ge n)\\
&=\begin{cases}
\sum_{k=n}^{\infty}e^{-\lambda t}\frac{(\lambda t)^k}{k!}&t\ge0\\
0&t<0\\
\end{cases}\\
\end{align*}\\
$$

$$
\begin{align*}
f_{W_n}(t)&=\sum_{k=n}^{\infty}[-\lambda e^{-\lambda t}\frac{(\lambda t)^k}{k!}+\lambda e^{-\lambda t}\frac{(\lambda t)^{k-1}}{(k-1)!}]\\
&=\lambda e^{-\lambda t}\sum_{k=n}^{\infty}[-\frac{(\lambda t)^k}{k!}+\frac{(\lambda t)^{k-1}}{(k-1)!}]\\
&=\lambda e^{-\lambda t}\frac{(\lambda t)^{n-1}}{(n-1)!}\\
&=\frac{1}{\Gamma(n)}(\lambda t)^ne^{-\lambda t}\frac{1}{t}
\end{align*}
$$

因此<u>**泊松过程的等待时间 $W_n$​​​ 满足 $\text{Gamma}(n,\lambda)$​​​ 分布**</u>。

记 $T_i=W_i-W_{i-1},T_1=W_1$​​​，称为相继出现的第 $i-1$​​ 个和第 $i$​​​ 个质点的点间间距。
$$
f_{T_{1}}(t)=f_{W_{1}}(t)=\lambda e^{-\lambda t}
$$

计算 $W_{i-1}=w$ 的条件下​ $T_i$​ 的概率分布：
$$
\begin{align*}
F_{T_i|W_{i-1}}(t)&=P(T_i\le t|W_{i-1}=w)\\
&=P(N(w,w+t)\ge 1)\\
&=1-P(N(w,w+t)<1)\\
&=1-P(N(w,w+t)=0)\\
&=1-P_0(w,w+t)\\
&=\begin{cases}
1-e^{-\lambda t}&t>0\\
0&t\le0\\
\end{cases}\\
f_{T_i|W_{i-1}}(t)&=\begin{cases}
\lambda e^{-\lambda t}&t>0\\
0&t\le0\\
\end{cases}
\end{align*}
$$
将条件概率转换为联合分布的概率：
$$
\begin{align*}
f_{T_i,W_{i-1}}(t,w)&=\begin{cases}
\lambda e^{-\lambda t}f_{W_{i-1}}(w)&t>0\\
0&t\le0\\
\end{cases}\\
f_{T_i}(t)&=\int_0^{+\infty}\lambda e^{-\lambda t}f_{W_{i-1}}(w)dw\\
&=\lambda e^{-\lambda t}\int_0^{+\infty}f_{W_{i-1}}(w)dw\\
&=\begin{cases}
\lambda e^{-\lambda t}&t>0\\
0&t\le0\\
\end{cases}
\end{align*}
$$
因此<u>**第 $i-1$ 个和第 $i$​ 个质点的点间间距满足 $\text{Expo}(\lambda)$​​ 分布，且相互独立**</u>。

> 1. 强度为 $\lambda$ 的泊松过程的点间间距是相互独立的随机变量且服从同一个指数分布。
> 2. 如果任意相继出现的两个质点的点间间距是相互独立的，且服从同一个指数分布，则质点流构成了强度为 $\lambda$ 的泊松过程。

### 12.3.2 维纳过程

研究布朗运动。

#### 12.3.2.1 推导

设 $W(t)$ 是微粒从 $0$ 到 $t$ 时刻的位移的横坐标（或纵坐标），且 $W(0)=0$。微粒在一段时间内的位移可以看作是许多小位移的矢量和。因此按照中心极限定理，可以把 $W(t_2)-W(t_1)$ 看作是正态分布。因为微粒的运动特性，可以认为在不重叠的时间段内，微粒的位移 $W(t)$​ 具有独立的增量。微粒在一段时间内的位移的概率分布只依赖于时间段的长度，与起始位置和起始时刻无关，可认为增量平稳。

因此，假设 $\{W(t),t\ge0\}$ 满足以下条件：

1. 具有独立增量。

2. $$
   \forall t>s\ge0,W(t)-W(s)\sim\mathcal N(0, \sigma^2(t-s))
   $$

3. $W(0)=0$

则称该随机过程是维纳过程。

#### 12.3.2.2 数字特征

维纳过程增量的分布只和时间差有关，因此它是齐次的。

对于任意 $n\ge1$​ 和任意 $t_1,t_2,\dots,t_n\in T$​，记 $W(t_k)=\sum_{i=1}^{k}[W(t_i)-W(t_{i-1})]$​​，则 $(W(t_1),\dots,W(t_n))$ 是 $n$ 维正态分布的随机变量，即 $W(t)$ 是正态过程。
$$
\begin{align*}
\mu_W(t)&=0\\
\Psi_W(t)&=\sigma^2t\\
\sigma_W^2(t)&=\sigma^2t\\
R_{WW}(t_1,t_2)&=\sigma^2\min(s, t)\\
C_{WW}(t_1,t_2)&=\sigma^2\min(s, t)\\
\end{align*}
$$

---

## 习题

### 1

抛硬币定义一个随机过程
$$
X(t)=\begin{cases}\cos\pi t&\text{it is head}\\2t&\text{it is tail}\end{cases}\quad t\in(-\infty,+\infty)
$$
$P(H)=P(T)=1/2$

$X(t)$ 的一维分布函数 $F(x;1/2),F(x;1)$。

> $$
> \begin{align*}
> F(x;1/2)&=P\{X(1/2)\le x\}\\
> &=P\{\cos\pi/2\le x\}P\{X(t)=\cos\pi t\}+P\{1\le x\}P\{X(t)=2t\}\\
> &=\begin{cases}
> 0&x\le0\\
> 1/2&0<x\le1\\
> 1&x>1
> \end{cases}\\
> F(x;1)&=P\{X(1)\le x\}\\
> &=P\{\cos\pi\le x\}P\{X(t)=\cos\pi t\}+P\{2\le x\}P\{X(t)=2t\}\\
> &=\begin{cases}
> 0&x\le-1\\
> 1/2&-1<x\le2\\
> 1&x>2
> \end{cases}
> \end{align*}
> $$

$X(t)$ 的二维分布函数 $F(x_1,x_2;1/2,1)$。

> $$
> \begin{align*}
> F(x_1,x_2;1/2,1)&=P\{X(1/2)\le x_1,X(1)\le x_2\}\\
> &=\begin{bmatrix}
> &x_1\le0&0<x_1\le1&x_1>1\\
> x_2\le-1&0&0&0\\
> -1<x_2\le2&0&1/4&1/2\\
> x_2>2&0&1/2&1
> \end{bmatrix}
> \end{align*}
> $$

### 2

给定一个随机过程 $\{X(t),t\in T\}$，$x\in\mathbb R$，定义另一个随机过程
$$
Y(t)=\begin{cases}1&X(t)\le x\\0&X(t)>x\end{cases}
$$
求 $Y(t)$ 的均值函数和自相关函数。
$$
\begin{align*}
\mu_Y(t)&=\text{E}(Y(t))\\
&=P\{X(t)\le x\}\\
&=F(x,t)\\
R_{YY}(t_1, t_2)&=\text{E}(Y(t_1)Y(t_2))\\
&=P\{X(t_1)\le x\}P\{X(t_2)\le x\}\\
&=F(x,x;t_1,t_2)
\end{align*}
$$

### 3

设随机过程 $X(t)=e^{-At},t>0$，$A\sim\text{U}(0,a)$，求 $X(t)$ 的均值函数和自相关函数。

> $$
> \begin{align*}
> \mu_X(t)&=\text{E}(X(t))\\
> &=\text{E}(e^{-At})\\
> &=\int_0^ae^{-At}\frac{1}{a}dA\\
> &=-\frac{1}{at}e^{-At}|_0^a\\
> &=\frac{1-e^{-at}}{at}\qquad(t>0)\\
> R_{XX}(t_1, t_2)&=\text{E}(X(t_1)X(t_2))\\
> &=\text{E}(e^{-At_1}e^{-At_2})\\
> &=\text{E}(e^{-A(t_1+t_2)})\\
> &=\frac{1-e^{-a(t_1+t_2)}}{a(t_1+t_2)}\qquad(t_1,t_2>0)\\
> \end{align*}
> $$

### 4

设随机过程 $X(t)\equiv X$，$\text{E}[X)=a,\text{D}(X)=\sigma^2(\sigma>0)$，求 $X(t)$ 的均值函数和自相关函数。

> $$
> \begin{align*}
> \mu_X(t)&=\text{E}(X(t))\\
> &=\text{E}(X)\\
> &=a\\
> C_{XX}(t_1, t_2)&=\text{E}((X(t_1)-\mu_X(t_1))(X(t_2)-\mu_X(t_2)))\\
> &=\text{E}((X-a)^2)\\
> &=\sigma^2\\
> \end{align*}
> $$

### 5

已知随机过程 $\{X(t),t\in T\}$ 的均值函数和自协方差函数，$\varphi(t)$ 是普通函数，求 $Y(t)=X(t)+\varphi(t),t\in T$ 的均值函数和自协方差函数。

> $$
> \begin{align*}
> \mu_Y(t)&=\text{E}(Y(t))\\
> &=\text{E}(X(t)+\varphi(t))\\
> &=\mu_X(t)+\varphi(t)\\
> C_{YY}(t_1, t_2)&=\text{E}((Y(t_1)-\mu_Y(t_1))(Y(t_2)-\mu_Y(t_2)))\\
> &=\text{E}((X(t_1)-\mu_X(t))(X(t_2)-\mu_X(t)))\\
> &=C_{XX}(t_1, t_2)\\
> \end{align*}
> $$

### 6

给定一个随机过程 $\{X(t),t\in T\}$ 和常数 $a$，用 $X(t)$ 的自相关函数表示随机过程 $Y(t)=X(t+a)-X(t)$ 的自相关函数。

> $$
> \begin{align*}
> R_{YY}(t_1, t_2)&=\text{E}(Y(t_1)Y(t_2))\\
> &=\text{E}((X(t_1+a)-X(t_1))(X(t_2+a)-X(t_2)))\\
> &=R_{XX}(t_1+a, t_2+a)-R_{XX}(t_1, t_2+a)\\
> &\quad-R_{XX}(t_1+a, t_2)+R_{XX}(t_1, t_2)\\
> \end{align*}
> $$

### 7

设 $Z(t)=X+Yt,t\in(-\infty,+\infty)$，若 $(X,Y)$ 的协方差矩阵为
$$
\begin{bmatrix}
\sigma_1^2&\rho\sigma_1\sigma_2\\
\rho\sigma_1\sigma_2&\sigma_2^2
\end{bmatrix}
$$
求 $Z(t)$ 的协方差函数。

> $$
> \begin{align*}
> C_{YY}(t_1, t_2)&=\text{E}((Z(t_1)-\mu_Z(t_1))(Z(t_2)-\mu_Z(t_2)))\\
> &=\text{E}((X+Yt_1-\text{E}(X)-\text{E}(Y)t_1)\\
> &\qquad(X+Yt_2-\text{E}(X)-\text{E}(Y)t_2))\\
> &=\text{E}((X-\text{E}(X)+Yt_1-\text{E}(Y)t_1)\\
> &\qquad(X-\text{E}(X)+Yt_2-\text{E}(Y)t_2))\\
> &=\sigma_1^2+(t_1+t_2)\rho\sigma_1\sigma_2+t_1t_2\sigma_2^2
> \end{align*}
> $$

### 8

设 $X(t)=A+Bt,t\in(-\infty,+\infty)$，若 $A,B\sim\mathcal{N}(0,\sigma^2)$ 且相互独立，证明 $X(t)$ 是正态过程且求出自相关函数和自协方差函数。

> 对于任意 $n\ge1$ 和任意 $t_1,t_2,\dots,t_n\in T$，$X(t_i)$ 是 $A,B$ 不同的线性组合，因此$(X(t_1),\dots,X(t_n))$ 服从 $n$ 维正态分布，$X(t)$ 是正态过程。
> $$
> \begin{align*}
> R_{XX}(t_1, t_2)&=\text{E}(X(t_1)X(t_2))\\
> &=\text{E}((A+Bt_1)(A+Bt_2))\\
> &=\text{E}(A^2+AB(t_1+t_2)+B^2t_1t_2)\\
> &=\sigma^2(1+t_1t_2)\\
> C_{XX}(t_1, t_2)&=\text{E}((X(t_1)-\mu_X(t_1))(X(t_2)-\mu_X(t_2)))\\
> &=\text{E}((A+Bt_1)(A+Bt_2))\\
> &=\text{E}(X-\text{E}(X)+Yt_1-\text{E}(Y)t_1)\\
> &=\sigma^2(1+t_1t_2)\\
> \end{align*}
> $$

### 9

设随机过程 $X(t)$ 和 $Y(t)$ 不相关，用它们的均值函数和协方差函数表示随机过程
$$
Z(t)=a(t)X(t)+b(t)Y(t)+c(t)
$$
的均值函数和自协方差函数，$a(t),b(t),c(t)$ 是一般的函数。

> $$
> \begin{align*}
> \mu_Z(t)&=\text{E}(Z(t))\\
> &=(a(t)X(t)+b(t)Y(t)+c(t))\\
> &=a(t)\text{E}(X(t))+b(t)\text{E}(Y(t))+c(t)\\
> &=a(t)\mu_X(t)+b(t)\mu_Y(t)+c(t)\\
> C_{ZZ}(t_1, t_2)&=\text{E}((a(t_1)[X(t_1)-\mu_X(t_1)]+b(t_1)[Y(t_1)-\mu_Y(t_1)])\\
> &\qquad(a(t_2)[X(t_2)-\mu_X(t_2)]+b(t_2)[Y(t_2)-\mu_Y(t_2)]))\\
> &=a(t_1)a(t_2)C_{XX}(t_1, t_2)+b(t_1)a(t_2)C_{XY}(t_1, t_2)\\
> &\qquad+a(t_1)b(t_2)C_{YX}(t_1, t_2)+b(t_1)b(t_2)C_{YY}(t_1, t_2)\\
> \end{align*}
> $$

### 10

设 $X(t)$ 和 $Y(t)$ 是相互独立的，强度为 $\lambda$ 和 $\mu$ 的泊松过程，证明 $S(t)=X(t)+Y(t)$ 是强度为 $\lambda+\mu$​ 泊松过程。

> 1. $S(t)$ 是独立增量过程
>
> 2. $$
>    \begin{align*}
>    S(t)-S(t_0)&=X(t)+Y(t)-X(t_0)-Y(t_0)\\
>    &=X(t)-X(t_0)+Y(t)-Y(t_0)\\
>    P_k\{S(t_0,t)\}&=\sum_{j=0}^{k}P_j\{X(t_0,t)\}P_{k-j}\{Y(t_0,t)\}\\
>    k=0&: P_0\{X(t_0,t)\}P_0\{Y(t_0,t)\}\\
>    &=[1-\lambda\Delta t+o(\Delta t)][1-\mu\Delta t+o(\Delta t)]\\
>    &=1-\lambda\Delta t-\lambda\Delta t+o(\Delta t)\\
>    k=1&: P_0\{X(t_0,t)\}P_1\{Y(t_0,t)\}\\
>    &\quad+P_1\{X(t_0,t)\}P_0\{Y(t_0,t)\}\\
>    &=[1-\lambda\Delta t+o(\Delta t)][\mu\Delta t+o(\Delta t)]\\
>    &\quad+[\lambda\Delta t+o(\Delta t)][1-\mu\Delta t+o(\Delta t)]\\
>    &=\lambda\Delta t+\mu\Delta t+o(\Delta t)\\
>    k>2 &: o(\Delta t)\\
>    \end{align*}
>    $$
>
> 3. $S(0)=0$


### 11

设 $W(t)$​ 是以 $\sigma^2$​ 为参数的维纳过程，求 $W(t)+At,W(t)+Xt,aW(t/a^2)$​ 的协方差函数

> $$
> \begin{align*}
> C_{XX}(s,t)&=\text{E}[(W(s)+As-\text{E}[W(s)+As])\\
> &\quad(W(t)+At-\text{E}[W(t)+At])]\\
> &=\text{E}[W(s)W(t)]\\
> &=\sigma^2\min(s,t)
> \end{align*}
> $$
>
> $$
> \begin{align*}
> C_{XX}(s,t)&=\text{E}[(W(s)+Xs-\text{E}[W(s)+Xs])\\
> &\quad(W(t)+Xt-\text{E}[W(t)+Xt])]\\
> &=\text{E}[(W(s)+Xs)(W(t)+Xt)]\\
> &=\text{E}[W(s)W(t)+XsW(t)+XtW(s)+X^2st]\\
> &=\sigma^2\min(s,t)+st
> \end{align*}
> $$
>
> $$
> \begin{align*}
> C_{XX}(s,t)&=\text{E}[(aW(s/a^2)-\text{E}[aW(s/a^2)])\\
> &\quad(aW(t/a^2)-\text{E}[aW(t/a^2)])]\\
> &=a^2\text{E}[W(s/a^2)W(t/a^2)]\\
> &=a^2/a^2\text{E}[W(s)W(t)]\\
> &=\sigma^2\min(s,t)
> \end{align*}
> $$
>
> 

