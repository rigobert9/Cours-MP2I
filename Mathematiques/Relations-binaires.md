# Relations binaire et ordre sur $\mathbb{R}$
## Relations binaires
### Définitions
> Soit $E$ un ensemble, on appelle relation binaire sur $E$, notée $\mathcal{R}$
> tout sous ensemble $\Gamma$ de $E^2$.
> Pour tout couple $(x,y) \in \Gamma$, on va dire que $x$ est en relation $\mathcal{R}$ avec $y$, et on le note
> $x \mathcal{R} y$.

- L'égalité ( $=$ ) est une relation sur E, où $\Gamma = \{(a, a), a \in E\}$
- La relation $\leq$ sur $\mathbb{R}$ est une relation où $\Gamma = \{(x,y) \in \mathbb{R}^2 \mid x \in ]-\infty, y]\}$
- Dans $\mathcal{P}(E)$, l'inclusion $\subset$ est une relation binaire

Soit $\mathcal{R}$ une relation binaire sur $E$, on dit que
- $\mathcal{R}$ est réflexive si $\forall x \in E, x \mathcal{R} x$
- $\mathcal{R}$ est symétrique si $\forall (x,y) \in E^2, x \mathcal{R} y \Rightarrow y \mathcal{R} x$
- $\mathcal{R}$ est antisymétrique si $\forall (x,y) \in E^2, [x \mathcal{R} y \land y \mathcal{R} x] \Rightarrow x = y$
- $\mathcal{R}$ est transitive si $\forall (x,y,z) \in E^3, x \mathcal{R} y \land y \mathcal{R} z \Rightarrow x \mathcal{R} z$

On s'intéressera principalement aux relations réflexives + symétriques + transitives et aux relations
réflexives + antisymétriques + transitives.

## Relations d'équivalence
### Définition
> Une relation binaire $\mathcal{R}$ sur $E$ est appelée relation d'équivalence
> si $\mathcal{R}$ est réflexive, symétrique et transitive.

- L'égalité $=$ sur $E$ est une relation d'équivalence
- En revanche, $\neq$ n'est ni réflexive ni transitive
- La congruence est une relation d'équivalence sur $\mathbb{Z}$, car soit $n \in \mathbb{N}^{\ast}$, on définit
  la congruence modulo n par $\forall (x,y) \in \mathbb{Z}^2, (x \equiv y[n] \Leftrightarrow \exists k \in \mathbb{Z}, x = y + kn)$. Ainsi, $. \equiv . [n]$ est une relation d'équivalence sur $\mathbb{Z}$.
- La congruence sur $\mathbb{R}$ est définie, soit $\alpha \in \mathbb{R}^{\ast}$, par
  $\forall (x,y) \in \mathbb{R}^2, x \equiv y[\alpha] \Leftrightarrow \exists k \in \mathbb{Z}, x = y + k\alpha$.
  $. \equiv . [\alpha]$ est donc une relation d'équivalence sur $\mathbb{R}$.

### Classe d'équivalence
> Soit $\mathcal{R}$ une relation d'équivalence sur $E$, pour tout élément $x \in E$,
> on définit la classe de $x$ comme l'ensemble des éléments en relation avec $x$

La classe d'équivalence de $x$ se note $cl(x)$, $\dot{x}$ ou $\overline{x}$, ce
qui est égal à $\{y \in E \mid y \mathcal{R} x\}$.

##### Exemple : Congruence dans $\mathbb{Z}$ modulo 2
Il n'y a que deux classes d'équivalences : $\dot{0} = \{n \in \mathbb{Z} \mid n \equiv 0[2]\} = \{n \in \mathbb{Z} \mid \text{n pair}\}$,
et $\dot{1} = \{n \in \mathbb{Z} \mid n \equiv 1[z]\} = \{n \in \mathbb{Z} \mid \text{n impair}\}$
(qui est par exemple identique à $\dot{37}$ et à $\dot{51}$).

##### Généralisation : Congruence dans $\mathbb{Z}$ modulo n
Les classes d'équivalences sont $\dot{k}$ pour $0 \leq k \leq n-1$, avec
chaque $\dot{k} = \{p \in \mathbb{Z} \mid p \equiv k[n]\} = \{k + nj, j \in \mathbb{Z}\} = k + n\mathbb{Z}$.
L'ensemble des classes d'équivalence $\{\dot{0}, \dot{1}, \ldots, \dot{n-1}\}$
est noté $\mathbb{Z} / n\mathbb{Z}$.
On a de plus une partition de $\mathbb{Z}$ par ces ensembles.

##### Et encore une fois : Congruence dans $\mathbb{R}$ modulo $2\pi$
Les différentes classes d'équivalences sont $\dot{\Theta} = \{\Theta + 2\pi k, k \in \mathbb{Z}\}$
$= \Theta + 2\pi \mathbb{Z}$ avec $\Theta \in ]-\pi, \pi]$.

##### Exemple avec un graphe
Avec la relation "avoir un chemin vers" dans un graphe, les classes
d'équivalences de cette relation sont les composantes connexes du graphe.

#### Partition des ensembles par les classes
> Soit $\mathcal{R}$ une relation d'équivalence sur $E$,
> les classes d'équivalences forment une partition de E.

##### Preuve
- Pour tout $x \in E$, $x \mathcal{R} x$ par réflexivité, donc $x \in \dot{x}$,
  donc $\dot{x} \neq \emptyset$.
- On a pour montrer que $E = \bigcup\limits_{x \in E} \dot{x}$ :
  - $\forall x \in E, \dot{x} \subset E$, donc $\bigcup\limits_{x \in E} \dot{x} \subset E$
  - $\forall x \in E, x \in \dot{x}$, donc $x \in \bigcup\limits_{x \in E} \dot{x}$
- Montrons que si $x,y \in E \mid x \mathcal{R} y$, alors  $\dot{x} = \dot{y}$.
  Supposons $x \mathcal{R} y$. On a par symétrie $y \mathcal{R} x$,
  alors $y \in \dot{x}$. De plus, si $z \in \dot{y}$, alors
  $z \mathcal{R} y$, or $y \mathcal{R} x$, donc la transitivité donne
  $z \mathcal{R} x$. On a donc $\dot{y} \subset \dot{x}$.
  Par symétrie, on a aussi $\dot{x} \subset \dot{y}$, d'où l'égalité
  $\dot{x} = \dot{y}$.
- On conclut que si $C_1$ et $C_2$ sont deux classes d'équivalences différentes
  $C_1 \neq C_2$, alors elles sont nécessairement disjointes ( $C_1 \cap C_2 = \emptyset$ ).
  En effet, par l'absurde, s'il existe $x \in C_1 \cap C_2$, alors
  $x \in C_1$ donc $\dot{x} = C_1$ et $x \in C_2$ donc $\dot{x} = C_2$
  donc $C_1 = C_2$, ce qui est absurde selon les précédentes déductions.

## Relation d'ordre
### Définitions
> Soit $\mathcal{R}$ une relation binaire sur $E$, $\mathcal{R}$ est une relation
> d'ordre sur $E$ si $\mathcal{R}$ est réflexive, antisymétrique et transitive.

- $\leq$ et $\geq$ sont des relations d'ordre sur $\mathbb{N}$, $\mathbb{Z}$, et $\mathbb{R}$
- $\subset$ est une relation d'ordre sur $\mathcal{P}(E)$

Si $E$ est muni d'une relation d'une relation d'ordre $\mathcal{R}$, on dit que
$(E, \mathcal{R})$ est un ensemble ordonné. On notera souvent $\preceq$ une
relation d'ordre quelconque.

##### Exemple : Divisibilité sur $\mathbb{N}$, notée $\mid$
Soit $(a,b) \in \mathbb{N}^2$, $a \mid b \Leftrightarrow \exists k \in \mathbb{N}, b = ak$.
$\mid$ est bien une relation d'ordre sur $\mathbb{N}$ car :
- Réflexive : Soit $a \in \mathbb{N}$, $a = a \times 1$ donc $a \mid a$
- Transitivité : Si $a \mid b$ et $b \mid c$ alors $\exists k, k' \in \mathbb{N}, b = ak \land c = bk'$,
  donc $c = akk'$, donc $a \mid c$.
- Antisymétrie : Si $a \mid b$ et $b \mid a$, $\exists k,k' \in nn, b = ak \land a = bk'$,
  donc $b = bkk'$.

Il s'agit néanmoins d'une relation d'ordre partielle, puisqu'elle ne permet pas
de lier en une hiérarchie tous les éléments de l'ensemble comme le ferait
$\leq$.

### Ordre total et ordre partiel
> Soit $(E,  \preceq)$ un ensemble ordonné (avec $\preceq$ une relation d'ordre
> quelconque) :
> - L'ordre est dit total si tous les éléments de $E$ sont comparables :
>   $\forall (x,y) \in E^2, x \preceq y \lor y \preceq x$.
> - Sinon l'ordre est partiel, au moins deux éléments de E ne sont pas
>   comparables : $\exists (x,y) \in E^2, \neg (x \preceq y) \land  \neg (y \preceq x)$.

Par exemple, $(\mathbb{R}, \leq)$ est un ensemble totalement ordonné. De même
$(\mathbb{N}, \leq), (\mathbb{Z}, \leq), (\mathbb{Q}, \leq)$ sont tous
totalement ordonnés.
En revanche, soit $E$ un ensemble ayant au moins deux éléments,
$(\mathcal{P}(E),  \subset)$ est partiellement ordonné, car pour un ensemble tel
que $a, b \in E$ avec $a \neq b$. $\{a\}, \{b\} \in \mathcal{P}(E)$,
$\{a\} \not\subset \{b\} \land \{b\} \not\subset \{a\}$, donc
$\{a\}$ et $\{b\}$ ne sont pas comparables. On a de même pour
$(\mathbb{N}, \mid)$ (la divisibilité).

##### Exemple : Créer un ordre sur $\mathbb{N}^2$
Idée 1 : "ordre produit", pour $(n,m), (n',m') \in \mathbb{N}^2$,
on définit $\preceq^x$ sur $\mathbb{N}^2$ par
$(n,m) \preceq^x (n',m') \Leftrightarrow n \leq n' \land m \leq m'$.
On a sa réflexivité, sa transitivité et son antisymétrie.
Cet ordre n'est néanmoins que partiel, puisque $(2,1)$ et $(1,2)$ ne sont pas
comparables.

Idée 2 : "ordre lexicographique", pour $(n,m), (n',m') \in \mathbb{N}^2$,
on définit $\preceq^{lex}$ sur $\mathbb{N}^2$ par
$(n,m) \preceq^{lex} (n',m') \Leftrightarrow n < n' \lor [n = n' \land m \leq m']$.
On a sa réflexivité, sa transitivité et son antisymétrie.
Cet ordre est bien total, car on peut comparer tous les cas possibles
dans $\mathbb{N}^2$.

On peut d'ailleurs utiliser cet ordre lexicographique total sur $\mathbb{C}$,
mais il ne permet pas de retenir les propriétés de l'ordre $\leq$ sur $\mathbb{R}$.

##### Exemple
Soit $(E, \preceq)$ un ensemble totalement ordonné, et $X$ un ensemble
quelconque. On peut munir l'ensemble $\mathfrak{F}(X, E)$ d'un ordre partiel.
Soient $f, g \in \mathfrak{F}(X, E)$ : $f \preceq g \Leftrightarrow (\forall x \in X, f(x) \preceq g(x))$.
Cet exemple présente donc un ordre sur des fonctions.

### Plus grand et plus petit élément
> Soit $(E, \preceq)$ un ensemble ordonné, et $A \subset E$ une partie de $E$,
> et un élément $a \in A$. On dit que a est le plus petit élément de A
> si $\forall x \in A, a \preceq x$.

> On dit que $a$ est le plus petit élément de $A$ si $\forall x \in A, x \preceq a$.

- Si le plus petit élément de A existe, il est unique et on le note $a = min(A)$.
- Si le plus grand élément de A existe, il est unique et on le note $a = max(A)$.

En effet, si $a$ et $a'$ sont deux éléments de A, et qu'ils sont tous deux le
plus petit élément de A, alors on a par définition $a \preceq a'$ et $a' \preceq a$,
soit $a = a'$ par antisymétrie (pour l'ordre bien fondé, cette démonstration se
transforme en simple raisonnement par l'absurde).

##### Exemples
- $min(\mathbb{N}) = 0$, et $\mathbb{Z}$ et $\mathbb{R}$ n'ont pas de plus petit
  élément
- $\mathbb{N}, \mathbb{Z}, \mathbb{R}$ n'ont pas de plus grand élément
- Soit $I = ]0, 1]$ un intervalle réel, $max(I) = 1$
  et $I$ n'a pan de plus petit élément (car $0 \not\in I$ ).

Soit dans $\mathcal{P}(E)$ avec l'inclusion $\subset$ :
- On a $\emptyset \in \mathcal{P}(E)$ et $\forall A \in \mathcal{P}(E)$,
  $\emptyset \subset A$ donc $\emptyset = min(\mathcal{P}(E))$.
- On a $E \in \mathcal{P}(E)$ et $\forall A \in \mathcal{P}(E)$,
  $A \subset E$ donc $E = max(\mathcal{P}(E))$.

Dans $\mathbb{N}$ muni de la divisibilité :
- $\forall n \in \mathbb{N}$, $1 \mid n$ car $n = 1 \times n$, donc
  $1 = min_\text{div}(\mathbb{N})$.
- $\forall n \in \mathbb{N}$, $n \mid 0$ car $0 = 0 \times n$, donc
  $0 = max_\text{div}(\mathbb{N})$.
- Dans $\mathbb{N}^{\ast}$ muni de la divisibilité, il n'y a pas de plus grand
  élément.

### Minorants et majorants
> Soit $(E, \preceq)$ un ensemble ordonné, $A \subset E$ une partie de $E$.
> - l'élément $m \in E$ vérifiant $\forall x \in A, m \preceq x$ est appelé minorant de $A$
> - l'élément $M \in E$ vérifiant $\forall x \in A, x \preceq M$ est appelé majorant de $A$

- L'intervalle $I = [2,  + \infty[$ possède notamment 0, 1 et 2 pour minorants.
  L'ensemble de tous les minorants à $I$ est $]-\infty, 2]$

Le minimum d'un ensemble le minore, et le maximum d'un ensemble le
majore. Si $m \in A$ et que $m$ est un minorant de $A$, alors m est le plus
petit élément de $A$, donc $m = min(A)$.

> $(E, \preceq)$ un ensemble ordonné et $A \subset E$, A est dite bornée s'il
> existe au moins un majorant de A et un minorant de A :
> $\exists m \in E, \exists M \in E \mid \forall x \in A, m \preceq x \land x \preceq M$.

On dit de même que $A$ est minorée si elle possède au moins un minorant :
$\exists m \in E, \forall x \in A, m \preceq x$; et on dit que $A$ est majorée
si elle possède au moins un majorant :
$\exists M \in E, \forall x \in A, x \preceq M$.

On peut à l'inverse noter que $A$ n'est pas majorée par
$\forall M \in E, \exists a \in A, a \succeq M$ (et inversement pour montrer que
$A$ n'est pas majoré).

##### Exemple
Dans $(\mathbb{N}, \mid)$ (divisibilité), on prend $A = \{12,18\}$.
On a ainsi 1, 2, 3, 6 des minorants de A et 36, 72 des majorants, et le plus
grand des minorants est $6 = pgcd(12,18)$ et le plus petit des majorants $36 = ppcm(12,18)$.

### Borne supérieure et borne inférieure d'un ensemble
> Soit $(E, \preceq)$ un ensemble ordonné et $A \subset E$ :
> - Si A possède des majorants et si l'ensemble de tous les majorants de A possède
>   un plus petit élément, cet élément est appelé *la* borne supérieure de A et on
>   le note $sup(A)$.
> - Si A possède des minorants et si l'ensemble de tous les majorants de A possède
>   un plus petit élément, cet élément est appelé *la* borne inférieure de A et on
>   le note $inf(A)$.

Pour $I = ]0,1[$ avec $(\mathbb{R}, \leq)$, les majorants de $I$ sont $[1,  +\infty[$
et donc $sup(I) = 1$. De même, ses minorants sont $]-\infty, 0]$, et donc
$inf(I) = 0$.

## Ordre sur les réels
### Ensemble totalement ordonné $(\mathbb{R}, \leq)$
À partir de l'ordre $\leq$ dans $\mathbb{R}$, on a les implications $\forall (a,b,c) \in \mathbb{R}$ :
- $a \leq b \Rightarrow a + c \leq b + c$
- $(a \leq b \land c \geq 0) \Rightarrow ac \leq bc$

On en déduit les propositions suivantes :
1. $(a \leq b \land c \leq d) \Rightarrow (a + c \leq b + d)$
2. $(0 \leq a \leq b) \land (0 \leq c \leq d) \Rightarrow (0 \leq ac \leq bd)$
3. $(a \leq b \land c \leq 0) \Rightarrow (ac \geq bc)$

##### Preuves
1. $\left\{\begin{matrix} a \leq b \Rightarrow a + c \leq b + c \\ c \leq d \Rightarrow b + c \leq b + d \end{matrix}\right. \Rightarrow a + c \leq b + d$
2. $\left\{\begin{matrix} 0 \leq a \leq b \\ 0 \leq c \end{matrix}\right. \Rightarrow 0 \leq ac \leq bc$\
  $\left\{\begin{matrix} 0 \leq c \leq d \\ 0 \leq b \end{matrix}\right. \Rightarrow 0 \leq bc \leq ad$\
  et par transitivité $0 \leq ac \leq bd$.
3. $c \leq 0 \Rightarrow c + (-c) \leq -c \Rightarrow 0 \leq -c$, or
  $a \leq b \Rightarrow (-c) \times a \leq (-c) \times b$, donc
  $-ac \leq -bc$, donc $-ac + ac \leq -bc + ac \Rightarrow 0 \leq -bc + ac$
  donc $bc \leq -bc + bc + ac$ donc $bc \leq ac$.

#### Majoration et minoration d'inégalité
Si on souhaite majorer $a-c$, il faut trouver un majorant de a et un minorant de
c.
En effet, si $a \leq M$ et si $c \geq m$, alors $-c \leq -m$, donc
$a-c \leq M-m$.

Pour majorer $\frac{a}{c}$, avec $a \geq 0$ et $c > 0$, il faut trouver un
majorant de $a$ et un minorant de $c$.
Si $0 \leq a \leq M$ et si $0 < m \leq c$, alors $0 < \frac{1}{c} \leq \frac{1}{m}$,
donc $0 \leq a \times \frac{1}{c} \leq M \times \frac{1}{m}$, soit
$0 < \frac{a}{c} \leq \frac{M}{m}$.

### Propriétés des réels
#### Existence du plus grand ou plus petit élément
Toute partie non vide de $\mathbb{N}$ possède un plus petit élément :
$A \subset \mathbb{N} \land A \neq \emptyset, \exists n_0 = min(A)$.

Toute partie non vide de $\mathbb{N}$ majorée possède un plus grand élément :
si $A \subset \mathbb{N} \land A \neq \emptyset, \exists N = max(A)$.

Sur $\mathbb{Z}$, toute partie non vide minorée admet un plus petit élément, et
toute partie non vide majorée admet un plus grand élément.

> Dans $\mathbb{R}$ on a le théorème de la borne supérieure :
> - Toute partie non vide majorée de $\mathbb{R}$ possède une borne supérieure.
> - toute partie non vide minorée de $\mathbb{R}$ possède une borne inférieure.

Soit $\sigma = sup(A)$ où A est une partie non vide majorée de $\mathbb{R}$
(tout pareil pour la minoration etc.) :
- $\sigma$ est un majorant de A
- $\sigma$ est le meilleur (le plus petit) majorant de A : on a ainsi
  $\forall x \in A, x \leq \sigma$ et $\forall M \in \mathbb{R}, (\forall x \in A, x \leq M) \Rightarrow \sigma \leq M$.

##### Exemple
$A = \{r \in \mathbb{Q} \mid r^2 < 2\}$. A est une partie non vide de $\mathbb{Q}$, majorée (par 100),
mais A n'a pas de borne supérieure dans $\mathbb{Q}$ : en effet, $A \subset ]-\infty,\sqrt{2}[$
(car $A = \mathbb{Q} \cap ]-\infty,\sqrt{2}[$). Les majorants de $A$ sont
$[\sqrt{2}, +\infty[ \cap \mathbb{Q}$ (qui ne possède pas de plus petit
élément).

##### Exemple
Soit la suite $u_{n} = \frac{1}{n + 1}$, pour $n \in \mathbb{N}$.
On définit $sup(u) = {sup}_{n \in \mathbb{N}} u_{n} = sup(\{u_{n}, n \in \mathbb{N}\})$
et $inf(u) = {inf}_{n \in \mathbb{N}} u_{n} = inf(\{u_{n}, n \in \mathbb{N}\})$.
$sup(u)$ et $inf(u)$ sont bien définis car $A = \{\frac{1}{n + 1}, n \in \mathbb{N}\}$
est une partie non vide de $\mathbb{R}$ bornée ( $A \subset [0,1]$ ).
Ainsi, par propriété des bornes supérieures et inférieures, ces bornes existent.

De plus, $u_0 = 1 \in A$ et $1$ est un majorant de $A$, donc $1$ est le plus
grand élément de $A$, soit $1 = max(A) = sup(A)$.

Pour la borne inférieure, $\forall n \in \mathbb{N}$, $0 < u_{n}$, donc $0$ est
un minorant de A, or $inf(A)$ est le plus grand des minorants donc $inf(A) \geq 0$.
De plus, $inf(A)$ est un minorant de $A$, $\forall n \in \mathbb{N}, inf(A) \leq \frac{1}{n + 1}$.
En passant à la limite quand $n \to  + \infty$, on a $inf(A) \leq 0$.
Avec ces deux résultats, on a $inf(A) = 0$.

#### Caractérisation des bornes
On peut poser pour "b est le plus petit majorant de A"
$\forall \varepsilon > 0, (b - \varepsilon) \text{ n'est pas un majorant de A}$\
$\Leftrightarrow \forall \varepsilon > 0, \neg (\forall a \in A, a \leq b - \varepsilon)$\
$\Leftrightarrow \forall \varepsilon > 0, \exists a \in A, b - \varepsilon < a$

Soit $A \subset \mathbb{R}$ non vide majoré $b = sup(A)$ si et seulement si b est un majorant de A et b est le plus petit
des majorants de A, soit $\left\{\begin{matrix} \forall x \in A, x \leq b \\ \forall \varepsilon > 0, \exists x \in A, b - \varepsilon < a \end{matrix}\right.$,
ce qui est équivalent à $\left\{\begin{matrix} \forall x \in A, x \leq b \\ \text{il existe une suite }(a_n)_n \text{ qui converge vers b} \end{matrix}\right.$.

### Droite numérique achevée
On pose $\overline{\mathbb{R}} = \mathbb{R} \cup \{+\infty; -\infty\}$.
On prolonge l'ordre à $\overline{\mathbb{R}}$ :
$\forall x \in \mathbb{R}, \left\{\begin{matrix} x \leq +\infty \\ -\infty \leq x \end{matrix}\right.$
et $-\infty \leq +\infty$.
Ainsi, dans $\overline{\mathbb{R}}$, $+\infty = sup(\mathbb{R})$ et $-\infty = inf(\mathbb{R})$.

Addition dans $\overline{R}$ (prolongement) :

$+$                | $-\infty$ | $y \in \mathbb{R}$ | $+\infty$
---                | ---       | ---                | ---
$-\infty$          | $-\infty$ | $-\infty$          | Undefined
$x \in \mathbb{R}$ | $-\infty$ | $x + y$            | $+\infty$
$-\infty$          | Undefined | $+\infty$          | $+\infty$

Ces formes indéterminées doivent être évitées dans les équations pour obtenir un
résultat. On dit donc que $\overline{\mathbb{R}}$ est muni d'une addition partielle (car
indéfinie entre $-\infty$ et $+\infty$).

$\times$ | $-\infty$ | $x \in \mathbb{R}^{\ast}_{-}$ | $0$ | $x \in \mathbb{R}^{\ast}_{+}$ | $+\infty$
---|---|---|---|---|---
$-\infty$ | $+\infty$ | $+\infty$ | Undefined | $-\infty$ | $-\infty$
$y \in \mathbb{R}^{\ast}_{-}$ | $+\infty$ | $xy$ | 0 | $xy$ | $-\infty$
$0$ | Undefined | $0$ | $0$ | $0$ | Undefined
$y \in \mathbb{R}^{\ast}_{+}$ | $-\infty$ | $xy$ | 0 | $xy$ | $+\infty$
$+\infty$ | $-\infty$ | $-\infty$ | Undefined | $+\infty$ | $+\infty$

On rencontre une forme indéterminée avec $0 \times \pm\infty$. On dit que $\overline{\mathbb{R}}$ est muni
d'une multiplication partielle.

Toute partie non vide de $\mathbb{R}$ possède toujours un $inf$ et un $sup$ dans
$\overline{\mathbb{R}}$.
Plus en détail, soit $A \subset \mathbb{R}$ non vide :
- Si $A$ est majorée, alors $sup(A) \in \mathbb{R}$
- Si $A$ n'est pas majorée, alors $sup(A) = + \infty$
- Si $A$ est minorée, alors $inf(A) \in \mathbb{R}$
- Si $A$ n'est pas minorée, alors $inf(A) = - \infty$

De plus, on étend ces remarques :
- Si $u \in \mathbb{R}^{\mathbb{N}}$ une suite réelle, on note
  $\left\{\begin{matrix} sup(u) = sup(\{u_{n}, n \in \mathbb{N}\}) \in \overline{\mathbb{R}} \\ inf(u) = inf(\{u_{n}, n \in \mathbb{N}\}) \in \overline{\mathbb{R}} \end{matrix}\right.$
- Si $f: X \to \mathbb{R}$ une application à valeurs réelles, on note
  $\left\{\begin{matrix} sup(f) = sup(f(X)) = sup\{(f(x), x \in X\}) \\ inf(f) = inf(f(X)) = inf(\{f(x), x \in X\}) \end{matrix}\right.$.
  Tous sont dans $\overline{\mathbb{R}}$.

##### Exemple
Soient $f: E \to \mathbb{R}$ et $g: e \to \mathbb{R}$ telles que $f \leq g$
( $\forall x \in E, f(x) \leq g(x)$ ). Montrer que
$\left\{\begin{matrix} sup f \leq sup g \\ inf f \leq inf g \end{matrix}\right.$
où ces quantités sont dans $\overline{\mathbb{R}}$.

Par définition de $sup g$, c'est un majorant de $\{g(x), x \in E\}$.
Donc $\forall x \in E, g(x) \leq sup g$, soit $\forall x \in E, f(x) \leq g(x) \leq sup g$.
Ici, $sup g$ est un majorant de $\{f(x), x \in E\} = A$, or $sup f$
est le plus petit majorant de A, donc $sup f \leq sup g$

##### Exercice
Soient $A,B$ deux parties non vides de $\mathbb{R}$ telles que $\forall a \in A, \forall b \in B, a \leq b$.
Montrer que $sup A \in \mathbb{R}$; que $inf B \in \mathbb{R}$; et que $sup A \leq inf B$.
Prenons $b_0 \in B$, on a bien $\forall a \in A, a \leq b_0$, donc $A$ est
majorée ($b_0$ en est un majorant).
Par propriété de la borne supérieure, $sup A$ existe dans $\mathbb{R}$.
De plus, $sup A$ étant le plus petit majorant de $A$, on a $sup A \leq b_0$.
On en conclut donc que $\forall b \in B, sup(A) \leq b$. Ainsi, $sup(A)$ est nu
minorant de $B$, donc $sup(A) \leq inf(B)$, or $sup(A) \in \mathbb{R}$, donc
$inf(B) \neq -\infty$.

Attention, les inégalités restent larges après application du $sup$ ou $inf$;
soit $A = ]0,1[$ et $B = ]1,2[$, $\forall a \in A, \forall b \in B, a < 1 < b$
et $sup A = 1 = inf B$.

##### Exercice
Soit $A \subset \mathbb{R}$ non vide et $x \in \mathbb{R}$, on définit la
distance du réel x à l'ensemble A par
$d(x, A) = inf(\{|x-a|, a \in A\})$.
Montrer que $\forall (x,y) \in \mathbb{R}^2, |d(x,A) - d(y,A)| \leq |x-y|$.

Pour $a \in A$, on a $|x-a| = |x - y + y - a| \leq |x - y| + |y - a|$ (par
inégalité triangulaire). Or, $d(x,A) \leq |x-a|$ et $d(y, A) \leq |y-a|$,
donc $d(x,A) \leq |x-a| \leq |x-y| + |y-a|$.
De plus, $|y-a| \geq d(x,A) - |x-y|$ (ce qui est donc son minorant, fixe, de
l'ensemble $\{|y-a|, a \in A\}$), donc (puisque $inf$ est le plus grand des
minorants) $d(y,A) \geq d(x,A) - |x-y|$, c'est-à-dire $d(x,A) - d(y,A) \leq |x-y|$.
En échangeant les rôles de $x$ et de $y$, on a aussi
$d(y,A) - d(x,A) \leq |y-x| = |x-y|$. On en conclut que
$|d(x,A) - d(y,A)| \leq |x-y|$.

### Partie entière
> L'ensemble $\mathbb{R}$ est archimédien : $\forall (x,y) \in \mathbb{R}^2$ tels que
> $0 < x < y$, $\exists n \in \mathbb{N}, nx \geq y$.

##### Preuve
Soit $0 < x < y$. On procède par l'absurde, et on suppose que
$\forall n \in \mathbb{N}, nx < y$. On a alors $A = \{nx, n \in \mathbb{N}\}$
une partie non vide et majorée de $A$ (majorée par $y$).
On note ainsi $a = sup(A)$ (qui existe par propriétés de $\mathbb{R}$),
et donc $\forall n \in \mathbb{N},nx \leq a$. Avec $n + 1$,
on a $(n + 1)x \leq a$, donc $xn \leq a - x$, ce qui est une contradiction
de la minimalité de $a$.

De plus, on peut noter que si $nx \leq a$, alors on a $n \leq \frac{a}{x}$, donc
$\mathbb{N}$ est borné, ce qui est une contradiction.

#### Propriété
> Pour tout réel $x \in \mathbb{R}$, il existe un unique entier $n \in \mathbb{Z}$
> tel que $n \leq x < n + 1$.
> Cet entier $n$ est alors appelé partie entière de $x$, et on note
> $\left\lfloor x \right\rfloor = n$.

##### Exemple
- $\forall x \in \mathbb{Z}, \left\lfloor x \right\rfloor = x$
- $\left\lfloor \pi \right\rfloor = 3$ et $\left\lfloor -\pi \right\rfloor = 4$
  car $-4 \leq -\pi < -3$.

##### Preuve
- Unicité : Si $n_1,n_2 \in \mathbb{Z} | \left\{\begin{matrix} n_1 \leq x < n_1 + 1 \\ n_2 \leq x < n_2 + 1 \end{matrix}\right.$,
  on a $\left\{\begin{matrix} x - 1 < n_1 \leq x \\ x - 1 < n_2 \leq x \end{matrix}\right.$
  donc $\left\{\begin{matrix} x - 1 < n_1 \leq x \\ -x \leq -n_2 < -x + 1 \end{matrix}\right.$.
  En sommant, on obtient $-1 < n_1 - n_2 < 1$, et donc $n_1 - n_2 \in (\mathbb{Z} \cap ]-1,1[) = \{0\}$,
  donc $n_1 - n_2 = 0 \Leftrightarrow n_1 = n_2$.
- Existence : On pose $A = \{k \in \mathbb{Z} \mid k \leq x\}$. $A$ est une
  partie de $\mathbb{Z}$, non vide et majorée (par x), donc elle admet un plus
  grand élément $n = max(A)$. $n \in A$, donc $n \leq x$. De plus, $n + 1 \not\in A$
  (car $n = max(A)$, des éléments plus grands que lui dans $\mathbb{Z}$ sont
  donc hors de $A$) et donc $n + 1 > x$ (donc n convient).

On peut prouver que $A \neq \emptyset$, car sinon $\forall k \in \mathbb{Z}, k > x$
donc $\mathbb{Z}$ serait minoré, ce qui est absurde.
De plus, $A$ est majorée car :
- si $x \leq 1$, $A$ est majorée par 12
- si $x > 1$, comme $\mathbb{R}$ est archimédienne, $\exists k \in \mathbb{N},
  k \times 1 \geq x$

#### Propriétés de la partie entière
1. $\begin{aligned} \left\lfloor  \right\rfloor: \mathbb{R} &\to \mathbb{R} \\ x &\mapsto \left\lfloor x \right\rfloor .\end{aligned}$ est croissante (bien que pas strictement).
  La fonction est discontinue en chaque point entier ( $\mathbb{Z}$ ),
  puisque pour tout $n \in \mathbb{Z}$, pour tout $x \in [n,n + 1[$,
  $\left\lfloor x \right\rfloor = n$. Comme la fonction est discontinue, elle
  n'est pas dérivable sur tout son domaine de définition (bien qu'on puisse la
  dériver sur ses intervalles continus, où la dérivé est nulle).
2. $\forall x \in Rr, \forall p \in \mathbb{Z} \left\lfloor x + p \right\rfloor = \left\lfloor x \right\rfloor + p$

##### Preuves
1. On a la continuité de la partie entière à droite en tout point puisque
  $\lim\limits_{x \to n < x} \left\lfloor x \right\rfloor = n = \left\lfloor n \right\rfloor$,
  car $\forall x \in ]n,n + 1[, \left\lfloor x \right\rfloor = n$.
  On obtient la discontinuité de la partie entière à gauche en tout point entier
  car $\lim\limits_{x \to n > x} = n - 1 \neq \left\lfloor n \right\rfloor$,
  car $\forall x \in ]n-1, n[, \left\lfloor x \right\rfloor = n- 1$.\
  \
  On peut montrer que $x \mapsto \left\lfloor x \right\rfloor$ est croissante sur
  $\mathbb{R}$. Soit $(x,y) \in \mathbb{R}^2 \mid x \leq y$, alors
  $\left\lfloor x \right\rfloor \leq x < \left\lfloor x \right\rfloor + 1$,
  et $\left\lfloor y \right\rfloor \leq y < \left\lfloor y \right\rfloor + 1$, et
  on a donc $\left\lfloor x \right\rfloor \leq x \leq y$, donc $\left\lfloor x \right\rfloor \leq y < \left\lfloor y \right\rfloor + 1$.
  Donc $\left\lfloor x \right\rfloor < \left\lfloor y \right\rfloor + 1$
  (donc ce sont deux entiers distincts), et donc
  $\left\lfloor x \right\rfloor + 1 \leq \left\lfloor y \right\rfloor + 1$, soit
  $\left\lfloor x \right\rfloor \leq \left\lfloor y \right\rfloor$.
2. On sait que $\left\lfloor x \right\rfloor \leq x < \left\lfloor x \right\rfloor + 1$,
  donc $\left\lfloor x \right\rfloor + p \leq x + p < \left\lfloor x \right\rfloor + p + 1$.
  On note $N$ la valeur de gauche et $N + 1$ celle de droite,
  et on a par définition $N, N + 1 \in \mathbb{Z}$.
  Donc par définition de la partie entière,
  $\left\lfloor x + p \right\rfloor = N = \left\lfloor x \right\rfloor + p$.

#### Partie décimale
> On note la partie décimale d'un réel $x$ par $\{x\} = x - \left\lfloor x \right\rfloor$,
> et on a pour tout $x \in \mathbb{R}, \{x\} \in [0,1[$.

On a de plus $\forall p \in \mathbb{Z}, \{x + p\} = (x + p) - \left\lfloor x + p \right\rfloor$
$= x + p - \left\lfloor x \right\rfloor - p = x - \left\lfloor x \right\rfloor = \{x\}$.

##### Exercice : Nombre de chiffres pour écrire dans une base
Soit $n \in \mathbb{N}^{\ast}$, combien de chiffres sont requis pour écrire n ?
On note $\varphi(n)$ le nombre de chiffres dans $\{0,\ldots,9\}$ pour écrire n.

On suppose que $\varphi(n) = k$, c'est-à-dire n possède k chiffres.
On a alors $10\ldots\text{(k -1)}0 \leq n \leq 9\ldots\text{(k)}9 < 10\ldots\text{(k)}0$.
On a donc $10^{k-1} \leq n < 10^k$, soit $k-1 \leq \log_{10}(n) < k$, donc $k-1 = \left\lfloor \log_{10}(n) \right\rfloor$.
Ainsi, $\varphi(n) = 1 + \left\lfloor \log_{10}(n) \right\rfloor$.

De façon plus générale, en base b, on a $b^{k-1} \leq n < b^k$, soit
$k-1 \leq \log_b < k$, et donc $\varphi_b(n) = \left\lfloor \log_b(n) \right\rfloor + 1$.

#### Valeur approchée
> Soit $a \in \mathbb{R}$ et $\varepsilon \in \mathbb{R}^{\ast}_{+}$, on appelle
> valeur approchée du réel a à $\varepsilon$ près tout réel x qui vérifie :
> $|x-a| \leq \varepsilon$.

Pour approximer des réels par des décimaux, donc soit $n \in \mathbb{N}, x \in \mathbb{R}$,
on pose $d_n = \frac{\left\lfloor 10^n \times x \right\rfloor}{10^n} \in \mathbb{D}$,
où $\mathbb{D} = \{\frac{m}{10^k} \mid m \in \mathbb{Z}, k \in \mathbb{N}\}$.

Par définition de $\left\lfloor  \right\rfloor$, $\left\lfloor 10^n x \right\rfloor \leq 10^n \times x < \left\lfloor 10^n x \right\rfloor + 1$,
donc $d_n \leq x < d_n + \frac{1}{10^n}$ (encadrement de x par une valeur
approchée de x par défaut à $10^{-n}$ près et par une valeur approchée de x par
excès à $10^{-n}$ près).

On remarque que $(d_n)_{n \in \mathbb{N}}$ est une suite de décimaux et
$\forall n \in \mathbb{N}, x - \frac{1}{10^n} < d_n \leq x$. Par théorème des
gendarmes, $(d_n)_{n \in \mathbb{N}}$ converge et $\lim\limits_{n \to \infty} d_n = x$.

### Densité des parties denses dans l'ensemble des réels
> Soit $A \subset \mathbb{R}$, on dit que la partie A est dense dans $\mathbb{R}$
> si l'une des deux assertions équivalentes suivantes est vérifiée.
> - Entre deux réels quelconques, on peut toujours trouver un élément dans A.
> - $\forall x \in \mathbb{R}, \forall \varepsilon > 0, \exists a \in A, |x-a| \leq \varepsilon$

Ces deux assertions sont bien équivalentes :
- En effet ( $\Rightarrow$ ), en fixant $x \in \mathbb{R}$ et $\varepsilon > 0$,
  avec les deux réel $(x - \varepsilon)$ et $(x + \varepsilon)$, la première
  assertion donne l'existence de $a \in A \mid x - \varepsilon \leq a \leq x + \varepsilon$,
  donc $|a - x| \leq \varepsilon$.
- De plus ( $\Leftarrow$ ), soient $x < y$ deux réels, on a la moitié de leur
  distance $d = \frac{y - x}{2}$. On applique la seconde assertion avec
  $\frac{x + y}{2} \in \mathbb{R}$ et $\frac{y - x}{2} > 0$.
  $\exists a \in A, |\frac{x + y}{2} - a| \leq \frac{y - x}{2}$, donc
  $\frac{x + y}{2} - (\frac{y - x}{2}) \leq a \leq \frac{x + y}{2} + (\frac{y - x}{2})$,
  donc $x \leq a \leq y$.

Ainsi, si A est dense dans $\mathbb{R}$, alors tout réel est la limite d'une
suite convergente de $A^{\mathbb{N}}$. En effet, si $A$ est dense dans $\mathbb{R}$,
on fixe $x \in \mathbb{R}$. Par la seconde assertion de la définition de la
densité, $\forall \varepsilon > 0, \exists a \in A, |x-a| \leq \varepsilon$.
Pour chaque entier $n \in \mathbb{N}^{\ast}$, on applique cette propriété avec
$\varepsilon_n = \frac{1}{n} > 0$, ce qui donne
$\exists a_n \in A, |x-a| \leq \frac{1}{n}$. On en conclut que
$\forall n \in \mathbb{N}^{\ast}, a_n \in A, |x - a_n| \leq \frac{1}{n}$. Par
encadrement, $\lim\limits_{n \to + \infty} (x - a_n) = 0$, la suite
$(a_n)_{n} \in A^{\mathbb{N}}$ converge vers x.

À partir de ces propriétés :
- $\mathbb{D}$ est dense dans $\mathbb{R}$
- $\mathbb{Q}$ est dense $\mathbb{R}$
- $\mathbb{R} \setminus \mathbb{Q}$ est dense dans $\mathbb{R}$

##### Preuves
- Pour tout $x \in \mathbb{R}$ et $\varepsilon > 0$, on pose
  $d_n = \frac{\left\lfloor 10^n x \right\rfloor}{10^n} \in \mathbb{D}$ tel
  que $|d_n - x| \leq 10^{-n}$. Il faut alors choisir n tel que
  $10^{-n} < \varepsilon$ :
  - Si $\varepsilon \geq 1$, on prend $n = 0$
  - Sinon $\varepsilon \in ]0,1[, 10^{-n} < \varepsilon \Leftrightarrow -n < \log_{10}(\varepsilon)$
    $\Leftrightarrow n > -\log_{10}(\varepsilon)$.
  Prenons par exemple $n_0 = \left\lfloor -\log_{10}(\varepsilon) \right\rfloor + 1$,
  on a donc $|d_{n_0} - x| \leq 10^{-n_0} < \varepsilon$, donc
  $\mathbb{D}$ est dense dans $\mathbb{R}$.
- $\mathbb{D} \subset \mathbb{Q}$, donc $\mathbb{Q}$ est aussi dense dans
  $\mathbb{R}$
- Soient $x < y$ deux réels quelconques. On applique la densité de $\mathbb{Q}$
  dans $\mathbb{R}$ avec les réels $x-\sqrt{2}$ et $y-\sqrt{2}$. Ainsi,
  $\exists a \in \mathbb{Q} \mid x-\sqrt{2} \leq a \leq y-\sqrt{2}$,
  et donc $x \leq a + \sqrt{2} \leq y$. Or $a + \sqrt{2} \in \mathbb{R} \setminus \mathbb{Q}$,
  et est donc bien un irrationnel (car $\sqrt{2} = a + \sqrt{2} - 2$,
  preuve par l'absurde par la stabilité par l'addition des rationnels).

#### Infinité dénombrable des parties denses
Entre deux réels distincts $x < y$, il y a
- une infinité de rationnels
- une infinité d'irrationnels

Si $x < a_1 < y$, alors $x < a_2 < a_1$ ou même $x < a_{n + 1} < a_n$.
On a l'ensemble $\mathbb{Q} = \{\frac{p}{q}, p \in \mathbb{Z}, q \in \mathbb{N}^{\ast}\}$.
Or il existe une bijection de $\mathbb{N} \to \mathbb{Z}$
(la fonction $\begin{aligned} \mathbb{N} &\to \mathbb{Z} \\ n &\mapsto \left\{\begin{matrix} n / 2 \text{ si n pair} \\ -(\frac{n + 1}{2}) \text{ si n impair} \end{matrix}\right. .\end{aligned}$),
et puisque $\mathbb{N}$ a une bijection dans $\mathbb{N} \times \mathbb{N}$, on
a bien une bijection de $\mathbb{N} \to \mathbb{Q}$, donc les éléments de
$\mathbb{Q}$ sont dénombrables.
