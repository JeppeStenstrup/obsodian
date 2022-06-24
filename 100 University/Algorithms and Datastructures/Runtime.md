[[Algorithms and Datastructures]]

# Runtime
## General information
$$\begin{array}{ccccc} \leq & \geq & = & < & > \\ O & \Omega & \Theta & o & \omega \end{array}$$

## $O$ (_Big o_)
Definition: $f(n)=O(g(n))$

Hvis $f(n)$ og $g(n)$ er funktioner $N \rightarrow R$ og findes $c > 0$ og $N_0$ så for alle $n \geq N_0 : f(n) \leq c \cdot g(n)$

![[big_o_graph.png]]

Mening: $f \leq g$ i voksehastighed

---
## $\Omega$ (_Omega_)
Definition: $f(n)=\Omega(g(n))$

Hvis $f(n)$ og $g(n)$ er funktioner $N \rightarrow R$ og findes $c > 0$ og $N_0$ så for alle $n \geq N_0 : f(n) \geq c \cdot g(n)$

![[big_omega_graph.png]]

Mening: $f \geq g$ i voksehastighed

---
## $\Theta$ (_Theta_)
Definition: $f(n)=\Theta(g(n))$

Hvis $f(n)=O(g(n))$ og $f(n)=\Omega(g(n))$

![[big_theta_graph.png]]

Mening: $f=g$ i voksehastighed

---
## Køretider
![[runtime_sorting_algorithms.png]]
![[runtime_sorting_algorithms2.png]]