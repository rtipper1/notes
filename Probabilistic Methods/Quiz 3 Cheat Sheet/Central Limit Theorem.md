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
A common corollary to this is the probability that the sample mean will be outside some constant $c$.

Consider $X_i$ to be i.i.d. $\mathcal{N}(0,1)$ standard normals. Let $\bar{X}_n$ be the average of $n$ of these random variables. Compute $\mathbb{P}\left(\left|\bar{X}_n\right|>c\right)$ in terms of the standard normal PDF.

$$\mathbb{P}\left(\left|\bar{X}_n\right|>c\right)=2(1-\Phi(\sqrt{n} c))$$

Approximately equivalent ways of stating the CLT are 

1. $\sqrt{n}\left(\frac{X_n-\mu}{\sigma}\right) \rightarrow \mathcal{N}(0,1)$

2. $\sqrt{n}\left(\bar{X}_n-\mu\right) \rightarrow \mathcal{N}\left(0, \sigma^2\right)$

3. $\bar{X}_n \rightarrow \mathcal{N}\left(\mu, \sigma^2 / n\right)$

## Limitations of CLT
The CLT is not always valid, some examples of situations in which it is not valid are 

1. CLT fails for small $n$
2. CLT fails for non-independent events
3. CLT fails for non-identically distributed events.
4. CLT fails for large Variance

___