---

---
___
## Bayes' Theorem
Assume two events such that $\mathbb{P}(A) > 0$ and $\mathbb{P}(B) > 0$ a. Then the following result holds.
$$
\mathbb{P}(A \mid B)=\frac{\mathbb{P}(B \mid A) \mathbb{P}(A)}{\mathbb{P}(B)}
$$
Bayes' Theorem allows you to switch conditional probabilities from $\mathbb{P}(B \mid A)$ to $\mathbb{P}(A \mid B)$.
___
## Law of Total Probability
The law of total probability states that for a partition $B_1, \ldots, B_n$ of $\Omega$ and for an event $A \in \mathcal{F}$ we have the following
$$
\mathbb{P}(A)=\sum_{i=1}^n \mathbb{P}\left(A \mid B_i\right) \mathbb{P}\left(B_i\right)
$$
The law of total probability allows you to decompose the probability of an event into smaller disjoint events. A corollary of Bayes' theorem and the law of total probability is that if you have a partition $B_1, \dots B_n$, then for any event $A \in \mathcal{F}$ we also get

$$
\mathbb{P}\left(B_i \mid A\right)=\frac{\mathbb{P}\left(A \mid B_i\right) \mathbb{P}\left(B_i\right)}{\sum_{i=1}^n \mathbb{P}\left(A \mid B_i\right) \mathbb{P}\left(B_i\right)}
$$
---
