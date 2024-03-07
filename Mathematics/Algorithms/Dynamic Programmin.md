# Dynamic Programming
Solving a problem by solving an array of problems
## Shortest Path in Layered Diagrams
- Layers look like columns 
- Each edge goes to an adjacent column  and not past
- Work way along storing distance travelled at each node
- Can find way back at the end 
## [Matrix](Matricies.md) Chain Product
We wish to compute the product $$A = A_1 · A_2 · A_3 \dots A_{n−1} · A_n$$ where $A_i$ is a $d_{i−1} × d_i$ matrix (for $i = 1,\dots , n$)

### Recurance Relation
- For $1 ⩽ i ⩽ k ⩽ n \text{ let } M [i, k]$ denote minimum number of scalar multiplications to compute $A_i · · · · · A_k$
	- $M[i,j] = 0$ for all $i$ with $i \leq i \leq n$
	- $M [i, k] = min_{i⩽j<k}\{M [i, j] + d_{i−1}d_j d_k + M [j + 1, k]\}$ for all $i,k$ with $1 \leq i < k \leq n$
- If the minimum in the expression for $M [i, k]$ is realised for $j$ then the last matrix multiplication in the product $A_i · · · A_k$ should be $(A_i · · · A_j ) · (A_{j+1} · · · A_k)$.
## Shortest Paths
## CYK Algorithm
## Travelling Salesman
