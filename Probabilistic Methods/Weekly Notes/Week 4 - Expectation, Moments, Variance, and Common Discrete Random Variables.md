## Expectation

The mean and standard deviation can be seen from the lens of random variables using expectation.

The expectation of a random variable $X$ is 

$$
\mathbb{E}[X]=\sum_{x \cong X(\Omega)} x p_X(x) .
$$
Expectation is the mean of the random variable $X$. We can think of $p_X(x)$ as the percentage of times the the random variable $X$ is $x$. When we sum over each $x$ multiplied by $p_{X}(x)$ we get the summation of the contribution of each $x$ which is the mean.

![[Pasted image 20250212020001.png]]

---
#### Example

Flip an unfair coin, where the probability of getting a head is $\frac{3}{4}$. Let $X$ be a random variable such that $X=1$ means getting a head. Then we can show that $p_X(1)=\frac{3}{4}$ and $p_X(0)=\frac{1}{4}$. The expectation of $X$ is therefore

$$
\mathbb{E}[X]=(1) p_X(1)+(0) p_X(0)=(1)\left(\frac{3}{4}\right)+(0)\left(\frac{1}{4}\right)=\frac{3}{4}
$$
---
#### Expectation VS Average

The difference between $\mathbb{E}(X)$ and the average is that the former is calculated from the ideal histogram not the empirical histogram. As $N$ samples approaches infinity we expect $\mathbb{E}(X)$ and the average to approach the same number.

---
### Existence of Expectation

Not every PMF has an expectation because we can construct a PMF such that the expectation is undefined. A PMF has an expectation when it is **absolutely summable**.

A discrete random variable $X$ is absolutely summable if 

$$
\mathbb{E}[|X|] \stackrel{\text { def }}{=} \sum_{x \in X(\Omega)}|x| p_X(x)<\infty .
$$

Not all random variables have a finite expectation.

***

### Properties of Expectation

The expectation of a random variable $X$ has the following properties

* Function. For any function $g$,
$$
\mathbb{E}[g(X)]=\sum_{x \in X(\Omega)} g(x) p_X(x)
$$
* Linearity. For any function $g$ and $h$,
$$
\mathbb{E}[g(X)+h(X)]=\mathbb{E}[g(X)]+\mathbb{E}[h(X)]
$$

* Scale. For any constant $c$,
$$
\mathbb{E}[c X]=c \mathbb{E}[X]
$$

* DC Shift. For any constant $c$,
$$
\mathbb{E}[X+c]=\mathbb{E}[X]+c
$$
---
## Moments and Variance

### Moment

The $k_{th}$ moment of a random variable $X$ is

$$
\mathbb{E}\left[X^k\right]=\sum_x x^k p_X(x)
$$
We call $\mathbb{E}(X)$ the first moment and $\mathbb{E}(X^{2})$ the second moment.

---
#### Example 

Flip a coin 3 times. Let $X$ be the number of heads. Then

$$
p_X(0)=\frac{1}{8}, \quad p_X(1)=\frac{3}{8}, p_X(2)=\frac{3}{8}, p_X(3)=\frac{1}{8}
$$

The second moment $\mathbb{E}\left[X^2\right]$ is

$$
\mathbb{E}\left[X^2\right]=(0)^2\left(\frac{1}{8}\right)+(1)^2\left(\frac{3}{8}\right)+(2)^2\left(\frac{3}{8}\right)+(4)^2\left(\frac{1}{8}\right)=3
$$
---

### Variance

The variance of a random variable $X$ is 
$$
\operatorname{Var}[X]=\mathbb{E}\left[(X-\mu)^2\right]
$$
$$
\operatorname{Var}[X]=\mathbb{E}\left[X^2\right]-\mathbb{E}[X]^2
$$
where $\mu=\mathbb{E}[X]$ is the expectation of $X$. The Variance of a random variable $X$ has the following properties

* Scale. For any constant $c$,
$$
\operatorname{Var}[c X]=c^2 \operatorname{Var}[X]
$$
* DC Shift. For any constant c,
$$
\operatorname{Var}[X+c]=\operatorname{Var}[X]
$$
---
## Common Discrete Random Variables

### Indicator Random Variable

Indicator random variables can only take values in the set $\{0,1\}$. If the set of outcomes for which the indicator random variable maps to 1 is denoted by $A$ then the corresponding indicator variable is denoted by $\mathbb{1}_A$ 

$$
\mathbb{1}_A(\omega)= \begin{cases}1 & \text { if } \omega \in A \\ 0 & \text { otherwise }\end{cases}
$$
---
### Bernoulli Random Variable

The Bernoulli Random Variable has two states; either 1 or 0. Bernoulli Random Variables are useful for binary state events.

#### Definition
---

Let $X$ be a Bernoulli random variable. Then, the PMF of $X$ is

$$
p_X(0)=1-p, \quad p_X(1)=p
$$

where $0<p<1$ is called the Bernoulli parameter, it controls the probability of obtaining 1. We write

$$
X \sim \operatorname{Bernoulli}(p)
$$

to say that $X$ is drawn from a Bernoulli distribution with a parameter $p$. 

----
#### Properties

* The Expectation is equal to the Bernoulli parameter $p$
$$\mathbb{E}[X]=p$$
* The Second Moment is equal to the Bernoulli parameter $p$
$$\mathbb{E}\left[X^2\right]=p$$
* Finally the variance
$$\operatorname{Var}[X]=p(1-p)$$


___
### Binomial Random Variable

Suppose we flip a coin $n$ times count the number of heads. Since each flip is a random variable (Bernoulli), the sum is also a random variable, called Binomial random variable.

#### Definition
---
Let $X$ be a binomial random variable. Then, the PMF of $X$ is

$$
p_X(k)=\binom{n}{k} p^k(1-p)^{n-k}, \quad k=0,1, \ldots, n
$$

where $0<p<1$ is the binomial parameter, and $n$ is the total number of states. We write

$$
X \sim \operatorname{Binomial}(n, p)
$$

to say that $X$ is drawn from a binomial distribution with a parameter $p$ of size $n$.

---
### Geometric Random Variable

When we are interested in trying a binary experiment until we success. For example we want to keep flipping a coin until we get heads. In this case the random variable can be defined as the outcome of many tails followed by a final heads. This is called the geometric random variable

---
#### Definition

Let $X$ be a geometric random variable. Then, the PMF of $X$ is

$$

p_X(k)=(1-p)^{k-1} p, \quad k=1,2, \ldots

$$

where $0<p<1$ is the geometric parameter. We write

$$
X \sim \text { Geometric }(p)
$$

to say that $X$ is drawn from a geometric distribution with a parameter $p$.

---
#### Properties

If $X \sim \operatorname{Geometric}(p)$, then
*  $\mathbb{E}[X]=\frac{1}{p}$
* $\mathbb{E}\left[X^2\right]=\frac{2}{p^2}-\frac{1}{p}$
* $\operatorname{Var}[X] =\frac{1-p}{p^2}$

---
### Poisson Random Variable

In many system, the arrivals of events are typically modeled as a Poisson random variable. The Poisson random variable models the number of occurrences of some event over a period of time or space.

---
#### Definition

Let $X$ be a Poisson random variable. Then, the PMF of $X$ is

$$
p_X(k)=\frac{\lambda^k}{k!} e^{-\lambda}, \quad k=0,1,2, \ldots
$$

where $\lambda>0$ is the Poisson rate. We write

$$
X \sim \operatorname{Poisson}(\lambda)
$$

to say that $X$ is drawn from a Poisson distribution with a parameter $\lambda$. The parameter $\lambda$ is the rate of arrival.

---
#### Properties

* $\mathbb{E}[X] = \lambda$
* $\mathbb{E}[X^2] = \lambda^2 + 1$ 
* $var(X) = \lambda$
