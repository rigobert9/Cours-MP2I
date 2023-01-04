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
