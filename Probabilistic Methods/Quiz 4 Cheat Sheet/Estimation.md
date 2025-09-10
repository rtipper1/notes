___
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
