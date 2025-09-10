___
## Expectation 
The expectation of a continuous random variable is defined as
$$
\mathbb{E}[X] \triangleq \int_{x=-\infty}^{\infty} x f_X(x) d x
$$
The expectation satisfies the following properties
1. $\mathbb{E}\left[X_1+X_2\right]=\mathbb{E}\left[X_1\right]+\mathbb{E}\left[X_2\right]$
2. $\mathbb{E}[a X]=a \mathbb{E}[X]$
3. $\mathbb{E}[X + a] = \mathbb{E}[x] + a$
4. $\mathbb{E}[g(X)]=\int_{x=-\infty}^{\infty} g(x) f_X(x) d x$

Note that any random variable can be split into its positive and negative parts and we can use that to calculate its expectation from its CDF
$$
\mathbb{E}[X]=\mathbb{E}\left[X^{+}\right]+\mathbb{E}\left[X^{-}\right]
$$
$$
\mathbb{E}[X]=\int_0^{\infty}\left(1-F_X(x)\right) d x-\int_{-\infty}^0 F_X(x) d x
$$
___
## Moments and Variance
The $k_{th}$ **moment** of a continuous random variable $X$ is defined as 
$$
\mathbb{E}\left[X^k\right]=\int_{x=-\infty}^{\infty} x^k f_X(x) d x
$$
The **variance** is defined as 
$$
\operatorname{var}(X)=\mathbb{E}\left[(X-\mu)^2\right]=\int_{x=-\infty}^{\infty}(x-\mu)^2 f_X(x) d x
$$
Where $\mu = \mathbb{E}[X]$. The variance also satisfies the following properties
1. $\operatorname{var}(X)=\mathbb{E}\left[X^2\right]-(\mathbb{E}[X])^2$
2. $\operatorname{var}(a X)=a^2 \operatorname{var}(X)$
3. $\operatorname{var}(X+a)=\operatorname{var}(X)$
___
## Medians, Means, Modes
The **median** of a continuous random variable $c$ satisfies 
$$
\int_{-\infty}^c f_X(x) d x=\int_c^{\infty} f_X(x) d x
$$
$$
F_X(c) = \frac{1}{2}
$$
The **mode** is the most likely value of a random variable. Since the PDF $f_X(x)$ measures the likelihood that the random variable takes values in the neighborhood around $x$ the mode is defined as follows.
$$
m = argmax f_X(x) = argmax \frac{d}{dx} F_X(x)
$$
The **mean** is simply the expectation $\mathbb{E}[X]$. 
$$
\mathbb{E}[X]=\int_{-\infty}^{\infty} x f_X(x) d x
$$
___
## Functions of Random Variables
Suppose $X$ is a random variable distributed according to the PDF $f_X(x)$ and the CDF $F_X(x)$. We are interested in computing the CDF and PDF of $Y=g(X)$.
$$
\begin{aligned}
F_Y(y)= & =\mathbb{P}(Y \leq y) \\
& =\mathbb{P}(g(X) \leq y) \\
& =\mathbb{P}\left(X \leq g^{-1}(y)\right) \\
& =F_X\left(g^{-1}(y)\right)
\end{aligned}
$$
Differentiating the above, we can recover the PDF
$$
f_Y(y)=\left(\frac{d}{d y} g^{-1}(y)\right) f_X\left(g^{-1}(y)\right)
$$
___
