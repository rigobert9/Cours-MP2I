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

Un polynôme est nul si et seulement si tous ses coefficients sont nuls.

> On définit sur les polynômes les opérations $+$ (somme), $\times$
> (produit interne) et $\cdot$ (produit externe) :
> - $A + B = (a_k + b_k)_{k \geq 0}$
> - Pour $\lambda \in \mathbb{K}, \lambda \cdot A = (\lambda a_k)_{k \geq 0}$
> - $A \times B = (C_k)_{k \geq 0} \mid \forall k \in \mathbb{N}, C_k = \sum\limits_{i,j \mid i + j = k} a_i b_j = \sum\limits_{i = 0}^{k} a_i b_{k-i}$

$A \times B$ est bien une suite presque nulle.

> $(\mathbb{K}[X], +, \times)$ est un anneau commutatif intègre.

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

Pour $n \in \mathbb{N}$, on note $\mathbb{K}_n[X] = \{P \in \mathbb{K}[X] \mid \text{deg}(P) \leq n\}$
l'ensemble de tous les polynômes de degré inférieur ou égal à $n$.
De façon générale, pour tout $n \leq m$, $\mathbb{K}_n[X] \subset \mathbb{K}_m[X]$.

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

## Divisibilité et division Euclidienne
### Multiples et diviseurs
> Soient $A,B \in \mathbb{K}[X]$, on dit que $B \mid A$ dans
> $\mathbb{K}[X]$ si $\exists C \in \mathbb{K}[X] \mid A = BC$.

On adapte ainsi les notations $B \mid A$ ($B$ divise $A$, $A$ est un multiple de
$B$), $\mathcal{D}(A)$ l'ensemble des diviseurs de $A$, et $B \cdot \mathbb{K}[X]$
les multiples de $B$.

La relation $\mid$ dans $\mathbb{K}[X]$ est réflexive et transitive, mais pas
antisymétrique. Par exemple, $(X^2 + 1) \mid (3X^2 + 1)$ et
$(3X^2 + 3) \mid (X^2 + 1)$.

> Soient $A,B \in \mathbb{K}[X]$, $(A \mid B \land B \mid A)$
> $\Leftrightarrow \exists \lambda \in \mathbb{K}^{\ast}, A = \lambda B$.
> On dit que $A$ et $B$ sont associés.

__Preuve :__ $\exists D_1, D_2 \in \mathbb{K}[X]$,
$\left\{\begin{matrix} B = AD_1 \\ A = BD_2 \end{matrix}\right.$,
donc $A = A D_1 D_2$.
- Si $A = 0$, alors $B = 0$
- Sinon, par intégrité, $1 = D_1 D_2$, donc $D_1$ et $D_2$ sont deux polynômes
  inversibles, donc ils sont constants et non nuls.

On prouve ainsi $\Rightarrow$, et on a réciproquement que si $\lambda \in \mathbb{K}^{\ast}$,
$A = \lambda B$ donc $B = \frac{1}{\lambda} A \in \mathbb{K}$,
donc $B \mid A$ et $A \mid B$.

On remarque qu'en se restreignant aux polynômes unitaires de $\mathbb{K}[X]$,
la divisibilité est alors antisymétrique.

- Tout $P \in \mathbb{K}[X]$ divise $0$
- Les multiples de $0$ sont $0$
- Soit $P = A \times B$ avec $A,B$ non nuls dans $\mathbb{K}[X]$,
  $\text{deg}(P) = \text{deg}(A) + \text{deg}(B)$ avec $\text{deg}(A)$
  et $\text{deg}(B)$ dans $\mathbb{N}$. Pour tout diviseur
  $A$ non nul de $P$, $\text{deg}(A) \leq \text{deg}(P)$

### Division euclidienne dans $\mathbb{K}[X]$
> Soient $A, B \in \mathbb{K}[X]$ et $B \neq 0$,
> il existe un unique couple $(Q,R) \in \mathbb{K}[X]^2$
> tel que $\left\{\begin{matrix} A = BQ + R \\ \text{deg}(R) < \text{deg}(B) \end{matrix}\right.$

##### Preuve d'unicité
Soient $(Q_1,R_1)$ et $(Q_2,R_2)$ tels que
$A = BQ_1 + R_1 = B Q_2 + R_2$ et
$\left\{\begin{matrix} \text{deg}(R_1) < \text{deg}(B) \\ \text{deg}(R_2) < \text{deg}(B) \end{matrix}\right.$.
Ainsi, $B(Q_1 - Q_2) = R_2 - R_1$, et donc $\text{deg}(B) + \text{deg}(Q_1 - Q_2) = \text{deg}(R2 - R_1)$.

...

Ainsi, $Q_1 - Q_2 = 0$, et on en déduit que $R_2 - R_1 = 0$, donc qu'il y a
unicité.


##### Preuve d'existence
On fixe $B \neq 0$, et on écrit $\left\{\begin{matrix} B = \sum\limits_{k = 0}^{m} b_k X^k \\ \text{deg}(B) = m \land b_m \neq 0 \end{matrix}\right.$.
On procède par récurrence sur le degré de $A$, avec pour hypothèse de récurrence
que pour tout polynôme $A \in \mathbb{K}_{n-1}[X]$, il existe $(Q,R) \in \mathbb{K}[X]$
permettant de poser une division euclidienne.

$\forall k \in [\![1, m]\!]$, l'hypothèse est vérifiée. En effet, si $A \in \mathbb{K}_{n-1}[X]$,
avec $k \leq m$, alors $\text{deg}(A) \leq k-1 < m$, donc l'écriture
$A = B \times 0 + A$ convient car $\text{deg}(A) < \text{deg}(B) = m$.
On a ainsi initialisé l'hypothèse.

Soit $n \geq m$ tel que l'hypothèse est vérifiée. On montre l'hypothèse au rang
suivant. $A \in \mathbb{K}_n[X]$, donc on peut écrire $A = a_n X^{n} + A_1$
où $\text{deg}(A_1) < n$. Or, $B = b_m X^m + B_1$, avec $\text{deg}(B_1) < m$.
Alors, $\frac{a_n}{b_n} X^{n - m \geq 0} \times B = a_n X^n + \frac{a_n}{b_n} X^{n- m} B_1$.
Le degré de ce dernier terme est inférieur à $n$. Donc $A - \frac{a_n}{b_n} X^{n-m} B$
$= A_1 - \frac{a_n}{b_m} X^{n-m} B_1 = A_2$, avec $\text{deg}(A_2) < n$.
Or, par hypothèse de récurrence sur $A_2$, $\exists (Q_1,R_1)$
tel que $\left\{\begin{matrix} A_2 = BQ_1 + R_1 \\ \text{deg}(R_1) < m \end{matrix}\right.$.
Finalement, $A - \frac{a_m}{b_m} X^{n-m} B = BQ_1 + R_1$
....

On en déduit ainsi un algorithme de division euclidienne.

#### Racines d'un polynôme
On peut remarquer que $B \mid A$ est équivalent au fait que le reste de la
division euclidienne de $A$ par $B$ soit nul.

> $P(a) = 0 \Leftrightarrow \exists Q \in \mathbb{K}[X], P = (X-a) \times Q$

On dit que $a$ est racine de $P$.

## Fonctions polynômes et racines
### Fonction polynomiales
> Soit $f: \mathbb{K} \to \mathbb{K}$, $f$ est une fonction polynomiale si il
> existe un polynôme $P = \sum\limits_{k = 0}^{n} a_k X^k \in \mathbb{K}[X]$ tel
> que $\forall x \in \mathbb{K}, f(x) = \sum\limits_{k = 0}^{n} a_k x^k$.

On notera $\tilde{P}$ l'application polynomiale associée à $P$. On
donc $P \in \mathbb{K}[X]$ et $\tilde{P} \in \mathcal{F}(\mathbb{K},\mathbb{K})$.

Si $P,Q \in \mathbb{K}[X]$ et $\lambda \in \mathbb{K}$ :
- $\tilde{P + Q} = \tilde{P} + \tilde{Q}$
- $\tilde{P \times Q} = \tilde{P} \times \tilde{Q}$
- $\tilde{\lambda P} = \lambda \tilde{P}$
- $\tilde{P \circ Q} = \tilde{P} \circ \tilde{Q}$

...

### Racine
> Soit $P \in \mathbb{K}[X]$ et $\alpha \in \mathbb{K}$, on dit que $\alpha$ est
> une racine de $P$ si $\tilde{P}(x) = 0$.

> Théorème de factorisation : $\alpha$ est une racine de $P$ si et seulement si
> $(X - \alpha)$ divise $P$.

__Preuve :__ Division euclidienne de $P$ par $(X - \alpha)$.

Par récurrence, on peut ainsi montrer la propriété suivante

> Si $\alpha_1,\alpha_2,\ldots,\alpha_n$ sont des racines deux à deux distincties
> du polynôme $P$, alors $\prod\limits_{i = 1}^{n} (X - \alpha_i)$ divise
> $P$.

__Preuve :__ On procède par récurrence sur $n \in \mathbb{N}^{\ast}$ :
- Si $n = 1$, alors on applique le théorème de factorisation
- Si $n \geq 1$, avec la proposition vraie au rang $n$, on prend les racines
  jusqu'au rang $n + 1$. On sait que le polynôme est divisible par le produit
  des racines jusqu'à $n$, donc on a le quotient de cette division un polynôme
  $Q$. Or, puisque $\tilde{P}(\alpha_{n+1}) = 0$, $\tilde{Q}(\alpha_{n+1}) = 0$
  par intégrité, donc $\alpha_{n+1}$ est racine de $Q$ et on applique le
  théorème de factorisation.

> Soit $P \in \mathbb{K}[X]$ de degré $n \in \mathbb{N}$, alors $P$ possède au
> plus $n$ racine distinctes.

__Preuve :__ Si $\alpha_1,\alpha_2,\ldots,\alpha_n$ des racines distinctes de $P$,
le produit des $(X - \alpha_i)$ divise $P$, donc $r \leq n$.

__Corollaire :__ Si $\text{deg}(P) = n \in \mathbb{N}$, et si
$\alpha_1,\ldots,\alpha_n$ sont $n$ racines distinctes de $P$, alors
$P = \lambda \times \prod\limits_{i = 1}^{n} (X - \alpha_i)$, avec $\lambda$ le
coefficient dominant de $P$.

__Corollaire :__ Soit $P \in \mathbb{K}_n[X]$, si $P$ possède $(n+1)$ racines
distinctes, $P = 0$.

__Preuve :__ Si $\text{deg}(P) \in \mathbb{N}$, alors le nombre de racines est
majoré par $\text{deg}(P)$. Ici, il faut $\text{deg}(P) \not\in \mathbb{N}$,
c'est à dire $P = 0$.

### Multiplicité
> Soit $P \in \mathbb{K}[X]$ et $\alpha \in \mathbb{K}$, avec $P \neq 0$,
> on appelle multiplicité de $\alpha$ dans $P$ l'entier
> $m = \text{max}\{k \in \mathbb{N} \mid (X - \alpha)^k \mid P\}$.

L'ensemble est non vide car il contient $0$, puisque $(X - \alpha)^0 = 1 \mid P$.
L'ensemble est majoré par $\text{deg}(P)$.

Ainsi, $\left\{\begin{matrix} (X - \alpha)^m \mid P \\ (X - \alpha)^{m + 1} \not\mid P \end{matrix}\right.$.
Si $m$ est la multiplicité de $\alpha$ dans $P$, alors
$P = Q \times (X - \alpha)^m \mid Q(\alpha) \neq 0$.

- $\alpha$ n'est pas racine de $P$ si et seulement si $m = 0$ ($(X - \omega)^1 \not\mid P$)
- $\alpha$ est racine de $P$ si et seulement si $m \geq 1$
- $\alpha$ est racine simple si $m = 1$
- $\alpha$ est racine double si $m = 2$

Si $P \in \mathbb{K}[X]$ non nul de degré $n \in \mathbb{N}$. On note
$\alpha_1,\alpha_2,\ldots,\alpha_r \in \mathbb{K}$ les $r$ racines distinctes de
$P$ de multiplicités respectives $m_1,m_2,\ldots,m_r \in \mathbb{N}^{\ast}$.
$\prod\limits_{i = 1}^{r} (X - \alpha_i)^{n_{i}}$ divise $P$,
et donc $\sum\limits_{i = 1}^{r} m_i \leq \text{deg}(P)$.

## Dérivation
### Dérivation formelle
> Soit $P = \sum\limits_{k = 0}^{n} a_k X^k \in \mathbb{K}[X]$, on définit le
> polynôme dérivé $P'$ par $P' = \sum\limits_{k = 1}^{n} k a_k X^{k-1}$
> $= \sum\limits_{k = 0}^{n-1} (k+1) a_{k+1} X^k$.

On peut ainsi voir qu'en pratique, $(\tilde{P})' = \tilde{P'}$.

On peut résumer par pour $k \in \mathbb{N}$, $(X^k)' = \left\{\begin{matrix} k X^{k+1}\text{ si } k \geq 1 \\ 0 \text{ si } k = 0 \end{matrix}\right.$.

> $P \in \mathbb{K}_0[X] \Leftrightarrow P' = 0$

En effet, la dérivée d'un polynôme constant est nulle. Ni $P' = 0$, tous les
coefficients sont nuls.

### Dérivées successives
> Soit $P \in \mathbb{K}[X]$, on note $P^{(k)}$ la dérivée $k$-ième de $P$,
> définie récursivement comme
> $\left\{\begin{matrix} P^{(0)} = P \\ \forall k \in \mathbb{N}, P^{(k+1)} = (P^{(k)})' \end{matrix}\right.$.

> Pour $n \in \mathbb{N}$ et $k \in \mathbb{N}$, $(X^k)^{(n)} = \left\{\begin{matrix} k (k-1) (k - n + 1)\text{ pour } n \leq k \\ 0 \text{ sinon} \end{matrix}\right.$.

$(X^k)^{k} = k \times (k-1) \times \ldots = k!$, une constante, donc pour tout
$n > k$, $(X^k)^{(n)} = 0$.

On peut remarquer que $\forall 0 \leq n \leq k, (X^k)^{(n)} = \frac{k!}{(k - n)!} X^{k-n}$
$= \frac{n!}{n!} \frac{k!}{(k-n)!} X^{k - n} = n! \binom{k}{n} X^{k-n}$.

On peut observer aussi la linéarité de la dérivation, donnant
$P^{(n)} = (\sum\limits_{k \geq 0} a_k X^k)^{(n)} = \sum\limits_{k \geq 0} a_k (X^k)^{(n)}$.
On peut aussi déduire $P^{(n)} = a_n \times n! \sum\limits_{k > n} a_k n! \binom{k}{n} X^{k-n}$,
donc $P^{(n)}(0) = a_n \times n! + 0$.

Ainsi $\forall ninn, a_n = \frac{P^{(n)}(0)}{n!}$, donc pour tout polynôme
$P \in \mathbb{K}[X]$, $P = \sum\limits_{k \geq 0} \frac{P^{(k)}(0)}{k!} X^{k}$.

Ce résultat correspond à la formule de Taylor-Young en $0$.

> On peut effectuer sur les dérivations les opérations suivantes, pour
> $P,Q \in \mathbb{K}[X]$ et $\lambda \in \mathbb{K}$ :
> - $(P + Q)' =  P' + Q'$
> - $(\lambda P)' = \lambda P'$
> - $(P \times Q)' = P' Q + P Q'$
> - $\forall n \in \mathbb{N}^{\ast}, (Q^n)' = n Q' Q^{n-1}$
> - $(P \circ Q)' = Q' \times (P' \circ Q)$

__Preuve :__
- Produit : $\left\{\begin{matrix} P = \sum\limits_{k \geq 0} a_k X^k \\ Q = \sum\limits_{k \geq 0} b_k X^k \end{matrix}\right.$,
  alors $PQ = \sum\limits_{k \geq 0} (\sum\limits_{i + j = k} a_i b_j) X^k$,
  donc $(PQ)' = \sum\limits_{k \geq 1} (\sum\limits_{i + j = k} a_i b_j) k X^{k-1}$\
  $= \sum\limits_{k \geq 1} (\sum\limits_{i + j = k} a_i b_j (i+j) X^{i + j - 1})$\
  $= \sum\limits_{k \geq 1} (\sum\limits_{i + j = k} a_i i X^{i-1} b_j X^j + a_i X^i j b_j X^{j-1})$\
  $= \sum\limits_{k \geq 1} (\sum\limits_{i + j = k} a_i i X^{i-1} b_j X^j) + \sum\limits_{k \geq 1} (\sum\limits_{i + j = k} a_i X^i j b_j X^{j-1})$\
  $= (\sum a_k k X^{k-1}) \times (\sum b_k X^{k}) + (\sum a_k X^k) \times (k b_j X^{k-1})$\
  $=P'Q + PQ'$

> Si $P \in \mathbb{K}[X]$, $\text{deg}(P') = \left\{\begin{matrix} -\infty \text{ si } P \text{ est constant} \\ \text{deg}(P) - 1 \text{ sinon} \end{matrix}\right.$.

Si $d = \text{deg}(P) \in \mathbb{N}^{\ast}$ et $a_d \neq 0$ est le coefficient
dominant de $P$, alors $d a_d$ est le coefficient dominant de $P'$.

On a les dérivées successives $(P + Q)^{(n)} = P^{(n)} + Q^{(n)}$,
$(\lambda P)^{(n)} = \lambda P^{(n)}$.

Pour les dérivées successives de $(P \times Q)$, on peut observer par récurrence
une expansion dans le même style que la puissance d'une addition, avec le binôme
de Newton.

> Formule de Leibniz : $\forall n \in \mathbb{N}, \forall P,Q \in \mathbb{K}[X]$,
> $(P \times Q)^{(n)} = \sum\limits_{k = 0}^{n} \binom{n}{k} P^{(k)} \times Q^{(n-k)}$

__Preuve :__ On pose par récurrence sur $n$.
- si $n = 0$, $(PQ)^{(0)} = PQ$ et $\binom{0}{0} P^{(0)} \times Q^{(0)} = 1 \times P \times Q$
- si $n = 1$, $(PQ)' = P' Q + P Q'$
- si $n \geq 1$ avec la formule vraie au rang $n$, $(PQ)^{(n+1)}$\
  $= [\sum\limits_{k = 0}^{n} \binom{n}{k} P^{(k)} Q^{(n-k)}]'$\
  $= \sum\limits_{k = 0}^{n} \binom{n}{k} \times [P^{(k)} Q^{(n-k)}]'$\
  $= \sum\limits_{k = 0}^{n} \binom{n}{k} P^{(k+1)} Q^{(n-k)} + \sum\limits_{k = 0}^{n} \binom{n}{k} P^{(k)} Q^{(n + 1 - k)}$\
  $= \sum\limits_{k = 0}^{n} \binom{n}{k-1} P^{(k)} Q^{(n-k+1)} + \sum\limits_{k = 0}^{n} \binom{n}{k} P^{(k)} Q^{(n + 1 - k)}$\
  $= P^{(n+1)} Q^{(0)} + \sum\limits_{k = 1}^{n} \binom{n+1}{k} P^{(k)} Q^{(n+1-k)} + P^{(0)} Q^{n + 1 - k}$\
  $= \sum\limits_{k = 0}^{n+1} \binom{n+1}{k} P^{(k)} Q^{(n-k + 1)}$

> Formule de Taylor sur les polynômes : Pour tout $P \in \mathbb{K}[X]$ et $a \in \mathbb{K}$,
> $P = \sum\limits_{k \geq 0} \frac{P^{(k)}(a)}{k!} (X - a)^k$.

La somme est finie car $\forall k > \text{deg}(P), P^{(k)} = 0$. Ainsi, les
indices $k$ de la somme varient de $0$ à $\text{deg}(P)$.

__Preuve :__ On pose $Q(X) = P(X + a)$, donnant $Q' = 1 \times P'(X + a)$.
Par récurrence, on obtient $Q^{(k)}(0) = P^{(k)}(a)$.
On applique la formule de Taylor en $0$, et on peut conclure.

### Multiplicité et dérivation
> Soit $P \in \mathbb{K}[X]$ non nul et $\alpha \in \mathbb{K}, m \in \mathbb{N}^{\ast}$.
> Si $\alpha$ est racine de $P$ avec multiplicité $m$, alors
> $\alpha$ est racine de $P'$ avec multiplicité $m-1$.

__Preuve :__ Si $\alpha$ est racine de $P$ avec multiplicité $m$,
alors $\exists Q \in \mathbb{K}[X] \mid \left\{\begin{matrix} P = (X - \alpha)^m \times Q \\ Q(\alpha) \neq 0 \end{matrix}\right.$.
Ainsi, $P' = m (X - \alpha)^{m-1} \times Q + (X - \alpha)^m \times Q'$
$= (X - \alpha)^{m-1} [m Q + (X - \alpha Q')]$.

> Soit $P \in \mathbb{K}[X]$ non nul, $\alpha \in \mathbb{K}, m \in \mathbb{N}^{\ast}$,
> on a l'équivalence des assertions 
> - $\alpha$ est racine de $P$ avec multiplicité $m$
> - $\left\{\begin{matrix} P(\alpha) = P'(\alpha) = \ldots = P^{(m-1)}(\alpha) = 0 \\ P^{m}(\alpha) \neq 0 \end{matrix}\right.$

__Preuve :__
- $\Rightarrow$ On prouve par récurrence finie que $\alpha$ est racine de $P^{(k)}$
  avec multiplicité $m-k$ sur $k \in [\![0,m]\!]$. Pour $k = 0$, la propriété
  est vraie, et soit $k \geq 0$ et $k < m$, avec la propriété vérifiée, on
  trouve une multiplicité de $m - k - 1$ par le lemme.
- $\Leftarrow$ On applique la formule de Taylor pour $P$ en $\alpha$, donnant
  $P = \sum\limits_{k \geq 0} \frac{P^{(k)}(\alpha)}{k!} (X - \alpha)^k$. Par
  hypothèse, tous les termes d'indices $k \in [\![0, m-1]\!]$ sont nuls,
  donc $P = \sum\limits_{k \geq m} \frac{P^{(k)}(\alpha)}{k!} (X - \alpha)^k$
  $= \frac{P^{(n)}(\alpha)}{m!} (X - \alpha)^m + (X - \alpha)^m \times (\sum\limits_{k \geq m+1} \frac{P^{(k)}(\alpha)}{k!} (X - \alpha)^{k-m})$.
  $P = (X - \alpha)^m \times Q(\alpha)$, avec $Q(\alpha) = \frac{P^{(m)}(\alpha)}{m!} + \sum\limits_{k \geq m + 1} \frac{P^{(k)}(\alpha)}{k!} (X - \alpha)^{k - m}$
  $= \frac{P^{(m)}(\alpha)}{m!}$.

## Arithmétique des polynômes
Voir polycopié.

## Factorisation dans $\mathbb{R}[X]$ et $\mathbb{C}[X]$
### Factorisation dans $\mathbb{C}[X]$
> Théorème d'Alembert-Gauss / Théorème fondamental de l'algèbre : Tout polynôme
> non constant de $\mathbb{C}[X]$ possède une racine dans $\mathbb{C}$.

On dit donc que le corps $\mathbb{C}$ est algébriquement clos.

__Corollaire :__ Les polynômes de $\mathbb{C}[X]$ irréductibles sont les
polynômes de degré $1$.

__Corollaire :__ Tout polynôme non constant de $\mathbb{C}[X]$ est scindé : il
s'écrit comme un produit de polynômes de degré $1$.
En effet, $\forall P \in \mathbb{C}[X]$, avec $\text{deg}(P) = n  \in \mathbb{N}^{\ast}$,
$\exists (x_1,x_2,\ldots,x_n) \in \mathbb{C}^n$, $\exists \lambda \in \mathbb{C}$,
$P = \lambda \times \prod\limits_{i = 1}^{n} (X - x_i)$.
En regroupant les racines identique, $P = \lambda \times \prod\limits_{i = 1}^{r} (X - \alpha_i)^{m_i}$.

Dans $\mathbb{C}[X]$, tout polynôme non constant a autant de racines (comptées
avec leur multiplicité) que son degré.

Ainsi, si $A \mid B$, toutes les racines dans $\mathbb{C}$ de $A$ sont racines
de $B$ avec une multiplicité égale ou supérieure.

### Factorisation dans $\mathbb{R}[X]$
- Si $p \in \mathbb{R}[X]$ et $\text{deg}(P) = 1$, alors $P$ est irréductible
  dans $\mathbb{R}[X]$
- Si $P = aX^2 + bX + c$ avec $(a,b,c) \in \mathbb{R}^3$ où
  $\left\{\begin{matrix} a \neq 0 \\ \Delta = b^2 - 4a c < 0 \end{matrix}\right.$,
  alors $P$ est irréductible dans $\mathbb{R}[X]$.

Soit $P \in \mathbb{R}[X]$ et $\alpha \in \mathbb{C}$ :
- $\alpha$ est racine de $P$ si et seulement si $\overline{\alpha}$ est racine
  de $P$
- $\alpha$ et $\overline{\alpha}$ ont la même multiplicité dans $P$

__Preuve :__
- Soit $P = \sum\limits_{k = 0}^{n} a_k X^k$, avec $(a_k)_k \in \mathbb{R}^{n+1}$,
  si $P(\alpha) = 0$, alors $\sum\limits_{k \geq 0} a_k \alpha^{k} = 0$,
  et donc $\sum\limits_{k \geq 0} a_k \alpha^k = 0$,
  alors $\sum\limits_{k \geq 0}  \overline{a_j} \overline{\alpha^k} = 0$,
  alors $\sum\limits_{k \geq 0} a_k (\overline{\alpha})^k = 0$,
  alors $P(\overline{\alpha}) = 0$.\
  Ainsi, si $\alpha$ est racine de $P$, $\overline{\alpha}$ est racine de $P$,
  et si $\overline{\alpha}$ est racine de $P$, $\overline{\overline{\alpha}}$
  est racine de $P$, d'où l'équivalence.
- Si $\alpha$ est de multiplicité $m$ dans $P$, $P = (X - \alpha)^m \times Q$
  avec $Q \in \mathbb{C}[X] \mid Q(\alpha) \neq 0$. Dans ce cas,
  on pose $\overline{P} = \overline{(X - \alpha)^m \times Q} = (X - \overline{\alpha})^m \times \overline{Q}$.
  Or, $P \in \mathbb{R}[X]$, donc $\overline{P} = P$ donc $P = (X - \overline{\alpha})^m \times \overline{Q}$.

> $\forall \alpha \in \mathbb{C}, (X - \alpha)(X - \overline{\alpha}) = X^2 - 2 \Re(\alpha) X + |\alpha|^2 \in \mathbb{R}[X]$

Les irréductibles de $\mathbb{R}[X]$ sont :
- Les polynômes de $\mathbb{R}$ de degré $1$
- Les polynômes de degré $2$ de déterminant négatif

En effet, si un polynôme est de degré supérieur à $3$, en le considérant comme
élément de $\mathbb{C}[X]$, il existe une racine $\alpha \in \mathbb{C}$. Si
celle-ci est réelle, on peut réduire le polynôme par une racine, et sinon on
travaille avec les racines complexes conjuguées, qui permettent de composer un
polynômes réel du second degré.

Si $P \in \mathbb{R}[X]$ et $\text{deg}(P) \equiv 1[2]$ impair, alors $P$
possède au moins une racine réelle.

> Soit $P \in \mathbb{R}[X]$ non constant,
> $P = \lambda \times \prod\limits_{i = 1}^{r} (X - \alpha_i)^{m_i} \times \prod\limits_{j = 1}^{l} (X^2 + b_j X + c_j)^{m_j}$.

## Interpolation de Lagrange
__Motivation :__ Soit un nuage de points dans un plan indexé par $\mathbb{R} \times \mathbb{R}$,
on cherche une fonction polynomiale qui passe par tous ces points.

1. On cherche pour chaque $i \in [\![0,n]\!]$ un polynôme $L_i \in \mathbb{K}_n[X]$
  tel que $(L_i(a_0), L_i(a_1),\ldots,L_i(a_n)) = \left\{\begin{matrix} 1 \text{ pour } a_i \\ 0 \text{ sinon} \end{matrix}\right.$.
  Si $L_i$ existe, alors $\forall j \in [\![0,n]\!] \setminus \{i\}, L_i(a_j) = 0$, donnant
  $n$ racines distinctes, les $a_j$ avec $j \neq i$. Ainsi,
  $A = \prod\limits_{0 \leq j \leq n \mid j \neq i} (X - a_j)$ divise $L_i$.
  $A$ est un polynôme de degré $n$, or on impose $L_i \in \mathbb{K}_n[X]$,
  donc il existe $\lambda \in \mathbb{K} \mid L_i = \lambda \times A$.
  De plus, on doit avoir $L_i(a_i) = 1$, c'est-à-dire
  $\lambda \times \prod\limits_{0 \leq j \leq n \mid j \neq i} (a_i - a_j) = 1$
  (les termes du produit sont non nuls car les $a_j$ sont distincts deux à
  deux). Ainsi, $L_i = \prod\limits_{0 \leq j \leq n \mid j \neq i} (a_i - a_j) \times A$,
  ce qui donne l'unicité de $L_i$.
  Par synthèse, on pose pour tout $i \in [\![0,n]\!]$
  $L_i = \prod\limits_{0 \leq j \leq n, j \neq i} \frac{X - a_j}{a_i - a_j}$.
  On vérifie facilement ces propriétés, et ils existent bien.
  Pour tout $k \in [\![0,n]\!], L_i(a_k) = S_{k,i}$.

On note par le symbole de Kronecker ces suites,
$S_{i,k} = \left\{\begin{matrix} 1\text{ si }i = k \\ 0\text{ sinon}\end{matrix}\right.$.

2. Soit un nuage de points de même taille $(b_0,\ldots,b_n)$, on cherche à montrer qu'il
  existe un unique polynôme $P \in \mathbb{K}_n[X]$ tel que
  $P(a_i) = b_i$.\
  On veut le polynôme de $\mathbb{K}_n[X]$ qui passe par $(a_i, b_j)$,
  $0 \leq i \leq n$, on devine $P = \sum\limits_{i = 0}^{n} b_i L_i$.
  Ainsi, $\text{deg}(P) \leq \text{max}(\text{deg}(b_i L_i), 0 \leq i \leq n) \leq n$,
  donc $P \in \mathbb{K}_n[X]$. De plus,
  $\forall j \in [\![0,n]\!], P(a_j) = \sum\limits_{i = 0}^{n} b_i L_i(a_j)$
  $= \sum\limits_{i = 0}^{n} b_i S_{i,j} = 0 + b_j S_{jj} = b_j$,
  donc $P$ convient.\
  On montre l'unicité : si $P$ et $Q$ conviennent, alors
  $(P - Q)(a_i) = 0$, ce qui donne $n + 1$ racine pour
  $P - Q$, donc $P - Q \in \mathbb{K}_n[X]$ est le polynôme nul,
  donc $P = Q$.

3. Si deux polynômes de $\mathbb{K}_n[X]$ coïncident en $(n+1)$ points,
  alors ils sont égaux. Soit $P \in \mathbb{K}_n[X]$, on pose
  $Q = \sum\limits_{i = 0}^{n} P(a_i) L_i$. On a
  $\text{deg}(Q) \leq n$, car $\forall i, \text{deg}(L_i) = n$.
  Pour $j \in [\![0,n]\!], Q(a_j) = \sum\limits_{i = 0}^{n} P(a_i) L_i(a_j) = P(a_j) S_{j,j} + 0 = P(a_j)$.

On peut remarquer que $\forall P \in \mathbb{K}_n[X]$, $P = \sum\limits_{i = 0}^{n} P(a_i) L_i$
$= \sum\limits_{k = 0}^{n} C_k X^k$.

4. $B = \sum\limits_{i = 0}^{n} L_i$, on a $B \in \mathbb{K}_n[X]$ et
  $\forall j \in [\![0,n]\!], B(a_j) = \sum\limits_{i = 0}^{n} \frac{L_i(a_j)}{S_{i,j}} = 1$.
  Ainsi, $B$ et $1$ coïncident en $n+1$ points donc $B = 1$.

5. ...
  Si $Q$ est solution, alors $\forall i \in [\![0,n]\!], Q(a_i) = b_i = P(a_i)$,
  donc $Q - P$ possède $(a_i)_{0 \leq i \leq n}$ pour racines. Alors,
  $\prod\limits_{i = 0}^{n} (X - a_i)$ divise $Q - P$.
  $\exists R \in \mathbb{K}[X], Q - P = (\prod\limits_{i = 0}^{n} (X - a_i)) \times R$,
  et donc $Q = P + R \times \prod\limits_{i = 0}^{n} (X - a_i)$,
  et ils conviennent tous.
  Par synthèse, les solutions sont telles que
  $\sum\limits_{i = 0}^{n} b_i L_i + \prod\limits_{i = 0}^{n} (X - a_i) \times R$,
  avec $R \in \mathbb{K}[X]$. Ainsi, le deuxième membre de la somme est de degré
  supérieur ou égal à $n+1$.

## Relations entre les coefficients et les racines
Soit $P = a X^2 + b X + c$, avec $a \neq 0$, avec $P$ scindé dans $\mathbb{C}$,
et on a $P = a \times (X - x_1) (X - x_2)$. En développant,
on a $P = a (X^2 - (x_1 + x_2) X + x_1 x_2)$.
Par égalité des coefficients, on a $x_1 + x_2 = \frac{-b}{a}$
et $x_1 \times x_2 = \frac{c}{a}$.

On peut effectuer le même raisonnement sur les polynômes de degré $3$,
nous donnant $x_1 \times x_2 \times x_3 = \frac{-a_0}{a_3}$,
$x_1 + x_2 + x_3 = \frac{-a_2}{a_3}$.

> Soit $P = \sum\limits_{k = 0}^{n} a_k X^k$ de degré $n$, tel que $P$ est
> scindé, $P = a_n \times \prod\limits_{i = 1}^{n} (X - x_i)$.

> On note alors $\sigma_1 = \sum\limits_{i = 1}^{n} x_i = \frac{- a_{n-1}}{a_n}$
> (la somme des racines) et $\sigma_n = \prod\limits_{i = 1}^{n} x_i = (-1)^n \frac{a_0}{a_n}$
> (le produit des racines).

Pour $k \in [\![1,n]\!], \sigma_k = \sum\limits_{i_1,\ldots,i_k \mid i_1 < i_2 < \ldots < i_k} x_{i_1} x_{i_2} \ldots x_{i_k}$
$= (-1)^k \frac{a_{n-k}}{a_n}$.

Les $\sigma_k$ sont des fonctions symétrique élémentaires des racines.
