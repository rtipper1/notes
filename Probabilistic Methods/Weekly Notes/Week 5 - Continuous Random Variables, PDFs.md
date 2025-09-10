Continuous Random Variables are similar to discrete random variables with some key differences. 

1. How do we assign probabilities to continuous intervals instead of discrete points? We can no longer count sets to calculate the sizes of events.

2. How do we unify the seemingly disparate notions of discrete and continuous random variables
___
## Probability Density Function (PDF)
Suppose we are given an event $A$ that is a subset of the sample space $\Omega$. In order to find the probability of $A$ we need to measure the relative size of the set.

Given $A = [2,3]$ and $\Omega = [0,5]$ we can describe the probability of event $A$ using integration.

$$
\mathbb{P}[\{x \in[2,3]\}]=\frac{\text { "size" of } A}{\text { "size" of } \Omega}=\frac{\int_A d x}{\int_{\Omega} d x}=\frac{\int_2^3 d x}{\int_0^5 d x}=\frac{1}{5} .
$$
![[Pasted image 20250224164711.png]]


A more general form can be written as 

$$
\begin{aligned}
\mathbb{P}[\{x \in A\}]=\frac{\int_A d x}{\int_{\Omega} d x} & =\frac{\int_A d x}{|\Omega|} \\
& =\int_A \underbrace{\frac{1}{|\Omega|}}_{\text {equally important over } \Omega} d x .
\end{aligned}
$$

This equation operates under the assumption that all events are equiprobable. If we want to relax this assumption we can write the equation in a form that integrates over a Probability Density Function $f_X(x)$ 

$$
\mathbb{P}[\{x \in A\}=\int_A \underbrace{f_X(x)}_{\text {replace } 1 /|\Omega|} d^{\prime} x .
$$

![[Pasted image 20250224165000.png]]

---
## Details of Probability Density Function
Let $X$ be a continuous random variable. The probability density function (PDF) of $X$ is a function $f_X: \Omega \rightarrow \mathbb{R}$ that, when integrated over an interval $[a, b]$, yields the probability of obtaining $a \leq X \leq b$ :

$$
\mathbb{P}[a \leq X \leq b]=\int_a^b f_X(x) d x
$$

A continuous random variable $X$ is defined by its probability density function $f_X$ which must satisfy the following criteria.

* **Non-negativity**: $f_X(x) \geq 0 \text{  for all  } x \in \Omega$

- **Unity**: $\int_{\Omega} f_X(x) d x=1$

- **Measure of a set**: $\mathbb{P}[\{x \in A\}]=\int_A f_X(x) d x$

The PDF $f_X(x)$ can be thought of intuitively as the probability per unit length at the point $x$. Importantly the probability that $X$ takes any specific value $x$ is zero.

$$
\mathbb{P}(X=x)=0
$$

However, the probability that $X$ takes a value in the neighborhood of $x$ is proportional to $f_X(x)$.

$$
\mathbb{P}\left(x-\frac{d x}{2} \leq X \leq x+\frac{d x}{2}\right) \approx f_X(x) d x .
$$
___
## Relating to PMF
The probability density function is more general than the probability mass function. To see this consider discrete random variable $X$ with a PMF $p_X(x)$. We can write $p_X$ as a train of delta functions.

$$
f_X(x)=\sum_{x_k \in \Omega} p_X\left(x_k\right) \delta\left(x-x_k\right)
$$

Recall the definition of a delta function $\delta(x-a)$. It integrates as follows

$$
\int_{x \in A} \delta(x-a) d x=\left\{\begin{array}{l}
1, \text { if } a \in A \\
0, \text { otherwise }
\end{array}\right.
$$

While $f_X(x)$ written as a train of delta functions is not a well-defined PDF, this provides the intuition behind the connection between the two.