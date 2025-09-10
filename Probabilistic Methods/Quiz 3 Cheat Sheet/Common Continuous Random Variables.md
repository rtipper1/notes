___
## Uniform 
$X$ is a uniform random variable over the interval $[a, b]$ if it takes values with equal likelihood from the entire interval. We denote this as $X \sim \operatorname{Uniform}(a, b)$.
$$
f_X(x)=\left\{\begin{array}{l}
\frac{1}{b-a}, \text { if } x \in[a, b] . \\
0, \text { otherwise } .
\end{array}\right.
$$
$$
F_X(x)=\left\{\begin{array}{l}
0, \text { if } x<0 \\
\frac{x-a}{b-a}, \text { if } x \in[a, b] \\
1, \text { if } x>1
\end{array}\right.
$$
$$
\mathbb{E}[X] = \frac{a + b}{2}
$$
$$
var(X) = \frac{(b-a)^2}{12}
$$
___
## Exponential
$X$ is an exponential random variable if its density decays exponentially over the set of positive real numbers. We denote this as $X \sim Exponential(\lambda)$
$$
f_X(x)=\left\{\begin{array}{l}
\lambda e^{-\lambda x}, \text { if } x \geq 0 \\
0, \text { otherwise }
\end{array}\right.
$$
$$
F_X(x)=\left\{\begin{array}{l}
0, \text { if } x<0 \\
1-e^{-\lambda x}, \text { if } x \geq 0
\end{array}\right.
$$
$$
\mathbb{E}[X] = \frac{1}{\lambda}
$$
$$
var(X) = \frac{1}{\lambda ^2}
$$
___
## Gaussian or Normal
$X$ is a Gaussian or normal random variable if its density satisfies the equation below. We denote this as $X \sim \mathcal{N}\left(\mu, \sigma^2\right)$
$$
f_X(x)=\frac{1}{\sqrt{2 \pi \sigma^2}} \exp \left[-\frac{(x-\mu)^2}{2 \sigma^2}\right]
$$
$$
\Phi(x) \triangleq F_X(x)=\int_{u=-\infty}^x f_X(u) d u
$$
$$
\mathbb{E}[X] = \mu
$$
$$
var(X) = \sigma ^2
$$
___
