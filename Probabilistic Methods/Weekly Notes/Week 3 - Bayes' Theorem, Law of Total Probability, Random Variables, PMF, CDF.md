## Bayes' Theorem and the Law of Total Probability

### Bayes' Theorem

For any two events $A$ and $B$ such that $\mathbb{P}[A] > 0$ and $\mathbb{P}[B] > 0$,

$$
\mathbb{P}[A \mid B]=\frac{\mathbb{P}[B \mid A] \mathbb{P}[A]}{\mathbb{P}[B]}
$$
Bayes' Theorem provides a way to switch $\mathbb{P}[A|B]$ and  $\mathbb{P}[B|A]$

### The Law of Total Probability

Let $\left\{A_1, \ldots, A_n\right\}$ be a partition of $\Omega$, i.e. $A_1, \dots, A_n$ are disjoint and $\Omega=A_1 \cup \cdots \cup A_n$. Then, for any $B \subseteq \Omega$,

$$
\mathbb{P}[B]=\sum_{i=1}^n \mathbb{P}\left[B \mid A_i\right] \mathbb{P}\left[A_i\right]
$$
The law of total probability can be understood as follows. If the sample space $\Omega$ consists of disjoint subsets $A_1,\dots,A_n$, we can compute the probability $\mathbb{P}[B]$ by summing over its portion $\mathbb{P}\left[B \cap A_1\right], \ldots, \mathbb{P}\left[B \cap A_n\right]$. However, each intersection can be written as

$$
\mathbb{P}\left[B \cap A_i\right]=\mathbb{P}\left[B \mid A_i\right] \mathbb{P}\left[A_i\right]
$$
In other words, we write $\mathbb{P}\left[B \cap A_i\right]$ as the conditional probability $\mathbb{P}\left[B \mid A_i\right]$ times the prior probability $\mathbb{P}\left[A_i\right]$. When we sum all these intersections, we obtain the overall probability. See figure below for a graphical portrayal.

![[Pasted image 20250206134707.png]]

### Example

Suppose there are three types of players in a tennis tournament: $A$, $B$, and $C$. Fifty percent of the contestants in the tournament are $A$ players, $25 \%$ are $B$ players, and $25 \%$ are $C$ players. Your chance of beating the contestants depends on the class of the player, as follows:

* 0.3 against an A player
* 0.4 against a B player
* 0.5 against a C player

If you play a match in this tournament, what is the probability of your winning the match? Supposing that you have won a match, what is the probability that you played against an $A$ player?

#### Solution

First list the probabilities that any given player is of each type,

$$
\mathbb{P}[A]=0.5, \quad \mathbb{P}[B]=0.25, \quad \mathbb{P}[C]=0.25
$$
Now let $W$ be the event that you win the match. Then the conditional probabilities are as follows.

$$
\mathbb{P}[W \mid A]=0.3, \quad \mathbb{P}[W \mid B]=0.4, \quad \mathbb{P}[W \mid C]=0.5
$$


![[Pasted image 20250206135402.png]]

By the law of total probability we can show that the probability of winning the match is 

$$
\begin{aligned}
\mathbb{P}[W] & =\mathbb{P}[W \mid A] \mathbb{P}[A]+\mathbb{P}[W \mid B] \mathbb{P}[B]+\mathbb{P}[W \mid C] \mathbb{P}[C] \\
& =(0.3)(0.5)+(0.4)(0.25)+(0.5)(0.25)=0.375
\end{aligned}
$$
By the Bayes' Theorem given that you have won the match, the probability of $A$ given $W$ is

$$
\mathbb{P}[A \mid W]=\frac{\mathbb{P}[W \mid A] \mathbb{P}[A]}{\mathbb{P}[W]}=\frac{(0.3)(0.5)}{0.375}=0.4
$$


### Summary

* Bayes' Theorem switches the role of the conditioning, from $\mathbb{P}[A|B]$ to $\mathbb{P}[B|A]$

$$
\mathbb{P}[\text { win the game } \mid \text { play with } \mathrm{A}] \text { and } \mathbb{P}[\text { play with } \mathrm{A} \mid \text { win the game }] \text {. }
$$

* The law of total probability decomposes an event into smaller events.

$$
\mathbb{P}[\text {win}]=\mathbb{P}[\text { win} \mid A] \mathbb{P}[A]+\mathbb{P}[\text { win} \mid B] \mathbb{P}[B] .
$$


## Random Variables

A **random variable** $X$ is a function $X: \Omega \rightarrow \mathbb{R}$ that maps an outcome $\xi \in \Omega$ to a number $X(\xi)$ on the real line. Random variables are mappings  from events to numbers. We call $X$ a random variable because it has states and it is not deterministic.

#### Example 
Suppose we flip a fair coin so that $\Omega=\{$ head, tail $\}$. We can define the random variable $X: \Omega \rightarrow \mathbb{R}$ as
$$
X(\text { head })=1, \quad \text { and } \quad X(\text { tail })=0
$$
When we write $\mathbb{P}[X = 1]$ we actually mean $\mathbb{P}[\text { head }]$, there is no difference between the two.

#### Example
Flip a coin 2 times. The sample space $\Omega$ is

$$
\Omega=\{(\text { head }, \text { head }),(\text { head }, \text { tail }),(\text { tail }, \text { head }),(\text { tail , tail })\} .
$$

Suppose that $X$ is a random variable that maps an outcome to a number representing the sum of "head," i.e.,
$$
X(\cdot)=\text { number of heads. }
$$

Then, for the $4 \xi$ 's in the sample space there are only 3 distinct numbers. More precisely, if we let $\xi_1=($ head, head $), \xi_2=($ head, tail $), \xi_3=($ tail, head $), \xi_4=($ tail, tail $)$, then, we have

$$
X\left(\xi_1\right)=2, \quad X\left(\xi_2\right)=1, \quad X\left(\xi_3\right)=1, \quad X\left(\xi_4\right)=0
$$

A pictorial illustration of this random variable is shown below This example shows that the mapping defined by the random variable is not necessarily a one-to-one mapping because multiple outcomes can be mapped to the same number.

![[Pasted image 20250212003601.png]]

### Probability Measure of Random Variable

Seems difficult but is not. 
$$
E=\{\xi \in \Omega \mid X(\xi)=a\} .
$$
This is the set that contains all possible $\xi$ such that $X(\xi) = a$. Therefore the probability of $X = a$ we are saying find the size of the set $E$. To find the size of the set $E$ we take the pre-image (inverse) of the random variable defined below. Think of this as a reverse mapping from the output of the random variable to the event it represents. 

$$
X^{-1}(a) \stackrel{\text { def }}{=}\{\xi \in \Omega \mid X(\xi)=a\} .
$$

We notice that the pre-image $X^{-1}(a)$ is the same as the event $E$. Therefore

$$
\mathbb{P}[X=a]=\mathbb{P}\left[X^{-1}(a)\right] = \mathbb{P}(E) 
$$

![[Pasted image 20250212004427.png]]

#### Example 
Throw a die twice. The sample space is then
$$
\Omega=\{, 1,1),(1,2), \ldots,(6,6)\}
$$

These elements can be translated to 36 outcomes:

$$
\xi_1=(1,1), \xi_2=(1,2), \ldots, \xi_{36}=(6,6)
$$
Let
$$
X=\text { sum of two numbers. }
$$

Then, if we want to find the probability of getting $X=7$, we can trace back and ask: Among the 36 outcomes, which of those $\xi_i$ 's will give us $X(\xi)=7$ ? Or, what is the set $X^{-1}(7) ?$ To this end, we can write
$$
\begin{aligned}
\mathbb{P}[X=7]= & \mathbb{P}[\{(1,6),(2,5),(3,4),(4,3),(5,2),(6,1)\}] \\
= & \mathbb{P}[(1,6)]+\mathbb{P}[(2,5)]+\mathbb{P}[(3,4)] \\
& +\mathbb{P}[(4,3)]+\mathbb{P}[(5,2)]+\mathbb{P}[(6,1)] \\
= & \frac{1}{36}+\frac{1}{36}+\frac{1}{36}+\frac{1}{36}+\frac{1}{36}+\frac{1}{36}=\frac{1}{6}
\end{aligned}
$$

## Probability Mass Function (PMF)

The probability mass function (PMF) of a random variable $X$ is a function which specifies the probability of obtaining a number $X(\xi)=x$. We denote a PMF as

$$
p_X(x)=\mathbb{P}[X=x]
$$

The set of all possible states of $X$ is denoted as $X(\Omega)$. The Probability Mass function is a histogram summarizing the probability of each state $X$ takes.

### Normalization Property

A PMF should satisfy the condition that.
$$
\begin{aligned}
&\sum_{x \in X(\Omega)} p_X(x)=1
\end{aligned}
$$
#### PMF Versus Histogram

A histogram is a plot that shows the frequency of a state. With enough samples a histogram will eventually approach the theoretical PMF. A histogram generated from an experiment is an empirical histogram. They will vary slightly with each experiment. Eventually they will converge to an ideal histogram, a PMF.

![[Pasted image 20250212010010.png]]

PMF's can be thought of as ideal histograms of random variables

### Cumulative Distribution Function

PMF's are technically not functions because the impulse in the histogram are delta functions. We handle this with the Cumulative Distribution Function (CDF).

Let $X$ be a discrete random variable with $\Omega=\left\{x_1, x_2, \ldots\right\}$. The cumulative distribution function $(C D F)$ of $X$ is

$$
F_X\left(x_k\right) \stackrel{\text { def }}{=} \mathbb{P}\left[X \leq x_k\right]=\sum_{\ell=1}^k p_X\left(x_{\ell}\right)
$$

If $\Omega=\{\ldots,-1,0,1,2, \ldots\}$, then the $C D F$ of $X$ is

$$
F_X(k) \stackrel{\text { def }}{=} \mathbb{P}[X \leq k]=\sum_{\ell=-\infty}^k p_X(\ell)
$$
A CDF is essentially the sum of a PMF from $-\infty$ to $x$, where the variable $x'$ in the sum is a dummy variable.

#### Example

Consider a random variable $X$ with PMF $p_X(0)=\frac{1}{4}, p_X(1)=\frac{1}{2}$ and $p_X(4)=\frac{1}{4}$. The CDF of $X$ can be computed as

$$
\begin{aligned}
& F_X(0)=\mathbb{P}[X \leq 0]=p_X(0)=\frac{1}{4} \\
& F_X(1)=\mathbb{P}[X \leq 1]=p_X(0)+p_X(1)=\frac{3}{4} \\
& F_X(4)=\mathbb{P}[X \leq 4]=p_X(0)+p_X(1)+p_X(4)=\frac{4}{4}
\end{aligned}
$$

As shown in below the CDF of a discrete random variable is a staircase function.

![[Pasted image 20250212010957.png]]

### Properties of the CDF

* The CDF is a sequence of increasing unit steps.
* The maximum of the CDF is when $x=\infty: F_X(+\infty)=1$.
* The minimum of the CDF is when $x=-\infty: F_X(-\infty)=0$.
* The unit steps have jumps at positions where $p_X(x)>0$.
* 

### Converting Between PMF and CDF

If $X$ is a discrete random variable, then the PMF of $X$ can be obtained from the CDF by

$$
p_X\left(x_k\right)=F_X\left(x_k\right)-F_X\left(x_{k-1}\right)
$$

where we assumed that $X$ has a countable set of states $\left\{x_1, x_2, \ldots\right\}$. If the sample space of the random variable $X$ contains integers from $-\infty$ to $+\infty$, then the PMF can be defined as

$$
p_X(k)=F_X(k)-F_X(k-1)
$$

#### Example

Continuing with the example in Figure 3.13, if we are given the CDF

$$
F_X(0)=\frac{1}{4}, \quad F_X(1)=\frac{3}{4}, \quad F_X(4)=1
$$

how do we find the PMF? We know that the PMF will have non-negative values only at $x=0,1,4$. For each of these $x$, we can show that

$$
\begin{aligned}
& p_X(0)=F_X(0)-F_X(-\infty)=\frac{1}{4}-0=\frac{1}{4} \\
& p_X(1)=F_X(1)-F_X(0)=\frac{3}{4}-\frac{1}{4}=\frac{1}{2} \\
& p_X(4)=F_X(4)-F_X(1)=1-\frac{3}{4}=\frac{1}{4}
\end{aligned}
$$




