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
  $d = \text{min}(\mathbb{N}^{\ast}ii(a\mathbb{Z} + b\mathbb{Z}))$,
  $r < d$ et $r \in \mathbb{N} \cap (a\mathbb{Z} + b\mathbb{Z})$,
  donc $r = 0$, donc $d$ divise $a$.\
  On montre de même que $d$ divise $a \wedge b$.

__Corollaire :__ $a\mathbb{Z} + b\mathbb{Z} = \{au + bv, (u,v) \in \mathbb{Z}^2\}$,
donc $a\mathbb{Z} + b\mathbb{Z} = (a \wedge b)\mathbb{Z}$.
