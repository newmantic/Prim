# Prim

Prim's Algorithm is an algorithm to find Minimum Spanning Tree (MST). Given a connected, undirected graph G = (V, E) with weights w(u, v) for each edge (u, v) in E, a minimum spanning tree is a subset of the edges that connects all vertices without cycles and with the minimum possible total edge weight.

Initialization:
Start with a vertex v from the graph G.
Let MST be an empty set of edges.
Initialize a priority queue (or min-heap) to keep track of edges with their weights.
Set visited = {v}, where visited is a set of vertices included in the MST.

Add Initial Edges:
For each edge (v, u) where u is adjacent to v, add the edge to the priority queue with its weight:
For each edge (v, u):
PQ.push((w(v, u), (v, u))) // Push the edge with weight to the priority queue.

While the priority queue is not empty and |MST| < |V| - 1:
Extract the minimum weight edge (u, v) from the priority queue:
weight, edge = PQ.pop()
Check if the vertex v is already visited:
If v is not in visited:
Add the edge (u, v) to the MST:
MST.add(edge)
Add v to the visited set:
visited.add(v)
For each edge (v, w) where w is adjacent to v and not visited, add to the priority queue:
For each edge (v, w):
If w is not in visited:
PQ.push((w(v, w), (v, w)))

Termination:
The algorithm terminates when all vertices are included in the MST, i.e., when |MST| = |V| - 1.

Time Complexity:
Using a binary heap (priority queue), the time complexity of Prim's algorithm is O(E log V), where E is the number of edges and V is the number of vertices.

Prim's algorithm is greedy; it always selects the smallest edge that expands the growing MST.
It works efficiently with dense graphs.
It can be implemented using adjacency lists or matrices.
