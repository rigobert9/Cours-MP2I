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
