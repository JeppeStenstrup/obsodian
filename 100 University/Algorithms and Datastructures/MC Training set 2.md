[[Test Exam MOC]]

# Spørgsmål 1
Hvilket af nedenstående svar gælder for følgende rekursionsligning?
$T(n)=T(n/4)+1$

1. $T(n)=\Theta(\log n)$
2. $T(n)=\Theta(n^{1/4})$
3. $\pmb{T(n)=\Theta(n)}$
4. $T(n)=\Theta(n\log n)$
5. $T(n)=\Theta(n^4)$
6. Rekursionsligningen kan ikke løses med [[Master Theorem#Definition]]

$a=1$
$b=4$
$d=1$

$\log_ba = \log_41 = 0 < 1 = d > log_ba$

$T(n)=O(n^d)=\Theta(n)$

# Spørgsmål 2
Hvilket af nedenstående svar gælder for følgende rekursionsligning?
$T(n)=3T(n/6)+n^{1/2}$

1. $T(n)=\Theta(\log n)$
2. $T(n)=\Theta(n^{1/2})$
3. $T(n)=\Theta(n^{1/2}\log n)$
4. $\pmb{T(n)=\Theta(n^{\alpha})}$ **med** $\pmb{\alpha = \log_6(3)}$
5. $T(n)=\Theta(n)$
6. $T(n)=\Theta(n \log n)$
7. $T(n)=\Theta(n^{\alpha})$ med $\alpha = \log_3(6)$
8. $T(n)=\Theta(n^2)$
9. Rekursionsligningen kan ikke løses med [[Master Theorem#Definition]]

$a=3$
$b=6$
$d=1/2$

$\log_ba = \log_63 \approx 0.61 > 1/2 = d < log_ba$

$T(n)=O(n^{\log_ba})=\Theta(n^{\log_ba})=\Theta(n^{\log_63})$

# Spørgsmål 3
Hvilket af nedenstående svar gælder for følgende rekursionsligning?
$T(n)=3T(n/3)+n\log n$

1. $T(n)=\Theta(\log n)$
2. $T(n)=\Theta(n^{1/3})$
3. $\pmb{T(n)=\Theta(n)}$
4. $T(n)=\Theta(n\log n)$
5. $T(n)=\Theta(n\log^3n)$
6. $T(n)=\Theta(n^3)$
7. Rekursionsligningen kan ikke løses med [[Master Theorem#Definition]]

$a=3$
$b=3$
$d=0$

$\log_ba = \log_33 = 1 > 0 = d < \log_ba$

$T(n)=O(n^{\log_ba})=\Theta(n^{\log_33})=\Theta(n)$

# Spørgsmål 4
Vi ser på en hashtabel $H$, der bruger linear probing og funktionen $h'(x) = (x+2) \mod 7$ som auxiliary hashfunktion. Hashtabellen har allerede nedenstående indhold.

$H=[89, x, x, x, 23, 45, 11]$

Vi indsætter nu værdien 73. Hvilken af nedenstående svar angiver udseendet af $H$ efter indsættelsen?

Med [[Linear probing|linear probing]] ser vores funktion nu således ud: $h(x,i)=((x+2) \mod 7+i) \mod 7$

$i=0$
$h(73, 0)=((73+2) \mod 7 + 0) \mod 7=5$
$H[5]$ er ikke tom, så vi prøver igen med $i=1$
$h(73, 0)=((73+2) \mod 7 + 1) \mod 7=6$
$H[6]$ er ikke tom, så vi prøver igen med $i=2$
$h(73, 0)=((73+2) \mod 7 + 2) \mod 7=0$
$H[0]$ er ikke tom, så vi prøver igen med $i=3$
$h(73, 0)=((73+2) \mod 7 + 3) \mod 7=1$

After insertion, $H=[89, \pmb{73}, x, x, 23, 45, 11]$


# Spørgsmål 5
Vi ser på en hashtabel $H$, der bruger linear probing og funktionen $h'(x) = (x+2) \mod 7$ og $h''(x)=(x\mod 6)+1$ som auxiliary hashfunktioner. Hashtabellen har allerede nedenstående indhold.

$H=[89, x, x, x, 23, 45, 11]$

Vi indsætter nu værdien 33. Hvilken af nedenstående svar angiver udseendet af $H$ efter indsættelsen?

Med [[Double hashing|double hashing]] har vi følgende hash funktion:
$(h'(x) + i \cdot h''(x))\mod7$
$((33+2) + 0 \cdot (33\mod 6) + 1) \mod7=1$
$H[1]$ er tom, så vi indsætter blot $33$

# Spørgsmål 6
Hvor lang tid tager søgning ([[Tree-Search]]) i et ubalanceret søgetræ?
1. $O(1)$
2. $O(\log n)$
3. $\pmb{O(n)}$

Givet at det er ubalanceret, kan vi kun antage at vi skal søge alle elementer igennem for at finde et element.

# Spørgsmål 7
Hvor lang tid tager søgning ([[Tree-Search]]) i et [[Red-Black Trees|rød sort træ]]?
1. $O(1)$
2. $\pmb{O(\log n)}$
3. $O(n)$

Da det ikke er defineret, må vi antage det rød-sorte træ er validt, så vi eliminerer 50% af træet hver gang vi gå itererer.

# Spørgsmål 8
Hvor lang tid tager et inorder gennemløb ([[Inorder-Tree-Walk]]) i et ubalanceret søgetræ?
1. $O(1)$
2. $O(\log n)$
3. $\pmb{O(n)}$

Givet at det er ubalanceret, kan vi kun antage at vi skal søge alle elementer igennem for at finde et element.

# Spørgsmål 9
Hvor lang tid tager et inorder gennemløb ([[Inorder-Tree-Walk]]) i et [[Red-Black Trees|rød sort træ]]?
1. $O(1)$
2. $\pmb{O(\log n)}$
3. $O(n)$

Da det ikke er defineret, må vi antage det rød-sorte træ er validt, så vi eliminerer 50% af træet hver gang vi gå itererer.

# Spørgsmål 10
På hvor mange forskellige måder kan knuderne i nedenstående træ farves, så træerne bliver til at lovligt [[Red-Black Trees|rød sort træ]]?
![[uncolored_red_black_tree.png]]

2 måder

eks1
eks2

# Spørgsmål 11
Følgende kode har til formål at neregne $2^n$.
```
ToPotens(n)
	x = n
	r = 1
	while x > 0
		r = 2r
		x = x - 1
	return r
```

Er $x \geq r$ en løkke-invariant for algoritmen `ToPotens` (dvs. er altid sandt, når testen i starten af while-løkken udføres) for alle input, der er heltal $n \geq 0$?
1. Sandt
2. **Falsk**

$r=1$, og givet $x=n\geq0$, vil $n=0$ give $r\not\geq x.

# Spørgsmål 12
Er $x+r=n+1$ en løkke-invariant for algoritmen `ToPotens` (dvs. er altid sandt, når testen i starte af while-lækken udføres) for alle input, der er heltal $n \geq 0$?
1. Sandt
2. **Falsk**

Hvis $n=0$, vil $x=n=0$, while-løkken vil blive sprunget over.

# Spørgsmål 13
Er $x \geq 0$ en løkke-invariant for algoritmen `ToPotens` (dvs. er altid sandt, når testen i starte af while-lækken udføres) for alle input, der er heltal $n \geq 0$?


# Spørgsmål 14
Er $r2^x=2^n$ en løkke-invariant for algoritmen `ToPotens` (dvs. er altid sandt, når testen i starte af while-lækken udføres) for alle input, der er heltal $n \geq 0$?
1. **Sandt**
2. Falsk

Simpelt, $x=n\geq0$

# Spørgsmål 15
For et optimeringsproblem (som her ikke beskrives nærmere) er input givet ved en omkostning (dvs. et tal) $c_i$ for alle heltal $i$. Det oplyses, at en løsning $l(i)$ til optimeringsproblemet kan beskrives med denne rekursionsligning:
![[ad_reccursion_equation.png]]
Hvis $l(n)$ findes via [[Dynamic Programming|dynamisk programmering]] baseret på ovenstående rekursionsligning, hvilken af nedenstående køretider opnås?
1. $\Theta(1)$
2. $\Theta(n)$
3. $\Theta(n^2)$
4. $\Theta(n^3)$


# Spørgsmål 16
Hvis $l(n)$ findes via dynamisk programmering baseret på ovenstående rekursionsligning, hvad er det mindste pladsforbrug, som kan opnås?
1. $\Theta(1)$
2. $\Theta(n)$
3. $\Theta(n^2)$
4. $\Theta(n^3)$

