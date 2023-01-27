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

## Applications aux structures de données connues
### Listes chaînées
Soient $\ell, \ell'$ deux listes possédant le même type de valeurs,
on peut définir un ordre structurel sur les listes tel que
$\ell \preceq \ell'$ si $\ell'$ est une liste composée de $n$ maillons en tête
suivis de $\ell$.
Cette relation est une relation bien fondée sur les listes chaînées.

### Piles et files
Les piles et les files ne sont pas des structures inductives (voir définition
plus loin), et ne possèdent pas d'ordre structurel. Cependant, on peut voir les
piles et les files comme un couple de listes, permettant d'utiliser l'ordre
structurel sur les listes dans un ordre lexicographique, donnant un ordre bien
fondé.

### Arbres binaires
On peut de même définir un ordre structurel sur les arbres, formé sur les
sous-arbres : pour deux arbres $A_1, A_2$, on a $A_1 \preceq A_2$ si $A_1$
fait partie des sous-arbres de $A_2$.
Cet ordre structurel est un ordre bien fondé.

### Structures inductives
Soit $S$ un ensemble appelé signature d'éléments appelées constructeurs, munis
chacun d'un entier naturel appelé arité. Un constructeur d'arité $0$ est appelé
constante ou constructeur constant. On supposera que $S$ contient au moins un
constructeur constant et un constructeur non constant.

> Un constructeur d'arité $k$ s'applique à k termes de la structure de signature
> $S$ pour construire un nouveau terme.

> On définit pour chaque entier $h \geq -1$ l'ensemble suivant :
> $E_{-1} = \{C \in S \mid C \text{ est d'arité 0}\}$, et
> $\forall k \in \mathbb{N}, E_k = E_{k-1} \cup (\bigcup\limits_{k \in \mathbb{N}^{\ast}} (\bigcup\limits_{C \in S, \,\text{d'arité k}} C(E_{k-1}^{k})))$.

On définit $E = \bigcup\limits_{k \in \mathbb{N}} E_k$ la structure inductive de
signature $S$. Si $t \in E$, le plus petit $k \in \mathbb{N} \cup \{-1\} \mid t \in E_k$
est appelé la hauteur de $t$. Les éléments de $E$ sont appelés termes.

Pour les arbres binaires, le constructeur d'arité $0$ est alors l'arbre vide, et
un nœud est un constructeur d'arité $2$, qu'il possède une étiquette ou non.
Pour les listes chaînées, la liste vide constitue un constructeur d'arité $0$
et un nœud est d'arité $1$.

> Si il existe $f: X \to S$ injective avec $X$ l'ensemble des valeurs d'un certain
> type, on peut dire que $f$ est un constructeur typé correspondant à l'ensemble
> des $f(x)$.

Par exemple, les arbres binaires étiquettés par un type $T$ ont la signature :
- `Vide` est un constructeur constant
- `Noeud` est un constructeur typé d'arité $2$

> Soit $E$ une structure inductive de signature $S$, $t \in E$ qui n'est pas un
> constructeur constant, alors il existe $C \in S, t_1, \ldots, t_k \in E$
> tels que $t = C(t_1;\ldots;t_k)$, avec $k > 0$. $t_1,\ldots,t_k$ sont appelés
> les sous-termes immédiats de $t$. On écrit $t_i \prec_i t$.

> On définit $\preceq$ comme la clôture réflexive transitive de $\prec_i$,
> c'est-à-dire $\forall u,v \in E$, $u \preceq v \Leftrightarrow \exists n \in \mathbb{N}, \exists (t_k)_{0 < k \leq n} \in E$,
> $u = t_0 \prec t_1 \prec \ldots \prec t_n = v$.

__Lemme :__ Soient $u,v \in E$ et $h_u, h_v$ leurs hauteurs, alors
si $u \prec v$, $h_u \prec h_v$.

__Preuve :__ $u \preceq v$, donc $\exists un \in \mathbb{N}, \exists (t_k)_{0 < k \leq n} \in E$,
$u = t_0 \prec \ldots \prec t_n = v$, mais $u \neq v$ donc $n \neq 0$.
On montre par récurrence sur $k \geq 1$ que la hauteur de $t_k$
est supérieur à $h_u$ :
- Initialisation : $u$ est un sous-terme immédiat de $t_1$, donc si $h$ est la
  hauteur de $t_1$, il existe $x_1,\ldots,x_n \in E_{k-1}$ et
  $C \in S$ d'arité $n$ tels que $t_1 = C(x_1,\ldots,x_n)$ et $u$ est l'un des
  $x_i$, donc $u \in E_{-1}$, donc $h_u \leq h - 1 < h$.
- Hérédité : Soit $k \geq 2$, $k \leq n$, on suppose que la hauteur de $t_{k-1}$
  est supérieure à $h_u$. Alors comme tout $t_{k_1}$ est un sous-terme immédi
