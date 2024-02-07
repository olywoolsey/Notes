# Connected Component
- A maximal connected subgraph of a graph is called a connected component. A disconnected graph is the disjoint union of its connected components
- Example: A disconnected graph with 3 connected components. ![](Pasted%20image%2020240207114601.png)
## Identifying connected components: 
- Find all nodes that can be reached from $s$
### Solution
- call DFS(G,s) or BFS(G,s).
- A node u is reachable from s if and only if visited[u]=true
## Counting
