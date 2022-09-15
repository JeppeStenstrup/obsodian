[[CS231n]]

[link](https://cs231n.github.io/linear-classify/)

# Linear Classification
![[Pasted image 20220914085733.png]]

## The backbone of neural networks
- Binary classification
	- Sick/not sick
- Multi-class classification
	- One-vs-All
		- Binary classification for each class
	- One-vs-one
		- Binary classifier for each class, against each of the other classes

## SVM / Hinge Loss
Scores are calculated by $f(x,W,b)=W\times x+b$, which gives $k$ classes scores $s$, one for each class $j$.
For example $x_i$ -> $s_j = W_j\times x_i+b_j$

Loss: $L_i=\sum_\limits{j\neq y_i} max(0,s_j-s_{y_i}+\Delta)$

## Softmax (Cross Entropy Loss)

Score is calculated as before, $f(x,W,b)=W\times x+b$, which results in the $k$ class score $s_j = W_j\times x_i+b_j$.

After scoring, the scores are converted into normalized probabilities though the $Softmax$-function.

$Softmax = P(Y=k|X=x_i)=\frac{e_k^s}{\sum_j^N=1^{e_j^s}}$

$L_i = -\log P(Y=y_i|X=x_i) \rightarrow L_i=-\log(\frac{e^{s_{y_i}}}{\sum_j=1^{e^{s_j}}})$
![[Pasted image 20220914093045.png]]

## Regularizing
> regularization loss

### L2 Regularization
$L(W)=1/N \sum\limits_{i=1}^N L_i(f(x_i,W),y_i)+\lambda R(W)$

Part 1(before $+$): Data loss: model predictions should match training data
Part 2(after $+$): Regularization: Model should be "simple", so it works on test data

## Summary
![[Pasted image 20220914093801.png]]
![[Pasted image 20220914093859.png]]