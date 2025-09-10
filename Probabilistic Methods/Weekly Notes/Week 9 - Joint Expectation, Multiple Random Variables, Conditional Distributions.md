___
## Joint Expectation
Let $X$ and $Y$ be two random variables. The **joint expectation** is 

$$
\mathbb{E}[X Y]=\sum_{y \in \Omega_Y} \sum_{x \in \Omega_X} x y \cdot p_{X, Y}(x, y)
$$
$$
\mathbb{E}[X Y]=\int_{y \in \Omega_Y} \int_{x \in \Omega_X} x y \cdot f_{X, Y}(x, y) d x d y
$$

___
### Covariance
In many practical problems, we work with central moments, i.e., $\mathbb{E}\left[\left(X-\mu_X\right)^2\right]$, instead of $\mathbb{E}[X^2]$. This is also true for the covariance between two random variables where we use centralized random variables. The covariance between two random variables $X$ and $Y$ is defined as follows.

$$
\operatorname{cov}(X, Y) \triangleq \mathbb{E}\left[\left(X-\mu_X\right)\left(Y-\mu_Y\right)\right]
$$

Where $\mu_x = \mathbb{E}[X]$ and $\mu_y = \mathbb{E}[Y]$ 

Covariance satisfies many important properties.

1. $\operatorname{cov}(X, Y)=\mathbb{E}[X Y]-\mathbb{E}[X] \mathbb{E}[Y]$

2. $\operatorname{cov}(X, X)=\operatorname{var}(X)$

3. $\operatorname{var}(X+Y)=\operatorname{var}(X)+\operatorname{var}(Y)+2 \operatorname{cov}(X, Y)$

4. If $X$ and $Y$ are independent, $\operatorname{cov}(X, Y)=0$.

##### Exercise 1
Prove each of the identities above.

![[20250414_202753000_iOS.jpg]]

##### Exercise 2
Suppose we sample points $(X, Y)$ uniformly from the unit circle centered on the origin. What is the joint distribution of $X, Y$. Find the marginal densities of $X$ and $Y$, and use them to show that $X$ and $Y$ are not independent.

![[20250414_202740000_iOS.jpg]]

##### Exercise  3
Let $Y=a X+b$. Compute $\operatorname{Cov}(X, Y)$.

![[20250414_202731000_iOS.jpg]]

___
### Correlation Coefficient
The **correlation coefficient** $\rho$ is the cosine angle of the centralized variables. That is,

$$\begin{aligned} \rho & =\cos \theta \\ & =\frac{\mathbb{E}\left[\left(X-\mu_X\right)\left(Y-\mu_Y\right)\right]}{\sqrt{\mathbb{E}\left[\left(X-\mu_X\right)^2\right] \mathbb{E}\left[\left(Y-\mu_Y\right)^2\right]}} .\end{aligned}$$

The denominator of the above expression is just $Var(X)$ and $Var(Y)$, therefore

$$
\rho_{X Y} \triangleq \frac{\operatorname{cov}(X, Y)}{\sqrt{\operatorname{var}(X) \operatorname{var}(Y)}} .
$$

The correlation coefficient also satisfies the following properties.

1. $\rho$ is always between -1 and 1, i.e., $-1 \leq \rho \leq 1$. This is due to the cosine angle definition

2. When $X=Y$ (fully correlated), $\rho=+1$

3. When $X=-Y$ (negatively correlated), $\rho=-1$

4. When $X$ and $Y$ are uncorrelated, $\rho=0$

Intuitively covariance and correlation coefficient measure the directional dependence of two random variables. If $X$ being large implies that $Y$ will also be large then they have a positive covariance and correlation. If the opposite is true then they will have a negative covariance and correlation.

We have already discussed in the properties above that independence of $X$ and $Y$ guarantees covariance and correlation coefficient to be zero, i.e. if $X$ and $Y$ are independent, then they are uncorrelated.

Is the converse true, i.e. if $X$ and $Y$ are uncorrelated, are they independent? Turns out, the answer is no. Correlation is strictly weaker than independence. Independence implies zero correlation, but zero correlation does not imply independence.

##### Exercise 4
Let $X \sim$ Uniform $(0,1)$. Let $Y=a X+b$ where $a \neq 0$ like in exercise 3. Show that $\operatorname{cov}(X, Y)=a \operatorname{var}(X)$. Further, show that $\rho_{X Y}=\frac{a}{|a|}$.

![[20250414_202719000_iOS.jpg]]

##### Exercise 5
Consider $Z \sim \operatorname{Uniform}(0,2 \pi)$. Let $X=\sin (Z)$ and $Y=\cos (Z)$. Compute $\operatorname{cov}(X, Y)$. Check if the two random variables are independent - what do you conclude?

![[20250414_202708000_iOS.jpg]]

______
## Multiple Random Variables
Just as we defined joint PMFs, PDFs, and CDFs for 2 random variables we can do so for a collection of $N$ random variables.

$$
p_{X_1 X 2 \ldots X_n}\left(x_1, x_2, \ldots, x_n\right)=\mathbb{P}\left(X_1=x_1, X_2=x_2, \ldots, X_n=x_n\right) .
$$

For any $A \in \mathbb{R}^N$ and $N$ continuous random variables.
$$
\mathbb{P}(\mathbf{X} \in A)=\int_A \ldots \int f_{X_1 \ldots X_n}\left(x_1, \ldots, x_n\right) d x_1 \ldots d x_n
$$
The CDF satisfies
$$
F_{X_1 \ldots X_n}\left(x_1, \ldots, x_n\right)=\mathbb{P}\left(X_1 \leq x_1, \ldots, X_n \leq x_n\right)
$$

A collection of $N$ random variables is independent of one another if their joint CDF factorizes. i.e. 
$$
F_{X_1 \ldots X_n}\left(x_1, \ldots, x_n\right)=F_{X_1}\left(x_1\right) \ldots F_{X_n}\left(x_n\right)
$$

___
## Conditional Distributions
Previously we discussed conditional probabilities. The probability $X = x$ given $Y = y$. Now we discuss the concepts of conditional PMF and CDF.

___
### Conditional PMF
Let $X$ and $Y$ be  two discrete random variables. The conditional PMF of $X$ given $Y$ is
$$
p_{X \mid Y}(x \mid y)=\frac{p_{X, Y}(x, y)}{p_Y(y)}
$$
We can use this to compute the probabilities conditioned on the event $Y = y$
$$
\mathbb{P}(X \in A \mid Y=y)=\sum_{x \in A} p_{X \mid Y}(x \mid y)
$$
Similar to the law of total probability 
$$
\mathbb{P}(X \in A)=\sum_{x \in A} \sum_{y \in \mathcal{Y}} p_{X \mid Y}(x \mid y) p_Y(y)
$$
##### Exercise 6
Consider $X=\{$ sum of two coin tosses $\}$ and $Y=\{$ the first coin toss $\}$.
Find the conditional PMFs $p_{X \mid Y}(x \mid 1)$ and $p_{X \mid Y}(x \mid 0)$.

![[20250414_202657000_iOS.jpg]]

___
### Conditional PDFs
Let $X$ and $Y$ be two continuous random variables. The conditional PDF of $X$ given $Y$ is 
$$
f_{X \mid Y}(x \mid y)=\frac{f_{X, Y}(x, y)}{f_Y(y)}
$$

We can use this to compute the probabilities conditioned on the event $Y = y$.
$$
\mathbb{P}(X \in A \mid Y=y)=\int_{x \in A} f_{X \mid Y}(x \mid y) d x
$$

Similar to the law of total probability
$$
\mathbb{P}(X \in A)=\int_{x \in A} \int_{y \in \mathcal{Y}} f_{X \mid Y}(x \mid y) f_Y(y) d y d x
$$

##### Exercise 7
Suppose $X \sim \operatorname{Uniform}(0,1)$ and $N \sim \mathcal{N}(0,1)$ are independent random variables. Let $Y_1=X N$ and $Y_2=X+N$. Find the conditional PDF of $Y_1$ and $Y_2$ given $X$.

![[20250414_202648000_iOS.jpg]]

___
### Conditional CDFs
For jointly continuous random variables, we can write the conditional CDF as 

$$
F_{X \mid Y}(x \mid y)=\mathbb{P}(X \leq x \mid Y=y)=\sum_{u \leq x} p_{X \mid Y}(u \mid y)
$$
The CDF of two jointly continuous random variables can also be computed as follows.

$$
F_{X \mid Y}(x \mid y)=\int_{-\infty}^x f_{X \mid Y}(u \mid y) d u
$$

##### Exercise 8
Suppose $X \sim \operatorname{Uniform}(1,2)$ and $Y \sim \operatorname{Exponential}(X)$. Find the conditional PDF of $Y$ given $X$. Also find CDF of $Y$.

![[20250414_202639000_iOS.jpg]]

___