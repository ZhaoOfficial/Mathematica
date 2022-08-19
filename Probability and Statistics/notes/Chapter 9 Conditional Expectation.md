# Chapter 9 Conditional \mathrm{E}xpectation

## 9.3 Properties of conditional expectation

### 9.3.10 Linear regression

The linear regression model uses a single explanatory variable $X$ to predict a response variable $Y$ , and it assumes that the conditional expectation of $Y$ is linear in $X$:
$$
\mathrm{E}(Y|X)=a+bX
$$
This is an equivalent way to express this is to write:
$$
Y=a+bX+\epsilon
$$
where $\epsilon$ is an r.v. (called the error) with $\mathrm{E}(\epsilon|X)=0$ since:
$$
\mathrm{E}(Y|X)=\mathrm{E}(a+bX+\epsilon|X)=\mathrm{E}(a|X)+\mathrm{E}(bX|X)+\mathrm{E}(\epsilon|X)=a+bX
$$
and conversely, define $\epsilon=Y-(a+bX)$:
$$
\mathrm{E}(\epsilon|X)=\mathrm{E}(Y|X)-\mathrm{E}(a+bX|X)=\mathrm{E}(Y|X)-(a+bX)=0
$$
Now we are going to solve $a$ and $b$.

By Adam's law, taking the expectation of both sides gives:
$$
\mathrm{E}(Y)=a+b\mathrm{E}(X)
$$
and:
$$
\begin{align*}
\mathrm{Cov}(X,Y)&=\mathrm{Cov}(X,a+bX+\epsilon)\\
&=\mathrm{Cov}(X,a)+\mathrm{Cov}(X,bX)+\mathrm{Cov}(X,\epsilon)\\
&=0+b\mathrm{Var}(X)+\mathrm{E}(X\epsilon)-\mathrm{E}(X)\mathrm{E}(\epsilon)
\end{align*}
$$
since:
$$
\begin{align*}
\mathrm{E}(X\epsilon)&=\mathrm{E}(\mathrm{E}(\epsilon X|X))=0\\
\mathrm{E}(X)\mathrm{E}(\epsilon)&=\mathrm{E}(X)\mathrm{E}(\mathrm{E}(\epsilon|X))=0
\end{align*}
$$
Then:
$$
\begin{align*}
a&=\mathrm{E}(Y)-\frac{\mathrm{Cov}(X,Y)}{\mathrm{Var}(X)}\cdot\mathrm{E}(X)\\
b&=\frac{\mathrm{Cov}(X,Y)}{\mathrm{Var}(X)}
\end{align*}
$$
Then:
$$
Y=\mathrm{E}(Y)+\frac{\mathrm{Cov}(X,Y)}{\mathrm{Var}(X)}(X-\mathrm{E}(X))
$$




















