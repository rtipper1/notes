___
To compute the distribution of the sum of independent random variables we need to compute the convolution of the corresponding distributions.

Some examples of sums of random variables with known distributions are 

1. If $X_1 \sim \operatorname{Poisson}\left(\lambda_1\right)$ and $X_2 \sim \operatorname{Poisson}\left(\lambda_2\right)$, then

$$
X_1+X_2 \sim \operatorname{Poisson}\left(\lambda_1+\lambda_2\right)
$$

2. If $X_1 \sim \mathcal{N}\left(\mu_1, \sigma_1^2\right)$ and $X_2 \sim \mathcal{N}\left(\mu_2, \sigma_2^2\right)$, then

$$
X_1+X_2 \sim \mathcal{N}\left(\mu_1+\mu_2, \sigma_1^2+\sigma_2^2\right)
$$
3. If $X_i \sim \operatorname{Bernoulli}(p)$. Then,

$$
X_1+X_2+\ldots+X_n \sim \operatorname{Binomial}(n, p)
$$

4. If $X_1 \sim \operatorname{Binomial}(n, p)$ and $X_2 \sim \operatorname{Binomial}(m, p)$ and Then,

$$
X_1+X_2 \sim \operatorname{Binomial}(n+m, p)
$$

5. If $X_i \sim \operatorname{Exponential}(\lambda)$, then

$$
X_1+\ldots+X_n \sim \operatorname{Erlang}(n, \lambda)
$$
___