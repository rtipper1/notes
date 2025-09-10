___
## Conditional Expectation
For discrete random variables the expectation is defined as follows.
$$
\mathbb{E}[X \mid Y=y] \triangleq \sum_{x \in \mathcal{X}} x p_{X \mid Y}(x \mid y)
$$
For continuous random variables we define it as follows.
$$
\mathbb{E}[X \mid Y=y] \triangleq \int_{-\infty}^{\infty} x f_{X \mid Y}(x \mid y) d x
$$
$\mathbb{E}[X \mid Y]$ is the conditional expectation of $X$ given $Y$. It computes the average value of $X$ assuming that the random variable $Y$ is fixed-leading to a function of $Y$. Thus, $\mathbb{E}[X \mid Y]$ is itself a random variable.

##### Exercise 1
Consider $X \sim \operatorname{Uniform}(0,1)$ and $N \sim \mathcal{N}(0,1)$. Let $Y=X N$. Then, compute $\mathbb{E}[Y \mid X]$. Similarly, let $Z=X+N$ and compute $\mathbb{E}[Z \mid N]$.

![[20250414_215504000_iOS.jpg]]

### Law of Total Expectation
The law of total expectation states that 

$$
\mathbb{E}[\mathbb{E}[X \mid Y]]=\mathbb{E}[X] .
$$

In particular, for discrete random variables, this simplifies to

$$
\sum_{y \in \mathcal{Y}} \mathbb{E}[X \mid Y=y] p_Y(y)=\mathbb{E}[X]
$$

Similarly for continuous random variables, this simplifies to

$$
\int_{-\infty}^{\infty} \mathbb{E}[X \mid Y=y] f_Y(y) d y=\mathbb{E}[X]
$$

##### Exercise 2
Suppose $X \sim \mathcal{N}\left(\mu, \sigma^2\right)$. Further $Y \mid X \sim \mathcal{N}\left(X, X^2\right)$. Compute $\mathbb{E}[Y]$.

![[20250414_215516000_iOS.jpg]]

##### Exercise 3
Suppose $X \sim \mathcal{N}(0,1)$. Further $Y \mid X \sim \operatorname{Uniform}(X-\pi, X+\pi)$. Compute $\mathbb{E}[\sin (X+Y)]$.

![[20250414_215525000_iOS.jpg]]

___
## Sums of Independent Random Variables
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