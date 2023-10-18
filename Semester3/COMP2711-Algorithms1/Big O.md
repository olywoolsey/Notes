#COMP2711 
- Worst case efficiency for input of size n
- Time complexity does not matter for small $n$
## Finding the O notation of a function
- $t(n) \leq cf(n)$ for $n \geq n_0$
	- $t(n)$ is the worst case
	- $n_0$ is the point where they diverge
	- $cf(n)$ is worst case where $c$ is a constant and $f)n)$ is the function of $n$
	- to get $c$ you take the maximum value c can be at that point
		- $100n + 5, c = 105$
		- $5n^3 -2n, c = 5$
		- $3n + 5nlog_2n, c = 8$
	- have to provide $c$ and $n_0$
### Log Classes
- $log_a(n)$ is in the same class as $log_b(n)$ when $a \neq b$ 
- therefore can write as $log(n)$
