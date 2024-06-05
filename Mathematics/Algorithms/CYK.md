# CYK Algorithm
The Cocke-Younger-Kasami (CYK) algorithm is a parsing algorithm for context-free grammars (CFGs) in Chomsky normal form (CNF).

## Membership Problem
- For a fixed [CFG](Context%20Free%20Grammer) in [CNF](Chomsky%20Normal%20Form.md), the membership problem is, given a string $s = x_1x_2\dots x_n$consisting of $n$ terminals $x_i \in T$ , is there a derivation $S ⇒∗ s$?
```pseudocode
fixed : A CFG G = (V, T, P, S) in CNF is not part of the input.
input : a string w = x1x2 . . . xn with xi ∈ T for i = 1, . . . , n
output: accept if w ∈ L(G) otherwise reject
begin
for i ← 1 to n do V (i, i) ← {A ∈ V | (A → xi) ∈ P } ;
for b ← 1 to n − 1 do
	for i ← 1 to n − b do
		k ← i + b; V (i, k) ← ∅;
		for j ← i to k − 1 do
			for (A → BC) ∈ P do
				if B ∈ V (i, j) and C ∈ V (j + 1, k) then
					V (i, k) ← V (i, k) ∪ {A} ;
if S ∈ V (1, n) then accept w else reject w;
```
### Example
We consider the CFG $(V, T, P, S)$ with $T = {a, b}, V = {S, A, B, C}$ and the productions:
$$
\begin{aligned}
S \rightarrow AB | BC \\
A \rightarrow BA | a  \\
B \rightarrow CC | b  \\
C \rightarrow AB | a  \\
\end{aligned}
$$
1. Fill in $V(i,k)$ where $i=k$

|       | $k=1$ | $k=2$ | $k=3$ | $k=4$ | $k=5$ |
| ----- | ----- | ----- | ----- | ----- | ----- |
| $i=1$ | {B}   |       |       |       |       |
| $i=2$ |       | {A,C} |       |       |       |
| $i=3$ |       |       | {A,C} |       |       |
| $i=4$ |       |       |       | {B}   |       |
| $i=5$ |       |       |       |       | {A,C} |
2. Fill in $V(i,k)$ where $i+1=k$

|       | $k=1$ | $k=2$ | $k=3$ | $k=4$ | $k=5$ |
| ----- | ----- | ----- | ----- | ----- | ----- |
| $i=1$ | {B}   | {S,A} |       |       |       |
| $i=2$ |       | {A,C} | {B}   |       |       |
| $i=3$ |       |       | {A,C} | {S,C} |       |
| $i=4$ |       |       |       | {B}   | {A,S} |
| $i=5$ |       |       |       |       | {A,C} |
4. Fill in $V(i,k)$ where $i+2=k$


|       | $k=1$ | $k=2$ | $k=3$       | $k=4$ | $k=5$ |
| ----- | ----- | ----- | ----------- | ----- | ----- |
| $i=1$ | {B}   | {S,A} | $\emptyset$ |       |       |
| $i=2$ |       | {A,C} | {B}         | {B}   |       |
| $i=3$ |       |       | {A,C}       | {S,C} | {B}   |
| $i=4$ |       |       |             | {B}   | {A,S} |
| $i=5$ |       |       |             |       | {A,C} |
5. Fill in $V(i,k)$ where $i+3=k$

|       | $k=1$ | $k=2$ | $k=3$       | $k=4$       | $k=5$   |
| ----- | ----- | ----- | ----------- | ----------- | ------- |
| $i=1$ | {B}   | {S,A} | $\emptyset$ | $\emptyset$ |         |
| $i=2$ |       | {A,C} | {B}         | {B}         | {S,A,C} |
| $i=3$ |       |       | {A,C}       | {S,C}       | {B}     |
| $i=4$ |       |       |             | {B}         | {A,S}   |
| $i=5$ |       |       |             |             | {A,C}   |
6. Fill in last square

|       | $k=1$                 | $k=2$                     | $k=3$                          | $k=4$                            | $k=5$                      |
| ----- | --------------------- | ------------------------- | ------------------------------ | -------------------------------- | -------------------------- |
| $i=1$ | <FONT color="red">{B} | <FONT color="green">{S,A} | <FONT color="blue">$\emptyset$ | <FONT color="orange">$\emptyset$ | {S,A,C}                    |
| $i=2$ |                       | {A,C}                     | {B}                            | {B}                              | <FONT color="red">{S,A,C}  |
| $i=3$ |                       |                           | {A,C}                          | {S,C}                            | <FONT color="green">{B}    |
| $i=4$ |                       |                           |                                | {B}                              | <FONT color="blue">{A,S}   |
| $i=5$ |                       |                           |                                |                                  | <FONT color="orange">{A,C} |
