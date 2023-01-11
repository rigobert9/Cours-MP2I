# Polynômes
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
