
---
## A Heuristic View of Probability

The probability of an event $Y$ is denoted by $P(Y)$  and can be expressed as:

$$
P(Y) = \frac{\\\text{\# of ways in which Y can happen}}{\\\text{\# of ways in which all events can happen}}
$$

This involves **counting**, or **measuring sizes of sets**. 
* For discrete spaces we do this via enumeration (counting).
* For continuous spaces we do this by measuring lengths, volumes, areas, i.e. integration.
---
#### Example

Roll a dice, let the event $Y$ be the event that the roll was even:

$$ Y = \{2,4,6\}
$$
Then, the probability of the event $Y$ is given by:
$$
P(Y) = \frac{\\\text{\# of ways in which Y can happen}}{\\\text{\# of ways in which all events can happen}} = \frac{3}{6} = \frac{1}{2}
$$
---
## Counting

#### Why are factorials useful?

Factorials are common in probability because they are an easy way to represent the number of $n$ unique items. 

For example if we are trying to order a set of $n$ distinct items then we can represent that as:

$$
\underbrace{n \text{ choices }}_{\text{position 1}} \times
\underbrace{(n - 1) \text{ choices }}_{\text{position 2}} \times
\underbrace{(n - 2) \text{ choices }}_{\text{position 3}} \times
\dots
\times
\underbrace{1 \text{ choice }}_{\text{position }n} \times
$$
Thus the number of arrangements is:
$$
n \times (n-1) \times (n-2) \times \dots \times 1 = n!
$$
Also remember that.
$$
0!  = 1
$$
---
### Permutations

Permutation is the number of **ordered** configurations of $k$ items in a set of $n$ total items. 

The number of ways to choose and uniquely order $k$ items from a set of $n$ distinct objects is given by

$$
_{n}P_{k} = \frac{n!}{(n-k)!}
$$

The number of ways to permute $k$ times with replacement from a set of $n$ distinct items is given by $n^r$

---
### Combinations

Combinations are the number of ways to choose $k$ items of a set of $n$ distinct items **without regard for ordering** 

The number of ways to choose $k$ distinct items from a set of $n$ distinct items is given by


$$
\binom{n}{k} =  _{n}C_{k} = \frac{n!}{k!(n-k!)} = \frac{_{n}P_{k}}{k!}
$$
Notice that the primary difference between permutations and combinations is that in combinations we do not care about the order of the items. Therefore to calculate the number of combinations we simply divide by $k!$ which is the number of unique ways the $k$ items can be ordered.

---
## Commonly Used Series

### Binomial Series
$$
(a + b)^n = \sum_{k=0}^n\binom{n}{k}a^kb^{n-k}
$$
#### Exercise
Figure out why this is equivalent to counting the number of ways in which we can choose $k$ items out of $n$ distinct items.

#### Exercise
Provide an algebraic proof as well as a combinatoric proof for the following identity. (Hint: Think about the number of ways in which you can construct subsets of different sizes from a set of $n$ distinct items. Each item has two possible choices, it can either belong to the subset or not)

$$
\sum_{k=0}^n\binom{n}{k}=2^n
$$

### Geometric Series

Another common series is the geometric series which takes the form

$$
1,r,r^2, \dots
$$
#### Example

Consider the probability that a coin takes k tosses to turn up heads for the first time. The number of all $k$ length coin toss sequences is $2^k$. The number of sequence with all tails for the first $k-1$ tosses and heads at the end is 1. So the probability we're interested in is given by $\frac{1}{2^k}$. Thus, this probability looks like a geometric progression as $k$ is varied.

## Basics of Set Theory

A set is any unordered collection of elements

### Operations of Sets

**Basic Operations**
- Unions: $A \cup B$
- Intersections: $A \cap B$
- Complements: $A^c$ or $A^{\prime}$
- Set Difference: $A \backslash B=A \cap B^c$

**Important Properties**
- $A \cup A^c=\Omega$.
- $A \cap A^c=\phi$.
- $A \cup \Omega=\Omega$.
- $\left(A^c\right)^c=A$.
- Commutative: $A \cup B=B \cup A$ and $A \cap B=B \cap A$.
- Associative: $A \cup(B \cup C)=(A \cup B) \cup C$ and $A \cap(B \cap C)=(A \cap B) \cap C$.
- Distributive: $A \cup(B \cap C)=(A \cup B) \cap(A \cup C)$ and $A \cap(B \cup C)=$ $(A \cap B) \cup(A \cap C)$.
- DeMorgan's Law: $(A \cap B)^c=A^c \cup B^c$.