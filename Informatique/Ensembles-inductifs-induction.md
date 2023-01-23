# Ensembles inductifs et induction
## Ordre bien fondé
> Soit $(E,\preceq)$ un ensemble ordonné. On dit que $\preceq$ est bien fondé si
> tout partie non vide de $E$ admet un élément minimal.

On écrit donc $\forall A \subset E, A \neq \emptyset \Rightarrow (\exists x \in A, \forall y \in A, y \not\preceq x)$.

On dit alors que $E$ est un ensemble inductif.

> Soit $(E, \preceq)$ un ensemble ordonné, l'ensemble est inductif
> si et seulement si il n'existe pas de suite strictement décroissante dans $E$.

__Preuve :__ $\Rightarrow$ On montre la contraposée. On suppose qu'il existe
$(u_n)_{n \in \mathbb{N}}$ strictement décroissante dans $E$. On pose alors
$A = \{u_n\}_{n \in \mathbb{N}}$. Si $A$ admettait un élément minimal, il y aurait
contradiction, et $A$ n'admet donc pas d'élément minimal, donc $E$ n'est pas inductif.\
$\Leftarrow$ On montre la contraposée. Soit $E$ non inductif, alors $\exists A \subset E$,
$A \neq \emptyset$ et $\forall x \in A, \exists y \in A, y \preceq a$. Pour tout
$x \in A$, soit $f(x)$ un tel élément, $f(x) \preceq x$. $A \neq \emptyset$,
donc on peut prendre $x_0 \in A$. On pose $\forall n \geq 1$, $x_n = f(x_{n-1})$,
alors $(x_n)_{n \in \mathbb{N}}$ est une suite stricte est décroissante.

$(\mathbb{P}(E), C)$ n'est pas inductif si $E$ est infini, car il existe une
injection de $\mathbb{N}$ dans $E$, donc $\mathbb{N} \subset E$, alors la suite
$(\mathbb{N} \setminus [\![0,n]\!])_{n \in \mathbb{N}}$ admet une suite
strictement décroissante de $\mathbb{P}(E)$.

$(\mathbb{N}, \mid)$ est un ensemble inductif. En effet, soit $A \subset \mathbb{N}$,
$A \neq \emptyset$. Si $A = \{0\}$, alors $0 = \text{min}(A)$.
Sinon, on pose $m = \text{min}(A \setminus \{0\})$.
Soit $x \in A$, si $x \mid m$, alors comme $m > 0$, il existe $k \geq 1$ tel que
$m = kx$. Or, $kx = m \leq x$. Donc, comme $x \neq 0$, $k \leq 1$, donc $k = 1$.
Donc tout diviseur de $m$ dans $A$ est $m$. $m$ est un élément minimal de $(A, \mid)$.

$(\mathbb{P}(E), \subset)$ avec $E$ fini est inductif. En effet, soit $A \subset \mathbb{P}(E), A \neq \emptyset$,
$n = \text{carg}(E)$. $\forall X \in A, \text{card}(X) \leq n$. Soit $m = \text{min}\{\text{card}(X)\}_{X \in A}$.
Ainsi, $m \in [\![0,n]\!]$. Soit $X_0 \in A$ tel que $\text{card}(X_0) = m$,
$X_0$ est minimal dans $(A, \subset)$. En effet, on suppose par l'absurde qu'il
existe $Y \in A$, $Y \not \subseteq X_0$ (pas strictement inclus), alors
$\text{card}(Y) < \text{card}(X_0) = m$, ce qui contredit la définition de $m$.

> Soient $(E, \preceq)$ et $(F, \preceq)$ inductifs, l'ordre lexicographique sur
> $E \times F$ est inductif.

__Preuve :__ Soit $A \subset E \times F$, $A \neq \emptyset$,
on pose $A_1 = \{x \in E \mid \exists y \in F, (x,y) \in A\}$. $A_1 \neq \emptyset$,
donc comme $E$ est inductif, il existe $x_0$ minimal dans $A_1$. De même pour un
$A_2$, qui admet un minimal $y_0$. Donc $(x_0,y_0)$ est minimal dans $A$.

__Corollaire :__ Soient $E_1,E_2,\ldots,E_n$ des ensembles inductifs, alors $E_1 \times E_2 \times \ldots \times E_n$
muni de l'ordre lexicographique est inductif. Soit $E$ un ensemble inductif,
$n \in \mathbb{N}$. Alors $E^n$ muni de l'ordre lexicographique est inductif.

## Principe d'induction
> Soit $(E, \preceq)$ un ensemble inductif, et $P$ une propriété sur les éléments
> de $E$, alors
> $(\forall x \in E, (\forall y \in E, y \preceq x \Rightarrow P(y)) \Rightarrow P(x)) \Rightarrow \forall x \in E, P(x)$.

Si $x$ est minimal, alors $\forall y \in E, y \not\rm\prec$, donc $y \prec x \Rightarrow P(y)$
sera toujours vrai, donc $\forall y \in E, y \prec x \Rightarrow P(y)$
est vrai.
Dans une preuve par induction, on traite le cas des éléments minimaux à part car
l'hypothèse d'induction $\forall y \in E, y \preceq x \Rightarrow P(y)$ est une
tautologie qui ne dépend pas de $P$.

On peut facilement reformuler ce théorème comme le principe de récurrence
(forte) sur $(\mathbb{N},, \leq)$.

__Preuve :__ On suppose $\forall x \in E, (\forall y \in E, y \preceq a \Rightarrow P(y)) \Rightarrow P(x)$.
Soit $F = \{x \in E \mid \overline{P(x)}\}$. Si $F = \emptyset$, $P(x)$
est vérifiée pour tout $x$.
Sinon, on suppose par l'absurde $F \neq 0$, et on prend $x \in F$. On a
$\overline{P(x)}$, donc $\forall y \in E, y \preceq x$ et $\overline{P(y)}$,
donc $y \in F$. Soit $f(x)$ un tel $y$ pour tout $x \in F$,
on pose $x_0 \in F$ quelconque et $\forall n \in \mathbb{N}^{\ast}, x_n = f(x_{n-1})$.
Cette suite est alors strictement décroissante, ce qui est absurde.
Soit $x$ un élément minimal de $F$, $\overline{P(x)}$,
donc $\overline{\forall y \in E, y \preceq x \Rightarrow P(y)}$,
donc $\exists y \in E, y \preceq x \land \overline{P(y)}$. Ainsi,
la minimalité de $x$ est contredite.

##### Exemple : la fonction d'Ackermann
On définit $A: \mathbb{N} \times \mathbb{N} \to \mathbb{N}$ telle que
$\left\{\begin{matrix} \forall n \in \mathbb{N}, A(0,n) = n+1 \\ \forall n \in \mathbb{N}^{\ast}, A(m,0) = A(m-1, 1) \\ \forall m \in \mathbb{N}^{\ast}, n \in \mathbb{N}^{\ast}, A(m,n) = A(m-1, A(m, n-1)) \end{matrix}\right.$

On prouve par induction que $\forall (m,n) \in \mathbb{N}^2, A(m,n)$ est bien
définie. On se place sur $\mathbb{N}^2$ muni de l'ordre lexicographique.
- Si $m = 0$, alors $A(0,n)$ est bien définie
- Soit $(m,n) \in \mathbb{N}^2$ avec $m \neq 0$, on suppose que $\forall (k,\ell) \in \mathbb{N}^2$
  avec $(k,\ell) < (m,n), A(k,\ell)$ est bien définie.
  Si $n = 0$, alors $(m-1, 1) < (m,n)$ et est dans $\mathbb{N}^2$,
  donc $A(m-1, 1)$ est bien définie, donc $A(m,n) = A(m-1,1)$ aussi.
  Si $n > 0$, alors $(m,n-1) < (m,n)$, donc $A(m,n-1)$ est bien définie,
  donc c'est un entier et $(m-1, A(m,n-1)) \in \mathbb{N}^2$,
  or $m-1 < m$, donc $(m-1, A(m,n-1)) < (m,n)$. Ainsi, $A(m-1, A(m,n-1))$
  est bien définie et $A(m,n)$ l'est donc aussi.
