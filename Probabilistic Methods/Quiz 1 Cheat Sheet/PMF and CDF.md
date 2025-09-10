---

---
___
## Probability Mass Function (PMF)
A probability mass function for a random variable $X$ describes the probability with which it takes a specific value $x$.

The probability mass function of a discrete random variable $X$ consists of the following values.
$$
p_X(x) \triangleq \mathbb{P}(X=x), \forall x \in \mathcal{X}
$$
A PMF must be normalized, **normalization** states that the sum of probability values over an entire PMF must be 1. 
$$
\sum_{x \in \mathcal{X}} p_X(x)=1
$$
Put Simply the PMF represents the $\mathbb{P}(X = x)$ 
___
## Cumulative Distribution Function (CDF)
The cumulative distribution function can be defined as following
$$
F_X(z)=\mathbb{P}(X \leq z)=\sum_{\{x \in \mathcal{X}: x \leq z\}} p_X(x)
$$
The valid CDF has the following properties

1. The CDF looks an increasing step function.

2. The maximum value of the CDF is 1 , i.e. $\lim _{x \rightarrow \infty} F_X(x)=1$.

3. The minimum value of the CDF is 0 , i.e. $\lim _{x \rightarrow-\infty} F_X(x)=0$.

4. $F_X(x)$ has jumps at points where $p_X(x)>0$. The size of each jump equals $p_X(x)$.

---
