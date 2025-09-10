___
## Conditional PMF and PDF
Let $X$ and $Y$ be two random variables. The Conditional PMF and PDF of $X$ given $Y = y$ is 
$$

p_{X \mid Y}(x \mid y)=\frac{p_{X, Y}(x, y)}{p_Y(y)} \quad \quad \quad f_{X \mid Y}(x \mid y)=\frac{f_{X, Y}(x, y)}{f_Y(y)}

$$
We can use this to compute the probabilities conditioned on the event $Y=y$
$$
\mathbb{P}(X \in A \mid Y=y)=\sum_{x \in A} p_{X \mid Y}(x \mid y) \quad \quad \quad \mathbb{P}(X \in A \mid Y=y)=\int_{x \in A} f_{X \mid Y}(x \mid y) d x
$$
Similar to the law of total probability 
$$
\mathbb{P}(X \in A)=\sum_{x \in A} \sum_{y \in \mathcal{Y}} p_{X \mid Y}(x \mid y) p_Y(y) \quad \quad \quad \mathbb{P}(X \in A)=\int_{x \in A} \int_{y \in \mathcal{Y}} f_{X \mid Y}(x \mid y) f_Y(y) d y d x
$$
___
## Conditional CDF
For jointly distributed random variables we can write the conditional CDF as
$$
F_{X \mid Y}(x \mid y)=\mathbb{P}(X \leq x \mid Y=y)=\sum_{u \leq x} p_{X \mid Y}(u \mid y) \quad \quad \quad F_{X \mid Y}(x \mid y)=\int_{-\infty}^x f_{X \mid Y}(u \mid y) d u
$$
___
## Conditional Expectation
For discrete random variables the expectation is defined as follows.
$$
\mathbb{E}[X \mid Y=y] \triangleq \sum_{x \in \mathcal{X}} x p_{X \mid Y}(x \mid y)
$$
For continuous random variables we define it as follows.
$$
\mathbb{E}[X \mid Y=y] \triangleq \int_{-\infty}^{\infty} x f_{X \mid Y}(x \mid y) d x
$$
$\mathbb{E}[X \mid Y]$ is the conditional expectation of $X$ given $Y$. It computes the average value of $X$ assuming that the random variable $Y$ is fixed-leading to a function of $Y$. Thus, $\mathbb{E}[X \mid Y]$ is itself a random variable.
___
## Law of Total Expectation
The law of total expectation states that 
$$
\mathbb{E}[\mathbb{E}[X \mid Y]]=\mathbb{E}[X] .
$$
In particular, for discrete random variables, this simplifies to
$$
\sum_{y \in \mathcal{Y}} \mathbb{E}[X \mid Y=y] p_Y(y)=\mathbb{E}[X]
$$
Similarly for continuous random variables, this simplifies to
$$
\int_{-\infty}^{\infty} \mathbb{E}[X \mid Y=y] f_Y(y) d y=\mathbb{E}[X]
$$
___
