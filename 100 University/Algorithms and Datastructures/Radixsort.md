[[AD Proofs MOC]]

# Radixsort
## Definition
A sorting algorithm sorting number by least significant to most significant.

The way it does this, is by looking at the last number (the 1’s) of each number in the list and sorts the list, then looks at the second last (the 10’s) and does the same, until it reaches the most significant number.

And when it has reached the end (or start, w/e), the list is sorted.

## Illustrated
![[readix_sort.png]]

## Pseudo code
```python:
RadixSort(A, d):
	for i = 1 in range(0,d):
		# Sort with a stable sorting algorithm, most likely CountingSort, to
		# to sort A on digit i (i.e. A has d digits)
```

## [[Runtime]]
Given $n$ $d$-digit numbers in which each digit can take up to $k$ possible values, Radix Sort correctly sorts these numbers in $\Theta(d(n+k))$ time, if the stable sort it uses takes $\Theta(n+k)$ time.