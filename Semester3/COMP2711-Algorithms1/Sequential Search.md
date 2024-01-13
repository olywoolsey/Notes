# Sequential Search
- Slower than [Binary Search](Binary%20Search.md), but works on unsorted arrays
- Uses Brute-force Strategy
- Time Complexity $= O(n)$
## The Process
1. Check if element matches value being searched for
2. If not move to next value
3. Repeat till value is found or searched all the array
### Pseudo-code
```pseudocode
ALGORITHM sequentialSearch(A[0..n-1],K)
// Input: an array A[0..n-1] and a search key K
// Output: the index of the element of A that
// matches K, or –1 if there is no such element
i <- 0
while i <= n-1 and A[i]!=K do
	i <- i+1
if i < n 
	return i        // i is the index of key K
else 
	return -1       // key K is not found
```
## Analysis
- Best case: A[0] == $K$
- Worst case: $K$ is not in the array - performs $n$ comparisons
- Average case: $\frac{n}{2}$ comparisons
- Time Complexity $= O(n)$