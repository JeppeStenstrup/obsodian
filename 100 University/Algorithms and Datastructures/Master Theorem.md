[[AD Proofs MOC]]

# Master Theorem
## Definition

![[master_theorem_rolf.png]]

Hvis $T(n) = aT(\lceil\frac{n}{b}\rceil) + O(n^d)$  for konstanterne $a > 0$, $b > 1$, $d \geq 0$, så:
$T(n) = O(n^d) \hspace{2em} \rightarrow d > log_b a$
$T(n) = O(n^dlogn) \rightarrow d=log_ba$
$T(n) = O(n^{log_b a}) \hspace{.8em}\rightarrow d < log_b a$

## Huskeregler
1. Hvis alle lag har lige stor sum, er den samlede sum træets højde gange den givne sum.
2. Hvis lagenes sum vokser eksponentielt ned igennem kørslen, er det det nederste lag der dominerer.
3. Hvis lagenes sum aftager eksponentielt ned igennem kørslen, er det det øverste lag der dominerer.

## Fremgangsmåde
Lav et træ med fanout $=a$ og med arbejde $=n/b^\text{d}$
Følg eksempler.


## Eksempler
$T(n)=2T(n/2)+n$
$a = 2$
$b = 2$
$d = n$
![[master_theorem_22n.png]]

Højde $=n/b^{\text{højde}}=1 \Longleftrightarrow b^{\text{højde}}=n \Longleftrightarrow \text{højde}=\log_bn$

Arbejde for hvert lag:
$0=n$
$1=2\cdot n/2=n$
$2=2^2\cdot n/2^2=n$
$\cdots$
$2^i\cdot n/2^i=n$
$2^\text{højde} = 2^{\log_2n}\cdot 1=n$

Alle lagene summet giver $n\log n$

---

$T(n)=3T(n/2)+n$
$a = 3$
$b = 2$
$d = n$
![[master_theorem_32n.png]]

Højde $=n/b^{\text{højde}}=1 \Longleftrightarrow b^{\text{højde}}=n \Longleftrightarrow \text{højde}=\log_bn$

Arbejde for hvert lag:
$0=n$
$1=3\cdot n/2=n(3/2)$
$2=3^2\cdot n/2^2=n(3/2)^2$
$3=3^3\cdot n/2^2=n(3/2)^3$
$\cdots$
$3^i\cdot n/2^i=n(3/2)^i$
$3^{\log_2n}\cdot 1=3^{\log_2n} = \Theta(3^{\log_2n}) = \Theta(n^{\log_23})$

---

$T(n)=3T(n/4)+n^2$
$a = 3$
$b = 4$
$d = n^2$
![[master_theorem_34n2.png]]

Højde $=n/b^{\text{højde}}=1 \Longleftrightarrow b^{\text{højde}}=n \Longleftrightarrow \text{højde}=\log_bn$

Da $d=n^2$ går vi hver knudepunkt igennem og får:
![[master_theorem_34n2_2.png]]

Arbejde for hvert lag:
$0=n^2$
$1=3\cdot (\frac{n}{4})^2=n^2(\frac{3}{4^2})$
$2=3^2\cdot (\frac{n}{4^2})^2=n^2(\frac{3}{4^2})^2$
$2=3^3\cdot (\frac{n}{4^3})^2=n^2(\frac{3}{4^2})^3$
$\cdots$
$2=3^i\cdot (\frac{n}{4^i})^2=n^2(\frac{3}{4^2})^i$
$3^{\log_4n}\cdot 1=3^{\log_4n} = \Theta(n^2)$ da første lag dominerer

---

$T(n) = 4T(\frac{n}{2})+O(n)$
$a = 4$
$b=2$
$d=1$
$log_2(4) = 2$
$d < log_ba \rightarrow T(n) = O(n^{log_ba}) = O(n^2)$
---
$T(n)=3T(\frac{n}{2})+O(n)$
$a=3$
$b=2$
$d=1$
$log_2(3) \approx 1.5$
$d<log_ba \rightarrow T(n) = O(n^{log_ba})=O(n^{log_23})$
---
$T(n)=2T(\frac{n}{2})+O(n^1)$
$a=2$
$b=2$
$d=1$
$log_2(2)=1$
$d=log_ba \rightarrow T(n)=O(n^dlogn)=O(nlogn)$
---
$T(n)=T(\frac{n}{2})+O(1)$
$a=1$
$b=2$
$d=0$
$log_21=0$
$d=log_ba \rightarrow T(n)=O(n^dlogn)=O(n^0logn)=O(logn)$