# Structures algébriques
## Loi de composition interne
### Loi de composition interne
> Soit $E$ un ensemble, une loi de composition interne sur $E$ est une application
> de $E \times E$ dans $E$.

Bien qu'on note ces opérations généralement avec une notation infixe, il s'agit
bien d'une application classique. On notera dans la suite du cours ces opérations
par des symboles $+, *, \times, \oplus, \otimes, \top$.

On utilise en général $*$ pour une loi indéfinie.

##### Exemple
Soit $E$ un ensemble muni d'une loi de composition interne $*$, on a donc
l'application $\begin{aligned} *: E \times E &\to E \\ (x,y) &\mapsto  x * y .\end{aligned}$.

En prenant 4 éléments de $E$ $a,b,c,d$, on ne peut pas donner de sens à
l'expression $a * b * c * d$ (car on ne connaît pas les propriétés de
l'opération : cette notation est valable uniquement pour une opération
associative). En ajoutant des parenthèses, on peut décider d'un sens
d'évaluation.

En notant $C_n$ le nombre de parenthésages possibles pour $a_1 * a_2 * \ldots * a_n$,
on a $C_2 = 1$, $C_3 = 2$, $C_4 = 5$, $C_5 = 14$ ...
On a une formule par récurrence, telle que $C_{n+1} = \sum\limits_{k = 1}^{n} C_k \times C_{n+1-k}$.
Il s'agit des nombres de Catalan.
