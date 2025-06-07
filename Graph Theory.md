>[!definition]
>A pseudograph consist of a set of vertices (or points) and pairs of these (not necessarily all pairs) are connected by edges (or line segments).
>Suppose G is a pseudograph. The set of verstices of G is ususally denoted by V; the set of edges is denoted by E; Then G can be indicated by G = (V,E)

- In pseudographs, loops (edges that connect a vertex to itself ) and multiple edges (more than one edge connecting two vertices) may exist.
>[!tip] Simple graph
>A pseudograph with no loops and multiple edges is called ~={purple}simple graph.=~

---
# Adjacency, Incidence, Degree
- **Adjacent** :
	Two vertices are said to be adjacent if they are connected to each other by an edge.
-  **Incident**:
	If a vertex(v) is an end vertex of some edge (e) then they (v and e) are said to be incident on each other.
- **Degree**:
	The number of incidents on a vertex is called the degree of that  vertex. (deg(v)
- A vertex with degree zero is called an isolated vertex.
---
# Hand shaking lemma
Let $G$ be a simple graph (or a pseudo graph)  
with $n$ vertices (say $V(G) = \{v_1, v_2, \cdots, v_n\}$) and $m$ edges. Then,

$$
\sum_{i=1}^{n} \deg(v_i) = 2m ; \text{m = The number of edges}
$$
Proof:
An edge is incident with two distinct vertices if it is not a loop. Otherwise, it is incident to the same vertex twice. In both cases, an edge gets counted twice. Therefore, if there are m edges in G, then the degree sum is 2m.

---
>[!theorem]
>In every simple graph, the number of vertices with odd degree is even.

---
>[!tip] Regular graph
>All vertices of the graph have the same degree.
>If a vertex of a regular graph has a degree of r, then it is called r-regular graph.

>[!tip] null graph
>Graph with no edges

>[!tip] complete graph
>Simple graph in which each pair of vertices connected by an edge.

---
>[!theorem]
>For each $( n \in \mathbb{N} )$, the complete graph $( K_n )$ contains
>$$\frac{n(n - 1)}{2}$$
>edges.

---
>[!tip] Subgraph
>A graph $G' = (V', E')$ is said to be a subgraph of a graph  
$G = (V, E)$ if whose vertex set and edge set are subsets of those of $G$. That is$$V' \subseteq V \quad \text{and} \quad E' \subseteq E$$
If $G'$ is a subgraph of $G$, then $G$ is said to be a supergraph of $G'$.

>[!tip] Complement or Inverse
>The complement or inverse of a graph $G$ is a graph $H$ on the  
same vertices such that two distinct vertices of $H$ are adjacent  
if and only if they are **not** adjacent in $G$. The complement (or inverse)  
of $G$ is denoted by $G^C$. (Here, graphs are assumed to be simple.)
>- Basically, its the graph which connect only the remaining parts of the graph for which it to be complete.
>- A simple graph $G$ is said to be self-complementary if  
$G \cong G^C$. (This simbol is not closely equal. It saying the graphs are similar in shape.)

>[!Thoerem]
>Any simple graph $(G^{c})^{c} = G$

>[!tip] Bipartite graph
>Is a simple graph where the vertices can be divided into two disjoint sets $V_1$ and $V_2$ such that all edges connect a vertex in one set to a vertex in other set. There are no edges between vertices in the set itself $V_1, V_2$
>- **Complete bipartite graph** is a bipartite graph in which every vertex in $V_1$ is joined to every vertex in $V_2$. 
>- The complete bipartite graph on bipartition sets m and n vertices is denoted as $K_{m,n}$

---
# Representation of graphs and graph isomorphism

- **Adjacency matrix** is suitable for dense graph
>[!tip] Adjacency matrix
>Let $G$ be a graph (simple or multi) with $n$ vertices (say $V(G) = \{v_1, \cdots, v_n\}$). Then the adjacency matrix $A(G)$ of $G$ is an $n \times n$ matrix and $$A(G) = (a_{ij})$$
where $a_{ij}$ is the number of edges between $v_i$ and $v_j$ for each $i, j \in \{1, \cdots, n\}$.

- If the adjacency matrix is not symmetric, it means that the edges are directed edges.
- The incidence matrix representation is particularly useful when dealing with sparse graphs with relatively few edges and when analyzing edge connectivity.
>[!tip] Incidence matrix
>Let $G$ be an undirected simple graph or a multi-graph with $n$ vertices,  
$V(G) = \{v_1, \cdots, v_n\}$, and $m$ edges, $E(G) = \{e_1, \cdots, e_m\}$.  
Then the incidence matrix $I(G)$ of $G$ is an $n \times m$ matrix and $$I(G) = (a_{ij}) \quad \text{where}$$$$a_{ij} =\begin{cases}1 & \text{if } v_i \text{ is adjacent to a distinct vertex by } e_j \\[6pt] 2 & \text{if } e_j \text{ is a loop at } v_i \\[6pt] 0 & \text{otherwise}
\end{cases} $$
> - The matrix basically has Edge as a column and vertex as a row. You have record if a certain vertex has a certain edge and the relationship as above.

>[!tip] Digraph - (The same old Directed graph)
>Its an ordered pair G = (V,E) where V is the  set of all vertices of G and E is a set of ordered pairs of vertices, called arcs, directed edges, arrows, or lines.
>Let $G$ be a simple digraph or a multi-digraph with $n$ vertices,  
$V(G) = \{v_1, \cdots, v_n\}$, and $m$ edges, $E(G) = \{e_1, \cdots, e_m\}$.  
Then the incidence matrix $I(G)$ of $G$ is an $n \times m$ matrix and  $$
I(G) = (a_{ij}) \quad \text{where}$$$$a_{ij} = 
\begin{cases}1 & \text{if } v_i \text{ is the tail of } e_j \\[6pt]
-1 & \text{if } v_i \text{ is the head of } e_j \\[6pt]2 & \text{if } e_j \text{ is a loop at } v_i \\[6pt]0 & \text{otherwise}
\end{cases}$$
> - $v_i$ is the **tail** of $e_j$ means $v_i$ is the **terminal vertex** of $e_j$, while $v_i$ is the **head** of $e_j$ means $v_i$ is the **initial vertex** of $e_j$.
![[Pasted image 20250607131241.png]]

- An ordered pair $(u, v)$ represents a directed edge from vertex $u$ to vertex $v$. The order indicates direction: the edge goes **from** $u$ **to** $v$.

## Graph isomorphism
- $G_1 = (V_1,E_1),G_2 = (V_2,E_2)$ are isomorphic if,
	1. $\exists$ a bijection $f: v_1 \rightarrow v_2$
	2. For each $u,v \in V_1$
			$(u,v) \in E_1 \iff (f(u),f(v)) \in E_2$
- Then we say $G_1 \cong G_2$
- It is easy to see that if two graphs G1 and G2 are isomorphic then they have the same number of vertices, the same number of edges, and the same degree sequence.

---
# Connectedness

Let G be a simple or multi-graph. 
>[!tip] Walk
>A **walk** in G is a finite alternating sequence of vertices and edges, which begins and ends with a vertex, so that each edge is incident with the vertices preceding and following it, and ==Any vertex or edge can appear more than once==

>[!tip] Trail
>A finite alternating sequence of vertices and edges, which begins and ends with a vertex, so that each edge is incident with the vertices preceding and following it, and ==Any edge cannot appear more than once, but vertices can be repeated==
>- Or you can say walk is a trail where repetition of edges is allowed.

>[!tip] Circuit
>A trail is called a circuit if its initial and terminal vertices are the same.
>- A circuit is a closed trail.

>[!tip] Path
>Its a trail in which ==no vertex appear more than once==.
>- Basically no edge and vertex repitions.

>[!tip] Cycle
>A closed path is a cycle.
>- A graph containing at least one cycle is called a cyclic graph, otherwise acyclic graph.
>- A simple graph consisting of only a cycle with n vertices is called an n-cycle and it is denoted by $C_n$.

---
>[!tip] Connected graph
>Let G be a simple or multi graph, it is a connected graph if each pair of vertices can be connected by a path in G. Otherwise, it is called disconnected graph.

