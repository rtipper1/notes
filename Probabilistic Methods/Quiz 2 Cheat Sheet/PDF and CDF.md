___
A probability density function $f_X(x)$ is the continuous version of the probability mass function $F_X(x)$. 

If we have some subset of the real line $A$ and we want to find the probability that $X$ lies in this subset, then we can calculate it as follows.
$$
\mathbb{P}(X \in A)=\int_{x \in A} f_X(x) d x
$$
The PDF $f_X(x)$ must satisfy the following properties

1. Non-negativity: $f_X(x) \geq 0, \forall x$ 
2. Normalization: $\int_{-\infty}^{\infty} f_X(x) d x=1$
3. Measure: $\mathbb{P}(X \in A)=\int_{x \in \Lambda} f_X(x) d x$

Note: Think about the PDF $f_X(x)$ as the probability per unit length at the point $x$. Seeing as the probability that the continuous random variable $X$ takes any specific value $x$ is zero.
$$
\mathbb{P}(X = x) = 0
$$
___
## Cumulative Distribution Function
The CDF $F_X(x)$ of a continuous random variable $X$ is defined as follows.
$$
F_X(x) \triangleq \mathbb{P}(X \leq x)=\int_{x=-\infty}^x f_X(x) d x
$$
The CDF $F_X(x)$ satisfies the following properties
1. Non-decreasing: $F_X\left(x_1\right) \leq F_X\left(x_2\right), \forall x_1<x_2$.
2. Maximum value of 1: $\lim _{x \rightarrow \infty} F_X(x)=1$
3. Minimum value of 0: $\lim _{x \rightarrow-\infty} F_X(x)=0$
___





