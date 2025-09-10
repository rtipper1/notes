___
## Geometric
Describes a binary experiment sequential binary experiments until success.

Let $X$ be a **geometric random variable**. Then the PMF of $X$ is 
$$
p_X(k)=\underbrace{(1-p)^{k-1}}_{k-1 \text { failures }} \underbrace{p}_{\text {final success }} \quad k=1,2, \ldots, $$
where $0 < p < 1$ is the geometric parameter. We write
$$
X  \sim Geometric(p)
$$
to say that $X$ is drawn from a geometric distribution with parameter $p$.

Geometric random variable $X$ satisfies the following properties
1. $\mathbb{E}[X] = \frac{1}{p}$
2. $\mathbb{E}[X^2]=\frac{2}{p^2} - \frac{1}{p}$
3. $Var[X] = \frac{1 - p}{p^2}$

___
## Poisson
Models the number of occurrences of some event over a period of time or space.

Let $X$ be a **poison random variable** with parameter $\lambda$. Then its PMF is give by
$$
p_X(k)=\frac{\lambda^k}{k!} e^{-\lambda},\quad \forall k=0,1,2,3, \ldots
$$
We say that $X$ is drawn from the poison distribution by writing it as
$$
X \sim Poisson(\lambda)
$$
$X$ satisfies the following properties
1. $\mathbb{E}[X] = \lambda$
2. $\mathbb{E}[X^2] = {\lambda}^2 + \lambda$
3. $var(X) = \lambda$
___
## Bernoulli
A Bernoulli random variable $X$ takes on values 0 and 1 . It's PMF is given by
$$
p_X(1)=p \text { and } p_X(0)=1-p
$$
Here $p \in[0,1]$ is called the Bernoulli parameter. We write
$$
X \sim \operatorname{Bernoulli}(p)
$$
to say that $X$ is a Bernoulli random variable with the parameter $p$. 

$X$ satisfies the following properties.
1. $\mathbb{E}[X]=p$
2. $\mathbb{E}\left[X^2\right]=p$
3. $\operatorname{var}(X)=p(1-p)$
___
## Binomial
Let $X$ be a binomial random variable with parameters $n$ and $p$. Then, its PMF is given by
$$
p_X(k)=\binom{n}{k} p^k(1-p)^{n-k}, \forall k \in\{0, \ldots, n\}
$$
We say that $X$ is drawn from a binomial distribution by writing it as $X \sim$ $\operatorname{Binomial}(n, p)$.

Note that the probability above is simply equal to the probability that $k$ out $n$ independent biased coin tosses end up being heads.

$X$ satisfies the following properties.
1. $\mathbb{E}[X]=n p$
2. $\mathbb{E}\left[X^2\right]=n p(n p+(1-p))$
3. $\operatorname{var}(X)=n p(1-p)$
---
