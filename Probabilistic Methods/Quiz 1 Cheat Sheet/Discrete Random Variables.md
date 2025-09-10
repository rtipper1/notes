A **random variable** $X$ on a probability space $(\mathbb{P}, \mathcal{F}, \Omega)$ is a mapping from the sample space to the set of real numbers i.e. $X : \Omega \rightarrow \mathbb{R}$

A random variable is discrete if it outputs values on a discrete set. The number of vales that it can possibly map to is either finite of countably infinite.
___
## Expectation
The expectation of a discrete random variable $\mathbb{E}[X]$ is defined as 
$$
\mathbb{E}[X] \triangleq \sum_{x \in \mathcal{X}} x p_X(x)
$$
Intuitively the expectation is the average of a random variable

Expectation has the following useful properties.

1. For any function $g$
$$
\mathbb{E}[g(X)]=\sum_{x \in \mathcal{X}} g(x) p_X(x)
$$
2. For any two random variables $X_1$ and $X_2$
$$
\mathbb{E}\left[X_1+X_2\right]=\mathbb{E}\left[X_1\right]+\mathbb{E}\left[X_2\right]
$$
3. For any constant $c$ 
$$
\mathbb{E}[c X]=c \mathbb{E}[X]
$$
$$
\mathbb{E}[X+c]=\mathbb{E}[X]+c .
$$
---
## Moments and Variance
The $k^{th}$ moment of random variable $X$ is defined as
$$
\mathbb{E}\left[X^k\right]=\sum_{x \in \mathcal{X}} x^k p_X(x)
$$
The variance of a random variable $X$ is defined as 
$$
\operatorname{var}(X)=\mathbb{E}\left[(X-\mu)^2\right],
$$
Where $\mu = \mathbb{E}[X]$, this simplifies to the following
$$
\operatorname{var}(X)=\mathbb{E}\left[X^2\right]-(\mathbb{E}[X])^2 .
$$

The variance of a random variable satisfies the following properties

1. Scaling:
$$
\operatorname{var}(c X)=c^2 \operatorname{var}(X)
$$
2. Translation:
$$
\operatorname{var}(X+c)=\operatorname{var}(X)
$$
---



