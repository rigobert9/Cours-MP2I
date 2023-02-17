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
