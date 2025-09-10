___
The **moment generating function  (MGF)** of a random variable $X$ is defined as follows 

$$
M_X(t) \triangleq \mathbb{E}\left[e^{t X}\right]
$$

It satisfies the following properties.

1. $M_X(0)=1$.

2. $\left.\frac{d^k}{d l^k} M_X(t)\right|_{t=0}=\mathbb{E}\left[X^k\right]$.

3. If two random variables have the same MGF, i.e. $M_X(t)=$ $M_Y(t), \forall t$, then they have the same CDF, i.e. $F_X(u)=F_Y(u), \forall u$.

4. If $X$ and $Y$ are independent random variables, then
$$
M_{X+Y}(t)=M_X(t) M_Y(t)
$$

For any discrete random variables the moment generating function can be written as a summation 
$$
M_X(s)=\sum_{x \subset \mathcal{X}} e^{s x} p_X(x)
$$
Similarly for continuous random variables it can be written as an integration
$$
M_X(s)=\int_{-\infty}^{\infty} e^{s x} f_X(x) d x
$$
___
## Common MGFs
$$
\begin{array}{|c|c|c|}
\hline \text { Distribution } & \text { Parameters } & \text { Moment Generating Function (MGF) } \\
\hline \text { Bernoulli } & p & M(t)=1-p+p e^t \\
\hline \text { Binomial } & n, p & M(t)=\left(1-p+p e^t\right)^n \\
\hline \text { Geometric } & p & M(t)=\frac{p e^t}{1-(1-p) e^t}, \quad t<-\ln (1-p) \\
\hline \text { Poisson } & \lambda & M(t)=\exp \left(\lambda\left(e^t-1\right)\right) \\
\hline \text { Uniform } & a, b & M(t)=\frac{e^{t t}-e^{a t}}{t(b-a)} \\
\hline \text { Exponential } & \lambda & M(t)=\frac{\lambda}{\lambda-\ell}, \quad t<\lambda \\
\hline \text { Normal } & \mu, \sigma^2 & M(t)=\exp \left(\mu t+\frac{\sigma^2 t^2}{2}\right) \\
\hline
\end{array}
$$

___