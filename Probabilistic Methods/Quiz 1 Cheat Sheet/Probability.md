___
The probability of an event $Y$ is denoted $\mathbb{P}(Y)$ and can be expressed as.
$$
\mathbb{P}(Y)=\frac{\# \text { of ways in which } Y \text { can happen }}{\# \text { of ways in which all events happen }}
$$
---
## Probability Spaces
The probability space $(\Omega, \mathcal{F}, \mathbb{P})$ consists of three parts.

1. **Sample Space $\Omega$ :** The sample space is the set of all possible atomic outcomes of our experiment of interest.

2. **Event Space $\mathcal{F}$ :** The event space is the set of all possible events from our experiment. Note that events are sets (collections) of atomic outcomes. So any event $E$ must be a subset of $\Omega$.

3. **Probability Measure $\mathbb{P}$ :** A mapping from an event $E$ in $\mathcal{F}$ to a real number in the interval $[0,1]$. This represents the likelihood of event $E$ happening as a result of the experiment and corresponds to the size or measure of the set $E$.

---
## Axioms of Probability
A probability measure $\mathbb{P}$ defined over a probability space $(\Omega, \mathcal{F}, \mathbb{P})$ must satisfy

1. **Axiom 1 (Non-negativity):** $\mathbb{P}(A) \geq 0, \forall A \in \mathcal{F}$.

2. **Axiom 2 (Normalization):** $\mathbb{P}(\Omega)=1$.

3. **Axiom 3 ( $\sigma$-Additivity):** For a countably infinite collection of disjoint sets $A_1, A_2, A_3, \ldots$ in the event space $\mathcal{F}$
$$
\mathbb{P}\left(\bigcup_{i=1}^{\infty} A_i\right)=\sum_{i=1}^{\infty} \mathbb{P}\left(A_i\right)
$$
---
## Axiom Corollaries
The following corollaries can be derived using only the axioms above. 

1. $\mathbb{P}\left(A^c\right)=1-\mathbb{P}(A)$.

2. $\mathbb{P}(A) \leq 1, \forall A$.

3. If $A \subseteq B$, then $\mathbb{P}(A) \leq \mathbb{P}(B)$.

4. $\mathbb{P}(A \cup B)=\mathbb{P}(A)+\mathbb{P}(B)-\mathbb{P}(A \cap B)$.

5. Axiom 3 is true for finite collections of disjoint sets $A_1, \ldots, A_k$ (Finite Additivity).
$$
\mathbb{P}\left(\bigcup_{i=1}^k A_i\right)=\sum_{i=1}^k \mathbb{P}\left(A_i\right)
$$
---
## Conditional Probability
The conditional probability of an event $A$ given event $B$ is denoted by $\mathbb{P}(A \mid B)$
$$
\mathbb{P}(A \mid B)=\frac{\mathbb{P}(A \cap B)}{\mathbb{P}(B)}
$$
---
## Independence
Two events $A$ and $B$ are independent if and only if 
$$
\mathbb{P}(A \cap B)=\mathbb{P}(A) \mathbb{P}(B)
$$From this we can also gather that as long as $\mathbb{P(A)} > 0$ and $\mathbb{P(B)} > 0$, if $A$ and $B$ are independent then
$$
\mathbb{P}(A \mid B)=\mathbb{P}(A) \text { and } \mathbb{P}(B \mid A)=\mathbb{P}(B)
$$
---


