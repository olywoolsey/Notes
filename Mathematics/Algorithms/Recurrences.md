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
- Applies to recurrences of the form $T (n) = a_1T (n − 1) + a_2T (n − 2) + a_3T (n − 3) + ··· + a_kT (n − k)$
### Master Method
- Applies to recurrences of the form $$T (n) = aT (n/b) + f (n)$$ where $a ⩾ 1$ and $b > 1$ are constants and $f (n) > 0$ for almost all n (means all but finite)
- Let a, b, f , and T as above.
- T (n) can be bounded asymptotically as follows.
	- If $f(n) = O(n^{log_b a−ε})$ for some constant $ε > 0$ then $T (n) = O(n^{log_b a})$.
	- If $f(n) = O(n^{log_b a})$ then $T(n) = O(n^{log_b a}log n)$.
	- If $n^{logb a+ε} = O(f (n))$ for some constant $ε > 0$, and if $af ( nb ) ⩽ cf (n)$ for some constant $c < 1$ and almost all $n$, then $T (n) = O(f (n))$
### Master Method How?
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
1. If $f(n) = O(n^(log_b a - ε))$ for some $ε > 0$:
	- If the work done outside the recursive calls is bounded by a polynomial of $n$ with a lower exponent than $log_b (a)$, then the time complexity is dominated by the recursive calls. In this case, the time complexity is $Θ(n^(log_b a))$.
2. If $f(n) = Θ(n^(log_b a))$: 
	- If the work done outside the recursive calls is of the same order as the work done by the recursive calls, then the time complexity is multiplied by a logarithmic factor. In this case, the time complexity is `Θ(n^(log_b a) * log n)`.
3. If `f(n) = Ω(n^(log_b a + ε))` for some `ε > 0` and if `a * f(n/b) ≤ c * f(n)` for some constant `c < 1` and sufficiently large `n`:** If the work done outside the recursive calls is greater than the work done by the recursive calls and satisfies the regularity condition, then the time complexity is dominated by the work done outside the recursive calls. In this case, the time complexity is `Θ(f(n))`.

To apply the Master Theorem, you need to identify the values of `a`, `b`, and `f(n)` from the given recurrence relation and compare `f(n)` with `n^(log_b a)` to determine which case applies. Once you identify the case, you can determine the time complexity accordingly.

The Master Theorem is a powerful tool for analyzing the time complexity of recursive algorithms, providing a quick and efficient way to determine the asymptotic behavior of functions defined by recurrence relations.

