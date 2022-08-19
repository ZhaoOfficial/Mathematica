# Chapter 5 Big Number Theorem and Central Limit Theorem

## 5.1 大数定律

### 5.1.1 弱大数定律

设 $X_1,\dots,X_n$ 是独立同分布的随机变量，且 $E(X_k)=\mu,\text{Var}(X_k)=\sigma^2$，则对于任意的 $\epsilon>0$，
$$
\lim_{n\to\infty}P\left\{\left|\frac{1}{n}\sum_{k=1}^{n}-\mu\right|<\epsilon\right\}=1
$$

<blockquote style="border-left: 5px solid #4545aa; border-radius: 3px 0 0 3px; padding: 10px 15px; background-color: rgba(70, 70, 188, 0.1)">
    Proof
</blockquote>

$$
E\left(\frac{1}{n}\sum_{k=1}^{n}X_k\right)=\frac{1}{n}\sum_{k=1}^{n}E(X_k)=\frac{1}{n}(n\mu)=\mu
$$

$$
\text{Var}(\frac{1}{n}\sum_{k=1}^{n}X_k)=\frac{1}{n^2}\sum_{k=1}^{n}\text{Var}(X_k)=\frac{1}{n^2}n\sigma^2=\frac{\sigma^2}{n}
$$

由 Chebyshev 不等式可以得到：
$$
1\ge P\left\{\left|\frac{1}{n}\sum_{k=1}^{n}-\mu\right|<\epsilon\right\}\ge1-\frac{\sigma^2}{n\epsilon^2}
$$
因此：
$$
\lim_{n\to\infty}P\left\{\left|\frac{1}{n}\sum_{k=1}^{n}-\mu\right|<\epsilon\right\}=1
$$
我们称：
$$
\frac{1}{n}\sum_{k=1}^{n}X_k
$$
依概率收敛于 $\mu$.

## 5.1.2 Central Limit Theorem 中心极限定理

设 $X_1,\dots,X_n$ 是独立同分布的随机变量，且 $E(X_k)=\mu,\text{Var}(X_k)=\sigma^2$，则随机变量之和 $\displaystyle{\sum_{k=1}^{n}X_k}$ 的标准化变量为：
$$
Y_n=\frac{\sum_{k=1}^{n}X_k-E(\sum_{k=1}^{n}X_k)}{\sqrt{\text{Var}(\sum_{i=1}^{k}X_k)}}=\frac{\sum_{k=1}^{n}X_k-n\mu}{\sqrt{n}\sigma}=\frac{\bar{X}-\mu}{\sigma/\sqrt{n}}
$$
其分布函数 $F_n(x)$ 对于任意 $x$ 都满足：
$$
\lim_{n\to\infty}F_n(x)=\lim_{n\to\infty}P\left\{Y_n\le x\right\}=\int_{-\infty}^{x}\frac{1}{\sqrt{2\pi}}e^{-t^2/2}dt=\Phi(x)
$$

<blockquote style="border-left: 5px solid #4545aa; border-radius: 3px 0 0 3px; padding: 10px 15px; background-color: rgba(70, 70, 188, 0.1)">
    Proof
</blockquote>

假设 $X_k$ 的 MGF 都存在，则令 $M(t)=E(e^{tX_k})$，则：
$$
E(e^{t(X_1+\dots+X_n-n\mu)/\sigma\sqrt{n}})=\left(M\left(\frac{t}{\sigma\sqrt{n}}\right)/e^{\sqrt{n}t\mu/\sigma}\right)^n
$$
令 $y=1/\sqrt{n}$，那么：
$$
\begin{align*}
\lim_{n\to\infty}n\log M\left(\frac{t}{\sigma\sqrt{n}}\right)-\frac{\sqrt{n}t\mu}{\sigma}&=\lim_{y\to0}\frac{\sigma\log M(yt/\sigma)-yt\mu}{y^2\sigma}\\
&=\lim_{y\to0}\frac{tM'(yt/\sigma)-t\mu}{2\sigma yM(yt)}\\
&=\frac{t}{2\sigma}\lim_{y\to0}\frac{M'(yt/\sigma)-\mu}{yM(yt/\sigma)}\\
&=\frac{t}{2\sigma}\lim_{y\to0}(t/\sigma)M''(yt/\sigma)\\
&=\frac{t^2}{2}\\
\end{align*}
$$
因此 $Y_n$ 的 MGF 为 $\exp(t^2/2)$，是 $\mathcal{N}(0,1)$ 的 MGF。















