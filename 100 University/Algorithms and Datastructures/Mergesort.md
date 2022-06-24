[[AD Proofs MOC]]

# Mergesort
## Definition
For hver [[Partition|partition]] bliver $n$ delt i to, indtil $n=1$. (Se figur 2)

Det vil sige:
$\frac{\frac{\frac{n}{2}}{2}}{...} = 1 \Rightarrow \frac{n}{2^k} \Rightarrow n = 2^k \Rightarrow k = n\log n$

## Illustrated
![[quicksort_fig_1.png]]
Figure 1
![[quicksort_fig_2.png]]
Figure 2

# [[Runtime]]
Worst case: $T(n)=T(0)+T(n-1)+cn = O(n^2)$

Average/expected case: $T(n)=T(n/2)+T(n/2)+cn = O(n \text{ log}n)$

Best case: $T(n)=T(n/2)+T(n/2)+cn = O(n \text{ log}n)$

## Pseudo code
```python:
def quicksort(A, p, r):
	q = Partition(A, p, r)
	quicksort(A, p, q - 1)
	quicksort(A, q + 1, r)
```