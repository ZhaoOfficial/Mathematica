# Chapter 6 Sampling

## 6.1 Random Sampling

设 $X$ 是具有分布函数 $F$ 的随机变量，如果 $X_1,\dots,X_n$ 是具有独立同 $F$ 分布的随机变量，则称 $X_1,\dots,X_n$ 是总体 $F$ 得到的容量为 $n$ 的简单随机样本，他们的值 $x_1,\dots,x_n$ 称为样本值。

## 6.3 Distribution of sampling

设 $X_1,\dots,X_n$ 是来自总体 $X$ 的一个样本，$g(X_1,\dots,X_n)$ 是样本的一个函数，如果 $g$ 不含有未知参数，则称 $g(X_1,\dots,X_n)$ 是一个统计量。统计量也是一个随机变量。设 $x_1,\dots,x_n$ 是样本的样本值，则 $g(x_1,\dots,x_n)$ 是 $g(X_1,\dots,X_n)$ 的观察值。

### 6.3.1 常用统计值

样本平均值
$$
\bar{X}=\frac{1}{n}\sum_{i=1}^{n}X_i
$$
样本方差
$$
S^2=\frac{1}{n-1}\sum_{i=1}^{n}(X_i-\bar{X})^2
$$
样本标准差
$$
S=\sqrt{\frac{1}{n-1}\sum_{i=1}^{n}(X_i-\bar{X})^2}
$$
样本 $k$ 阶原点矩
$$
\frac{1}{n}\sum_{i=1}^{n}X_i^k
$$
样本 $k$ 阶中心矩
$$
\frac{1}{n}\sum_{i=1}^{n}(X_i-\bar{X})^k
$$












