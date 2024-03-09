---
Percent: 7%
Status: Doing
Due: 2024-03-11
Type: Course Work
---
# Dynamic Programming
# Q1
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
# Q2 
```python
##  # Floyd Warshall Algorithm in python

INF = 999
# The number of vertices
nV = 6

# Algorithm implementation
def floyd_warshall(G):
    distance = list(map(lambda i: list(map(lambda j: j, i)), G))

    # Adding vertices individually
    for k in range(nV):
        for i in range(nV):
            for j in range(nV):
                distance[i][j] = min(distance[i][j], distance[i][k] + distance[k][j])
    print_solution(distance)

# Printing the solution
def print_solution(distance):
    for i in range(nV):
        for j in range(nV):
            if(distance[i][j] == INF):
                print("INF", end=" ")
            else:
                print(distance[i][j], end="  ")
        print(" ")

G = [[0, 2, INF, 3, 3, INF],
	[2, 0, 1, INF, 3, INF],
	[INF, 1, 0, INF, 2, 3],
	[-1, INF, INF, 0, -3, INF],
	[3, -2, 2, 4, 0, 3],
	[INF, INF, 3, INF, -2, 0]
	]
floyd_warshall(G)
```