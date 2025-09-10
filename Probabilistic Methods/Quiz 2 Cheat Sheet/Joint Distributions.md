___
## Joint PMF
Joint distributions encode how two random variables relate to each other. The joint PMF of two discrete random variables is given by.
$$
p_{X Y}(x, y) \triangleq \mathbb{P}(X=x \cap Y=y)=\mathbb{P}(X=x \text { and } Y=y)
$$
The joint distribution PMF follows the same properties of all other PMFs including one more (marginalization).
___
## Marginalization
Summing over one of the dimensions of the join distribution yields the distribution of the remaining dimensions.
$$

\sum_{y \in \mathcal{Y}} p_{X Y}(x, y)=p_X(x)
$$
$$
\sum_{x \in \mathcal{X}} p_{X Y}(x, y)=p_Y(y)
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
1. $-1 \leq \rho_{X Y} \leq 1$
2. $\rho_{X X}=1$
3. If $X$ and $Y$ are independent, $\rho_{X Y}=0$.
___