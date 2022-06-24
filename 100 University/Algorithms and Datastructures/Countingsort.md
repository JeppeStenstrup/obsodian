[[AD Proofs MOC]]

# Countingsort
$A = [3,1,4,3,5,0,3,1]$

Count occurrences for each value:
$B_1 =$

|0|1|2|3|4|5|
|-|-|-|-|-|-|
|1|2|0|3|1|1|

Add numbers from left to right:
$B_2 =$

|0|1|2|3|4|5|
|-|-|-|-|-|-|
|1|3|3|6|7|8|

Shift the bottom part of the list one to the right:
$B_3 =$

|0|1|2|3|4|5|
|-|-|-|-|-|-|
|0|1|3|3|6|7|

We now have the position where each number begins, so the result is:

$C = [0,1,1,3,3,3,4,5]$