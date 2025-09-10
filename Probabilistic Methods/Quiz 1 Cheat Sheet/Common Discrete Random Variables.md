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
