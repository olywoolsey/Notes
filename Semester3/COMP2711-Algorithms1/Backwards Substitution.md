# Backwards Substitution
## Recurrence Relations
1. Find your recurrence relation $M(n) = \dots$
2. Substitute the Relation into the formula where it is called i.e. M(n-1) 
3. Repeat till you see a pattern. Advise till $C(n-3) - C(n-4)$.
4. Substitute $i$ in the relation
5. Simplify the series (where is not $C(n-i)$)
6. Find $i$ so that $C(n-i)$ is equivalent to the initial condition
7. Sub in for $i$
8. Simplify
### E.G.
$C(n) = C(n-1) + 4n$ for $n \geq 1$ with initial condition $C(0) = 1$
$C(n) = (C(n-2) + 4(n-1)) + 4n$
$C(n) = ((C(n-3) + 4(n-2)) +4(n-1)) + 4n$
$C(n) = C(n-i) + 4(i+(i-1)+(i-2)...+1$
$C(n) = C(n-i)  + 4(1 + 2 + 3 +...+ i)$
$C(n) = C(n-i) + 4(\frac{1}{2}(i+1)i)$
$C(n) = C(n-i) + 2i(i+1)$
$i = n$
$C(n) = C(0) + 2n(n+1)$
$C(n) = 1 + 2n(n+1)$
$C(n) = 2n^2 +2n +1$
### E.G.
$C(n) = 3M(n-1) + 2$ for $n > 1$ with initial condition $M(1) = 2$
$C(n) = 3(3M(n-2) + 2) + 2$
$C(n) = 3(3(3M(n-3) + 2) + 2) + 2$
$C(n) = 3^iM(n-i) + 2 +3^12 + 3^22$
$C(n) = 3^iM(n-i) + 2(1 +3^1 + 3^2 + 3^n)$
$C(n) = 3^iM(n-i) + 2(\frac{3^{n-1}-1}{3-1})$
$n - i = 1 \rightarrow i = n-1$
$C(n) = 3^{(n-1)}M(n-(n-1)) + 2\frac{3^{n-1}-1}{2}$
$C(n) = 3^{(n-1)}M(1) + 3^{n-1}-1$
$C(n) = 3^{(n-1)}2 + 3^{n-1}-1$
$C(n) = \frac{2}{3}3^n + \frac{1}{3}3^n-1$
$C(n) = 3^n-1$
