# Dynamic Programming
Solving a problem by solving an array of problems
## Shortest Path in Layered Diagrams
- Layers look like columns 
- Each edge goes to an adjacent column  and not past
- Work way along storing distance travelled at each node
- Can find way back at the end 
## [Matrix](Matricies.md) Chain Product
We wish to compute the product $$A = A_1 · A_2 · A_3 \dots A_{n−1} · A_n$$ where $A_i$ is a $d_{i−1} × d_i$ matrix (for $i = 1,\dots , n$)

### Recurrence Relation
- For $1 ⩽ i ⩽ k ⩽ n \text{ let } M [i, k]$ denote minimum number of scalar multiplications to compute $A_i · · · · · A_k$
	- $M[i,j] = 0$ for all $i$ with $i \leq i \leq n$
	- $M [i, k] = min_{i⩽j<k}\{M [i, j] + d_{i−1}d_j d_k + M [j + 1, k]\}$ for all $i,k$ with $1 \leq i < k \leq n$
- If the minimum in the expression for $M [i, k]$ is realised for $j$ then the last matrix multiplication in the product $A_i · · · A_k$ should be $(A_i · · · A_j ) · (A_{j+1} · · · A_k)$.
#### pseudocode
**input:** an integer $n > 0$ (number of matrices $A_i$ to multiply)and an array $d[0..n]$ (sizes, $A_i$ is a $d[i − 1] \times d[i]$ matrix)
**output:** $M [1, n]$ the minimum number of scalar multiplications
begin:
	for $i \leftarrow 1$ to $n$ do $M [i, i] \leftarrow 0$;
	for $b \leftarrow 1 \text{ to } n − 1$ do
		for $i \leftarrow 1 \text{ to } n − b$ do
			$k \leftarrow i + b; m ← d[i − 1] ∗ d[k]; M [i, k] \leftarrow ∞;$
			for $j ← i \text{ to } k − 1$ do
				$N ← M [i, j] + m ∗ d[j] + M [j + 1, k];$
				$M [i, k] ← \text{min}(M [i, k], N)$

```python
# Python program using memoization
import sys
dp = [[-1 for i in range(100)] for j in range(100)]

# Function for matrix chain multiplication
def matrixChainMemoised(p, i, j):
    if(i == j):
        return 0

    if(dp[i][j] != -1):
        return dp[i][j]
	
    dp[i][j] = sys.maxsize
	
    for k in range(i,j):
        dp[i][j] = min(dp[i][j], matrixChainMemoised(p, i, k) + matrixChainMemoised(p, k + 1, j)+ p[i - 1] * p[k] * p[j])
	
    return dp[i][j]

def MatrixChainOrder(p,n):
    i = 1
    j = n - 1
    return matrixChainMemoised(p, i, j)

# Driver Code
arr = [3,4,6,4,2,3,5]
n = len(arr)
print("Minimum number of multiplications is",MatrixChainOrder(arr, n))
```


## Shortest Paths
## CYK Algorithm
## Travelling Salesman

```python
# Python program using memoization
import sys
dp = [[-1 for i in range(100)] for j in range(100)]

# Function for matrix chain multiplication
def matrixChainMemoised(p, i, j):
    if(i == j):
        return 0

    if(dp[i][j] != -1):
        return dp[i][j]
	
    dp[i][j] = sys.maxsize
	
    for k in range(i,j):
        dp[i][j] = min(dp[i][j], matrixChainMemoised(p, i, k) + matrixChainMemoised(p, k + 1, j)+ p[i - 1] * p[k] * p[j])
        print(f"{i},{j} = {dp[i][j]}")
	
    return dp[i][j]

def MatrixChainOrder(p,n):
    i = 1
    j = n - 1
    return matrixChainMemoised(p, i, j)

# Driver Code
arr = [3,4,6,4,2,3,5]
n = len(arr)
print("Minimum number of multiplications is",MatrixChainOrder(arr, n))
```