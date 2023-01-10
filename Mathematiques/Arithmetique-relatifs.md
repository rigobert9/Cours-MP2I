# Arithmétique dans les relatifs
## Divisibilité et division euclidienne
Toute partie non vide de $\mathbb{N}$ possède un plus petit élément.
Toute partie non vide majorée de $\mathbb{N}$ possède un plus grand élément.

### Théorème de la division euclidienne
> Soit $a \in \mathbb{Z}$ et $b \in \mathbb{N}^{\ast}$, il existe un unique couple
> $(q,r) \in \mathbb{Z}^2$ tel que $\left\{\begin{matrix} a = bq + r \\ 0 \leq r < b \end{matrix}\right.$.

On appelle $q$ le quotient et $r$ le reste.

__Preuve d'unicité :__ Soit $(q,r)$ et $(q',r')$ tels que
$a = bq + r = bq' + r'$ et $\left\{\begin{matrix} 0 \leq r < b \\ 0 \leq  r' < b \end{matrix}\right.$.
Alors $r - r' = b \times (q' - q)$ et $-b < r - r'< b$, soit $|r - r'| < b$, et
$|r - r'| = b \times |q' - q|$ car $b \in \mathbb{N}^{\ast}$.
Ainsi, $b |q - q'| < b$, or $b > 0$ donc $|q - q'| < 1$, donc $|q - q'| = 0$,
donc $r = r'$.

__Preuve d'existence :__ Soit $A = \{k \in \mathbb{Z} \mid kb \leq a\}$,
$A$ est une partie de $\mathbb{Z}$ non vide majorée, donc elle admet un plus
grand élément. On pose $q = \text{max} A$ et $q + 1 \not\in A$, donc
$qb \leq a$ et $(q+1)b > a$, donc $0 \leq a - bq < b$.
On pose $r = a - bq$, on a bien
$\left\{\begin{matrix} a = bq + r \\ 0 \leq r < b \end{matrix}\right.$

### Divisibilité
> Soit $(a,b) \in \mathbb{Z}^2$, on dit que $b$ divise $a$ si
> $\exists k \in \mathbb{Z}, a = bk$ (ou si $a \equiv 0[b]$).
> On note $b \mid a$, soit $b$ est un diviseur de $a$ ou $a$ est un multiple de $b$,
> soit que le reste de la division de $a$ par $b$ est nul.

Soit $n \in \mathbb{Z}$, les multiples de $n$ sont notés
$n\mathbb{Z} = \{kn, k \in \mathbb{Z}\}$, et les diviseurs de $n$ sont notés
$D(n) = \{k \in \mathbb{Z} \mid k \mid n\}$.

Soit $a \in \mathbb{Z}$ :
- $a \mid a, -a \mid a$
- $1 \mid a, -1 \mid a$
- $a \mid 0$ car $0 = a \times 0$
- Si $0 \mid b$, alors $b = 0$

Les diviseurs d'un nombre sont toujours finis, sauf pour les diviseurs de $0$
qui sont $\mathbb{Z}$. Pour $a \neq 0, D(a) \subset [\![- |a|, |a|]\!]$.

> $\forall (a,b) \in \mathbb{Z}^2, b \mid a \Leftrightarrow a\mathbb{Z} \subset b\mathbb{Z}$
> $\Leftrightarrow D(b) \subset D(a)$

__Preuve :__
- si $b \mid a$, $b$ est un diviseur de $a$. Soit $d$ un diviseur de $b$, par
  transitivité, $d \mid a$, d'où $D(b) \subset D(a)$. Soit $m$ un multiple de a,
  $a$ divise $m$. Par transitivité, $b \mid m$, donc $m$ est un multiple de $b$,
  d'où $a\mathbb{Z} \subset b\mathbb{Z}$.
- si $D(b) \subset D(a)$, $b \in D(b)$, donc $b \in D(a)$ donc $b \mid a$
- si $a\mathbb{Z} \subset b\mathbb{Z}$, $a \in a\mathbb{Z}$, donc $a \in b\mathbb{Z}$,
  et $|a|$ est un multiple de $b$ donc $b \mid a$

La relation $\mid$ est une relation d'ordre partiel sur $\mathbb{N}$,
et $\mid$ est un relation réflexive et transitive sur $\mathbb{Z}$.
Elle n'est pas antisymétrique car $\forall (a,b) \in \mathbb{Z}^2$,
$(a \mid b \land b \mid a) \Rightarrow \left\{\begin{matrix} a = b \\ \text{ou} \\ a = -b \end{matrix}\right.$
(on dit que les entiers $a$ et $b$ sont associés).

- Si $a \mid b$ et $c \mid d$, alors $ac \mid bd$
- Si $a \mid b$ et $k \in \mathbb{N}^{\ast}$, alors $a^k \mid b^k$
- Si $d \mid a$ et $d \mid b$, alors pour tout $(u,v) \in \mathbb{Z}^2$,
  $d \mid (au + bv)$

### Congruence
> Soit $(a,b) \in \mathbb{Z}^2$ et $n \in \mathbb{N}^{\ast}$,
> $a \equiv b[n] \Leftrightarrow \exists k \in \mathbb{Z}, a = b + kn$.

- Si $a \equiv b[n]$ et $a' \equiv b'[n]$, alors $a+a' \equiv b+b'[n]$
- Si $a \equiv b[n]$ et $a' \equiv b'[n]$, alors $aa' \equiv bb'[n]$
- Si $a \equiv b[n]$, alors pour tout $p \in \mathbb{N}$, $a^p \equiv b^p[n]$
- Pour tout $\lambda \in \mathbb{Z}^{\ast}$, $a \equiv b[n] \Leftrightarrow \lambda a \equiv \lambda b[n]$

## PGCD, PPCM
### Plus grand diviseur commun pour 2 entiers
> Pour $(a,b) \in \mathbb{Z}^2 \setminus \{(0,0)\}$, le $\text{PGCD}$
> de $a$ et $b$, noté $\text{PGCD}(a,b)$ ou $a \wedge b$, est le plus grand
> élément de $D(a) \cap D(b)$.

- Puisque $1 \mid a$ et $1 \mid b$, $1 \in D(a) \cap D(b)$, qui est donc non
  vide : il existe toujours un PGCD pour doux entiers.
- Comme $(a,b) \neq (0,0)$, donc $(a \neq 0 \lor b \neq 0)$,
  donc $D(a)$ ou $D(b)$ est fini, donc $D(a) \cap D(b)$ est fini et admet un
  maximum (partie non vide majorée).
- Puisque $1 \in D(a) \cap D(b)$, $a \wedge b \geq 1 \Leftrightarrow a \wedge b \in \mathbb{N}^{\ast}$

Pour tout $n \in \mathbb{Z} \setminus \{0\}, n \wedge 0 = |n|$ (par convention,
$0 \wedge 0 = 0$).

Pour $a,b \in \mathbb{Z}$, $a \wedge b = |a| \wedge b = a \wedge |b| = |a| \wedge |b|$.
De plus, $a \wedge a = |a|$, $a \wedge 0 = |a|$, $a \wedge 1 = 1$.

On peut travailler uniquement dans $\mathbb{N}$ au lieu de $\mathbb{Z}$ dans les
calculs de PGCD.

### Algorithme d'Euclide
> Lemme : $\forall (a,b,k) \in \mathbb{Z}^3, a \wedge b = (a + k b) \wedge b$

__Preuve :__ On cherche à montrer que $D(a) \cap D(b) = D(a + kb) \cap D(b)$.\
$\subset$ : Soit $d \in D(a) \cap D(b)$, on a $\left\{\begin{matrix} d \mid a \\ d \mid b \end{matrix}\right.$,
donc $d \mid kb$ pour $k \in \mathbb{Z}$, donc $d \mid a + kb$, donc $d \in D(a + kb)$.\
$\supset$ : Soit $d \in D(a + kb) \cap D(b)$, comme $d \mid b$, $d \mid kb$,
donc $d \mid -kb$. Or, $d \mid (a+kb)$, soit $d \mid a$, donc $d \in D(a)$

__Corollaire :__ Pour $\left\{\begin{matrix} a \in \mathbb{N}, b \in \mathbb{N}^{\ast} \end{matrix}\right.$,
la division euclidienne de $a$ par $b$ donne
$\exists! (q,r) \in \mathbb{N}^2 \mid a = bq + r \land \left\{\begin{matrix} 0 \leq r < b \\ r = a - bq \end{matrix}\right.$.
Par le lemme précédemment prouvé, $a \wedge b = b \wedge r$.

L'algorithme d'Euclide exploite donc ce corollaire pour calculer $a \wedge b$ :
- si $b = 0$, alors il s'agit de $|a|$
- sinon, on calcule $b \wedge a \text{ mod } b$

On construit une suite $(r_k)$ de restes successifs, avec $r_0 = a$, $r_1 = b$.
Pour tout $k \geq 1$, $r_{k+1}$ est le reste de la division euclidienne de $r_{k-1}$
par $r_k$. Ainsi, la suite des $(r_k)_k$ est dans $\mathbb{N}$ et est
strictement décroissante, ce qui signifie que la suite est nécessairement finie
(ordre bien fondé). Ainsi, il existe un $N$ tel que $r_{N+1} = 0$ et $r_N \neq 0$.
Par le lemme, $a \wedge b = r_N$

Cet algorithme est de complexité $O(5 \log_\varphi(b))$.

> Soit $(a,b) \neq (0,0)$ un couple d'entiers et $d = a \wedge b$,
> alors $\forall n \in \mathbb{Z}, (n \mid d \Leftrightarrow (n \mid a \land n \mid b))$
> c'est-à-dire $D(a \wedge b) = D(a) \cap D(b)$.

On prouve ce résultat par l'algorithme d'Euclide, en étudiant pour tout $n$
$D(r_n) \cap D(r_{n+1})$ : ainsi, par égalité successives,
$D(a) \cap D(b) = D(r_N) \cap D(r_{N+1}) = D(r_N) \cap \mathbb{Z} = D(r_N) = D(a \wedge b)$.

Le PGCD est associatif, car
$D(a \wedge b) \cap D(c) = D(a) \cap D(b) \cap D(c) = D(a) \cap D(b \wedge c)$.
On peut aussi factoriser par un diviseur commun, soit
$(ka) \wedge (kb) = |k| \times (a \wedge b)$.

__Preuve :__ On suppose $k \neq 0$, et on pose $d = a \wedge b$.
- On sait que $d \mid a$ et $d \mid b$, donc $kd \mid ka$
  et $kd \mid kb$ donc $kd \mid (ka \wedge kb)$
- On note $\delta = (ka \wedge kb)$,
  or $k \mid ka$ et $k \mid kb$, donc $k \mid (ka) \wedge (kb)$,
  soit $k \mid \delta$. Ainsi, $\exists c \in \mathbb{Z}, \delta = kc$.
  Or, $\left\{\begin{matrix} \delta \mid ka \\ \delta \mid kb \end{matrix}\right.$,
  donc $\left\{\begin{matrix} kc \mid ka \\ kc \mid kb \end{matrix}\right.$
  donc $\left\{\begin{matrix} c \mid a \\ c \mid b \end{matrix}\right.$,
  soit $c \mid a \wedge b$, donc $kc \mid k \times (a \wedge b)$,
  donc $\delta \mid k \times (a \wedge b)$.
  $\delta et kd$ sont associés (ils se divisent mutuellement),
  donc $|\delta| = |k d|$, d'où le résultat.

On peut aussi en déduire que pour $(a,b) \neq (0,0)$,
en posant $d = a \wedge b$, il existe $a', b' \in \mathbb{Z}$ tels que
$\left\{\begin{matrix} a = da' \\ b = db' \end{matrix}\right.$.
$d = a \wedge b = (da') \wedge (db') = d \times (a' \wedge b')$,
donc $1 = a' \wedge b'$ (ils sont premiers entre eux).

### Relation de Bézout
> Soient $a,b \in \mathbb{Z}, \exists (u,v) \in \mathbb{Z}^2, au + bv = a \wedge b$.

Le couple $(u,v)$ est appelé coefficients de Bézout. Il n'y a pas unicité.

__Preuve :__ $(a,b) \neq (0,0)$. On a $|a| + |b| \in \mathbb{N}^{\ast} \cap (a\mathbb{Z} + b\mathbb{Z})$.
Donc $\mathbb{N}^{\ast} \cap (a\mathbb{Z} + b\mathbb{Z})$ est une
parie non vide de $\mathbb{N}^{\ast}$, donc possède un plus petit élément, noté
$d$. $d = \text{min}(\mathbb{N}^{\ast} \cap (a\mathbb{Z} + b\mathbb{Z}))$,
donc $\exists (u,v+ \in \mathbb{Z}^2 \mid d = au + bv)$.\
On cherche à montrer que $d = a \wedge b$ :
- on a  $a \wedge b \mid a$ et $a \wedge b \mid b$, donc $a \wedge b \mid (au + bv)$
  donc $a \wedge b \mid d$.
- Par division euclidienne de $a$ par $d$,
  $\exists! (q,r), a = dq + r$ avec $\left\{\begin{matrix} 0 \leq r < q \\ r = a - dq \end{matrix}\right.$,
  donc $r = a - (au + bv)q$. Puisque $r \geq 0$ et $r \in a\mathbb{Z} + b\mathbb{Z}$,
  $d = \text{min}(\mathbb{N}^{\ast} \cap (a\mathbb{Z} + b\mathbb{Z}))$,
  $r < d$ et $r \in \mathbb{N} \cap (a\mathbb{Z} + b\mathbb{Z})$,
  donc $r = 0$, donc $d$ divise $a$.\
  On montre de même que $d$ divise $a \wedge b$.

__Corollaire :__ $a\mathbb{Z} + b\mathbb{Z} = \{au + bv, (u,v) \in \mathbb{Z}^2\}$,
donc $a\mathbb{Z} + b\mathbb{Z} = (a \wedge b)\mathbb{Z}$.

On peut calculer un coefficient de Bézout à l'aide d'un Algorithme d'Euclide
étendu. On calcule les divisions euclidiennes successives de $r_{k-1}$ par
$r_k$. On peut alors remonter l'algorithme en fonction des deux entrées.

### PGCD d'une famille d'entiers
Comme $\wedge$ est associative, on peut l'étendre à une famille finie. Soit
$(a_1, a_2,\ldots,a_r) \in \mathbb{Z}^r$. Le PGCD de cette famille est noté
$(\bigwedge\limits_{i = 1}^{r} a_i)$. Il s'agit donc du plus grand élément pour
$\bigcap\limits_{i \in  I}^{r} D(a_i)$.

Ainsi, le PGCD de $(a_1,a_2,\ldots,a_r)$ est aussi le plus grand élément au
sens de la divisibilité : $\bigcap\limits_{i = 1}^{r} D(a_i) = D(\bigwedge\limits_{i = 1}^{r} a_i)$.
En notant $d = \bigwedge\limits_{i = 1}^{r} a_i$, on a
$\forall n \in \mathbb{Z}, (n \mid d \Leftrightarrow \forall i \in [\![1,r]\!], n \mid a)$.
On a utilisé $r$ fois le résultat $D(a) \cap D(b) = D(a \wedge b)$.

Il existe une relation de Bézout :
$\exists (u_1,u_2,\ldots,u_r) \in \mathbb{Z}^r \mid \sum\limits_{i = 1}^{r} a_i u_i = \bigwedge\limits_{i = 1}^{r} a_i$,
c'est-à-dire $\sum\limits_{i = 1}^{r} a_i \mathbb{Z} = (\bigwedge\limits_{i = 1}^{r} a_i) \mathbb{Z}$.

## Plus petit multiple commun
> Soit $(a,b) \in \mathbb{Z}^2$, avec $(a,b) \neq (0,0)$, le PPCM de
> $a$ et $b$, noté $a \vee b$, est le plus petit élément de l'ensemble
> $\mathbb{N}^{\ast} \cap a\mathbb{Z} \cap b\mathbb{Z}$.

Il existe toujours un PPCM, car $a\mathbb{Z}$ et $b\mathbb{Z}$ contiennent $0$,
donc $a\mathbb{N} \cap b\mathbb{N}$ est non vide. De plus, le PPCM d'un nombre
et $0$ est toujours $0$.

Pour $(a,b) \in (\mathbb{Z} \setminus \{0\})^2, a\mathbb{Z} \cap b\mathbb{Z} = (a \vee b)\mathbb{Z}$,
c'est-à-dire $\forall n \in \mathbb{Z}, (a \mid n \land b \mid n) \Leftrightarrow (a \vee b) \mid n$.

__Preuve :__ \
$\supset$ Soit $n \in (a \vee b)\mathbb{Z}$, alors $a \vee b \mid n$.
Or, $\left\{\begin{matrix} a \mid a \vee b \\ b \mid a \vee b \end{matrix}\right.$, donc
$(a \mid n \land b \mid n)$ par transitivité.\
$\subset$ Soit $n \in a\mathbb{Z} \cap b\mathbb{Z}$, on a $a \mid n$
et $b \mid n$. On va effectuer la division Euclidienne de $n$ par $a \vee b$ :
$\exists! (q,r) \in \mathbb{Z}^2, n = q \times (a \vee b) + r$, avec
$0 \leq r < a \vee b$.
Donc $r = n - q \times (a \vee b)$, or $\left\{\begin{matrix} a \mid n \\ b \mid n \end{matrix}\right.$
et $\left\{\begin{matrix} a \mid a \vee b \\ b \mid a \vee b \end{matrix}\right.$,
donc $a \mid r$ et $b \mid r$ donc $r \in (a\mathbb{Z} \cap b\mathbb{Z} \cap \mathbb{N})$
et $r < a \vee b$, or $a \vee b = \text{min}(a\mathbb{Z} \cap b\mathbb{Z} \cap \mathbb{N}^{\ast})$,
donc $r = 0$.
Ainsi, $n = q \times (a \vee b)$, donc $a \vee b \mid n$, donc $n \in (a \vee b)\mathbb{Z}$.

On a les propriétés suivantes :
- $a \vee b = b \vee a$
- $a \vee a = |a|$
- $a \mid b \Leftrightarrow a \vee b = |b| \Leftrightarrow a \wedge b = |a|$
- associativité
- factorisation : $(ka) \vee (kb) = |k| \times (a \vee b)$

> $\forall (a,b) \in (\mathbb{Z} \setminus \{0\})^2, (a \wedge b) \times (a \vee b) = |ab|$

Ainsi, les calculs efficaces du PGCD (l'algorithme d'Euclide) permettent de
déduire le PPCM.

## Entiers premiers entre eux
> $a$ et $b$ sont premiers entre eux si $a \wedge b = 1$.

Leurs diviseurs communs sont donc $\pm 1$.

On se ramène souvent aux entiers premiers entre eux :
Soient $(a,b) \in (\mathbb{Z} \setminus \{0\})^2$, on note $d = a \wedge b$.
Alors $\exists a',b' \mid \left\{\begin{matrix} a = da' \\ b = db' \end{matrix}\right.$
avec $a' \wedge b' = 1$.

En effet, $d = a \wedge b = (da') \wedge (db') \Rightarrow d = d \times (a' \wedge b')$
$\Rightarrow 1  = a' \wedge b'$.

On peut généraliser à r entiers $a_1,a_2,\ldots,a_r \in \mathbb{Z} \setminus \{0\}$.
On a deux notions possibles non équivalentes :
- Deux à deux premiers entre eux : $a_1,a_2,\ldots,a_r$ sont premiers deux à
  deux entre eux si $\forall i \forall j, i \neq j \Rightarrow a_i \wedge a_j = 1$
- Premiers dans leur ensemble : $a_1,a_2,\ldots,a_r$ sont premiers entre eux
  dans leur ensemble si $\bigwedge\limits_{i = 1}^{r} a_i = 1$.

On a une implication de la première propriété à la seconde, mais pas l'inverse.

### Théorème de Bézout et lemme de Gauss
> Théorème de Bézout : Soit $(a,b) \in \mathbb{Z}^2$, on a équivalence entre :
> - $a$ et $b$ sont premiers entre eux
> - $\exists (u,v) \in \mathbb{Z}^2, au + bv = 1$

Ainsi, en trouvant une relation de Bézout, on peut trouver que $a$ et $b$ sont
premiers entre eux.

__Preuve :__ $\Rightarrow$ Si $a \wedge b = 1$, alors il existe une relation de
Bézout.\
$\Leftarrow$ Si $au + bv = 1$, on prends un diviseur commun à $a$ et $b$.
Ainsi, $d \mid a$ et $d \mid b$, donc $d \mid (au + bv)$ donc
$d \mid 1$, donc $d = \pm 1$, donc $a \wedge b = 1$.

> Lemme de Gauss : Soit $(a,b,c) \in \mathbb{Z}^3$, si $a \mid b \times c$
> et $a \wedge b = 1$, alors $a \mid c$.

__Preuve :__ $a \wedge b = 1$ donc $\exists (u,v) \in \mathbb{Z}^2$,
$au + bv = 1$, alors $acu + bcv = c$. Si $a \mid bc$,
alors $a \mid (bc \vee  + acu)$ donc $a \mid c$.

On remarque que si $a \wedge b = 1$, alors $\exists (u,v) \in \mathbb{Z}^2$,
$au + bv = 1$, soit modulo $a$ $bv \equiv 1[a]$
donc $b$ est inversible pour $x$ dans l'anneau $\mathbb{Z} / a\mathbb{Z}$.
Le calcul de $v$ se fait par l'algorithme d'Euclide étendu.

On peut aussi se référer au fait que les inversibles de
$(\mathbb{Z}/n\mathbb{Z}, +, \times)$ soient exactement
$\{k \mid k \wedge n = 1\}$.

On peut ainsi résoudre l'équation $ax + by = 1$ avec $x,y \in \mathbb{Z}$
par l'algorithme d'Euclide étendu.

Soit $(x,y) \in \mathbb{Z}^2$ une solution $ax + by = 1 = ax_0 + by_0$
donc $ax - ax_0 = by_0 - by$ donc $a(x - x_0) = b(y_0 - y)$.
Ainsi, $a$ divise $b \times (y_0 - y)$. Or, $a \wedge b = 1$.
Par Gauss, $a \mid y_0 - y$, donc $\exists k \in \mathbb{Z}, y_0 - y = a_k$,
donc $\exists k \in \mathbb{Z}, y_0 - y = a_k$, donc
$a(x - x_0) = b \times ak$, donc $(a \neq 0)$, $x - x_0 = bk$.\
Pour $k \in \mathbb{Z}$, on pose $\left\{\begin{matrix} x = x_0 + bk \\ y = y_0 - ak \end{matrix}\right.$,
soit $ax + by = a(x_0) + b(y_0) + 0 = 1$\
On en conclut que $\left\{\begin{matrix} ax + by = 1 \\ a \wedge b = 1 \end{matrix}\right.$
a pour solution $\{(x_0 + bk, y_0 - ak), k \in \mathbb{Z}\}$.

> Soient $(a,b,c) \in \mathbb{Z}^3$ :
> - $a \wedge b = 1 \land a \wedge c = 1 \Leftrightarrow a \wedge bc = 1$
> - $a \wedge b \Rightarrow (a \mid b \land a \mid c \Rightarrow ab \mid c)$

__Preuves :__
- $\Rightarrow$ On suppose $\left\{\begin{matrix} a \wedge b = 1 \\ a \wedge c = 1 \end{matrix}\right.$.
  Par Bézout, $\exists (u,v), (u',v') \in \mathbb{Z}^2, \left\{\begin{matrix} au + bv = 1 \\ au' + cv' = 1 \end{matrix}\right.$.
  On fait le produit, donnant $a \times [uau' + ucv' + bvu'] + bc \times  vv' = 1$,
  donc $aU + bcV = 1$, donc par Bézout, $a \wedge (bc) = 1$.\
  $\Leftarrow$ Si $a \wedge bc = 1$, en utilisant Bézout, $\exists (u,v) \in \mathbb{Z}^2 \mid au + bcv = 1$.
  Par Bézout, $a \wedge b = 1$ et $a \wedge c = 1$.
- On suppose que $a \wedge b = 1$, et $a \mid c$ et $b \mid c$. On cherche à montrer que
  $ab \mid c$. $\exists k,k' \in \mathbb{Z} \mid c = ka = k'b$. Ainsi,
  $b \mid ka$. Or $a \wedge b = 1$, donc par Gauss, $b \mid k$. Ainsi,
  $\exists k'' \in \mathbb{Z} \mid k = bk''$, d'où $c = bk'' a$, soit $ba \mid c$.

On peut le refaire avec des congruences : si $a \wedge b = 1$ et
$\left\{\begin{matrix} c \equiv 0[a] \\ c \equiv 0[b] \end{matrix}\right.$,
alors $c \equiv 0[ab]$.

> $(a \wedge b) \times (a \vee b) = |a \times b|$

__Preuve :__ Posons $d = a \wedge b$. Ansi,
$\exists a',b' \in \mathbb{Z}, a = da', b = db'$ où $a' \wedge b' = 1$.
Alors $a \vee b = (da') \vee (db') = d \times (a' \vee b')$,
alors $d \times (a \vee b) = d^2 \times (a' \vee b')$. Il reste à montrer que
$a' \vee b' = |a'b'|$ lorsque $a' \wedge b' = 1$. On note $m = a' \vee b'$.
Or, $\left\{\begin{matrix} a' \mid a'b' \\ b' \mid a'b' \end{matrix}\right.$,
donc $a' \vee b' \mid a'b'$. De plus, $\left\{\begin{matrix} a' \mid m \\ b' \mid m \end{matrix}\right.$
et $a' \wedge b' = 1$, donc $a'b' \mid m$. Ainsi, $m = |a'b'|$.\
On en conclut que $(a \wedge b) \times (a \vee b)$\
$= d \times d \times (a' \vee b')$\
$= d \times d \times |a'b'|$\
$= |da'| \times |db'|$\
$= |ab|$

On peut ainsi généraliser cette relation en prenant $n,a_1,a_2,\ldots,a_r \in \mathbb{Z}$
tels que $(\forall i \in [\![1,r]\!], n \wedge a_i = 1)$
$\Leftrightarrow n_1 (a_1 a_2 \ldots a_r) = 1$.
On a donc $r$ relations de Bézout possibles dans le premier terme, de la
forme $u_i n + a_i v_i = 1$. Par produit $n \times U + a_i \ldots a_r V = 1$,
d'où $n_1(a_1 \ldots a_r) = 1$.

Si les $a_i$ sont deux à deux premiers entre eux et si $\forall i \in [\![1, n]\!]$,
$a_i \mid n$ alors  $\prod\limits_{i = 1}^{r} (a_i) \mid n$.

__Écriture d'un rationnel sous forme irréductible :__

> Tout rationnel $r \in \mathbb{Q}$ s'écrit de manière unique sous la forme $\frac{p}{q}$
> avec $\left\{\begin{matrix} p \in \mathbb{Z} \\ q \in \mathbb{N}^{\ast} \\ p \wedge q = 1 \end{matrix}\right.$.

Soit $r = \frac{a}{b} \in \mathbb{Q}, \frac{a}{b} = \frac{-a}{-b}$, donc on
peut imposer un dénominateur dans $\mathbb{N}^{\ast}$.

__Preuve :__
- Unicité : si $r = \frac{p_1}{q_1} = \frac{p_2}{q_2}$, alors $p_1 \times q_2 = p_2 \times q_1$,
  avec $p_1 \wedge q_1 = 1 \land p_2 \wedge q_2 = 1$.
  Ainsi, $\left\{\begin{matrix} q_1 \mid p_1 q_2 \\ p_1 \wedge q_1 = 1 \end{matrix}\right.$,
  donc $q_1 \mid q_2$. De même, $q_2 \mid q_1$, soit $|q_1| = |q_2|$,
  or $q_1,q_2 \in \mathbb{N}^{\ast} \Leftrightarrow q_1 = q_2$, donc $p_1 = p_2$.
- Existence : on factorise par le PGCD, soit $d = a \wedge b$
  alors $\left\{\begin{matrix} a = da' \\ b = db' \end{matrix}\right.$
  avec $a' \wedge b' = 1$. Ainsi, $r = \frac{a}{b} = \frac{da'}{db'} = \frac{a'}{b'}$.

## Nombres premiers
### Définition
> Soit $p \in \mathbb{N}$, $p$ est premier si il admet exactement $2$ diviseurs
> positifs, soit $\text{card}(D(p) \cap \mathbb{N}) = 2$.

Ainsi, $p$ est premier si $p \neq 1$ et $D(p) \cap \mathbb{N} = \{1, p\}$.
On note $\mathbb{P} = \{2,3,5,7,11,13,17,\ldots\}$.

> L'ensemble $\mathbb{P}$ est infini.

__Preuve :__ Par l'absurde, on pose que $\mathbb{P}$ est fini avec $N$ éléments.
Soit $A = \prod\limits_{i = 1}^{N} p_i + 1$, $\forall i \in [\![1,N]\!]$,
$A \equiv 1[p_i]$, donc $\forall i, p_i \not\mid A$. Si $A \not\in \mathbb{P}$,
il existe un diviseur premier de $A$, ce qui est faux, donc $A \in \mathbb{P}$,
donc $A = p_{i_0}$, ce qui est absurde.

> Soit $p \in \mathbb{P}$, en $a \in \mathbb{Z}$, si
> $p \not\mid a$, alors $a \wedge p = 1$.

__Preuve :__ Par contraposée, on pose $a \wedge p \neq 1$.
On pose donc $d = a \wedge p$, et alors $d \in D(p) \cap \mathbb{N}$,
donc $d \in \{1,p\}$ et $d \neq 1$ donc $d = p$, donc
$p \mid a$.

> Si $p$ premier divise le produit $ab$ alors $p \mid a \lor p \mid b$.

On peut reformuler l'énoncé en congruences comme
$ab \equiv 0[p] \Rightarrow (a \equiv 0[p] \lor b \equiv 0[p])$,
soit l'intégrité dans l'anneau $\mathbb{Z}/p\mathbb{Z}$.

__Preuve :__ Si $p \mid a$, la propriété est vérifiée, et sinon $p \wedge a = 1$,
donc $p \mid ab$ permet de déduire par Gauss que $p \mid b$.

> Tout entier $n \geq 2$ s'écrit comme produit de facteurs premiers.

__Preuve :__ On cherche à prouver par récurrence forte la proposition.
- $2$ est premier, et se décompose comme $2$.
- Soit $n \geq 2$, tel que tout entier de $[\![2,n]\!]$ soit décomposable en
  facteurs premiers, si $n + 1 \in \mathbb{P}$, il est décomposable comme
  lui-même, et sinon $\exists d \neq 1 \mid d \neq n + 1$ tel
  que $d \mid n + 1$ (car $n + 1$ n'est pas premier). On pose
  $n + 1 = d \times a$, avec $2 \leq d \leq n$ et $a \mid n + 1$
  avec $a \in \{1,n+1\}$ donc $2 \leq a \leq n$. Par hypothèse de récurrence, la
  décomposition de $n + 1$ est le produit des décompositions de $a$ et $d$.

> Si $n \in \mathbb{N}^{\ast}$ n'est pas un nombre premier, alors $n$ possède un
> diviseur premier avec $p \leq \sqrt{n}$ (crible d'Eratosthène).

En effet $n \not\in \mathbb{P}$, donc $n = a \times b$, avec $2 \leq a \leq b$,
donc $a^2 \leq ab = n$, donc $a \leq \sqrt{n}$ et $a$ possède au moins
un diviseur $p$ premier.

> Soit $p \in \mathbb{P}$ et $n \in \mathbb{N}^{\ast}$, l'ensemble
> $\{k \in \mathbb{N} \mid p^k \mid n\}$ possède un plus grand élément, qu'on note
> $v_p(n)$, la valuation $p$-adique de $n$ (le nombre de fois où apparaît $p$
> dans la factorisation de $n$).

On peut remarquer que pour tout $n \in \mathbb{N}^{\ast}$ et $p \in \mathbb{P}$,
$n = p^{v_p(n)} \times q$, où $q \wedge p = 1$
(car $p \not\mid q$).

> $\forall p \in \mathbb{P}, \forall (a,b) \in \mathbb{N}^{\ast}^2, v_p(ab)$
> $= v_p(a) + v_p(b)$.

__Preuve :__ $ab = p^{v_p(a)} \times q_1 \times p^{v_p(b)} \times q_2$,
avec $\left\{\begin{matrix} q_1 \wedge p = 1 \\ q_2 \wedge p = 1 \end{matrix}\right.$,
donc $ab = p^{v_p(a) + v_p(b)} \times q_1 q_2$ et $p_1(q_1 q_2) = 1$.
Ainsi, $v_p(ab) = v_p(a) + v_p(b)$.

> $\forall n \in \mathbb{N}^{\ast}, n = \prod\limits_{p \in \mathbb{P}} p^{v_p(n)}$,
> où la suite $(v_p(n))_{p \in \mathbb{P}}$ est presque nulle
> (ainsi, le produit est fini).

L'écriture de la décomposition est donc unique à l'ordre des facteurs près.
Le produit est fini car si $n \in \mathbb{P}$, il contient un seul terme, et
sinon, le plus grand facteur premier $p \mid n$ vérifie $p \leq \sqrt{n}$.

__Preuve de l'unicité :__ Si $n = p_1^{\alpha_1} p_2^{\alpha_2} \ldots p_r^{\alpha_r}$
avec $\alpha_i \in \mathbb{N}^{\ast}$ et $p_1 < p_2 < \ldots < p_r$,
et $n = q_1^{\beta_1} \ldots q_l^{\beta_l}$ avec $\beta_j \in \mathbb{N}^{\ast}$
et $q_1 < \ldots < q_l$.\
Soit $p_i$, $p_i \mid n$ car $\alpha_i \geq 1$, donc $p_i \mid \prod\limits_{j = 1}^{r} q_j^{\beta_j}$.\
Si $q_i \neq p_i$, alors $q_j \wedge p_j = 1$. Si $p_i \not\in \{q_1,\ldots,q_l\}$.\
Ainsi $\{p_1,\ldots,p_r\} \subset \{q_1,\ldots,q_l\}$. Par symétrie,
on a l'inclusion inverse et donc l'égalité, donnant $l = r$,
et $\forall i \in [\![1,r]\!], p_i = q_i$. Ainsi,
$\forall i, v_{p_i}(n) = \alpha_i = v_{q_i}(n) = \beta_i$.

On peut relier ceci avec la divisibilité, le PGCD et le PPCM. Soit $(a,b) \in \mathbb{N}^{\ast}^2$ :
- $a \mid b \Leftrightarrow (\forall p \in \mathbb{P}, v_p(a) \leq v_p(b))$
- $a \wedge b = \prod\limits_{p \in \mathbb{P}} p^{\text{min}(v_p(a), v_p(b))}$
- $a \vee b = \prod\limits_{p \in \mathbb{P}} p^{\text{max}(v_p(a),v_p(b))}$
