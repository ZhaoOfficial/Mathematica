# Chapter 1 Introduction: Vector and Tensors

The first order tensor is vector. The Cartesian components of vector $\mathbf v$ is $(v_x,v_y,v_z)$. The Cartesian components of $\mathbf v$ may be referred to as the components of $\mathbf v$ relative to the standard Cartesian basis. 
$$
\mathbf v = v_x\mathbf e_x + v_y\mathbf e_y + v_z\mathbf e_z
$$
The second order tensor is matrix.
$$
\begin{align*}
\mathbf T\mathbf v&=\mathbf T(v_x\mathbf e_x + v_y\mathbf e_y + v_z\mathbf e_z)\\
&=v_x\mathbf T\mathbf e_x + v_y\mathbf T\mathbf e_y + v_z\mathbf T\mathbf e_z
\end{align*}
$$
Then 
$$
\mathbf T\mathbf e_x=T_{xx}\mathbf e_x+T_{yx}\mathbf e_y+T_{zx}\mathbf e_z\\
\mathbf T\mathbf e_y=T_{xy}\mathbf e_x+T_{yy}\mathbf e_y+T_{zy}\mathbf e_z\\
\mathbf T\mathbf e_z=T_{xz}\mathbf e_x+T_{yz}\mathbf e_y+T_{zz}\mathbf e_z\\
$$
The subscripts is: $T_{xy}=\mathbf e_x^T\mathbf T\mathbf e_y$.

The Cartesian base matrix of $\mathbf T$ is:
$$
\begin{align*}
\mathbf T
&=T_{xx}\mathbf e_x\mathbf e_x+T_{xy}\mathbf e_x\mathbf e_y+T_{xz}\mathbf e_x\mathbf e_z\\
&+T_{yx}\mathbf e_y\mathbf e_x+T_{yy}\mathbf e_y\mathbf e_y+T_{yz}\mathbf e_y\mathbf e_z\\
&+T_{zx}\mathbf e_z\mathbf e_x+T_{zy}\mathbf e_z\mathbf e_y+T_{zz}\mathbf e_z\mathbf e_z
\end{align*}
$$

# Chapter 2 General Bases and Tensor Notation

The target is for coordinate-free system.

## The Summation Convention

Let $\{\mathbf g_1,\mathbf g_2,\mathbf g_3\}$ be fixed set of non-coplanar vectors, then any vector $\mathbf v$ may be represented uniquely as:
$$
\mathbf v=\sum_{i=1}^3v^i\mathbf g_i
$$
The base vectors need not be of unit length nor mutually orthogonal.

## Computing the Dot Product in a General Basis

$$
\mathbf u\cdot\mathbf v=u^iv^j\mathbf g_i\cdot\mathbf g_j
$$

## Reciprocal Base Vectors

Let $\mathbf u=u^1\mathbf g_1+u^2\mathbf g_2+u^3\mathbf g_3$, $\mathbf v=v_1\mathbf g^1+v_2\mathbf g^2+v_3\mathbf g^3$, then:
$$
\mathbf u\cdot\mathbf v=u^iv_j\mathbf g_i\cdot\mathbf g^j
$$
If we want the expression reduce to:
$$
\mathbf u\cdot\mathbf v=u^iv_j
$$
Then it requires:
$$
\mathbf g_i\cdot\mathbf g^j=\delta^i_j=\begin{cases}1&i=j\\0&i\ne j\end{cases}
$$
where $\delta^i_j$ is the Kronecker delta.

$\{\mathbf g^j\}$​ is called a reciprocal basis, can be obtain by Gram Schmidt process. And if 
$$
G = \begin{bmatrix}g_1,\dots\end{bmatrix}
$$
then:
$$
G^{-1}=\begin{bmatrix}g^1,\dots\end{bmatrix}^T
$$

## The Roof and Cellar Components of a Vector

A vector can be expressed
$$
\mathbf v=v^i\mathbf g_i=v_i\mathbf g^i
$$
in both form. For the former, $v^i$ is roof components of $\mathbf v$ and the $\mathbf g_i$ the cellar base vector.

Then another way to calculate the dot product is:
$$
\color{red}\mathbf u\cdot\mathbf v=u_iv^j\quad(\mathbf u=u_i\mathbf g^i,\mathbf v=v^j\mathbf g_j)
$$

## Computing the Cross Product in a General Basis

$$
\begin{align*}
(\mathbf u\times\mathbf v)_k&=(\mathbf u\times\mathbf v)\cdot\mathbf g_k\\
&=u^iv^j(\mathbf g_i\times\mathbf g_j)\cdot\mathbf g_k\\
&=u^iv^j\epsilon_{ijk}
\end{align*}
$$

where $\epsilon_{ijk}$ is the cellar components of the permutation tensor.
$$
\epsilon_{ijk}=(\mathbf g_i\times\mathbf g_j)\cdot\mathbf g_k
$$
Then:
$$
\mathbf u\times\mathbf v=(u^iv^j\epsilon_{ijk})\mathbf g_k
$$
Similarly:
$$
\mathbf u\times\mathbf v=(u_iv_j\epsilon^{ijk})\mathbf g^k
$$

## A Second Order Tensor Has Four Sets of Components in General

We can express the component of a second order tensor $\mathbf T$ in four way:
$$
T_{ij}=\mathbf g_i\cdot\mathbf T\mathbf g_j\quad\mathbf T=T_{ij}\mathbf g^i\mathbf g^j\\
T^{ij}=\mathbf g^i\cdot\mathbf T\mathbf g^j\quad\mathbf T=T^{ij}\mathbf g_i\mathbf g_j\\
T^i_{\cdot j}=\mathbf g^i\cdot\mathbf T\mathbf g_j\quad\mathbf T=T^i_{\cdot j}\mathbf g_i\mathbf g^j\\
T^{\cdot i}_j=\mathbf g_j\cdot\mathbf T\mathbf g^i\quad\mathbf T=T^{\cdot i}_j\mathbf g^j\mathbf g_i\\
$$

$$
\begin{align*}
\mathbf T\mathbf v&=\mathbf T(v^j\mathbf g_j)\\
&=v^j\mathbf T\mathbf g_j\\
&=v^jT_{ij}\mathbf g^i\\
&=T_{ij}\mathbf g^i(\mathbf g^j\cdot\mathbf v)
\end{align*}
$$

## Change of Basis

Geometric invariants: Within a given frame, vectors and tensors are blissfully unaware of the bases we choose to represent them.

Let:
$$
\tilde{G}=GA\quad\text{or}\quad\tilde{\mathbf g}_j=\mathbf A^i_j\mathbf g_i
$$
Then:
$$
G=\tilde{G}A^{-1}\quad\text{or}\quad\mathbf g_j=(\mathbf A^{-1})^i_j\tilde{\mathbf g}_i
$$
Therefore:
$$
\tilde{G}^{-1}=A^{-1}G^{-1}\quad\text{or}\quad\tilde{\mathbf g}^i=\mathbf (A^{-1})^i_j\mathbf g^j\\
G^{-1}=A\tilde{G}^{-1}\quad\text{or}\quad\mathbf g^i=\mathbf A^i_j\tilde{\mathbf g}^j
$$
So for the vector:
$$
\tilde{v}_j=\tilde{\mathbf g}_j\cdot\mathbf v=\mathbf A^i_j\mathbf g_i\cdot\mathbf v=\mathbf A^i_j\mathbf g_i\cdot\mathbf g^iv_i\\
\Rightarrow\tilde{v}_j=\mathbf A^i_jv_i\\
\Rightarrow\tilde{v}^i=(\mathbf A^{-1})^i_jv^j\\
$$
For the matrix:
$$
\tilde{T}_{ij}=\tilde{\mathbf g}_i\cdot\mathbf T\tilde{\mathbf g}_j=A^k_i\mathbf g_k\cdot\mathbf TA^p_j\mathbf g_p=A^k_i\mathbf g_k\cdot T_{kp}\mathbf g^k\mathbf g^pA^p_j\mathbf g_p
$$

$$
\tilde{T}_{ij}=A^k_iA^p_jT_{kp}\qquad909 
$$







