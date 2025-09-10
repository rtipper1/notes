___
## Intro to Statistics
 Probability captures how an entire population behaves - what is the likelihood that some datapoint in the population lies in a certain interval.
 
 Statistics on the other had assumes no knowledge of distributions - but assumes that data has been generated from some underlying unknown probability.
___
### Estimation
The simplest statistic to estimate from a dataset is the population mean. Given the LLN and CLT results from earlier, a reasonable guess is to choose the sample mean so our estimate of $\hat{\mu}$ is given by 
$$
\hat{\mu}=\frac{X_1+\ldots+X_n}{n}
$$
1. This estimate is unbiased because 
$$
\mathbb{E}[\hat{\mu}]=\mu .
$$
2. For large $n$, $\hat{\mu}$ converges to the true value $\mu$ with high probability because of LLN.

For other statistics like variance, mode, and percentiles we do not have a symmetric approach and must use other methods.

Suppose we want to estimate some parameter $\theta$ of a population, and our estimate using data samples is denoted by $\hat{\theta}$. We can use the mean-squared error metric to measure how good our estimate is
$$
\mathrm{MSE} \triangleq \mathbb{E}\left[(\hat{\theta}-\theta)^2\right]
$$
This gives us a way to formally define a good/best estimate. Find the $\hat{\theta}$ that minimizes MSE.

$$
\theta^* \in \arg \min _{\hat{\theta}} \mathbb{E}\left[(\hat{\theta}-\theta)^2\right]
$$
If we break down the mean squared error

$$
\begin{aligned}
\mathrm{MSE} & =\mathbb{E}\left[(\hat{\theta}-\theta)^2\right] \\
& =\mathbb{E}\left[(\hat{\theta}-\theta)^2\right]-\operatorname{var}(\hat{\theta}-\theta)+\operatorname{var}(\hat{\theta}-\theta) \\
& =(\mathbb{E}[\hat{\theta}-\theta])^2+\operatorname{var}(\hat{\theta}-\theta) \\
& =(\mathbb{E}[\hat{\theta}-\theta])^2+\operatorname{var}(\hat{\theta}) .
\end{aligned}
$$

Now we can interpret the two terms in MSE separately.

The bias of an estimator is defined as the expected gap between the estimator and the true value. 
$$
b \triangleq \mathbb{E}[\hat{\theta}]-\theta .
$$

Thus, the MSE is simply the sum of the bias squared and the variance of the estimator. A good estimator should have low bias and low variance.

___
## Parameter Estimation
At a high level we start by assuming that our population of interest is modeled by some distribution $f_X(x;\theta)$ where $\theta$ is an unknown parameter. This distribution generates samples that are collected in a dataset $X_1, \dots, X_N$ . We then run our estimation algorithms on this dataset to estimate a value of the parameter $\hat{\theta}$ 

The **Frequentist** assumes that the parameter $\theta$ itself is not random. it is fixed but unknown and our goal is to estimate its value. The Frequentist deals with distributions over $x$ as a function of the parameter $\theta$ i.e. $f_X(x;\theta)$ 

The **Bayesian** assumes that the parameter $\theta$ itself is random. Thus a Bayesian must assume a prior distribution $f_\theta (\theta)$ on the parameter space itself. The Bayesian needs to look a conditional probabilities and joint distributions.

$$
f_{X, \theta}(x, \theta)=f_{\Theta}(\theta) f_{X \mid \Theta}(x \mid \theta) .
$$

Suppose that our population generates $n$ independent coin tosses with an unknown parameter $p$. A **Frequentist** will start by writing down a distribution for the $i_{th}$ coin toss as follows

$$
p_{X_i}(x ; p)=p^x(1-p)^{1-x}, \forall k=0,1
$$

A **Bayesian** first needs to assume a prior on $p$. Let's say that $P \sim \operatorname{Uniform}(0,1)$. Then, the Bayesian can write down the distribution $p$

$$
f_P(p)=\left\{\begin{array}{l}
1, \text { if } p \in(0,1) \\
0, \text { otherwise }
\end{array}\right.
$$

and the conditional distribution for the $i_{th}$ coin toss given $p$ as

$$
p_{X_i \mid P}(x ; p)=p^x(1-p)^{1-x}, \forall k=0,1
$$

___
## Maximum Likelihood Estimation
The maximum likelihood estimate of a parameter tries to find a value $\hat{\theta}$ that maximizes the likelihood of observing the data that we observed.

Let $\mathbf{X}=\left(X_1, \ldots, X_N\right)$ drawn from i.i.d. the PDF $f_X(x ; \theta)$. The likelihood function is function of the parameter $\theta$ given the realizations $x_1, x_2, \ldots, x_N$ :

$$
\mathcal{L}(\theta \mid \mathbf{x})=\prod_{i=1}^N f_X\left(x_i ; \theta\right)
$$
 We can also defined the log-likelihood for a i.i.d. random variables as follows 

$$
\log \mathcal{L}(\theta \mid \mathbf{x})=\sum_{i=1}^N \log \left(f_X\left(x_i ; \theta\right)\right)
$$
The maximum likelihood estimate of a parameter $\theta$ is a solution to the following optimization problem. 

$$
\hat{\theta}_{M L} \triangleq \arg \max _\theta \mathcal{L}(\theta \mid \mathbf{x}) .
$$
___
##### Example 1
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

We can define tow important properties of a parameter estimate now.

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
##### Exercise 1
Show that the ML estimate for the mean $\mu$ computed above is both unbiased and consistent

![[20250505_172555000_iOS.jpg]]

___
##### Exercise 2
Design an estimator for the variance of the form $\hat{\sigma}^2=c \hat{\sigma}_{M L}^2$ that is unbiased

![[20250505_172605000_iOS.jpg]]

___
