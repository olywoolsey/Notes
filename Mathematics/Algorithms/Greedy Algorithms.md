# Greedy Algorithms
#COMP2721 
## Paradigm
- Build a solution incrementally by choosing the next solution component using alocal and not forward-looking criteria
- Take a solution that looks locally optimal
- works for problems, where a non-optimal solution can be improved to an optimalsolution by incrementally replacing locally non-optimal solution components
- leads to very efficient algorithms
## Minimum Spanning Tree
Given a connected, undirected graph a MST is the graph that connects all the nodes with the lowest total edge weight
- a graph can have exponentially many spanning trees, e.g., the complete graph $K_n$ on n vertices has $n^{n−2}$ spanning trees (Cayley’s theorem)
- Therefore, it is not possible to solve the MST-problem by enumerating all possible spanning trees
- fortunately, there exists much more efficient algorithms for the problem that employ the greedy approach
### Prim's Algorithm
Start with some root node $s$ and greedily grow a tree $T$ from $s$ outward. At each step, add a cheapest edge $e$ to $T$ that has exactly one endpoint in $T$
### Kruskal's Algorithm
Start with $E(T ) = ∅$. Consider edges in ascending order of weight. Insert edge $e \text{ in } T$ unless doing so would create a cycle