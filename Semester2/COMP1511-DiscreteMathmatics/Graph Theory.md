[Chapter 10 / 11](https://docs.google.com/viewer?a=v&pid=sites&srcid=ZGVmYXVsdGRvbWFpbnxzYWVlZG9vbjF8Z3g6N2JmM2Y5YWEzMmRlNWUzNw)
## Graph Theory
- A simple graph $G=(V(G),E(G))$ with $p$ vertices and $q$ edges consists of a vertex set( or node set) $V(G)= \{v_1, .. v_p\}$ and an edge set $E(G) = \{e_1, ..e_q\}$ 
- each edge os an unordered pair of vertices
- An edge $e = \{uv\}$, is also denoted by $uv$ or $vu$
- The vertices in an edge $e$ are it's endpoints (or endnodes or endvertices) and $e$ is said to connect $u$ and $v$
- An edge is said to be incident to it's endpoints
- Two vertices that are endpoints to the same edge are adjacent vertices
- Two edges that are incident to the same vertex are said to be adjacent edges
- Two adjacent vertices are also called neighbouring vertices

### Multigraphs
- allow loops (edges joining a vertex to itself)
- allow parallel edges (several edges joining the same two vertices)
### Directed Graphs
- also called digraphs
- edges are ordered pairs of vertices and are called directed edges or arcs
### Weighted Graphs
- each edge is assigned a weight

## Isomorphic Graphs
- Two graphs that have the same structural properties, even if the labels of the vertices and edges differ
- Let $G$ and $H$ be simple graphs. $G$ is isomorphic to $H$, denoted by $G ∼= H$, if there exists a bijection $f : V(G) →V(H)$ such that $uv ∈ E(G)$ if and only if $f(u)f(v) ∈ E(H)$
- Since we will mostly be interested in structural properties of graphs, we will often omit labels when drawing graphs
- An unlabelled graph can be thought of as a representative of an equivalence class of isomorphic graphs
- We assign labels to vertices and edges in a graph for the purpose of referring to them
### Problem
determine in polynomial time whether two graphs are isomorphic. (This is a very difficult problem that is still unsolved).

## Vertex Degree
- Denoted $d_G(v)$ or $d(v)$ or $deg(v)$
- Is the number of edges that are incident to $v$ with loops counted twice
$THEOREM1$ If $G$ is a graph with vertices $V_1, v_2,...v_n$ then $\sum\limits_{i=1}^n d(v_i) = 2|E(G)|$
$Proof:$ Each loop contributes 2 to the summation and each edge $e=uv$ that is not a loop is counted exactly twice, once in $d(u)$ and once in $d(v)$ 
### Friendship puzzle
- Used with the [[Combinatrics - Counting Methods#Pigeon hole principle |Pigeon hole principle]]