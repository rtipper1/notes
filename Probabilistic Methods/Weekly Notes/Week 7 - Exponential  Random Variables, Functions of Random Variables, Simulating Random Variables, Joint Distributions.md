___
## Exponentials and Poisson
The exponential random variable is the **interarrival time** between tow consecutive Poisson events. The exponential random variable is the time it takes to go from $N$ to $N + 1$ Poisson counts.

Suppose the arrival of people/packets/events/cars etc. in to some system is modeled as Poisson process of rate $\lambda$. Let $X$ denote the number of arrivals in the interval $(0,t]$. Then $X$ is distributed as Poisson($\lambda t$)

$$
p_X(k)=\mathbb{P}(X=k)=\frac{e^{-\lambda t}(\lambda t)^k}{k!}
$$

Suppose the zeroth arrival happens at $t = 0$. Let $Y$ be the amount of time taken to get the first arrival. It turns out that $Y$ ~ Exponential($\lambda$)
___
## Gaussian or Normal Random Variables
A **Gaussian random variable** is a random variable $X$ such that its PDF is 

$$
f_X(x)=\frac{1}{\sqrt{2 \pi \sigma^2}} \exp \left\{-\frac{(x-\mu)^2}{2 \sigma^2}\right\}
$$

The corresponding CDF does not have a closed-form mathematical expression.

$$
\Phi(x) \triangleq F_X(x)=\int_{u=-\infty}^x f_X(u) d u
$$


The CDF of the Gaussian random variable also satisfies the following.

$$
F_X(x)=\Phi\left(\frac{x-\mu}{\sigma}\right)
$$

where $\left(\mu, \sigma^2\right)$ are parameters of the distribution. We write

$$
X \sim \operatorname{Gaussian}\left(\mu, \sigma^2\right) \quad \text { or } \quad X \sim \mathcal{N}\left(\mu, \sigma^2\right)
$$

to say that $X$ is drawn from a Gaussian distribution of parameter $\left(\mu, \sigma^2\right)$.

The Gaussian random variable has two parameters. $\mu$ is the mean and $\sigma^2$ is the variance. These two parameters are also the first and second moments.

![[Pasted image 20250303183203.png]]

___
## Functions of Random Variables
How do we compute the PDF and the CDF of a function of a random variable.

Suppose $X$ is a random variable distributed according the the PDF $f_X(x)$ and the CDF $F_X(x)$. We are interested in computing the CDF and PCDF of $Y = g(X)$

$$
\begin{aligned}
F_Y(y)= & =\mathbb{P}(Y \leq y) \\
& =\mathbb{P}(g(X) \leq y) \\
& =\mathbb{P}\left(X \leq g^{-1}(y)\right) \\
& =F_X\left(g^{-1}(y)\right)
\end{aligned}
$$

Differentiating the above we get the PDF.

$$
f_Y(y)=\left(\frac{d}{d y} g^{-1}(y)\right) f_X\left(g^{-1}(y)\right)
$$

This approach only works if the function $g(.)$ is invertible/monotonic. However it can be extended to non-invertible functions. Instead of writing $X \leq g^{-1}(y)$ we write the following.

$$
\mathbb{P}(g(X) \leq y)=\mathbb{P}(X \in A),
$$
---
## Simulating Random Variables
Suppose we have access to a uniform random variable $U \sim \operatorname{Uniform}(0,1)$. Can we use it to generate any continuous random variable with a monotonic CDF $F(x)$. The answer is Yes!

Define $X=F^{-1}(U)$. Let's compute the CDF of $X$.

$$
\begin{aligned}
F_X(x) & =\mathbb{P}(X \leq x) \\
& =\mathbb{P}\left(F^{-1}(U) \leq x\right) \\
& =\mathbb{P}(U \leq F(x)) \\
& =F(x)
\end{aligned}
$$


Thus $X$ has the CDF $F(x)$. So if we generate samples according to $U$ and apply the function $F^{-1}(\cdot)$ on these samples, we obtain samples distributed according to $F(\cdot)$.
___
