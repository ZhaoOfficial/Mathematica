# Monte Carlo Statistical Methods

## Monte Carlo Methods

计算积分的蒙特卡罗方法是考虑 $N$ 个样本来估计积分的值。
The Monte Carlo approach to computing the integral is to consider $N$ samples to estimate the value of the integral.

假设要计算一个积分：
$$
\int_{a}^{b}f(x)dx
$$
我们将 $f(x)$ 分解为某个函数 $g(x)$ 和一个定义在 $[a,b]$ 上的概率密度函数 $p(x)$ 的乘积，因此：
$$
\int_{a}^{b}f(x)dx=\int_{a}^{b}g(x)p(x)dx=E_{p}[g(x)]=E_{p}[\frac{f(x)}{p(x)}]
$$
这样，原积分就等于 $g(x)$ 在 $p(x)$ 上分布的期望。通过采样均值，我们可以近似这个期望，得到积分的值：
$$
\int_{a}^{b}f(x)dx=E_{p}\left[\frac{f(x)}{p(x)}\right]\approx\frac{1}{N}\sum_{i=1}^{N}\frac{f(x_i)}{p(x_i)}
$$
我们把
$$
I=\frac{1}{N}\sum_{i=1}^{N}\frac{f(x_i)}{p(x_i)}
$$
称为 $f(x)$ 的一个估计。

Monte Carlo 积分的主要优势之一是它可以无缝扩展到多个维度。
One of the main strengths of Monte Carlo integration is that it can be extended seamlessly to multiple dimensions.
$$
\begin{align}
I&=\iint f(x,y)dxdy\\
\lang I\rang&=\frac{1}{N}\sum_{i=1}^{N}\frac{f(x_i,y_i)}{p(x_i,y_i)}
\end{align}
$$

## Sampling: Simulation of Random Variables

### Inverse Transform Method

给定一个 $\text{Unif}(0, 1)$ 随机变量，我们可以构造一个任意连续分布的随机变量。
Given a $\text{Unif}(0, 1)$ random variable, we can construct an random variable with any continuous distrubution we want.

相反，给定一个任意连续分布的随机变量，我们可以创建一个 $\text{Unif}(0, 1)$ 随机变量。
Conversely, given an random variable with an arbitary continuous distribution, we can create a $\text{Unif}(0, 1)$ random variable. 

<blockquote style="border-left: 5px solid #42b983; border-radius: 3px 0 0 3px; padding: 10px 15px; background-color: rgba(66, 185, 131, 0.1)">
    Theorem
</blockquote>

令 $F$ 是一个连续函数并在分布的支持域中严格递增的累积分布函数。这确保了反函数 $F^{-1}$ 作为从 $(0, 1)$ 到 $\mathbb R$ 的函数的存在性。
Let $F$ be a CDF which is a continuous function and strictly increasing on the support of the distribution. This ensures that the inverse function $F^{-1}$ exists, as a function from $(0, 1)$ to $\mathbb R$.

Let $U\sim\text{Unif}(0, 1)$ and $X=F^{-1}(U)$. Then $X$ us an random variable with CDF $F$.

Let $X$ be an random variable with CDF $F$. Then $F(X)\sim\text{Unif}(0, 1)$.

<blockquote style="border-left: 5px solid #4545aa; border-radius: 3px 0 0 3px; padding: 10px 15px; background-color: rgba(70, 70, 188, 0.1)">
    Proof
</blockquote>

$$
P(X\le x)=P(F^{-1}(U)\le x)=P(U\le F(x))=F(x)
$$

Then the CDF of $X$ is $F$.

Let $Y=F(X)$, then:
$$
P(Y\le y)=P(F(X)\le y)=P(X\le F^{-1}(y))=F(F^{-1}(y))=y
$$
Then $F(X)\sim\text{Unif}(0, 1)$.

```python
u = random(0, 1)
x = F_inv(u)
```

### Acceptance-Rejection Method

假设可以从 PDF 为 $g$ 的分布函数中（相对容易地）生成样本，如何从 PDF 为 $f$ 的分布函数中模拟生成样本？
Suppose one can generate samples (relatively easily) from PDF $g$, how can random samples be simulated from PDF $f$?

<blockquote style="border-left: 5px solid #42b983; border-radius: 3px 0 0 3px; padding: 10px 15px; background-color: rgba(66, 185, 131, 0.1)">
    Theorem
</blockquote>

The random variable generated by the Acceptance-Rejection method has the desired PDF $f$.

The number of iterations of the algorithm that are needed is a first-success random variable with mean $c\ge1$.

<blockquote style="border-left: 5px solid #4545aa; border-radius: 3px 0 0 3px; padding: 10px 15px; background-color: rgba(70, 70, 188, 0.1)">
    Proof
</blockquote>

Let $c$ be
$$
c\ge\sup_{y}\frac{f(y)}{g(y)}
$$
Let $A$ be the event that:
$$
u\le\frac{f(y)}{cg(y)}
$$
Then the PDF of $X$ is:
$$
f_{X}(x)=f_{Y}(y|A)=\frac{P_{A|Y}(A|Y=y)}{P(A)}f_Y(y)
$$
Since $U$ and $Y$ are independent
$$
P_{A|Y}(A|Y=y)=P\left(u\le\frac{f(y)}{cg(y)}|Y=y\right)=P\left(u\le\frac{f(y)}{cg(y)}\right)=\frac{f(y)}{cg(y)}
$$
And 
$$
P(A)=\int P_{A|Y}(A|Y=y)f_Y(y)=\frac{1}{c}\int f(y)dy=\frac{1}{c}
$$
Then $f_{X}(x)=f(x)$.

The number of iteration follows First Success distribution with parameter $1/c$, then its expectation is $c$.

```python
while True:
    Y = g()
    u = random(0, 1)
    if u <= f(y) / (c * g(y)):
        x = y
        break
```

### Importance Sampling