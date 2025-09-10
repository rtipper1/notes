___
## Multi-Variate Normal Random Variables
An $n$-dimensional multi-variate Gaussian vector has the PDF

$$
f_{\mathbf{X}}(\mathbf{x})=\frac{1}{\sqrt{(2 \pi)^n \operatorname{det}(\mathbf{\Sigma})}} \exp \left(-\frac{1}{2}(\mathbf{x}-\boldsymbol{\mu})^T \mathbf{\Sigma}^{-1}(\mathbf{x}-\boldsymbol{\mu})\right)
$$

We denote this as $\mathbf{X} \sim \mathcal{N}(\boldsymbol{\mu}, \mathbf{\Sigma})$. It has the following useful properties.

1. $\mathbb{E}[\mathbf{X}]=\mu$.
2. $\operatorname{cov}(\mathbf{X})=\mathbf{\Sigma}$.
3. If $\mathbf{Y}=\mathbf{A X}+\mathbf{b}$, then $\mathbf{Y}$ is also multi-variate Gaussian. More specifically, $\mathbf{Y} \sim \mathcal{N}\left(\mathbf{A} \boldsymbol{\mu}+\mathbf{b}, \mathbf{A} \Sigma \mathbf{A}^T\right)$.
4. If the multi-variate Gaussians are uncorrelated, i.e. $\boldsymbol{\Sigma}$ is a diagonal matrix, then they are also independent.

Suppose $X_1, \ldots, X_n$ are jointly Gaussian and also jointly independent. Further $X_i \sim \mathcal{N}\left(\mu_i, \sigma_i^2\right)$. What does their covariance matrix look like?
$$
\mathbf{\Sigma}=\left[\begin{array}{ccc}
\sigma_1^2 & \ldots & 0 \\
\vdots & \ddots & \vdots \\
0 & \ldots & \sigma_n^2
\end{array}\right]
$$
Substituting this into the joint Gaussian PDF formula, we get 
$$
f_{\mathbf{X}}(\mathbf{x})=\prod_{i=1}^n \frac{1}{\sqrt{2 \pi \sigma_i^2}} \exp \left(-\frac{\left(x-\mu_i^2\right)}{2 \sigma_i^2}\right)
$$
This implies the following important properties. Suppose $\mathbf{X} \sim \mathcal{N}\left(\boldsymbol{\mu}_X, \boldsymbol{\Sigma}_X\right)$ and $\mathbf{Y}=\mathbf{A X}+\mathbf{b}$. Then,

1. $\mathbb{E}[Y]=\mathbf{A} \boldsymbol{\mu}_X+\mathbf{b}$.
2. $\operatorname{cov}(Y)=\boldsymbol{\Sigma}_Y=\mathbf{A} \boldsymbol{\Sigma}_X \mathbf{A}^T$.

##### Exercise 1
Suppose the joint density of two jointly Gaussian random variables ( $X_1, X_2$ ) satisfies the following proportionality
$$
f_{\mathbf{X}}(\mathbf{x}) \propto \exp \left(-\frac{1}{2}\left(x_1^2+4 x_2^2-4 x_1+4 x_2-2 x_1 x_2\right)\right)
$$
Find $\operatorname{cov}\left(X_1, X_2\right), \operatorname{var}\left(X_1\right), \operatorname{var}\left(X_2\right), \mathbb{E}\left[X_1\right]$ and $\mathbb{E}\left[X_2\right]$.

![[20250415_181411000_iOS.jpg]]

___
## Law of Large Numbers
To discuss the law of large numbers we first introduce the setting in which it applies. Consider a collection of $n$ independent and identically distributed random variables $X_1, \dots, X_n$. The sample average of these random variables is
$$
\bar{X}_N=\frac{1}{N} \sum_{n=1}^N X_n
$$
Where the CDF is given by $F_X(x)$, the expectation $\mathbb{E}[X_i] = \mu$, and $Var(X_i) = \sigma^2$ 

For $X_1, \ldots, X_n$ random variables with finite well-defined expectation $\mu$. The weak law of large numbers (WLLN) states that for any $\epsilon>0$

$$
\lim _{n \rightarrow \infty} \mathbb{P}\left(\left|\bar{X}_n-\mu\right|>\epsilon\right)=0
$$

![[Pasted image 20250415124644.png]]


Where $\epsilon$ is some arbitrary threshold for the "tightness" of the distribution. Intuitively this limit means that the larger the value of $n$ the closer the sample average $\bar{X_n}$ concentrates around $\mu$.

Why is WLLN true? We won't provide a formal proof for this. However, we can provide intuitive justification. Consider the mean of $\bar{X}_n$.

$$
\mathbb{E}\left[\bar{X}_n\right]=\frac{1}{n} \sum_{i=1}^n \mathbb{E}\left[X_i\right]=\frac{n \mu}{n}=\mu
$$
This allows us to conclude that $\bar{X}_n$ is centered around the expectation. Now, let's look at the variance of $\bar{X}_n$.

$$
\operatorname{var}\left(\bar{X}_n\right)=\sum_{i=1}^n \frac{1}{n^2} \sigma^2=\frac{\sigma^2}{n}
$$
Now observe that the variance goes to zero as $n$ becomes larger.

$$
\lim _{n \rightarrow \infty} \operatorname{var}\left(\bar{X}_n\right)=0
$$

Thus, as $n$ becomes larger and larger, $\bar{X}_n$ has a distribution that is concentrated more and more around $\mu$ with a narrower and narrower spread (variance). More formally, we can use a result called the Chebyshev's inequality to relate the spread of a distribution around its mean to its variance. We state this inequality without proof here (you can find a short proof in the SC book).

$$
\mathbb{P}\left(\left|\bar{X}_n-\mu\right|>\epsilon\right) \leq \frac{\operatorname{var}\left(\bar{X}_n\right)}{\epsilon^2}=\frac{\sigma^2}{n \epsilon^2}
$$

Thus, for any fixed $\epsilon>0$, we get that $\mathbb{P}\left(\left|\bar{X}_n-\mu\right|>c\right)$ converges to zero, which is the statement of the WLLN.

### When does LLN Fail?
The law of large numbers is not always true. LLN is contingent upon $\mathbb{E}[X^2] < \infty$. Distributions whose variance is unbounded do not follow the weak law of large numbers.

### How Fast Does $\bar{X_n}$ Converge
$\bar{X_n}$ converges at a rate at least as fast as $\frac{c}{n}$ where $c$ is a constant. The actual rate at which it converges is determined by the central limit theorem.


##### Exercise 2
Consider $X_i$ to be i.i.d. $\mathcal{N}(0,1)$ standard normals. Let $\bar{X}_n$ be the average of $n$ of these random variables. Compute $\mathbb{P}\left(\left|\bar{X}_n\right|>c\right)$ in terms of the standard normal PDF.

![[20250415_181402000_iOS.jpg]]

___
## Central Limit Theorem
The **Central Limit Theorem** stats that for independent and identically distributed random variables $X_1, \ldots, X_n$ with a finite mean $\mu$ and a finite variance $\sigma^2$, the CDF of $Z_n$ converges (pointwise) to that of the standard normal. Here, $Z_n$ is defined as
$$
Z_n \triangleq \sqrt{n}\left(\frac{\bar{X}_n-\mu}{\sigma}\right)
$$
More formally
$$
\lim _{n \rightarrow \infty} F_{Z_n}(z)=\Phi(z)
$$
where $\Phi(\cdot)$ is the standard normal CDF.

How do we use this result? Consider $X_1, \ldots, X_n$ to be i.i.d. with finite means and variances. Let $\bar{X}_n$ be the average of these. Then, the distribution of $\bar{X}_n$ can be approximated as $\mathcal{N}\left(\mu, \sigma^2 / n\right)$. using this we can reason about the average lying in any interval $A$

$$
\mathbb{P}\left(\bar{X}_n \in A\right) \approx \int_A \frac{\sqrt{n}}{\sqrt{2 \pi \sigma^2}} \exp \left(-\frac{n(x-\mu)^2}{2 \sigma^2}\right) d x
$$

More specifically, using our prior results on the Gaussian, we can say that

$$
\mathbb{P}\left(a \leq \bar{X}_n \leq b\right) \approx \Phi\left(\sqrt{n} \frac{b-\mu}{\sigma}\right)-\Phi\left(\sqrt{n} \frac{a-\mu}{\sigma}\right)
$$
##### Exercise 3
Prove the above statements using the CLT.

![[20250415_181352000_iOS.jpg]]

Approximately equivalent ways of stating the CLT are 

1. $\sqrt{n}\left(\frac{X_n-\mu}{\sigma}\right) \rightarrow \mathcal{N}(0,1)$

2. $\sqrt{n}\left(\bar{X}_n-\mu\right) \rightarrow \mathcal{N}\left(0, \sigma^2\right)$

3. $\bar{X}_n \rightarrow \mathcal{N}\left(\mu, \sigma^2 / n\right)$

### Limitations of CLT
The CLT is not always valid, some examples of situations in which it is not valid are 

1. CLT fails for small $n$
2. CLT fails for non-independent events
3. CLT fails for non-identically distributed events.
4. CLT fails for large Variance


##### Exercise 4
Suppose we have 100 datapoints from an unknown distribution. The only thing we know is that the true population mean is $\mu=500$ and the standard deviation is $\sigma=80$.

1. Find the probability that the mean of the datapoints will be inside the interval $(490,510)$.

2. Find an interval of the form $(500-x, 500+x)$ such that the sample mean falls inside this interval with $95 \%$ probability (often called a $95 \%$ confidence interval).

![[20250415_181343000_iOS.jpg]]

___