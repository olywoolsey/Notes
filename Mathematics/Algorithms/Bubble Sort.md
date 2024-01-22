# Bubble Sort
#COMP2711 #Sort
## The Process
1. Move along the array and swap and time the next value is less than the current value
2. Once at the end go to the beginning and repeat
3. Stop when you pass through the array with no swaps
### Pseudo-code
```pseudocode
ALGORITHM bubbleSort (A[0..n-1])
for i in A do
	for j in A do
		if A[j] > A[j+1]
			A[j], A[j+1] = A[j+1], A[j]
```
## Analysis
- Can check if no swaps are made in a run through then it can exit early to increase efficiency in practice (doesn't effect O notation)
- Time Complexity $= O(n^2)$
- Slower than both [Selection Sort](Selection%20Sort.md) and [Insertion Sort](Insertion%20Sort.md)
