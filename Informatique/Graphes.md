# Graphes
## Graphes orientés
> Un graphe orienté est la donnée d'une ensemble $S$ et d'un ensemble $A \subset S \times S$.
> Si $G = (S,A)$, on dit que $S$ est l'ensemble des sommets de $G$ et $A$ est
> l'ensemble de ses arcs.

> Soit $a \in S$, $\{v \in S \mid (u,v) \in A\}$ est l'ensemble des successeur de
> $u$. Le cardinal de cet ensemble est le degré sortant de $u$.
> $\{v \in S \mid (v,u) \in A\}$ est l'ensemble des prédécesseurs de $u$. Le
> cardinal de cet ensemble est le degré entrant de $u$.

Si $(u,v) \in A$, on notera $u \to v$.

> Soient $u,v \in S$, le chemin de $u$ à $v$ dans $G = (S,A)$ est un tuple
> d'éléments de $S$ tel que $u = s_0 \to s_1 \to \ldots \to s_n = v$.
> Le nombre d'arcs $k$ est la longueur du chemin.

S'il existe un chemin de $u$ à $v$, on note $u \to^{\ast} v$

> Un chemin simple est un chemin ne passant jamais deux fois par le même arc.

> Soit $G = (S,A)$ un graphe orienté, et $u,v \in S$. S'il existe $u \to^{\ast} v$,
> il existe un chemin simple de $u$ à $v$.

__Preuve :__ Soit $u \to^{\ast} v$ un chemin de $u$ à $v$ de longueur minimale $k$.
On suppose par l'absurde que ce chemin n'est pas simple. Il existe alors
$i$ et $j$, tels que $0 \leq i< j < k$ et que $s_i = s_j$, $s_{i+1} = s_{j+1}$.
La longueur d'un chemin qui suit le même déroulé jusqu'à $s_i$, puis s'identifie
sur les étapes à partir de $s_j$, sera de longueur $i + 1 + k - (j + 1) = k + (i - j) < k$,
contredisant la minimalité de la longueur du chemin. Tout chemin de longueur
minimale est donc simple.

> On appelle cycle un chemin de longueur non nulle d'un somme à lui-même.

Ce chemin doit être non nul, car il existe toujours un "chemin" de longueur
nulle d'un nœud à lui-même.

> Un graphe orienté qui ne contient pas de cycle est appelé DAG (Direct Acyclic
> Graph).

> Soit $G = (S,A)$ un DAG, alors $\to^{\ast}$ est une relation d'ordre sur $S$.

__Preuve :__ On a bien la réflexivité en utilisant les chemins de longueur
nulle. La transitivité s'obtient en concaténant des chemins, et l'antisymétrie
peut s'obtenir par l'absurde en posant un chemin non nul d'un point à l'autre,
construisant un cycle.

> Soit $G = (S,A)$ un graphe orienté $S' \subset S$, on appelle sous-graphe induit
> par $S'$ de $G$ le graphe $(S', A \cap S' \times S')$.

> Soit $G = (S,A)$ un graphe orienté, on dit que $G$ est fortement connexe
> si $\forall u,v \in S$, $u \to^{\ast}$ et $v \to^{*} u$.

On appelle composante fortement connexe de $G$ une partie $C \subset S$ maximale
pour l'inclusion, telle que le sous-graphe induit par $C$ dans $G$ est fortement
connexe et telle que $\forall C'$ tel que $C \not\subset C' \subset S$, le
sous-graphe induit par $C'$ de $G$ n'est pas fortement connexe.

> Soit $G = (S,A)$ avec $S$ fini un graphe orienté, alors les composantes fortement
> connexes de $G$ forment une partition de $S$.

__Preuve :__ Soit $u \in S$. Le sous-graphe induit par $\{u\}$ dans $G$ est
fortement connexe car réduit à son seul sommet. Ainsi, $\{S' \subset S \mid \text{ Le sous graphe induit par } S' \text{ de } G \text{ est fortement connexe}\}$
est non vide et $u \in S'$.
Cet ensemble de $\mathcal{P}(S)$ est non vide et fini, et admet donc un élément
maximal pour l'inclusion. Il est aussi maximal dans $\{S' \subset S \mid \text{ Le sous-graphe induit par } S' \text{ de } G \text{ est fortement connexe.}\}$,
car tout sur-ensemble de $S'$ contient toujours $u$, donc cet ensemble maximal
est une composante fortement connexe qui contient $u$.\
On suppose par l'absurde qu'il existe $C_1,C_2$ des composantes fortement
connexes telles que $C_1 \neq C_2 \land C_1 \cap C_2 \neq \emptyset$. On peut
alors supposer $\exists u \in C_1 \setminus C_2$, et $v \in C_1 \cap C_2$.
Soit $S' = C_2 \cup C_1$, le sous-graphe induit par $S'$ de $G$ est fortement
connexe, contredisant la minimalité de $C_2$ par inclusion.\
En effet, soient $s_1,s_2 \in S'$, si $s_1,s_2 \in C_1$
ou $s_1,s_2 \in C_2$. Par hypothèse, $s_1 \to^{\ast} s_2$ et $s_2 \to^{\ast} s_1$
dans le sous-graphe induit par $C_1 \cup C_2$.
Sinon, $s_1 \in C_1$, $s_2 \in C_2$, alors $s_i \to^{\ast} v$
et $v \to^{\ast} s_i$ dans le sous-graphe induit par $C_1 \cup C_2$,
de plus, $s_2 \to^{\ast} v$ et $v \to^{\ast} s_2$ dans le sous-graphe
induit pour $C_2$ est pour l'union. Ainsi, par transitivité,
$s_1 \to^{\ast} s_2$ et inversement, donc le sous-graphe induit par $S'$ est
fortement connexe.\
Ainsi, tout $u \in S$ appartient à une unique composante fortement connexe, et
donc ces composantes fortement connexes forment une partition de $S$.

> Soit $G = (S,A)$ un graphe orienté, $\sum\limits_{x \in S} d_{+}(x) = \sum\limits_{x \in S} d_{-}(x) = |A|$.

__Preuve :__ $\sum\limits_{x \in S} d_{+}(x) = \sum\limits_{x \in S} |\{(u,v) \in A \mid u = x\}|$
$= |\{(u,v) \in A \mid u = x\}| = |A|$.

## Graphes non orientés
> Un graphe non orienté est la donnée d'un ensemble de sommets $S$ et d'un
> ensemble d'arrêtes $E \subset \{e \in \mathcal{P}(S) \mid \text{Card}(e) = 2\}$.

> Un chemin de $x$ à $y$ est un tuple $(u_i)_{[\![0,n]\!]} \in S^{n+1}$ tel que
> $\forall i \in [\![0,n-1]\!], \{u_i, u_{i+1}\} \in E$, et $x = u_0$, $y = u_n$.
> On notera encore $x \to^{\ast} y$. De même $u \to v$ ou $v \to u$ signifient
> tous deux $\{u;v\} \in E$. Un chemin simple est un chemin où chaque arête
> apparaît au plus une fois.

Comme pour les graphes orientés, chaque sommet a un chemin de longueur $0$ vers
lui-même : $x = u_0 = x$.
En revanche, il n'existe aucune arête reliant un sommet à lui-même,
donc aucun chemin de $x$ à $x$ de longueur $1$.

> Un cycle est un chemin simple de longueur non nulle dont les deux extrémités sont le même sommet.

Il n'existe pas dans un graphe non orienté de cycle de longueur 1, ni de
longueur 2 (car il n'est alors pas simple). La longueur minimale d'un cycle dans
un graphe orienté est donc de 3.

> Soit $x \in S$, on définit son degré $d(x) = \text{Card}(\{e \in E \mid x \in e\})$.

> $\sum\limits_{x \in S} d(x) = 2 \text{Card}(E)$

__Preuve :__ Pour $S$ fini, on le munit d'un ordre total, donnant
$\sum\limits_{x \in S} d(x) = \sum\limits_{x \in S} \text{Card}(\{e \in E \mid x \in e\})$
$= \sum\limits_{x \in S} \text{Card}(\{e \in E \mid e = \{x;y\} \text{ avec } y < x\})$
$+ \text{Card}(\{e \in E \mid e = \{x;y\} \text{ avec } y > a\})$.
Or, si $x \neq x'$, alors $\{e \in E \mid e = \{x;y\} \text{ avec } y < x\}$
et $\{e \in E \mid e = \{x';y\} \text{ avec } y < x'\}$ sont disjoints.\
Ainsi, la somme des cardinaux est le cardinal de l'union,
c'est à dire $\text{Card}(E) + \text{Card}(E)$.

> Soit $G = (S,E)$ un graphe non orienté, on définit son graphe orienté
> sous-jacent $G = (S,A)$ par $A = \{(x;y) \in S^2 \mid \{x;y\} \in E\}$.

On en déduit une preuve beaucoup plus simple de la propriété précédente :
$\forall x \in S, d_G(x) = d_{G^{+}}(x) = d_{G^{-}}(x)$, donc la somme
est le cardinal de $A$ qui est deux fois plus grand que celui de $E$.

Si $G$ a au moins une arête, celle-ci correspond dans son graphe orienté
sous-jacent à deux arcs qui forment un cycle de longueur 2. Ainsi, même si
$G$ n'a pas de cycle, son graphe orienté sous-jacent en aura.

> $G = (S,E)$ est connexe si $\forall x,y \in S, x \to^{\ast} y$.

> $G$ est connexe si et seulement si son graphe orienté sous-jacent est fortement
> convexe.

Soit $G = (S,E)$, une composante connexe de $G$ est une partie $C$ de $S$ telle
que le sous-graphe de $G$ induit par $C$ est connexe, et $C$ est maximale pour
l'inclusion.

> Les composantes connexes de $G$ forment une partition de $S$.

> Un graphe non orienté acyclique est appelé forêt. Un graphe non orienté
> acyclique connexe est appelé arbre.

Rien à voir avec les arbres enracinés.

## Structure de données
Ici, tous les graphes sont finis. Les graphes non orientés vont être représentés
par leur graphe orienté sous-jacent. On notera $n = \text{Card}(S)$ et $m = \text{Card}(A)$.

On souhaite avoir les opérations élémentaires suivantes :
- Créer un graphe sans arêtes de sommets $S$ en $\Theta(n)$
- Supprimer un graphe on $O(n + m)$
- Ajouter un arc en $\Theta(1)$
- Supprimer un arc en $\Theta(1)$
- Vérifier si un arc existe en $\Theta(1)$
- Connaître $\text{Card}(S)$ en $\Theta(1)$
- Obtenir l'ensemble des successeurs de $x \in S$ en $\Theta(d_{+}(x))$
- Obtenir l'ensemble $A$ en $\Theta(n + m)$

En pratique, les deux implémentations les plus utilisées ne respectent pas
toutes ces complexités idéales. On choisira donc selon nos besoins.

### Matrice d'adjacence
$G$ est représenté par $M$ un tableau de $m$ tableaux de $n$, qui sont vrais si
il y a un arc et faux sinon.
Un graphe non orienté est donc représenté par une matrice symétrique.

### Liste d'adjacence
$G$ est représenté par un tableau de $m$ listes, de longueur $n$ maximum, qui
contiennent des pointeurs ou des identifiants vers les successeurs du noeud à
l'indice de la liste. La liste ne doit pas de contenir de doublon dans un graphe
simple, et n'a pas besoin d'être triée dans un certain ordre.

## Parcours de graphe
Ces parcours sont différents d'un parcours d'arbre, car la structure set moins
linéaire :
- on peut à priori visiter un sommet par plusieurs chemins depuis le sommet
  source
- on doit maintenir la mémoire des sommets déjà visités, sans quoi on les
  visiterait deux fois
- l'ordre entre les successeurs n'est en général pas pertinent

### Parcours en profondeur (Depth First Search)
Pour un graphe $G$, un sommet $s \in S$, ainsi qu'un tableau $V$ de booléens
initialisés à faux, on traverse l'arbre en profondeur à partir de $s$
en suivant l'algorithme :\
Si `V[s]` est faux, on le met à vrai, et on répète pour tous ses successeurs.
Dans tous les cas, on renvoie $V$ mis à jour.

Ce parcours visite uniquement les sommets accessibles depuis $s$.

__Preuve :__ On prouve que l'algorithme se termine. Chaque appel récursif est
dans une boucle qui est parcourue au plus $n$ fois. De plus, avant de rentrer
pour la première fois dans cette boucle, on a passé `v[s]` de faux à vrai,
opération qu'on ne réalise qu'une seule fois. Donc à chaque $s \in S$ correspond
au plus $n$ appels récursifs.\
Soit $G \in S$ :
- si $t$ est visité par l'algorithme, on considère la pile d'exécution quand il
  est visité. Comme chaque appel de DFS est soit l'appel initial, soit un appel
  récursif depuis un prédécesseur, en suivant la pile du fond au sommet on a un
  chemin de $s$ à $t$.
- réciproquement, on suppose $s \to^{\ast} t$. On montre par récurrence sur $n \geq 0$
  que tout sommet pour lequel il existe un chemin de longueur $n$ depuis $s$ est
  visité. En effet, $s$ est bien le seul sommet pour lequel il y ait un chemin de
  longueur $0$ vers lui-même, et si $n \geq 1$, on a bien le chemin qui est
  composé.

__Corollaire :__ Soit $G = (S,E)$ un graphe non orienté avec $S \neq \emptyset$,
$s \in S$, alors le parcours en profondeur de $G$ depuis $S$ visite la
composante connexe de $G$ qui contient $S$.

__Preuve :__ Soit $C$ cette composante connexe,
$t \in C \Leftrightarrow s \to^{\ast} t \land t \to^{\ast} s$\
$\Leftrightarrow s \to^{\ast} t$ (car $G$ est non orienté)\
$\Leftrightarrow t$ est visité par le DFS depuis $s$.

> L'arborescence d'un parcours en profondeur de $G$ à partir d'un sommet $s$ est
> l'arbre enraciné dont la racine est $s$ et pour lequel chaque nœud a pour
> enfants ses successeurs visités pour la première fois.

> Soit $G = (S,E)$ non-orienté et connexe, un arbre couvrant de $G$ est un arbre (au
> sens des graphes) dont les sommets sont $S$ et les arêtes un sous-ensemble de $E$
> (de cardinal $\text{Card}(S) - 1$).

> Un parcours en profondeur sur un graphe connexe non orienté donne un arbre
> couvrant du graphe en retirant l'orientation de l'arborescence.

### Parcours en largeur
On commence par une fiel qui ne contient que le sommet source, et tant qu'il
reste des sommets à traiter (donc que la file n'est pas vide), on en défile un :
s'il n'est pas visité, on continue avec la suite, sinon on le marque comme
visité et on ajoute ses successeurs au bout de la file.

> Soit $G = (S,A)$ un graphe orienté, et $s \in S$, alors $\forall t \in S$
> tel que $s \to^{\ast} t$, le parcours en largeur de $G$ depuis $s$ indique la
> distance de $s$ à $t$.

__Preuve :__ On montre d'abord que la BFS termine. Chaque ajout à la file $f$,
outre l'ajout initial, est fait par la ligne 48 après avoir fait passer une case
de distances de $-1$ à une valeur positive. La ligne 48 ajoute au plus $n$
sommets dans la file, donc il y a au plus $n^2 + 1$ ajouts dans la file et la
boucle termine après au plus $n^2 + 1$ itérations.\
On montre maintenant par récurrence sur $n \geq 0$ que $\forall E \in S$,
tel que $s \to^{\ast} t$ et $\text{dist}(s,t) = n$, BFS affecte la distance $n$
à $t$. On initialise sur $s$ qui est le seul sommet à une distance $0$ de $s$,
et pour $n \geq 0$, avec la propriété vraie pour $n - 1$, la propriété est vraie
(plus éloigné de $1$ de $s$). En effet, par hypothèse de récurrence, le sommet a
été ajouté à la file, et comme l'algorithme se termine, il sera bien défilé, en
lui affectant la bonne distance.

On peut d'ailleurs remarquer que BFS calcule aussi la distance dans un graphe
non-orienté.

### Accessibilité d'un sommet
> Soit $G = (S,A)$ un graphe orienté, et $s,t \in S$, on dit que $t$ est
> accessible depuis $s$ si $s \to^{\ast} t$. On définit ainsi l'ensemble des
> sommets accessibles depuis $s$.

> Si $G$ est non-orienté (ou le graphe orienté sous-jacent d'un graph
> non-orienté), l'ensemble des sommets accessibles depuis $s$ est la composante
> connexe de $G$ qui contient $s$.

> Les sommets visités par un parcours de $G$ (DFS ou BFS) depuis $s$ sont
> exactement les sommets accessibles depuis $s$.

__Preuve :__ Pour la BFS, voir la preuve précédente, et pour DFS, la preuve est
la même que pour prouver que la composante connexe de $s$ est l'ensemble des
sommets visités pour $G$ non orienté.
