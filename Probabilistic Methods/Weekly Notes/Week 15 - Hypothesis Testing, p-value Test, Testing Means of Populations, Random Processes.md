___
## Hypothesis Testing
A central aspect of statistics is analyzing data from experiments to check whether a proposed hypothesis is true or not.

A **hypothesis** is any statement or assertion that requires testing by observation to determine its validity.

- A coin is unbiased
- Algorithm A is better than Algorithm B
- Receiving a 0 or a 1 over a communication channel
- Public policy A is better than public policy B
- A defendant is innocent or guilty

The process of testing a hypothesis' validity based on data is what we call hypothesis testing. In binary hypothesis testing we have to hypotheses. 

- $H_0$ : the null hypothesis. It is the "status quo", or as things are expected to be by default. While conducting an experiment, this is usually the pessimistic view. For example, during a drug trial, the null hypothesis is that the drug being proposed as a treatment does not actually work.

- $H_1$ : the alternative hypothesis. It is the alternative to the null hypothesis, and usually the optimistic view. We can only reject $H_0$ and accept $H_1$ if we have overwhelming statistical evidence to suggest that $H_0$ is unlikely.

Some examples include the following.

Suppose we want to test whether a coin is fair or not. We will write down three possible sets of hypotheses we can test

1. $H_0: \theta=0.5$ and $H_1: \theta \neq 0.5$. This is a double-sided hypothesis test because evidence that $\theta$ is far from 0.5 in either direction would invalidate $H_0$.

2. $H_0: \theta=0.5$ and $H_1: \theta>0.5$. This is a single-sided hypothesis test towards the right.

3. $H_0: \theta=0.5$ and $H_1: \theta<0.5$. This is also a single-sided hypothesis test, but towards the left.

___
## P-Value Test
Consider mean estimation using i.i.d. observations. Then our estimator is

$$
\hat{\Theta}=\left(X_1+\ldots+X_N\right) / N
$$

Suppose that the null hypothesis is that $\theta=\theta_0$ and that $\operatorname{var}\left(X_i\right)=\sigma^2$. If the null hypothesis is true, we know that
$$
\hat{Z}=\frac{\hat{\Theta}-\theta_0}{\sigma / \sqrt{N}}
$$

is approximately standard normal. To do hypothesis testing, we collect datapoints $x_1, \ldots, x_N$ and compute a realization of the random variable $\hat{Z}$, given by

$$
\hat{z}=\frac{\left(x_1+\ldots+x_N\right) / N-\theta_0}{\sigma / \sqrt{N}}
$$

**Case 1: Double-sided testing:** In this case, our alternative hypothesis $H_1$ is that $\theta \neq \theta_0$. To compute the $p$-value we must look at the following probability
$$
p=\mathbb{P}(|\hat{Z}|>|\hat{z}|)=2 \Phi(-|\hat{z}|)
$$

If $p<\alpha$ we accept $H_1$, otherwise, we accept $H_0$.


**Case 2: Single sided testing towards the left:** In this case, our alternative hypothesis $H_1$ is that $\theta<\theta_0$. To compute the $p$-value, we need to look at the following probability
$$
p=\mathbb{P}(\hat{Z}<\hat{z})=\Phi(\hat{z})
$$

If $p<\alpha$ we accept $H_1$, otherwise, we accept $H_0$.


**Case 3: Single sided testing towards the right** In this case, our alternative hypothesis $H_1$ is that $\theta>\theta_0$. To compute the $p$-value, we need to look at the following probability
$$
p=\mathbb{P}(\hat{Z}>\hat{z})=1-\Phi(\hat{z})
$$

If $p<\alpha$ we accept $H_1$, otherwise, we accept $H_0$.
___
##### Exercise 1
Consider data from polling - a pollster chose 500 people at random from a large population, and 225 of them said that they prefer $A$ over $B$. Our null hypothesis $H_0$ is that both candidates have equal vote-shares, while $H_1$ is that $\theta_A \neq 0.5$. Can we reject the null hypothesis with a critical probability $\alpha=0.05$ ? What if our alternate hypothesis is one sided $\theta_{\Lambda}<0.5$ ? What if instead of 225 people, now only 200 people support candidate $A$.

![[20250505_182740000_iOS.jpg]]

___
##### Exercise 2
Consider data from a medical trial. Pharma company F administers the drug that is under trial to 100 people picked at random, and administers a placebo to another 100 people picked at random. All the people in the trial have the disease that can potentially be cured by the drug. Out of the people in group 1, 40 people show improvement after 6 months, while for group 2 (the placebo group), 26 people show improvement after 6 months. Our null hypothesis $H_0$ is that the drug is only as good as the placebo. Do we have enough evidence to suggest that the null hypothesis is unlikely at $\alpha=0.05$ ? What about at $\alpha=0.005$ ?

![[20250505_182802000_iOS.jpg]]

___
## Testing Means of Two Populations
The last example above asks us to test the difference between the means of two different populations. Suppose we have $N_1$ samples from one population whose true (unknown) mean is $\theta_1$ and $N_2$ samples from population 2 whose true (unknown) mean is $\theta_2$.

We want to conduct the following hypothesis test - the null hypothesis $H_0$ is that $\theta_1=\theta_2$ and the alternate hypothesis is that $\theta_1>\theta_2$. We can construct estimates for the true means using the sample means as follows
$$
\hat{\Theta}_1=\left(X_1+\ldots+X_{N_1}\right) / N_1
$$
$$
\hat{\Theta}_2=\left(Y_1+\ldots+Y_{N_2}\right) / N_2
$$

Using the CLT, we know that $\hat{\Theta}_1 \sim \mathcal{N}\left(\theta_1, \sigma_1^2 / N_1\right)$ and $\hat{\Theta}_2 \sim \mathcal{N}\left(\theta_2, \sigma_2^2 / N_2\right)$. Assuming the two populations are independent, we can then say that

$$
\hat{\Theta}_1-\hat{\Theta}_2 \sim \mathcal{N}\left(\theta_1-\theta_2, \sigma_1^2 / N_1+\sigma_2^2 / N_2\right)
$$


This gives us a way to perform hypothesis tests. We define $Z$ as follows

$$
Z=\frac{\hat{\Theta}_1-\hat{\Theta}_2}{\sqrt{\hat{S}_1^2 / N_1+\hat{S}_2^2 / N_2}}
$$

Now using the CLT, $Z \sim \mathcal{N}(0,1)$ for large $N_1$ and $N_2$. Notice that we have replaced population variances $\sigma_1^2$ and $\sigma_2^2$ with estimates of the variances, so that they can be calculated from data. Since we are doing the $p$-value test towards the right, we compute it as follows

$$
p=\mathbb{P}(Z>z)
$$

where $z$ is a realization of $Z$ as computed from data. As usual, we compute the $p$-value and then compare to $\alpha$ to make a decision.
___
## Random Processes
How do we study infinite collections of random variables?

**Random Processes:** A random process is an infinite collection of random variables. We will usually denote a random variable from a random process as $X(t)$ where $t$ denotes the index of the random variable.

Intuitively, we can think of random processes as the probabilistic version of a signal. A random variable maps outcomes $\omega \in \Omega$ to real numbers. A random process maps outcomes $\omega \in \Omega$ to functions.

Suppose $A \sim$ Uniform $[-1,1]$ and $B \sim$ Uniform $[-1,1]$ are independent random variables. We can define a random process as follows

$$
X(t)=A t+B, \forall t \in[-2,2] .
$$

Given any particular realization of the random variables $A$ and $B$, we see that $X(t)$ is a straight
line. However, without knowing $A$ and $B, X(t)$ is a collection of uncountably many random variables indexed by $t$.

Similarly, let's say that $\Theta \sim$ Uniform $[0,2 \pi]$. We can define a random process $X(t)$ as follows

$$
X(t)=\cos \left(2 \pi f_0 t+\Theta\right)
$$
___
## Distributions and Independence
A random process $X(t)$ is fully defined if we can compute the joint distribution of it at all finite collection of points $t_1, \dots, t_N$. i.e. we know the joint distribution $f_{X\left(t_1\right), \ldots, X\left(t_N\right)}\left(x_1, \ldots, x_N\right)$.

Two random processes $X(t)$ and $Y(t)$ are independent if for all finite collections of time stamps $t_1, \ldots, t_N$ the following holds

$$
\begin{gathered}
f_{X\left(t_1\right), \ldots, X\left(t_N\right), Y\left(t_1\right), \ldots, Y\left(t_N\right)}\left(x_1, \ldots, x_N, y_1, \ldots, y_N\right)= \\
f_{X\left(t_1\right), \ldots, X\left(t_N\right)}\left(x_1, \ldots, x_N\right) f_{Y\left(t_1\right), \ldots, Y\left(t_N\right)}\left(y_1, \ldots, y_N\right)
\end{gathered}
$$

___
## Statistical and Temporal Perspectives
Since random processes are functions of the index $t$ as well as the experiment outcome $\omega$, they are 2-dimensional objects. When we want to explicitly show the dependence of the random process on experimental outcomes, we will use the notation $X(t, \omega)$.

Temporal perspective: For this view, we fix our outcome $\omega$ and vary the index $t$ (which will represent time). Thus, for each value of $\omega$, we get a fixed function of $t$, i.e. $X(t, \omega)$. This is a horizontal view of $X$.

$$
X\left(t_0, \omega\right), X\left(t_1, \omega\right), \ldots, X\left(t_N, \omega\right)
$$
Statistical perspective: For this view, we fix our time index $t$, and vary the outcomes from the sample space $\omega$. This gives us a collection of possible values for the random process, all evaluated at the same fixed time instant, i.e. $X(t, \omega)$. This is a vertical view of $X$.

$$
\begin{array}{r}
X\left(t, \omega_0\right) \\
X\left(t, \omega_1\right) \\
\vdots \\
X\left(t, \omega_N\right)
\end{array}
$$

### Averages
We can compute the average of a random process along either of the two dimensions.

- Temporal Average: The temporal average of a random process gives us a random variable
$$
\bar{X}(\omega)=\frac{1}{T} \int_0^T X(t, \omega) d t
$$

- Statistical Average: The statistical average of a random process gives us a deterministic function that varies over time.
$$
\mu(t)=\mathbb{E}[X(t)]
$$

It is important to note that these averages are fundamentally different notions, and hence not equal in general.

In general, Statistical Average $\neq$ Temporal Average. However, for special processes, called ergodic processes, the statistical average and temporal average become are equal (and constant).
___
##### Example 1
Examples: Suppose $A \sim$ Uniform $[0,1]$ and $X(t)=A \cos (2 \pi t)$. Observe that the dependence of $X$ on the outcome $\omega$ is hidden through $A$ since $A$ is a function that maps $\omega$ to real numbers. So, more precisely,

$$
X(t, \omega)=A(\omega) \cos (2 \pi t)
$$
However, for ease of analysis and notation, we can usually hide this dependence as done earlier.

Let's look at the temporal view of this random process. If we fix $\omega$ such that $A(\omega)=0.5$ then our random process is just $0.5 \cos (2 \pi t)$. If we want to take the temporal average of our process over the interval $t \in[0,1]$, we can compute it as follows

$$
\bar{X}(\omega)=\frac{1}{1} \int_0^1 A(\omega) \cos (2 \pi t) d t=0 .
$$

Thus the temporal average is $\bar{X}=0$.
Let's look at the statistical view - if we fix a time instant, say $t=1 / 6$, then our random process is $A \cos (\pi / 3)=A / 2$. If we want to compute the statistical average at any time instant $t$, we can do so as follows
$$
\mu(t)=\mathbb{E}[A \cos (2 \pi t)]=0.5 \cos (2 \pi t) .
$$
___
## Mean and Correlation
The mean of a random process is simply its statistical average. The mean function of a random process is defined as
$$
\mu(t)=\mathbb{E}[X(t)] .
$$

The autocorrelation function of a random process $X(t)$ is defined as

$$
R_X\left(t_1, t_2\right) \triangleq \mathbb{E}\left[X\left(t_1\right) X\left(t_2\right)\right] .
$$


The autocorrelation is fairly straightforward to compute. As an exercise, try computing it for the processes we have discussed earlier. The tricky part about autocorrelations is understanding their interpretation. The autocorrelation function tries to measure how closely two different timestamps of a random process are related.

For two separate random processes $X(t)$ and $Y(t)$, we can also define the correlation function between them. The correlation function between $X$ and $Y$ is defined as

$$
R_{X, Y}\left(t_1, t_2\right)=\mathbb{E}\left[X\left(t_1\right) Y\left(t_2\right)\right]
$$

We say that $X(t)$ and $Y(t)$ are uncorrelated if

$$
R_{X, Y}\left(t_1, t_2\right)=\mathbb{E}\left[X\left(t_1\right)\right] \mathbb{E}\left[Y\left(t_2\right)\right] .
$$

___
## Wide Sense Stationary Processes
Armed with the definitions above, we can now define Wide Sense Stationary (WSS) random processes. These processes have nice properties that allow for analysis in the frequency domain using Fourier transforms.

A WSS random process must satisfy the following two properties.

1. $\mu_X(t)=\mu, \forall t$, i.e. the statistical average is constant over time.

2. $R_X\left(t_1, t_2\right)=R\left(t_1-t_2\right), \forall t_1, t_2$, i.e. the auto correlation only depends on the difference between timestamps and not where they are actually located.

Next, we list some important properties of WSS processes.

1. The autocorrelation function for a WSS process can be written down using a single variable $\tau$ that represents the difference between the two timestamps $t_1-t_2$. So

$$
R_X\left(t_1, t_2\right)=R_X\left(t_1-t_2\right)=R_X(\tau)=\mathbb{E}[X(\tau) X(0)] .
$$

2. $R_X(0)$ represents the average power of the signal.

$$
R_X(0)=\mathbb{E}[X(0) X(0)]=\mathbb{E}[X(t) X(t)]=\mathbb{E}\left[X^2(t)\right]
$$

3. $R_X(\tau)$ is symmetric around 0 .

$$
R_X(\tau)=R_X(-\tau)
$$

4. $R_X(\tau)$ has a peak at zero. $\left|R_X(\tau)\right| \leq R_X(0)$


##### Example 2
Suppose $X(t)=\cos (2 \pi f t+\Theta)$ and $\Theta \sim$ Uniform $[0, \pi]$. Let's compute the mean and autocorrelation function

$$
\mu_X(t)=\mathbb{E}[X(t)]=\int_0^{2 \pi} \frac{1}{2 \pi} \cos (2 \pi f t+\theta) d \theta=0
$$
$$
\begin{aligned}
R_X\left(t_1, t_2\right) & =\mathbb{E}\left[X\left(t_1\right) X\left(t_2\right)\right]=\int_0^{2 \pi} \frac{1}{2 \pi} \cos \left(2 \pi f t_1+\theta\right) \cos \left(2 \pi f t_2+\theta\right) d \theta \\
& =\int_0^{2 \pi} \frac{1}{2 \pi}\left(0.5 \cos \left(2 \pi f\left(t_1-t_2\right)\right)+0.5 \cos \left(2 \pi f\left(t_1+t+2\right)+2 \theta\right)\right) d \theta \\
& =\frac{1}{2} \cos \left(2 \pi f\left(t_1-t_2\right)\right)
\end{aligned}
$$
##### Exercise 3
Exercise: Consider $X(t) \sim A t$ where $A \sim$ Uniform $[-1,1]$. Is $X(t)$ WSS?



___
## Power Spectral Density
The power spectral density of a WSS random process is defined as the Fourier Transform of the autocorrelation function.

$$
S_X(\omega)=\int_{-\infty}^{\infty} R_X(\tau) e^{-j \omega \tau} d \tau=\mathcal{F}\left(R_X(\tau)\right)
$$


Why would we call this the power spectral density of a random process? We will try to understand this through an example. Suppose $\Theta \sim$ Uniform $[0,2 \pi]$ and $X(t) \sim \cos (2 \pi f t+\Theta))$. If someone asked you to draw the Fourier transform of this signal - what would you guess? Two symmetric delta functions in the frequency domain?

Let's compute the autocorrelation function first

$$
\begin{aligned}
R_X(\tau) & =\mathbb{E}[X(0) X(\tau)] \\
& =\frac{\cos (2 \pi f \tau)}{2}
\end{aligned}
$$

Now, we can compute the Fourier transform of $R_X(\tau)$. Note the following well know result

$$
\mathcal{F}(\cos (2 \pi f t))=\frac{\pi}{2} \delta(\omega-2 \pi f)+\frac{\pi}{2} \delta(\omega+2 \pi f)
$$


This gives us the power spectral density for our random process

$$
S_X(\omega)=\frac{\pi}{2} \delta(\omega-2 \pi f)+\frac{\pi}{2} \delta(\omega+2 \pi f)
$$
___