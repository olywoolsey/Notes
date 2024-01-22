# Binary Search
#COMP2711 #Search
- Much faster than [Sequential Search](Sequential%20Search.md), but only works on sorted arrays
- Time Complexity $= O(logn)$
## The Process
1. **Divide:** if a stopping criteria is not reached; divide problem instance into smaller instances
2. **Recur:** the smaller instances are solved recursively
3. **Conquer:** *if necessary*, the problems obtained for the smaller instances are combined in order to get a solution for the original problem
### Pseudo-code
```pseudocode
//Input: an array A[l..r] sorted in ascending
// order, defined by its left and right
// indices l and r;
// a search key K
//Output: an index of the array’s element that
// is equal to K,
// or –1 if there is no such element
```
#### Iterative
```pseudocode
ALGORITHM binarySearch(A[l..r],K)
while l <= r do
	mid <- (l+r)/2
	if K == A[mid] 
		return mid 
	else
		if K < A[mid] r <- mid-1
		else l <- mid+1
return –1 //Search key not in array
```
#### Recursive
```pseudocode
ALGORITHM binarySearch(A[l..r],K)
if l > r return –1 //there are no elements to search
else
	mid <- (l+r)/2
	if K == A[mid] return mid
	else
		if K < A[mid] 
			return binarySearch(A[l..mid-1],K)
		else 
			return binarySearch(A[mid+1..r],K)
```
### Example
1. Array: n=13, K=19:
2. Compare K with 25

| l=0 | 1 | 2 | 3 | 4 | 5 | <font color=#ee4444>6 | 7 | 8 | 9 | 10 | 11 | r=12 |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| 11 | 12 | 13 | 16 | 19 | 20 | <font color=#ee4444>25 | 27 | 30 | 35 | 39 | 41 | 46 |
3. Choose Left as K<25
4. Compare K with 13

| l=0 | 1 | <font color=#ee4444>2 | 3 | 4 | r=5 |
| ---- | ---- | ---- | ---- | ---- | ---- |
| 11 | 12 | <font color=#ee4444>13 | 16 | 19 | 20 |
5. Choose right sub array as K > 13
6. Compare k with 19

| l=3 | <font color=#ee4444>4 | r=5 |
| ---- | ---- | ---- |
| 16 | <font color=#ee4444>19 | 20 |
7. Search key is found. Return it's index: 4
## Analysis
- We make 1 of two assumptions:
	1. $n$ is a power of 2
		- $n=2^q$ for some $q$
	2. $n$ is not a power of 2
		- $n=2^{q-1}$ for some $q$
- We can always find an integer q that $2^{q-1} \leq n < 2^q$
- Therefore: $q-1 \leq log_2n < q$
- Algorithm performs no more than $q$ iterations to obtain a sub-array with one element
- Time Complexity $= O(logn)$