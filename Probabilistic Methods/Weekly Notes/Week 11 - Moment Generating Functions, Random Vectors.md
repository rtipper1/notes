___
## Moment Generating Functions
Computing convolutions is hard and we know that taking Laplace/Fourier transforms converts convolutions into simple multiplications. We can do this with random variables using moment generating functions.'

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
### Common MGFs
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

##### Exercise 1
Compute the MGF of $X \sim \operatorname{Binomial}(n, p)$ from first principles. Compute the MGF of $X_1+\ldots+X_n$ where $X_i$ are i.i.d. Bernoulli $(p)$. Use the properties of MGFs to show that both these random variables have the same distribution.

![[20250415_152806000_iOS.jpg]]

##### Exercise 2
Use MGFs to show that the sum of independent Poisson random variables is Poisson. Show a similar result for sums of independent normal random variables. Hint: These two problems are solved in the SC textbook.

![[20250415_152817000_iOS.jpg]]

___
## Random Vectors
Recall that we denote a random vector as a collection of random variables

$$
\mathbf{X}=\left(X_1, \ldots, X_n\right) .
$$

We define the joint distribution of this vector as 

$$
\begin{aligned}
p_{\mathbf{X}}(\mathbf{x}) & =p_{X_1, \ldots, X_n}\left(x_1, \ldots, x_n\right) \\
f_{\mathbf{X}}(\mathbf{x}) & =f_{X_1, \ldots, X_n}\left(x_1, \ldots, x_n\right)
\end{aligned}
$$

The expectation of this random vector is defined as

$$
\boldsymbol{\mu}=\mathbb{E}[\mathbf{X}]=\left[\begin{array}{c}
\mathbb{E}\left[\boldsymbol{X}_{\mathbf{1}}\right] \\
\mathbb{E}\left[\boldsymbol{X}_{\mathbf{2}}\right] \\
\ldots \\
\mathbb{E}\left[\boldsymbol{X}_{\boldsymbol{n}}\right]
\end{array}\right]
$$
### Covariance Matrix
We want to study how random variables within the vector vary together. In order to do this we consider a random vector $\mathbf{X}=\left(X_1, \ldots, X_n\right)^T$. Its covariance matrix is defined as 

$$
\Sigma \triangleq \operatorname{cov}(\mathbf{X})=\mathbb{E}\left[(\mathbf{X}-\boldsymbol{\mu})(\mathbf{X}-\boldsymbol{\mu})^T\right]=\left[\begin{array}{cccc}
\operatorname{var}\left(X_1\right) & \operatorname{cov}\left(X_1, X_2\right) & \ldots & \operatorname{cov}\left(X_1, X_n\right) \\
\operatorname{cov}\left(X_2, X_1\right) & \operatorname{var}\left(X_2\right) & \ldots & \operatorname{cov}\left(X_2, X_n\right) \\
\vdots & \vdots & \ddots & \vdots \\
\operatorname{cov}\left(X_n, X_1\right) & \operatorname{cov}\left(X_n, X_2\right) & \ldots & \operatorname{var}\left(X_n\right)
\end{array}\right]
$$

Note that the covariance matrix is always symmetric, i.e. $\boldsymbol{\Sigma}=\mathbf{\Sigma}^T$.

### Properties
Suppose $\mathbf{p}=\left(p_1, \ldots, p_n\right)^T$ is a constant vector. Define

$$
Y=\mathbf{p}^T \mathbf{X}=p_1 X_1+\ldots+p_n X_n .
$$
Then 
$$
\mathbb{E}[Y]=\mathbb{E}\left[\mathbf{p}^T \mathbf{X}\right]=\mathbf{p}^T \mathbb{E}[\mathbf{X}]=\mathbf{p}^T \boldsymbol{\mu}=\sum_{i=1}^n p_i \mathbb{E}\left[X_i\right]
$$
Next we can compute the variance.
$$
\begin{aligned}
\operatorname{var}(Y) & =\mathbb{E}\left[(Y-\mathbb{E}[Y])^2\right] \\
& \\
& =\sum_{i=1}^n p_i^2 \operatorname{var}\left(X_i\right)+\sum_i \sum_{j \neq i} p_i p_j \operatorname{cov}\left(X_i, X_j\right)
\end{aligned}
$$
We can do the same thing  but with matrix multiplication. Define a new m-dimensional random vector $Z$ as follows
$$
\mathbf{Z}=\mathbf{A X}
$$
Then, its expectation is given by
$$
\mathbb{E}[\mathbf{Z}]=\mathbb{E}[\mathbf{A X}]=\mathbf{A} \mathbb{E}[\mathbf{X}]=\mathbf{A} \boldsymbol{\mu}_X
$$
And its covariance is given by 
$$
\begin{aligned}
\boldsymbol{\Sigma}_Z=\operatorname{cov}(\mathbf{Z}) & =\mathbb{E}\left[\left(\mathbf{Z}-\boldsymbol{\mu}_Z\right)\left(\mathbf{Z}-\boldsymbol{\mu}_Z\right)^T\right] \\
& \\
& =\mathbf{A} \boldsymbol{\Sigma}_X \mathbf{A}^T .
\end{aligned}
$$
##### Exercise 3
Define $Z = X + b$. Using similar technique as above, compute the mean $\mu_Z$ and covariance matrix $\Sigma _Z$.

![[20250415_152827000_iOS.jpg]]

___