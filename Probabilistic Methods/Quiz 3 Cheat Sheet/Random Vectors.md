___
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
___
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
___
### Properties
Suppose $\mathbf{p}=\left(p_1, \ldots, p_n\right)^T$ is a constant vector. Define

$$
Y=\mathbf{p}^T \mathbf{X}=p_1 X_1+\ldots+p_n X_n .
$$
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
$$___
