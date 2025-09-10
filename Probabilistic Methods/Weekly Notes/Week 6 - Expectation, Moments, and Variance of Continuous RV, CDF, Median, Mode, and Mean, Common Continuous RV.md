___
## Expectation, Moment, and Variance
Similarly to discrete random variables and PMF's we can define expectation, moment, and variance for continuous random variables and PDF's.

___
### Expectation
The **expectation** of a continuous random variable $X$ is 

$$
\mathbb{E}[X]=\int_{\Omega} x f_X(x) d x
$$

Notice that this is the same as for a discrete random variable but with an integral instead of a summation. Similarly the following properties can be defined for the expectation of a continuous random variable.

$$\mathbb{E}\left[X_1+X_2\right]=\mathbb{E}\left[X_1\right]+\mathbb{E}\left[X_2\right] . $$
$$\mathbb{E}[a X]=a \mathbb{E}[X] . $$
$$\mathbb{E}[X+a]=\mathbb{E}[X]+a $$
$$\mathbb{E}[g(X)]=\int_{x=-\infty}^{\infty} g(x) f_X(x) d x$$
___
### Moment and Variance
The $k_{th}$ **moment** of a continuous random variable $X$ is defined as follows.

$$
\mathbb{E}\left[X^k\right]=\int_{x=-\infty}^{\infty} x^k f_X(x) d x
$$

The **variance** of a continuous random variable $X$ is defined as follows.

$$
\operatorname{var}(X)=\mathbb{E}\left[(X-\mu)^2\right]=\int_{x=-\infty}^{\infty}(x-\mu)^2 f_X(x) d x
$$

The variance of a continuous random variable $X$ also has the following properties

$$\operatorname{var}(X)=\mathbb{E}\left[X^2\right]-(\mathbb{E}[X])^2 $$
$$\operatorname{var}(a X)=a^2 \operatorname{var}(X) $$
$$\operatorname{var}(X+a)=\operatorname{var}(X)$$

___
## Cumulative Distribution Function (CDF)
Let $X$ be a continuous random variable with a sample space $\Omega = \mathbb{R}$. The **cumulative distribution function (CDF)** of $X$ is 

$$
F_X(x) \stackrel{\text { def }}{=} \mathbb{P}[X \leq x]=\int_{-\infty}^x f_X\left(x^{\prime}\right) d x^{\prime}
$$

Intuitively the CDF $F_X$ evaluated at $x$ is the integration of $f_X$ from $-\infty$ to a point $x$ as shown in the image below.

![[Pasted image 20250225114242.png]]

___
### Properties of a CDF
Let $X$ be a random variable (either continuous or discrete), then the CDF of $X$ has the following properties.

1. The CDF is **non-decreasing**

2. The **maximum** of the CDF is when $x = \infty : F_X(+\infty) = 1$

3. The **minimum** of the CDF is when $x = -\infty : F_X(-\infty) = 0$

A CDF can be used for both continuous and discrete random variables however we need a tool to handle the discontinuities. The following definitions are useful

A function $F_X(x)$ is said to be

- **Left-continuous** at $x=b$ if $F_X(b)=F_X\left(b^{-}\right) \stackrel{\text { def }}{=} \lim _{h \rightarrow 0} F_X(b-h)$

- **Right-continuous** at $x=b$ if $F_X(b)=F_X\left(b^{+}\right) \stackrel{\text { def }}{=} \lim _{h \rightarrow 0} F_X(b+h)$

- **Continuous** at $x=b$ if it is both right-continuous and left-continuous at $x=b$. In this case, we have
$$
\lim _{h \rightarrow 0} F_X(b-h)=\lim _{h \rightarrow 0} F_X(b+h)=F(b)
$$

![[Pasted image 20250225114836.png]]

For any random variable $X$ $F_X(x)$ must be **right-continuous**. 

$$
F_X(b)=F_X\left(b^{+}\right) \stackrel{\text { def }}{=} \lim _{h \rightarrow 0} F_X(b+h)
$$
Or visually,

![[Pasted image 20250225115000.png]]
___
### Retrieving PDF from CDF
Thus far we have seen how to obtain $F_X(x)$ from $f_X(x)$. In order to go in the reverse direction we must use the fundamental theorem of calculus. 

The probability density function (PDF) is the derivative of the cumulative distribution function (CDF):
$$
f_X(x)=\frac{d F_X(x)}{d x}=\frac{d}{d x} \int_{-\infty}^x f_X\left(x^{\prime}\right) d x^{\prime},
$$
Provided that $F_X$ is differentiable at $x$. If $F_X$ is not differentiable at $x = x_0$, then 

$$
f_X\left(x_0\right)=\mathbb{P}\left[X=x_0\right] \delta\left(x-x_0\right)
$$
___
### Unifying Discrete and Continuous Random Variables
For both continuous and discrete random variables CDF's are defined in the same way

$$
F_X(x) \triangleq \mathbb{P}(X \leq x)
$$

The difference is in the appearance of the CDF of a continuous random variable will be continuous whereas the CDF of a discrete random variable will contain jumps, these discontinuities in the CDF happen where the random variable $X$ takes positive probability.

With these discontinuities in consideration we can make the following unifying definition. 

For any random variable $X$, the corresponding CDF $F_X(x)$$ is always right-continuous. 

$$
F_X(a)=F_X\left(a^{+}\right)=\lim _{h \rightarrow 0} F_X(a+h), \forall a
$$
For any random variable $X$, the probability that it takes a fixed value $a$ is given by

$$
\mathbb{P}(X=a)=F_X(a)-\lim _{h \rightarrow 0} F_X(a-h)=F_X(a)-F_X\left(a^{-}\right)
$$
___
### Means, Medians, and Modes
#### Median
Let $X$ be a continuous random variable with PDF $f_X$. The median of $X$ is a point $c \in \mathbb{R}$ such that

$$
\int_{-\infty}^c f_X(x) d x=\int_c^{\infty} f_X(x) d x
$$

To find the median of a CDF, find a point $c$ such that

$$
F_X(c)=0.5 .
$$

![[Pasted image 20250225120254.png]]

___
#### Mode
Let $X$ be a continuous random variable. The mode is the point $c$ such that $f_X(x)$ attains the maximum
$$
c=\underset{x \in \Omega}{\operatorname{argmax}} f_X(x)=\underset{x \in \Omega}{\operatorname{argmax}} \frac{d}{d x} F_X(x) .
$$

Intuitively the mode is the argument (random variable) that when passed into the PDF has the highest value, or when passed into the CDF, achieves the greatest slope or jump.

![[Pasted image 20250225120730.png]]

___
#### Mean
The mean of a continuous random variable is simple the expectation $\mathbb{E}[x]$. We have defined how to calculate the expectation from the PMF

$$
\mathbb{E}[X]=\int_{-\infty}^{\infty} x f_X(x) d x
$$
Calculating the expectation from a CDF is a little bit more complicated. We must split the positive and negative parts of the random variable $X$. 

The expectation of a **non-negative** random variable is 

$$
\mathbb{E}[X]=\int_0^{\infty}\left(1-F_X(x)\right) d x
$$
The expectation of **negative** random variables is 

$$
\mathbb{E}[X]=-\int_{-\infty}^0 F_X(x) d x
$$

We can split any random variable into its positive and negative parts

$$
X=X^{+}+X^{-}
$$
$$
\begin{aligned}
& X^{+}=\left\{\begin{array}{l}
X, \text { if } X \geq 0 \\
0, \text { otherwise } .
\end{array}\right.
& X^{-}=\left\{\begin{array}{l}
X, \text { if } X<0 \\
0, \text { otherwise } .
\end{array}\right.
\end{aligned}
$$

Using the linearity of expectation we can combine these results to get that for any continuous random variable $X$, we can compute the expectation as follows. 

$$
\mathbb{E}[X]=\int_0^{\infty}\left(1-F_X(x)\right) d x-\int_{-\infty}^0 F_X(x) d x
$$
___
## Common Continuous Random Variables
### Uniform Random Variable
Let $X$ be a continuous **uniform random variable**. The PDF of $X$ is 

$$
f_X(x)= \begin{cases}\frac{1}{b-a}, & a \leq x \leq b \\ 0, & \text { otherwise }\end{cases}
$$

Where $[a,b]$ is the interval on which $X$ is defined. We write

$$
X \sim \operatorname{Uniform}(a, b)
$$
The corresponding CDF is given by
$$
F_X(x)=\left\{\begin{array}{l}
0, \text { if } x<0 \\
\frac{x-a}{b-a}, \text { if } x \in[a, b] \\
1, \text { if } x>1
\end{array}\right.
$$

![[Pasted image 20250225124254.png]]

The **uniform random variable** $X$ has the following properties related to expectation and variance
$$
\mathbb{E}[X] = \frac{a+b}{2}
$$
$$
\mathbb{E}[X^2] = \frac{a^2+ab+b^2}{3}
$$
$$
var(X) = \frac{(b-a)^2}{12}
$$
___
### Exponential Random Variable
Let $X$ be an **exponential random variable**. The PDF of $X$ is 

$$
f_X(x)= \begin{cases}\lambda e^{-\lambda x}, & x \geq 0 \\ 0, & \text { otherwise }\end{cases}
$$

Where $\lambda > 0$ is the parameter. We write
$$
X \sim \operatorname{Exponential}(\lambda)
$$
The corresponding CDF is given by
$$
F_X(x)=\left\{\begin{array}{l}
0, \text { if } x<0 \\
1-e^{-\lambda x}, \text { if } x \geq 0
\end{array}\right.
$$
![[Pasted image 20250303181659.png]]


The **exponential random variable** $X$ has the following properties related to expectation and variance


$$
\mathbb{E}[X] = \frac{1}{\lambda}
$$
$$
\mathbb{E}[X^2] = \frac{2}{\lambda^2}

$$
$$
var(X) = \frac{1}{\lambda^2}
$$
___


