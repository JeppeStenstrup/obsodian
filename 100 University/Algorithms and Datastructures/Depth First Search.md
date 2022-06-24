---
aliases: DFS
---

[[AD Proofs MOC]]

# Depth First Search
## Definition
A method to locate / traverse over all nodes in a graph, by running through the graph child, grandchild, etc., and then back.

# Illustrated
![[dfs_graph.png]]

## Runtime
$O(n+m)$

## Edges
Nodes in the stack is colored gray, when discovered and we traverse back, we color them black.

When an edge $(u, v)$:
1. **Tree edges**: $v$ is white
2. **Back edges**: $v$ is gray (in the stack)
3. **Forward edge**: $v$ is black (not in the stack, but has been with $u$)
4. **Cross edge**: $v$ is black (not in the stack, and hasn't been with $u$)

In unordered lists, forward edges and cross edges cannot occur.