# Divide and Conquer
- The running time of a divide-and-conquer algorithm can be bounded by a function $T : N → N$ given by a recurrence.
- Each recurrence consists of initial conditions $T (n) = cn$ for small $n$ and a recursive equation that describes $T (n)$ in terms of $n$ and $T (m)$ for some $m < n$.
## Solving Recurrences
### Direct Method
- Also known as substitution method
- Always applies
- Substitute LHS of the function into the RHS of the function
#### Example
1. $T (n) = n + T (n − 1)$	
2. $= n + (n − 1) + T (n − 2)$
3. $= n + (n − 1) + (n − 2) + T (n − 3)$
4. $= n + (n − 1) + (n − 2) + · · · + 2 + 1 + T (0)$
5. $= n + (n − 1) + (n − 2) + · · · + 2 + 1 + 0$
6. $=\frac{1}{2}n(n+1)$
7. $=O(n^2)$
### Guessing Solution 
- Applies to recurrences of the form 
$$
T (n) = a_1T (n − 1) + a_2T (n − 2) + a_3T (n − 3) + ··· + a_kT (n − k)$
$$

### Master Method
The general form of a recurrence relation that can be solved using the Master Theorem is:
$$
T(n) = aT(n/b) + f(n)
$$
where:
- $T(n)$ is the time complexity function being analysed.
- $a$ is the number of recursive sub-problems and $a \geq 1$
- $n/b$ is the size of each sub-problem and $b > 1$
- $f(n)$ is the work done outside of the recursive calls, which includes the cost of dividing the problem and combining the solutions.

The Master Theorem provides three cases:
1. If $f(n) = O(n^{log_b a - ε})$ for some $ε > 0$:
	- Time complexity is $Θ(n^{log_b a})$.
	- If the work done outside the recursive calls is bounded by a polynomial of $n$ with a lower exponent than $log_b (a)$, then the time complexity is dominated by the recursive calls. 
2. If $f(n) = O(n^{log_b a})$:
	- $T(n) = O(n^{log_b a}log n)$.
	- If the work done outside the recursive calls is of the same order as the work done by the recursive calls, then the time complexity is multiplied by a logarithmic factor. 
3. If $n^{logb a+ε} = O(f (n))$ for some constant $ε > 0$, and if $af ( nb ) ⩽ cf (n)$ for some constant $c < 1$ and almost all $n$:
	- Time Complexity is $T (n) = O(f (n))$
	- If the work done outside the recursive calls is greater than the work done by the recursive calls and satisfies the regularity condition, then the time complexity is dominated by the work done outside the recursive calls.

To apply the Master Theorem, you need to identify the values of `a`, `b`, and `f(n)` from the given recurrence relation and compare `f(n)` with `n^(log_b a)` to determine which case applies. Once you identify the case, you can determine the time complexity accordingly.

