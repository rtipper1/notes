___
The maximum likelihood estimate of a parameter tries to find a value $\hat{\theta}$ that maximizes the likelihood of observing the data that we observed.

Let $\mathbf{X}=\left(X_1, \ldots, X_N\right)$ drawn from i.i.d. the PDF $f_X(x ; \theta)$. The likelihood function is function of the parameter $\theta$ given the realizations $x_1, x_2, \ldots, x_N$ :
$$
\mathcal{L}(\theta \mid \mathbf{x})=\prod_{i=1}^N f_X\left(x_i ; \theta\right)
$$
$$
\log \mathcal{L}(\theta \mid \mathbf{x})=\sum_{i=1}^N \log \left(f_X\left(x_i ; \theta\right)\right)
$$
The maximum likelihood estimate of a parameter $\theta$ is a solution to the following optimization problem.
$$
\hat{\theta}_{M L} \triangleq \arg \max _\theta \mathcal{L}(\theta \mid \mathbf{x})
$$
___
#### Example 1
Lets compute the ML estimate for $n$ independent coin tosses. Suppose the outcomes of the $n$ coin tosses were $x_1,\dots,x_N$ where $x_i \in {0,1}$ represents a tails or a heads. Suppose the total number of heads that occurs is $K$.
$$
\begin{aligned}
\log \mathcal{L}(p \mid \mathbf{x}) & =\sum_{i=1}^N \log \left(p^{x_i}(1-p)^{1-x_i}\right) \\
& =\sum_{i=1}^N\left(x_i \log (p)+\left(1-x_i\right) \log (1-p)\right) \\
& =K \log (p)+(N-K) \log (1-p)
\end{aligned}
$$
To optimize w.r.t to $p$ we differentiate and set the derivative to 0 .
$$
K / p-(N-K) /(1-p)=0
$$
Solving this, we get the ML estimate of $p$
$$
\hat{p}_{M L}=\frac{K}{N} .
$$
Thus, the maximum likelihood estimate of a coin toss probability is simply the fraction of heads observed in $N$ coin tosses.
___
##### Example 2
Lets apply the same maximum likelihood approach to estimate the mean of a Gaussian distribution. Lets assume our population is modeled by $\mathcal{N}(\mu, \sigma^2)$ where both $\mu$ and $\sigma$ are unknown parameters.

We first write down the density of one sample $X_i$
$$
f_{X_i}\left(x_i\right)=\frac{1}{\sqrt{2 \pi \sigma^2}} \exp \left(-\frac{\left(x_i-\mu\right)^2}{2 \sigma^2}\right)
$$
Now, using the fact that all generated samples are independent, we can write down their joint density, or alternatively the likelihood function
$$
\mathcal{L}\left(\mathbf{X} \mid \mu, \sigma^2\right)=f_{\mathbf{X}}(\mathbf{x})=\frac{1}{\left(2 \pi \sigma^2\right)^{n / 2}} \exp \left(-\frac{\sum_{i=1}^N\left(x_i-\mu\right)^2}{2 \sigma^2}\right)
$$
Let's look the log-likelihood.
$$
\log \left(\mathcal{L}\left(\mathbf{X} \mid \mu, \sigma^2\right)\right)=-\frac{n}{2} \log \left(2 \pi \sigma^2\right)-\frac{1}{2 \sigma^2}\left(\sum_{i=1}^N\left(x_i-\mu\right)^2\right)
$$
Now, we can maximize the log-likelihood as a function of $\mu$ - we differentiate w.r.t. to $\mu$ and set it to zero.
$$
\frac{\partial}{\partial \mu} \log \left(\mathcal{L}\left(\mathbf{X} \mid \mu, \sigma^2\right)\right)=\frac{1}{2 \sigma^2}\left(\sum_{i=1}^N 2\left(x_i-\mu\right)\right)
$$
Setting this to zero and simplifying, we obtain
$$
\hat{\mu}_{M L}=\frac{x_1+x_2+\ldots+x_N}{N}
$$
Thus, the ML estimate is the sample mean!
___
### Properties
The **bias** of a parameter estimate $\hat{\theta}$ is defined as 
$$
b \triangleq \mathbb{E}[\hat{\theta}-\theta] .
$$
It represents the amount by which the estimate under or over estimates the true value of the parameter on average. An unbiased estimate has $b=0$.

An estimator is called **consistent** if it converges to the true estimate as the number of samples grows large
$$
\lim _{n \rightarrow \infty} \hat{\theta}=\theta .
$$
Intuitively, a consistent estimate ensures that we will converge to the right answer as long as we collect large enough data sets.
___