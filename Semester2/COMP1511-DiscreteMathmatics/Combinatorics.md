#COMP1511
[K.H.Rosen Discrete Mathematics and it's applications - Chapter 6.1 - 6.5](https://docs.google.com/viewer?a=v&pid=sites&srcid=ZGVmYXVsdGRvbWFpbnxzYWVlZG9vbjF8Z3g6N2JmM2Y5YWEzMmRlNWUzNw)
The study of arrangements of objects
It is used, for example, in determining the complexity of algorithms, determining whether there are enough Internet protocol addressees to meet the demand, and when probabilities of events are computed.

## Basic Counting Principles
### Product Rule
> Multiplication Principle for Counting Procedures
- Satisfies all:
	1. The steps are ordered i.e. any two sequences of different outcomes represents distinguishable composite outcomes.
	2. The steps are independent i.e. the number of outcomes of one step is not affected by the outcomes of the preceding steps.
	3. the steps are complete i.e. each composite outcome consists of a complete sequence of individual outcomes, one for each step.
- Suppose that a procedure can be broken down into a sequence of two tasks. If there are n<sub>1</sub> ways to do the first task and for each of these ways of doing the first task, there are n<sub>2</sub> ways to do the second task, then there are  $n_1n_2$ ways to do the procedure.
### Sum Rule
> Addition Principle for Counting Procedures
- If a task can be done either in one of $n_1$ ways or in one of $n_2$ ways, where none of the set of $n_1$ ways is the same as any of the set of $n_2$ ways, then there are $n_1$ + $n_2$ ways to do the task.

### Subtraction Rule
> Principle of Inclusion-Exclusion:
- If a task can be done in either n<sub>1</sub> ways or n<sub>2</sub> ways, then the number of ways to do the task is n<sub>1</sub>+ n<sub>2</sub> minus the number of ways to do the task that are common to the two different ways.
![[Pasted image 20230302214538.png]]  
$$ |A_1 \cup A_2| = |A_1| + |A_2| - |A_1 \cap A_2|$$
### Division Rule
There are $\frac{n}{d}$ ways to do a task if it can be done using a procedure that can be carried out in n ways, and for every way $w$, exactly $d$ of the $n$ ways correspond to
way $w$.

## Selections
- When Stating repetition add "with unlimited repetition" after, otherwise assume no repeats are allowed
### Permutations
- k-permutation
	- Order matters
	- selection of $k$ objects from a set of $n$ objects
	- Denoted by $P(n,k)$
If n is a positive integer and r is an integer with 1 ≤ k ≤ n, then there are

P(n, k) = n(n − 1)(n − 2) ⋯ (n − k + 1)
k-permutations of a set with n distinct elements.

If n and r are integers with 0 ≤ k ≤ n, then:
$P(n, k) = \frac{n!}{(n − k)!}$

### Combinations
- k-Combination
	- Order does not matter
	- selection of $k$ objects from a set of $n$ objects
	- Denoted by $C(n.k)$

The number of r-combinations of a set with n elements, where n is a non-negative integer and r is an integer with 0 ≤ r ≤ n, equals
$C(n, r) = \frac{n!}{r! (n − r)!}$

![[Pasted image 20230220133956.png]]
- r is number of elements
- n is number of items in the set

## Binomial Coefficients and Combinatorial Identities
### Binomial Theorem
If $a$ and $b$ are real numbers and $n$ is a positive integer then:
$(a+b)^2 = \sum\limits_{k=1}^n {n\choose k} a^{n-k}b^k$

### Pascal's Identity
Identity Let $n$ and $k$ be positive integers with $n \geq k$
${n+1\choose k} = {n\choose k-1}+{n\choose k}$

### Vandermonde’s Identity
Let $m, n, r$ be non-negative integers with r not exceeding either m or n.
${m+n\choose r} = \sum\limits_{k=0}^m {n\choose r-k} {n\choose k}$

## Pigeon hole principle
- If $n$ pigeons fly into $k$ pigeonholes and k $< n$, then some pigeonhole contains at least 2 pigeons
> Example:
Show that for every integer n there is a multiple of n that has only 0s and 1s in its decimal expansion.
Solution:
Let n be a positive integer. Consider the n + 1 integers 1, 11, 111, ... , 11 ... 1 (where
the last integer in this list is the integer with n + 1 1s in its decimal expansion). Note that there
are n possible remainders when an integer is divided by n. Because there are n + 1 integers in
this list, by the pigeonhole principle there must be two with the same remainder when divided
by n. The larger of these integers less the smaller one is a multiple of n, which has a decimal,
expansion consisting entirely of 0s and 1s.

#### The Generalised Pigeonhole Principle
If $N$ objects are placed into $k$ boxes, then there is at least one box containing at least $N ∕ k$ objects.
