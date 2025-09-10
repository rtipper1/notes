___
## Maximum A Posteriori Estimation
Maximum a posteriori (MAP) estimates are the Bayesian approach  to parameter estimation. At a high level we start by assuming that our parameter is random and has a prior distribution $f_\Theta (\theta)$.

The samples $X = (X_1, \dots, X_N)$ have a conditional distribution given the value $\Theta$ that is described as $f_{X|\Theta} (x|\theta)$.

Now suppose that the collected data samples are $\left(x_1, \ldots, x_N\right)$. We want to compute the conditional density of $\theta$ given these data samples.

$$
f_{\Theta \mid \mathbf{X}}(\theta \mid \mathbf{x})=\frac{f_{X, \theta}(x, \theta)}{f_{\mathbf{X}}(\mathbf{x})}=\frac{f_{\Theta}(\theta) f_{\mathbf{X} \mid \Theta}(\mathbf{x} \mid \theta)}{f_{\mathbf{X}}(\mathbf{x})}
$$
Look at the three distributions above carefully.

- **Prior:** $f_{\Theta}(\theta)$ models the randomness in the parameter - it is our prior belief of how likely the parameter is going to be in any interval.

- **Likelihood**: $f_{\mathbf{X} \mid \Theta}(\mathbf{x} \mid \theta)$ is the conditional distribution of data given a parameter value. It models how likely it is that we observe a set of datapoints if the parameter $\Theta$ has a value of $\theta$.

- **Posterior:** $f_{\Theta \mid \mathbf{X}}(\theta \mid \mathbf{x})$ models how likely it is that the true value of the parameter is $\theta$ given the realized data points $\left(x_1, \ldots, x_N\right)$.

The MAP estimate for i.i.d. observations $\left(X_1, \ldots, X_N\right)$ is given by
$$
\hat{\theta}_{M A P}=\arg \max _\theta f_{\Theta \mid \mathbf{X}}(\theta \mid \mathbf{x})
$$
$$
=\arg \max _\theta\left\{\log \left(f_{\mathbf{X} \mid \Theta}(\mathbf{x} \mid \theta)\right)+\log \left(f_{\Theta}(\theta)\right)\right\}
$$
Notice how the MAP is different from the ML estimate, which instead maximizes the likelihood $f_{\mathbf{X} \mid \Theta}(\mathrm{x} \mid \theta)$.
$$
\hat{\theta}_{M L}=\arg \max _\theta \quad \log \left(f_{\mathbf{X} \mid \Theta}(\mathbf{x} \mid \theta)\right) .
$$

This shows that the only difference between MAP and ML is the prior belief parameter.
___
##### Example 1
Let's assume that our population is modeled by a Gaussian distribution $\mathbb{N}\left(\Theta, \sigma^2\right)$ where only $\theta$ is unknown. We are given $N$ samples generated from this distribution. We also know that $\Theta \sim \mathcal{N}\left(\mu_0, \sigma_0^2\right)$. Let's compute the MAP estimate.

$$
\log \left(f_{\Theta}(\theta) f_{\mathbf{X} \mid \Theta}(\mathbf{x} \mid \theta)\right)=-\frac{N}{2} \log \left(2 \pi \sigma^2\right)-\frac{1}{2 \sigma^2}\left(\sum_{i=1}^N\left(x_i-\theta\right)^2\right)-\frac{\log \left(2 \pi \sigma_0^2\right)}{2}-\frac{1}{2 \sigma_0^2}(\theta
$$

Maximizing this w.r.t to $\theta$ by differentiating and setting the derivative to zero, we get

$$
\hat{\theta}_{M A P}=\frac{\sum_{i=1}^N x_i+\frac{\sigma^2}{\sigma_0^2} \mu_0}{N+\frac{\sigma^2}{\sigma_0^2}}
$$

Re-arranging the above expression and recalling our earlier result for $\hat{\theta}_{M L}$, we get

$$
\hat{\theta}_{M A P}=\frac{\sigma_0^2 \hat{\theta}_{M L}+\frac{\sigma^2}{N} \mu_0}{\sigma_0^2+\frac{\sigma^2}{N}}
$$

When does the MAP estimate start to look like the ML estimate? This happens when $f_{\Theta}(\theta)$ is a constant over a large range of $\theta$ values, since it doesn't influence the optimization anymore. Thus, if our prior belief is that $\theta$ is uniformly distributed over a large range, then it doesn't affect our MAP calculations and we obtain the ML estimate again.

Another case when MAP estimates start to look like ML estimates is when $N$ is large. In this case, the effect of the prior will start to "wash off" as more and more data is acquired.
___
##### Exercise 1
Suppose our prior is $\Theta \sim$ Uniform $[0.7,1]$. We do 100 i.i.d. coin tosses that are Bernoulli $(\theta)$. Find the MAP estimator $\hat{\theta}_{M A P}$ if

1. there are 60 heads in the 100 coin tosses.

2. there are 85 heads in the 100 coin tosses.

![[20250505_175830000_iOS.jpg]]

___
## Confidence Intervals
The confidence interval is an interval of the form $\mathcal{I}=[\hat{\Theta}-\epsilon, \hat{\Theta}+\epsilon]$ that contains the true parameter $\theta$ with confidence $1-\alpha$.$$
\mathbb{P}(\theta \in \mathcal{I})=1-\alpha .
$$Often, we will set $\alpha=0.05$ or a $95 \%$ confidence interval.

Important things to remember about confidence intervals

1. Since $\hat{\Theta}$ is random (it's a function of the data we observe, which is inherently random), so the confidence interval $\mathcal{I}$ is also random.

2. It is different from the deterministic interval $[\theta-\epsilon, \theta+\epsilon]$. However, the following equality holds
$$
\mathbb{P}(\hat{\Theta}-\epsilon \leq \theta \leq \hat{\Theta}+\epsilon)=\mathbb{P}(\theta-\epsilon \leq \hat{\Theta} \leq \theta+\epsilon)
$$

3. It does not mean that all the values collected during the experiment (or all the values of the population) would lie in this interval with probability $(1-\alpha)$. It only talks about confidence regarding the population mean/parameter.

4. Computing the confidence interval does not require any knowledge about the true parameter $\theta$.

___
## Computing Confidence Intervals
In this class we stick to computing confidence intervals for estimators that are the man of the collected data. So, we assume that we have i.i.d. observations with true mean $\mu$ and our estimator is of the following form.
$$
\hat{\Theta}=\frac{X_1+\ldots+X_N}{N}
$$
___
### Known Variance
We assume that we know the variance of $X_i$. i.e. $var(X_i) = \sigma^2$. In order to construct the confidence interval we use the central limit theorem.

Recall that for large $N$, the sample average behaves approximately like a Gaussian.

$$
Z=\frac{\hat{\Theta}-\mu}{\sigma / \sqrt{N}} \rightarrow \mathcal{N}(0,1)
$$
Given a confidence level $(1 - \alpha)$, we want to solve the following
$$
\begin{aligned}
\mathbb{P}(\hat{\Theta}-\epsilon \leq \mu \leq \hat{\Theta}+\epsilon) & =\mathbb{P}(|\hat{\Theta}-\mu| \leq \epsilon) \\
& =\mathbb{P}\left(\frac{|\hat{\Theta}-\mu|}{\sigma / \sqrt{N}} \leq \sqrt{N} \frac{\epsilon}{\sigma}\right) \\
& =\mathbb{P}\left(|Z| \leq \sqrt{N} \frac{\epsilon}{\sigma}\right) \\
& =2 \Phi\left(\sqrt{N} \frac{\epsilon}{\sigma}\right)-1
\end{aligned}
$$

We want this probability to be higher than our confidence level $1-\alpha$, so we get

$$
\begin{aligned}
2 \Phi\left(\sqrt{N} \frac{\epsilon}{\sigma}\right)-1 & \geq 1-\alpha \\
\Phi\left(\sqrt{N} \frac{\epsilon}{\sigma}\right) & \geq 1-\frac{\alpha}{2} \\
\sqrt{N} \frac{\epsilon}{\sigma} & \geq \Phi^{-1}\left(1-\frac{\alpha}{2}\right) \\
\epsilon & \geq \frac{\sigma}{\sqrt{N}} \Phi^{-1}\left(1-\frac{\alpha}{2}\right)
\end{aligned}
$$

Typically, $\alpha=0.05$, which means we need $\Phi^{-1}(1-0.025)=1.96$.

For i.i.d. random variables $X_1, \ldots, X_N$ with known variance $\sigma^2$, the $95 \%$ confidence interval for the true sample mean is given by
$$
\mathcal{I}_{0.95}=\left[\hat{\Theta}-\frac{1.96 \sigma}{\sqrt{N}}, \hat{\Theta}+\frac{1.96 \sigma}{\sqrt{N}}\right]
$$

where $\hat{\Theta}$ is the sample average of the $N$ random variables. More generally,

$$
\mathcal{I}_{1-\alpha}=\left[\hat{\Theta}-\frac{\Phi^{-1}(1-\alpha / 2) \sigma}{\sqrt{N}}, \hat{\Theta}+\frac{\Phi^{-1}(1-\alpha / 2) \sigma}{\sqrt{N}}\right]
$$

___
### Unknown Variance
we assume that we have i.i.d. observations $X_1, \ldots, X_N$ with true mean $\mu$ and our estimator is of the following form

$$
\hat{\Theta}=\frac{X_1+\ldots+X_N}{N} .
$$
However, now we do not know the variance of the individual random variables $X_i$. How do we go about creating a confidence interval?

First, we need to estimate the variance itself. That is reasonably straightforward and we have discussed it for Gaussians before. Consider the following estimator for variance

$$
\hat{S}^2 \triangleq \frac{1}{N-1} \sum_{n=1}^N\left(X_n-\hat{\Theta}\right)^2 .
$$

We could replace the variance in our previous discussion with this new estimate and call it a day. However, there is a flaw in our logic. Consider the random variable $T$
$$
T \triangleq \frac{\hat{\Theta}-\theta}{\hat{S} / \sqrt{N}}
$$

Unlike $Z$ from earlier, we cannot apply the CLT here, since it is not in the same format. Since $T$ does not converge to the standard normal, we cannot use $\Phi(\cdot)$ as we had done earlier.

How do we get around this issue? We introduce a new distribution called Student's $\mathbf{t}$-distribution and state the following result without proof.

The random variable $T$ defined above follows the Student t -distribution with parameter $N-1$. The PDF is fairly complicated and not very relevant to our discussion. We will just represent it as $f_T(t ; N-1)$.

Now, our confidence interval discussion becomes straightforward. We want

$$
\mathbb{P}(|T| \leq \sqrt{N} \epsilon / \hat{S}) \geq(1-\alpha)
$$

Assume that the inverse CDF of the t -distribution is given by $\Psi_{N-1}^{-1}(\cdot)$. Then, doing analysis similar to that for the known variance case, we obtain the $1-\alpha$ confidence.

$$
\mathcal{I}_{1-\alpha}=\left[\hat{\Theta}-\frac{\Psi_{N-1}^{-1}(1-\alpha / 2) \hat{S}}{\sqrt{N}}, \hat{\Theta}+\frac{\Psi_{N-1}^{-1}(1-\alpha / 2) \hat{S}}{\sqrt{N}}\right]
$$
___