___
### Properties
A joint distribution should satisfy the following properties.

1. **Non-Negativity** 
$$p_{XY}(x,y) \geq 0, \forall (x,y)$$
2. **Normalization** 
$$
\sum_{x \in \mathcal{X}} \sum_{y \in \mathcal{Y}} p_{X Y}(x, y)=1 \quad \quad \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} f_{X Y}(x, y) d y d x=1
$$
3. **Measure** 
$$
\mathbb{P}((X, Y) \in A)=\sum_{(x, y) \in A} p_{X Y}(x, y) \quad \quad \mathbb{P}((X, Y) \in A)=\iint_{(x, y) \in A} f_{X Y}(x, y) d x d y
$$
4. **Marginalization**, i.e. summing up over one of the dimensions of the joint distribution, yields the distribution of the remaining dimension/s.

$$

\sum_{y \in \mathcal{Y}} p_{X Y}(x, y)=p_X(x) \quad \quad f_X(x)=\int_{y=-\infty}^{\infty} f_{X Y}(x, y) d y
$$
$$
\sum_{x \in \mathcal{X}} p_{X Y}(x, y)=p_Y(y) \quad \quad f_Y(y)=\int_{x=-\infty}^{\infty} f_{X Y}(x, y) d x

$$
___
### Relationship With CDF
In order to compute the joint CDF random variables we do the following
$$
\begin{gathered}
F_{X Y}(x, y)=\mathbb{P}(X \leq x, Y \leq y)=\sum_{u \leq x} \sum_{v \leq y} p_{X Y}(u, v) \\
F_{X Y}(x, y)=\mathbb{P}(X \leq x, Y \leq y)=\int_{u=-\infty}^x \int_{v=-\infty}^y f_{X Y}(u, v) d v d u .
\end{gathered}
$$
In order to compute the joint PDF from the joint CDF, we simply double differentiate.
$$
f_{X Y}(x, y)=\frac{d^2}{d x d y} F_{X Y}(x, y)
$$
If you wanted to compute the marginal CDF $F_X(x)$ from $F_{XY}(x,y)$ you can use the following.
$$

F_X(x)=\lim _{y \rightarrow \infty} F_{X Y}(x, y)
$$
$$
F_Y(y)=\lim _{x \rightarrow \infty} F_{X Y}(x, y)
$$
___
## Independence
We have defined independence for events before. We can define the same for joint distributions. Two random variables $X$ and $Y$ are independent if 
$$
\begin{gathered}
p_{X Y}(x, y)=p_X(x) p_Y(y), \text { or } \\
f_{X Y}(x, y)=f_X(x) f_Y(y), \text { or } \\
F_{X Y}(x, y)=F_X(x) F_Y(y)
\end{gathered}
$$
___
## Joint Expectation
Suppose $X$ and $Y$ are jointly distributed according to the PDF $f_{XY}(x,y)$. Let $Z = g(X, Y)$ be another variable. Then, 
$$
\mathbb{E}[Z]=\mathbb{E}[g(X, Y)] \triangleq \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} g(x, y) f_{X Y}(x, y) d y d x
$$
___
## Covariance and Correlation
The **covariance** between two random variables $X$ and $Y$ is defined as follows.
$$
\operatorname{cov}(X, Y) \triangleq \mathbb{E}\left[\left(X-\mu_X\right)\left(Y-\mu_Y\right)\right]
$$
covariance also satisfies the following properties.
1. $\operatorname{cov}(X, Y)=\mathbb{E}[X Y]-\mathbb{E}[X] \mathbb{E}[Y]$
2. $\operatorname{cov}(X, X)=\operatorname{var}(X)$
3. $\operatorname{var}(X+Y)=\operatorname{var}(X)+\operatorname{var}(Y)+2 \operatorname{cov}(X, Y)$
4. If $X$ and $Y$ are independent, $\operatorname{cov}(X, Y)=0$.

The **correlation coefficient** between any two random variables $X$ and $Y$ is defined as 
$$
\rho_{X Y} \triangleq \frac{\operatorname{cov}(X, Y)}{\sqrt{\operatorname{var}(X) \operatorname{var}(Y)}} .
$$
The correlation coefficient also satisfies the following properties.

1. $\rho$ is always between -1 and 1, i.e., $-1 \leq \rho \leq 1$. This is due to the cosine angle definition
2. When $X=Y$ (fully correlated), $\rho=+1$
3. When $X=-Y$ (negatively correlated), $\rho=-1$
4. When $X$ and $Y$ are uncorrelated, $\rho=0$

___