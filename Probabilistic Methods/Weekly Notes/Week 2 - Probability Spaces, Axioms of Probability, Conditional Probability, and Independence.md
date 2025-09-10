## Probability Spaces

An **Experiment** is any action or process whose outcome is subject to uncertainty. We call the individual results of any experiment an **outcome**. When we collect all possible outcomes of an experiment we get the **sample space**.

The probability space $(\Omega, \mathcal{F}, \mathbb{P})$ consists of three parts.

1. **Sample Space** $\Omega$ : The sample space is the set of all possible atomic outcomes of our experiment of interest.
2. **Event Space** $\mathcal{F}$ : The event space is the set of all possible events from our experiment. Note that events are sets (collections) of atomic outcomes. So any event $E$ must be a subset of $\Omega$.
3. **Probability Measure** $\mathbb{P}$ : A mapping from an event $E$ in $\mathcal{F}$ to a real number in the interval $[0,1]$. This represents the likelihood of event $E$ happening as a result of the experiment and corresponds to the size or measure of the set $E$.

---
## Sample Space $\Omega$

The sample space is the set of all possible outcomes form an experiment. We denote $\xi$
as an element in $\Omega$.

#### Examples (Discrete Outcomes)
* Coin flip: $\Omega = \{H, T\}$
* Throw a die: $\Omega = \{1,2,3,4,5\}$
* Draw an even integer: $\Omega = \{2,4,6,8,\dots\}$

#### Examples (Continuous Outcomes)
- Waiting time for a bus in West Lafayette: $\Omega=\{t \mid 0 \leq t \leq 30$ minutes $\}$.
- Phase angle of a voltage: $\Omega=\{\theta \mid 0 \leq \theta \leq 2 \pi\}$.
- Frequency of a pitch: $\Omega=\left\{f \mid 0 \leq f \leq f_{\max }\right\}$.

---
### Event Space $\mathcal{F}$
An event $E$ is a subset in the sample space $\Omega$. The set of all possible events is denoted as $\mathcal{F}$.

#### Example of Events
Throw a die. Let $\Omega = \{1,2,3,4,5,6\}$. The following are two possible events as shown in the figure below.

* $E_1=\{\text { even numbers }\}=\{2,4,6\}$
* $E_2=\{\text { less than } 3\}=\{1,2\}$

![[Pasted image 20250203120122.png]]

Above are two events within the event space $\mathcal{F}$.

We need $\mathcal{F}$ because the probability law $\mathbb{P}$ is mapping a set to a number. $\mathbb{P}$ does not take an outcome from $\Omega$ but a subset inside $\Omega$.

---
## Probability Law $\mathbb{P}$

A probability law is a function $\mathbb{P}: \mathcal{F} \rightarrow[0,1]$ of an event $E$ to a real number in $[0,1]$.

$\mathbb{P}$ is a function therefore there must be an input and an output. In our case the input is an event $E$ in the sample space $\Omega$ and the output is a number between $0$ and $1$. 

Any probability law must follow the axioms of probability which are discussed below.

#### Example
Consider flipping a coin. The event space is $\mathcal{F}=\{\emptyset,\{H\},\{T\}, \Omega\}$. We can define the probability law as:

$$
\mathbb{P}[\emptyset]=0, \mathbb{P}[\{H\}]=\frac{1}{2}, \quad \mathbb{P}[\{T\}]=\frac{1}{2}, \mathbb{P}[\Omega]=1,
$$
#### Summary
* A probability law $\mathbb{P}$ is a function
* It takes a subset (an element in  $\mathcal{F}$ ) and maps it to a number between 0 and 1.
*  $\mathbb{P}$ is a measure of the size of a set.
* For $\mathbb{P}$ to be valid it must satisfy the axioms of probability.

---
## Axioms of Probability
A probability space $\mathbb{P}$ defined over a probability space $(\Omega, \mathcal{F}, \mathbb{P})$ must satisfy

1. **Axiom 1 (Non-negativity):** $\mathbb{P}(A) \geq 0, \forall A \in \mathcal{F}$.

2. **Axiom 2 (Normalization):** $\mathbb{P}(\Omega)=1$.

3. **Axiom 3 ( $\sigma$-Additivity):** For a countably infinite collection of disjoint sets $A_1, A_2, A_3, \ldots$ in the event space $\mathcal{F}$

$$
\mathbb{P}\left(\bigcup_{i=1}^{\infty} A_i\right)=\sum_{i=1}^{\infty} \mathbb{P}\left(A_i\right)
$$
---
## Conditional Probability
The **conditional probability** of an event $A$ given an event $B$ is denoted by $\mathbb{P}(A|B)$ and is defined as 
$$
\mathbb{P}(A \mid B)=\frac{\mathbb{P}(A \cap B)}{\mathbb{P}(B)}
$$
Note: only defined when $\mathbb{P}(B) > 0$

$\mathbb{P}(A \mid B)$ captures the likelihood that an event $A$ occurs given the information that event $B$ occurs. Since we know that $B$ has occurred we are only interested in the set of outcomes within $B$. To decide whether $A$ occurred we look at the outcomes within $A \cap B$.

---
## Independence
Two events $A$ and $B$ are independent if and only if 
$$
\mathbb{P}(A \cap B)=\mathbb{P}(A) \mathbb{P}(B)
$$
We use the notation $A \perp\!\!\!\perp B$ to denote independent events.


Note that as long as $\mathbb{P}(A) > 0$, if $A$ and $B$ are independent then 
$$\mathbb{P}(A \mid B)=\mathbb{P}(A) \text{  and  } \mathbb{P}(B \mid A)=\mathbb{P}(B)$$.
In other words the conditional probability that event $A$ occurs given that $B$ occurred is the same as if you did not know whether $B$ occurred or not. The occurrence of $B$ does not tell you anything about the likelihood of $A$ occurring and vice-versa.

---