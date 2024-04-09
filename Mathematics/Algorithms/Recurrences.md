# Divide and Conquer
- The running time of a divide-and-conquer algorithm can be bounded by a function $T : N → N$ given by a recurrence.
- Each recurrence consists of initial conditions $T (n) = cn$ for small $n$ and a recursive equation that describes $T (n)$ in terms of $n$ and $T (m)$ for some $m < n$.
## Solving Recurrences
### Direct Method
- Also known as substitution method
- Always applies
- Substitute LHS of the function into the RHS of the function
#### Example
1. <F$T (n) = n + T (n − 1)$	
2. $= n + (n − 1) + T (n − 2)$
3. $= n + (n − 1) + (n − 2) + T (n − 3)$
4. $= n + (n − 1) + (n − 2) + · · · + 2 + 1 + T (0)$
5. $= n + (n − 1) + (n − 2) + · · · + 2 + 1 + 0$
6. $=\frac{1}{2}n(n+1)$
7. $=O(n^2)$
### Guessing Solution 
- Applies to recurrences of the form $T (n) = a_1T (n − 1) + a_2T (n − 2) + a_3T (n − 3) + ··· + a_kT (n − k)$
### Master Method
- Applies to recurrences of the form $T (n) = aT (n/b) + f (n)$
