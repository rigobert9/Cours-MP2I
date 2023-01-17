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
