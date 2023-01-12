# Polynômes
## Structure
### Définition
> Soit $\mathbb{K}$ un corps, un polynôme à coefficients dans $\mathbb{K}$ est une
> suite $(a_k)_{k \in \mathbb{N}} \in \mathbb{K}^{\mathbb{N}}$ presque nulle.

> Une suite presque null est une suite $(a_k)_{k \in \mathbb{N}}$ telle que
> $\exists n_0, \forall n \geq n_0, a_n = 0$.

On note $\mathbb{K}[X]$ l'ensemble des polynômes à coefficients dans $\mathbb{K}$.

> La suite nulle $(0)_{n \geq 0} \in \mathbb{K}[X]$ est appelée le polynôme nul,
> noté $0$.

> Deux polynômes $A$ et $B$ son égaux si leur suites de coefficients sont égales,
> soit $\forall k \in \mathbb{N}, a_k = b_k$ (identification des coefficients).

Un polynôme si et seulement si tous ses coefficients sont nuls.

> On définit sur les polynômes les opérations $+$ (somme), $\times$
> (produit interne) et $\cdot$ (produit externe) :
> - $A + B = (a_k + b_k)_{k \geq 0}$
> - Pour $\lambda \in \mathbb{K}, \lambda \cdot A = (\lambda a_k)_{k \geq 0}$
> - $A \times B = (C_k)_{k \geq 0} \mid \forall k \in \mathbb{N}, C_k = \sum\limits_{i,j \mid i + j = k} a_i b_j = \sum\limits_{i = 0}^{k} a_i b_{k-i}$

$A \times B$ est bien une suite presque nulle.

> $(\mathbb{K}[X], +, \times)$ est un anneau commutatif interne.

__Preuve :__
- Groupe abélien : Sous groupe de $\mathbb{K}^{\mathbb{N}}, +$, avec $0$ le
  neutre et si $A \in \mathbb{K}[X], A = (a_k)_k$. Son opposé est
  $-A = (-a_k)_k = (-1) A$
- $\times$ commutative : $B \times A = A \times B$, car $\sum a_i b_j = \sum b_j a_i$
- $\times$ a un élément neutre : On pose $1$ tel que $A \times 1 = A$.
  On choisit $1 = (1,0,0,\ldots) \in \mathbb{K}[X]$, et la propriété est
  vérifiée.
- $\times$ distributive : Pour $(A + B) \times C$, le coefficient d'indice $k$
  vaut $\sum\limits_{i = 0}^{k} (a_i + b_i) C_{k-1}$.
- $\times$ associative : $D = AB = (d_k)_k$ et $F = DC = (f_k)_k$,
  et on a $d_k = \sum\limits_{i = 0}^{k} a_i b_{k-1}$ et
  $f_k = \sum\limits_{i = 0}^{k} d_i c_{k - i}$, soit
  $f_k = \sum\limits_{i = 0}^{k} (\sum\limits_{j = 0}^{k} a_j b_{i-j}) c_{k-i}$
  $= \sum\limits_{n_1,n_2,n_3 \mid n_1 ) n_2 + n_3 = k} a_{n_1} b _{n_2} c_{n_3}$.

Si on prend un $X = (0,1,0,0,\ldots)$, les itérés de $X$ font avancer le $1$
dans la suite au $n$-ième rang. De plus, on a $X^0 = (1,0,0,\ldots)$.

On peut noter tout polynôme quelconque $A = (a_0,a_1,\ldots,a_n, 0,0,\ldots)$
sous la forme d'une somme finie de polynômes contenant uniquement un rang de
la suite, dans laquelle chaque terme est $a_k \cdot X^k$, permettant d'écrire
$A = \sum\limits_{k = 0}^{n} a_k X^{k}$.

Il s'agit donc d'une somme de monômes.

> Soit $X$ une indéterminée, les polynômes à coefficient dans $\mathbb{K}$
> d'indéterminée $X$ sont $\mathbb{K}[X] = \{\sum\limits_{k \geq 0} a_k X^k \mid (a_k)_k \in \mathbb{K}^{\mathbb{N}}\}$
> (et même une suite presque nulle).

Tout polynôme $P \in \mathbb{K}[X]$ s'écrit $\exists n \in \mathbb{N}, \exists (a_0,\ldots,a_n) \in \mathbb{K}^{n + 1}$
tel que $P = a_0 + a_1 X + a_2 X^2 + \ldots + a_n X^n$.

> $\mathbb{K}[X]$ est un anneau commutatif, donc la formule du binôme de Newton
> tient : $(P + Q)^n = \sum\limits_{k = 0}^{n} \binom{n}{k} P^k Q^{n-k}$.
> En particulier $(1 + X)^n = \sum\limits_{k = 0}^{n} \binom{n}{k} X^{k}$.

##### Exemple : formule de Vandermonde
Soit $[n,m,k] \in \mathbb{N}^3$, $\sum\limits_{i,j \mid i + j = k} \binom{n}{i} \binom{m}{j} = \binom{n + m}{k}$.
L'idée est de poser $P$ un polynôme avec pour coefficients $\binom{n}{i}$, qui
est par application du binôme de Newton $(1 + X)^n$, et de même, $Q = (1 + X)^m$.
Ainsi, $PQ = (1 + X)^{n+m}$, nous permettant de retrouver les coefficients du
résultat.

### Degré d'un polynôme
Soit $P \in \mathbb{K}[X], \exists (a_k)_ki-n\mathbb{K}^{\mathbb{N}}$ une suite
presque nulle, telle que $P = \sum\limits_{k \geq 0} a_k X^k$. La somme est
finie par définition des suites presque nulles, donc $\sum\limits_{k = 0}^{n_0 - 1} a_k X^k$.

> Si $P \in \mathbb{K}[X]$ n'est pas le polynôme nul, on définit son degré par
> $\text{deg}(P) = \text{max}\{k \in \mathbb{N} \mid a_k \neq 0\}$.

Ainsi, pout $P \in \mathbb{K}[X]$ et $P \neq 0$, en notant $d = \text{deg}(P)$,
on a $P = a_0 + a_1 X + a_2 X^2 + \ldots + a_d X^d$ avec $a_d \neq 0$.

Par convention, on posera $\text{deg}(0) = -\infty$.

- $\forall P \in \mathbb{K}[X], \text{deg}(P) \in \mathbb{N} \cup \{-\infty\}$
- Si $P = \sum\limits_{k = 0}^{n} a_k X^k$, alors $\text{deg(P)} \leq n$
- On dit que $P$ est un polynôme unitaire si son coefficient dominant (le
  coefficient d'ordre de son degré) vaut $1$.

Pour $ \in \mathbb{N}$, on note $\mathbb{K}_n[X] = \{P \in \mathbb{K}[X] \mid \text{deg}(P) \leq n\}$
l'ensemble de tous les polynômes de degré inférieur ou égal à $n$.
De façon générale, pour tout $n \leq m$, $\mathbb{K}_n[X] \subset \mathbb{K}_m[X]$.

INK

$\mathbb{K}_0[X] = \{a_0 \mid a_0 \in \mathbb{K}\}$ correspond aux polynômes
constants (non nuls), qu'on peut identifier avec $\mathbb{K}$.

> - $\text{deg}(P + Q) \leq \text{max}(\text{deg}(P), \text{deg}(Q))$
> - $\text{deg}(P \times Q) = \text{deg}(P) + \text{deg}(Q)$
> - $\text{deg}(\lambda P) = \left\{\begin{matrix} \text{deg}(P) \text{ si } \lambda \neq 0 \\ -\infty \text{ si } \lambda = 0 \end{matrix}\right.$

__Preuve :__ Pour $P \neq 0$ et $Q \neq 0$,
si $P = \sum\limits_{k = 0}^{d} a_k X^k$ et $Q = \sum\limits_{k = 0}^{e} b_k X^k$,
alors quitte à ajouter des coefficients nuls,
$\left\{\begin{matrix} \forall k > d, a_k = 0 \\ \forall k > e, b_k = 0 \end{matrix}\right.$.
Ainsi, on peut déduire les propriétés précédentes.

- si $\text{deg}(P) \neq \text{deg}(Q)$ alors $\text{deg}(P+Q) = \text{max}(\text{deg}(P), \text{deg}(Q))$
- si $\text{deg}(P) = \text{deg}(Q) = d$ et $a_d = -b_d$, alors $\text{deg}(P+Q) < d$

> Soit $n \in \mathbb{N}$, $\mathbb{K}_n[X]$ est stable par combinaison linéaire.

$(\mathbb{K}_n[X],+,\cdot)$ est donc un $\mathbb{K}$-espace vectoriel, ce qui
permet d'obtenir des morphismes naturels très pratiques vers les structures
d'algèbre linéaire.

> L'anneau $(\mathbb{K}[X],+,\times)$ est intègre.

__Preuve :__ Si $PQ = 0$, alors $\text{deg}(PQ) = \text{deg}(0) = -\infty$,
alors $\text{deg}(P) + \text{deg}(Q) = -\infty$.

> Si $P,Q \in \mathbb{K}[X] \mid P \times Q = 1$, alors $P$ et $Q$ sont des
> polynômes constants et non nuls.

Si $PQ = 1$, alors $\text{deg}(PQ) = \text{deg}(1)$, soit
$\text{deg}(P) + \text{deg}(Q) = 0$, donc puisque
$\text{deg}(P), \text{deg}(Q) \in \mathbb{N}$ et que leur somme est $0$,
ils sont tous les deux de degré nul, et sont donc des polynômes constants non
nuls.

Les inversibles de l'anneau $\mathbb{K}[X]$ sont
$\mathbb{K} \setminus \{0\} = \mathbb{K}_0[X] \setminus \{0\}$.

##### Exercice
Trouver tous les polynômes vérifiant $(X^2 - 1) \times P^2 = (X + 1) \times P$.

Si $P$ convient, alors $(X - 1)(X + 1) \times P^2 = (X + 1) \times P$.
Puisque $(X + 1)$ n'est pas le polynôme nul, donc $(X - 1)P^2 = P$.
Si $P = 0$, $P$ convient, et si $P \neq 0$, $(X-1)P = 1$, alors
$\text{deg}((X - 1)) + \text{deg}(P) = \text{deg}(1)$,
soit $1 + \text{deg}(P) = 0 \Leftrightarrow \text{deg}(P) = -1$.
La seule solution est donc $P = 0$.

### Composition
> Soit $P = \sum\limits_{k \geq 0} a_k X^k \in \mathbb{K}[X]$,
> et $Q \in \mathbb{K}[X]$, la composée de $P$ par $Q$, notée $P \circ Q$,
> est définie par $P \circ Q = \sum\limits_{k \geq 0} a_k Q^k$, ce qui est un
> polynôme.

Si $n = \text{deg}(P) \in \mathbb{N}$ (avec $P \neq 0$), alors 
$P \circ Q = a_0 + a_1 Q + a_2 Q^2 + \ldots + a_n Q^n$, avec $a_n \neq 0$.

Si $\text{deg}(Q) = d$, on a $\text{deg}(Q^n) = n \text{deg}(Q) = nd$,
donc $\text{deg}(a_n Q^n) = nd$. On suppose que $d \in \mathbb{N}^{\ast}$ et
$n \in \mathbb{N}^{\ast}$, $n-1 < n \Rightarrow d(n-1) < dn$,
donc $\text{deg}(P \circ Q) = \text{deg}(a_n Q^n) = nd$.
On a donc bien $\text{deg}(P \circ Q) = \text{deg}(P) \times \text{deg}(Q)$.\
Dans le cas où $P$ est constant non nul, $P \circ Q$ sera constant non nul, donc
la proposition tient aussi.\
Dans le cas où $P$ est nul, alors tout dépend du degré de $Q$.

> Si $P \neq 0$ et $\text{deg}(Q) \geq 1$, $\text{deg}(P \circ Q) = \text{deg}(P) \times \text{deg}(Q)$.
> Sinon, $\text{deg}(P \circ Q) \leq 0$.

> - $(P_1 + P_2) \circ Q = (P_1 \circ Q) + (P_2 \circ Q)$
> - $(P_1 \times P_2) \circ Q = (P_1 \circ Q) \times (P_2 \circ Q)$

Il s'agit des mêmes propriétés que pour les applications à valeur dan $\mathbb{K}$.

$P \circ X = X \circ P = P$. On le note parfois $P(X) = P$.
