[[AD Proofs MOC]]

# Tree-Search

![[search_tree.png]]

## Pseudo code
```
tree_search(x,k):
	if x == NIL or k == key[x]
		return x
	if k < x.key
		return tree_search(x.left,k)
	else return tree_search(x.right,k)
```

We always assume the left child is smaller than the node we're on, and the right child to be larger.