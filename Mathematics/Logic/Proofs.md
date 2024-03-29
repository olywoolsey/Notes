# Proofs
#logic #COMP1421 
## Direct Proof
In a direct proof, the statement is proven ‘directly’, i. e. without any detours
Often in a chain of implications, equalities or equivalences
	The integer $n$ is even if there exists an integer $k$ such that $n = 2k$, and n is odd if there exists an integer $k$ such that $n = 2k + 1$

## Contra-position
In a proof by contra-position, a statement of the form $p → q$ is proved by showing $¬q → ¬p$. This is correct, because the statements are logically equivalent

## Contradiction
- By Proving there is a fault when the opposite is assumed then you prove that's it's always correct

## Equivalence
-Proving if and only if ($\leftrightarrow$)

## Induction
- If is true for a value (n = 1)
- and is true for the next value assuming was true for the previous one (n = k, n = k+1)
- then is true for all values (n $\in \mathbb{N}$)
- Steps:
	1. Basis: Prove for lowest number
	2. Inductive: $P(n) \rightarrow P(n+1)$
	3. Assume: $P(n)$
	4. 

## Common Mistakes
- inadmissible argumentation with examples,
- using the same symbol to denote different things,
- using notions that have not been defined exactly, or even have inconsistent definitions,
- inadmissible gaps in the argumentation
- using unproven claims to justify proof steps,
- thinking that you are finished when there is still something to show, circular reasoning, i. e. using the statement that you are about to prove in the proof,
- mistakes in arithmetic and basic algebra