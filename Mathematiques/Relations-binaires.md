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
- $\mathcal{R}$ est réfléxive si $\forall x \in E, x \mathcal{R} x$
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
chaque $\dot{k} = \{\p \in \mathbb{Z} \mid p \equiv k[n]\} = \{k + nj, j \in \mathbb{Z}\} = k + n\mathbb{Z}$.
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
On définit $sup(u) = {sup}\limits_{n \in \mathbb{N}} u_{n} = sup(\{u_{n}, n \in \mathbb{N}\})$
et $inf(u) = {inf}\limits_{n \in \mathbb{N}} u_{n} = inf(\{u_{n}, n \in \mathbb{N}\})$.
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
résultat.
