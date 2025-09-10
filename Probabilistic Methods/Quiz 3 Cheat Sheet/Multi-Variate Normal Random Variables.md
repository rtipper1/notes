___
An $n$-dimensional multi-variate Gaussian vector has the PDF

$$
f_{\mathbf{X}}(\mathbf{x})=\frac{1}{\sqrt{(2 \pi)^n \operatorname{det}(\mathbf{\Sigma})}} \exp \left(-\frac{1}{2}(\mathbf{x}-\boldsymbol{\mu})^T \mathbf{\Sigma}^{-1}(\mathbf{x}-\boldsymbol{\mu})\right)
$$

We denote this as $\mathbf{X} \sim \mathcal{N}(\boldsymbol{\mu}, \mathbf{\Sigma})$. It has the following useful properties.

1. $\mathbb{E}[\mathbf{X}]=\mu$.

2. $\operatorname{cov}(\mathbf{X})=\mathbf{\Sigma}$.

3. If $\mathbf{Y}=\mathbf{A X}+\mathbf{b}$, then $\mathbf{Y}$ is also multi-variate Gaussian. More specifically, $\mathbf{Y} \sim \mathcal{N}\left(\mathbf{A} \boldsymbol{\mu}+\mathbf{b}, \mathbf{A} \Sigma \mathbf{A}^T\right)$.

4. If the multi-variate Gaussians are uncorrelated, i.e. $\boldsymbol{\Sigma}$ is a diagonal matrix, then they are also independent.

Suppose $X_1, \ldots, X_n$ are jointly Gaussian and also jointly independent. Further $X_i \sim \mathcal{N}\left(\mu_i, \sigma_i^2\right)$. What does their covariance matrix look like?
$$
\mathbf{\Sigma}=\left[\begin{array}{ccc}
\sigma_1^2 & \ldots & 0 \\
\vdots & \ddots & \vdots \\
0 & \ldots & \sigma_n^2
\end{array}\right]
$$

Substituting this into the joint Gaussian PDF formula, we get 
$$
f_{\mathbf{X}}(\mathbf{x})=\prod_{i=1}^n \frac{1}{\sqrt{2 \pi \sigma_i^2}} \exp \left(-\frac{\left(x-\mu_i^2\right)}{2 \sigma_i^2}\right)
$$

This implies the following important properties. Suppose $\mathbf{X} \sim \mathcal{N}\left(\boldsymbol{\mu}_X, \boldsymbol{\Sigma}_X\right)$ and $\mathbf{Y}=\mathbf{A X}+\mathbf{b}$. Then,

1. $\mathbb{E}[Y]=\mathbf{A} \boldsymbol{\mu}_X+\mathbf{b}$.
2. $\operatorname{cov}(Y)=\boldsymbol{\Sigma}_Y=\mathbf{A} \boldsymbol{\Sigma}_X \mathbf{A}^T$.

___