---
aliases: DSM
---
[[Concepts MOC]]

# Design Structure Matrix
## Structural Dependencies
![[DSM_structural_dependencies.png]]

### Observations
- Quite sparse
	- Not heavily structural coupled
	- Easy to change files independently
	- Little architectural debt

![[DSM_strucural_dependencies_2.png]]

### Observations
- Rather dense
	- Strongly evolutionary coupled
- Annotations above the diagonal
	- Coupling in all directions
- High architectural debt
	- Confirmed by architects
	- Every change is costly and complex