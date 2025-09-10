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

___