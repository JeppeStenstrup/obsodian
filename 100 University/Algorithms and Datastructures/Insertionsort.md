[[AD Proofs MOC]]

# Insertionsort
## Example
$A = [12, 11, 13, 5, 6]$
$i = 0$
$A = [12, 11, 13, 5, 6]$
$A[i] > A[i+1]$
$A = [12 \leftrightarrow 11, 13, 5, 6]$
$A = [11, 12, 13, 5, 6]$
$i++$ ($i = 1$)

$A = [11, 12, 13, 5, 6]$
$A[i] < A[i+1]$ so we move on
$i++$ ($i = 2$)

$A = [11, 12, 13, 5, 6]$
$A[i] > A[i+1]$ 
$A = [11, 12, 13 \leftrightarrow 5, 6]$
$A = [11, 12, 5, 13, 6]$
$A = [11, 12 \leftrightarrow 5, 13, 6]$
$A = [11, 5, 12, 13, 6]$
$A = [11 \leftrightarrow 5, 12, 13, 6]$
$A = [5, 11, 12, 13, 6]$
$i++$ ($i=3$)

$A = [5, 11, 12, 13, 6]$
$A[i] < A[i+1]$ so we move on
$i++$ ($i = 4$)

$A = [5, 11, 12, 13, 6]$
$A[i] > A[i+1]$ 
$A = [5, 11, 12, 13 \leftrightarrow 6]$
$A = [5, 11, 12 \leftrightarrow 6, 13]$
$A = [5, 11 \leftrightarrow 6, 12, 13]$
$A = [5, 6, 11, 12, 13]$