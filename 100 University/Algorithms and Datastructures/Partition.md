[[AD Proofs MOC]]

# Partition
## Pseudo code
```python:
def partition(A, p, r):
	x = A[r]
	i = p - 1
	for j in range(p, r - 1):
		if A[j] <= x:
			i += 1
			A[i], A[j] = A[j], A[i]
	A[i + 1], A[r] = A[r], A[i + 1]
	return i + 1
```
