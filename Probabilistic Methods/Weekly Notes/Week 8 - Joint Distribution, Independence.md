___
## Joint Distributions
Joint distributions are high-dimensional PDFs.
$$
\underbrace{f_X(x)}_{\text {one variable }} \Longrightarrow \underbrace{f_{X_1, X_2}\left(x_1, x_2\right)}_{\text {two variables }} \Longrightarrow \cdots \underbrace{f_{X_1, \ldots, X_N}\left(x_1, \ldots, x_N\right)}_{N \text { variables }} .
$$
Joint distributions encode how two (or more) random variables relate to each other. 
___
### Joint PMF
The joint PMF of discrete random variables is given by
$$
p_{X Y}(x, y) \triangleq \mathbb{P}(X=x \cap Y=y)=\mathbb{P}(X=x \text { and } Y=y)
$$
![[Pasted image 20250409221317.png]]

##### Exercise 1
Consider $X$ to be a Bernoulli(0.5) random variable and $Y$ to be the outcome of a fair die. Compute the joint probability space $(\Omega _X \times \Omega _Y)$, and the joint PMF of $X$ and $Y$.

![[20250410_024714000_iOS.jpg]]

##### Exercise 2
Consider the same pair of random variables as above. Compute the joint PMF of $X + Y$ and $X$.

![[20250410_024726000_iOS.jpg]]

___
### Joint PDF
The joint PDF of two continuous random variables $X$ and $Y$ is a function that can be integrated to yield a probability
$$
\mathbb{P}((X, Y) \in A)=\iint_{(x, y) \in A} f_{X, Y}(x, y) d x d y
$$
for any $A \in \mathbb{R}^2$.
![[Pasted image 20250409221711.png]]

##### Exercise 3
Suppose $(X, Y)$ are uniformly distributed over the unit square $[0,1]^2$, find the joint PDF of $(X,Y)$

![[20250410_025831000_iOS.jpg]]

##### Exercise 4
Suppose $(X, Y)$ are uniformly distributed over some finite region $A$ where $A \subset \mathbb{R}^2$. Find the joint PDF of $(X, Y)$.

![[20250410_030402000_iOS.jpg]]

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
F_{X Y}(x, y)=\mathbb{P}(X \leq x, Y \leq y)=\sum_{u \leq x} \sum_{v \leq y} p_{X Y}(u, v)
$$
$$
F_{X Y}(x, y)=\mathbb{P}(X \leq x, Y \leq y)=\int_{u=-\infty}^x \int_{v=-\infty}^y f_{X Y}(u, v) d v d u .
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

##### Exercise 5
Suppose $(X, Y)$ are distributed according to
$$
f_{X Y}(x, y)=\left\{\begin{array}{l}
c e^{-x} e^{-y}, \text { if } x \geq 0, y \geq 0 \\
0, \text { otherwise } .
\end{array}\right.
$$
compute the marginalization constant $c$, the joint CDF $F_{XY}(x,y)$ and the marginals $f_X(x)$ and $f_Y(y)$.

![[20250410_040401000_iOS.jpg]]
![[20250410_040642000_iOS.jpg]]

##### Exercise 6
Suppose $(X, Y)$ are distributed according to
$$
f_{X Y}(x, y)=\frac{1}{2 \pi \sigma^2} \exp \left(-\frac{\left(x-\mu_X\right)^2+\left(y-\mu_Y\right)^2}{2 \sigma^2}\right)
$$
Compute the marginals $f_X(x)$ and $f_Y(y)$

![[20250410_041559000_iOS.jpg]]

___
## Independence
Lets define the notion of independence for pairs of random variables. If $X$ and $Y$ are independent random variables, then for any sets $A \subset \mathbb{R}$ and $B \subset \mathbb{R}$, the following holds.
$$
\mathbb{P}(X \in A \cap Y \in B)=\mathbb{P}(X \in A) \mathbb{P}(Y \in B)
$$
Which leads to our definition for independence. Two random variables $X$ and $Y$ are independent if either.

$$
p_{X Y}(x, y)=p_X(x) p_Y(y), \text { or } 
$$
$$
f_{X Y}(x, y)=f_X(x) f_Y(y), \text { or } 
$$
$$
F_{X Y}(x, y)=F_X(x) F_Y(y)
$$
##### Exercise 7
Consider the PMF in exercises 1 and 6. Compute the marginals if needed and determine whether each of the are independent or not.

![[20250410_045031000_iOS.jpg]]

___
