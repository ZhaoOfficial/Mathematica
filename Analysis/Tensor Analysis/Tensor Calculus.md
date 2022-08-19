# Tensor Calculus

## 0 Introduction

## 1 Multi-variable Calculus

Multi-variable chain rule:
$$
\frac{\mathrm{d}z}{\mathrm{d}t}=\frac{\partial{z}}{\partial{x^i}}\frac{\mathrm{d}x^i}{\mathrm{d}t}
$$
Multi-variable differential:
$$
\mathrm{d}z=\frac{\partial{z}}{\partial{x^i}}\mathrm{d}x^i
$$
Length of a curve
$$
\left\|\frac{\mathrm{d}z}{\mathrm{d}t}\right\|=\sqrt{\frac{\mathrm{d}x^i}{\mathrm{d}t}\frac{\mathrm{d}x^j}{\mathrm{d}t}\frac{\partial{z}}{\partial{x^i}}\frac{\partial{z}}{\partial{x^j}}}
$$

## 2 Cartesian Polar Coordinates

Polar to Cartesian
$$
x=r\cos\theta\\
y=r\sin\theta
$$
Cartesian to Polar
$$
r=\sqrt{x^2+y^2}\\
\theta=\arctan(\frac{y}{x})
$$

### Derivative are Vectors

$$
\frac{\partial\mathbf{R}}{\partial{x}}=\lim_{h\to0}\frac{\mathbf{R}(x+h,y)-\mathbf{R}(x,y)}{h}=\mathbf{e}_x\\
\frac{\partial\mathbf{R}}{\partial{y}}=\lim_{h\to0}\frac{\mathbf{R}(x,y+h)-\mathbf{R}(x,y)}{h}=\mathbf{e}_y\\
\frac{\partial\mathbf{R}}{\partial{r}}=\lim_{h\to0}\frac{\mathbf{R}(r+h,\theta)-\mathbf{R}(r,\theta)}{h}=\mathbf{e}_r\\
\frac{\partial\mathbf{R}}{\partial{\theta}}=\lim_{h\to0}\frac{\mathbf{R}(r,\theta+h)-\mathbf{R}(r,\theta)}{h}=\mathbf{e}_{\theta}\\
$$

In Cartesian coordinate, the basis vectors are constant. While in Polar coordinate, the basis change both length and direction.

## 3 Jacobian

Transform from old basis to n.

Polar to Cartesian
$$
\begin{align*}
\mathbf{e}_r&=\frac{\partial\mathbf{R}}{\partial{r}}=\frac{\partial\mathbf{R}}{\partial{x}}\frac{\partial{x}}{\partial{r}}+\frac{\partial\mathbf{R}}{\partial{y}}\frac{\partial{y}}{\partial{r}}\\
&=\cos\theta\frac{\partial\mathbf{R}}{\partial{x}}+\sin\theta\frac{\partial\mathbf{R}}{\partial{y}}=\cos\theta\mathbf{e}_x+\sin\theta\mathbf{e}_y\\
&=\frac{x}{r}\mathbf{e}_x+\frac{y}{r}\mathbf{e}_y\\
\mathbf{e}_\theta&=\frac{\partial\mathbf{R}}{\partial{\theta}}=\frac{\partial\mathbf{R}}{\partial{x}}\frac{\partial{x}}{\partial{\theta}}+\frac{\partial\mathbf{R}}{\partial{y}}\frac{\partial{y}}{\partial{\theta}}\\
&=-r\sin\theta\frac{\partial\mathbf{R}}{\partial{x}}+r\cos\theta\frac{\partial\mathbf{R}}{\partial{y}}=-r\sin\theta\mathbf{e}_x+r\cos\theta\mathbf{e}_y\\
&=-y\mathbf{e}_x+x\mathbf{e}_y\\
\end{align*}
$$

$$
{\color{red}F=\begin{bmatrix}\dfrac{\partial{x}}{\partial{r}}&\dfrac{\partial{x}}{\partial{\theta}}\\\dfrac{\partial{y}}{\partial{r}}&\dfrac{\partial{y}}{\partial{\theta}}\end{bmatrix}}=
\begin{bmatrix}\dfrac{x}{r}&-y\\\dfrac{y}{r}&x\end{bmatrix}
$$

Cartesian to Polar
$$
{\color{red}B=\begin{bmatrix}\dfrac{\partial{r}}{\partial{x}}&\dfrac{\partial{r}}{\partial{y}}\\\dfrac{\partial{\theta}}{\partial{x}}&\dfrac{\partial{\theta}}{\partial{y}}\end{bmatrix}}=
\begin{bmatrix}\dfrac{x}{r}&\dfrac{y}{r}\\-\dfrac{y}{r^2}&\dfrac{x}{r^2}\end{bmatrix}
$$
The forward tensor is the Jacobian matrix. The backward tensor is the inverse of the Jacobian matrix.

## 4 Derivative are Vectors (Covariant)

$$
\color{red}\mathbf v=v^i\mathbf e_i=\tilde{v}^i\tilde{\mathbf e}_i\\
\color{red}\frac{\partial}{\partial \lambda}=\frac{\partial c^i}{\partial \lambda}\frac{\partial}{\partial c^i}=\frac{\partial p^i}{\partial \lambda}\frac{\partial}{\partial p^i}
$$

Jacobian matrix transform old basis to new basis.

## 5 Derivative Transform Rules (Contravariant)

Transform of vector component.
$$
\frac{\partial{\mathbf{R}}}{\partial{\lambda}}=\frac{\partial{c^i}}{\partial{\lambda}}\frac{\partial{\mathbf{R}}}{\partial{c^i}}=\frac{\partial{c^i}}{\partial{\lambda}}\left(\frac{\partial{p^j}}{\partial{c^i}}\frac{\partial\mathbf R}{\partial{p^j}}\right)=\left(\frac{\partial{c^i}}{\partial{\lambda}}\frac{\partial{p^j}}{\partial{c^i}}\right)\frac{\partial\mathbf R}{\partial{p^j}}
$$

$$
\color{red}\tilde{v}^i=B^i_jv^j\\
\color{red}\frac{\partial p^i}{\partial \lambda}=\frac{\partial p^i}{\partial c^j}\frac{\partial c^j}{\partial \lambda}
$$

## 6 Differential Forms are Covectors

Re-interpret the $\mathrm{d}$ symbol: it maps from a scalar field $f$ to **a covector field $\mathrm{d}f$**.

Or maps from a function to its level set.

We call scalar field **0-form** and covector field **1-form**.

$\mathrm{d}f(v)$ is the directional derivative of $f$ at $v$.

## 7 Covector Field Components

$$
\mathrm{d}f\left(\frac{\partial}{\partial{x}}\right)=\frac{\partial{f}}{\partial{x}}\\
\mathrm{d}f\left(\frac{\partial}{\partial{y}}\right)=\frac{\partial{f}}{\partial{y}}
$$

Since:
$$
\begin{align*}
\mathrm{d}x\left(\frac{\partial}{\partial{x}}\right)&=\frac{\partial{x}}{\partial{x}}=1&\mathrm{d}x\left(\frac{\partial}{\partial{y}}\right)&=\frac{\partial{x}}{\partial{y}}=0\\
\mathrm{d}y\left(\frac{\partial}{\partial{x}}\right)&=\frac{\partial{y}}{\partial{x}}=0&\mathrm{d}y\left(\frac{\partial}{\partial{y}}\right)&=\frac{\partial{y}}{\partial{y}}=1\\
\end{align*}
$$
Then $\mathrm{d}x,\mathrm{d}y$ are the basis of covector field.
$$
\color{red}\mathrm{d}f=\frac{\partial{f}}{\partial{c}^i}\mathrm{d}c^i=\frac{\partial{f}}{\partial{p}^i}\mathrm{d}p^i
$$

## 8 Covector Field Transformation Rules (Contravariant)

Substitute $f$ with $r$ and $\theta$, we can transform old covector basis to new covector basis using inverse Jacobian matrix: 
$$
\color{red}\mathrm{d}\mathbf{p}^i=\frac{\partial{p}^i}{\partial{c}^j}\mathrm{d}\mathbf{c}^j
$$












