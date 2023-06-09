# Algorithmes sur les graphes pondérés
> On appelle graphe orienté pondéré un triplet $(S, A, w)$
> Avec $(S,A)$ un graphe orienté et $w : A \to \mathbb{R}$.
> De même, on appelle graphe non orienté pondéré est la même chose avec une
> Fonction sur des arêtes non orientées.

On imposera, selon les problèmes que les poids (et donc la fonction) soient
positifs (cela permet d'utiliser Dijkstra plutôt que Bellman-Ford et
Floyd-Warshall).

Selon le problème, on pourra aussi placer des arcs de poids $+\infty$, ou
parfois on enlèvera l'arc.

On peut représenter un graphe pondéré par listes d'adjacences contenant des
tuples avec le poids des arêtes, ou par des matrices d'adjacence contenant le
poids plutôt qu'un booléen (il faut alors choisir un poids représentant
l'absence d'arête).

## Algorithme de Floyd-Warshall
Cet algorithme prend un graphe pondéré $G$ tel qu'il n'existe aucun cycle de
poids total strictement négatif, et dont les arcs absents ont un poids de $+\infty$.
Il renvoie une matrice indiquant pour chaque paire de sommets le poids total
minimum d'un chemin entre ces sommets. S'il n'y a pas de chemin possible, on
considère que tous les chemins entre eux sont de poids $+\infty$.

> Sous les hypothèses données, pour toute paire de sommets du graphe pour
> lesquelles il existe un chemin, il existe un chemin de poids total minimal.

__Preuve :__ Tout chemin entre les deux sommets est soit un chemin simple, soit
un chemin avec un cycle. Tout chemin avec un cycle peut engendrer des chemins
simples, puis on peut les comparer un par un.

On note pour $S' \subset S$ $G\restriction_{S'}$ le sous-graphe induit
$(S', A \cap (S'^2), w\restriction_{A \cap S'^2})$
$= (S', S'^2, w\restriction_{S'^2})$ (car on suppose que le graphe est complet
quitte à rajouter des poids infinis).
$\forall s,t \in S, \forall S' \subset S$, le plus court chemin dans
$G\restriction_{S' \cup \{s;t\}}$ est simple.\
On note $d(s,t,S')$ la longueur de ce plus court chemin (qui peut être $+\infty$ s'il n'y a pas de chemin).
Si ce chemin ne passe par aucun sommet autre que $s$ et $t$ (chemin direct),
alors on a $d(s,t,S') = d(s,t,\emptyset)$. Sinon, soit $u \in S'$, $u \neq s$
et $u \neq t$ tel que le plus court chemin passe par $u$, alors le chemin ne
passe qu'une seule fois par $s$ et $t$, donc la portion des chemins de $s$ à $u$
est le plus court chemin de $s$ à $u$ dans $G\restriction_{S' \cup \{s,t\}}$ et
ne passe pas par $t$.
De même, la portion du chemin de $u$ à $t$ est le plus court chemin de $u$ à $t$ dans $G\restriction_{S' \cup \{s,t\}}$ et ne passe pas par $s$.\
Or, on a $S' \cup \{s\} = (S' \setminus \{u\}) \cup \{u,s\}$
et $S' \cup \{t\} = (S' \setminus \{u\}) \cup \{u,t\}$.
Dans ce cas, on a donc
$d(s,t,S') = d(s,u,S' \setminus \{u\}) + d(u,t,S' \setminus \{u\})$.\
On se donne donc $u \in S'$ si $S'$ est non vide
(sinon $d(s,t,\emptyset) = \left\{\begin{matrix} 0 \text{ si } s = t \\ w(s,t) \text{ sinon} \end{matrix}\right.$).
$u$ est dans le plus court chemin de $s$ à $t$ dans $G\restriction_{S' \cup \{s,t\}}$ ou il ne l'est pas,
donc $d(s,t,S') = \text{min}(d(s,t,S' \setminus \{u\}), d(s,u,S' \setminus \{u\}) + d(u,t,S' \setminus \{u\}))$.

On pourrait mémoïser cette relation de récurrence. En prenant toujours $u = \text{max}(S')$, on aurait un cache indexé
sur $[\![0;n]\!]^2 \times [\![0;n]\!]$, de taille $\Theta(n^3)$.
Il semble préférable de faire une stratégie de bas en haut.
Le cache est alors de taille $n^2$ : la matrice des distances que l'on veut
renvoyer.

L'algorithme consiste donc à créer la matrice, puis à y donner une valeur de
$0$ pour les cases diagonales et le poids entre les deux sommets sinon (ce qui
donne $+\infty$ si les sommets ne sont pas directement reliés).\
On passe ensuite sur tous les sommets intermédiaires $u$, en itérant sur tous
les départs $s$, en itérant sur toutes les arrivées $t$, en plaçant $D_{s,t} = \text{min}(D_{s,t}, D_{s,u} + D_{u,t})$.\
On a ainsi une complexité de $O(n^3)$ en temps et de $O(n^2)$ en espace.

La terminaison de l'algorithme est triviale (terminaison des boucles). On prouve
donc la correction de l'algorithme. Après la première boucle, $D$ est la matrice
des $d(s,t,\emptyset)$. On peut remarquer comme invariant de boucle qu'après le
passage dans la deuxième boucle avec un certain $u$, $D$ est la matrice des $d(s,t,[\![0;u]\!])$.

__Preuve :__ Récurrence sur $u$ :
- si $u = 1$, cf ci-dessus
- Si $u \geq 0$, pendant l'exécution de la boucle à l'étape de $u$, $D_{s,t}$
  peut valoir son ancienne valeur $d(s,t,[\![0;n-1]\!])$ ou bien $D_{s,u} + D_{u,t}$.
  Si $s \leq u$, on a $D_{u,u}$ qui est calculé après $D_{s,u}$, donc
  $D_{s,u} = \text{min}(d(s,u,[\![0;u-1]\!]), d(s,u,[\![0;n-1]\!]) + d(u,u,[\![0;n-1]\!])) = d(s,u,[\![0;u]\!])$.
  Sinon, $D_{s,u} = \text{min}(d(s,u,[\![0;n-1]\!]), d(s,u,[\![0;n-1]\!]) + d(u,u,[\![0;n]\!])) = d(s,u,[\![0;n]\!])$.
  De même pour $D_{u,t}$, donc le calcul utilise les valeurs avec $S' = [\![0;n-1]\!]$
  ou $S' = [\![0;u]\!]$, et dans les deux cas ces valeurs sont identiques car $u$ est une extrémité du chemin.

Pour cet algorithme, il est plus efficace d'utiliser une matrice d'adjacence (la
première étape correspond à la copie de cette matrice).

## Algorithme de Dijkstra
L'algorithme prend un graphe orienté pondéré de poids positifs ou nuls, et
renvoie le plus court chemin d'un sommet $s$ à sommet $t$ si il existe (sinon,
il peut indiquer que le chemin n'existe pas).

On se donne un tableau $\text{dist}$ des distances de $s$ aux autres sommets de
$S$. Les sommets se divisent donc en 3 catégories : les sommets visités, les
voisins de sommets visités, et les autres. On procède comme un parcours en
largeur, mais plutôt que d'utiliser une file, on utilise un file de priorité,
dont les poids correspondent à la distance de $s$ des points. On extrait ainsi à
chaque étape le chemin le plus court disponible.

> Si on commence en visitant $s$, et qu'à chaque sommet visité pour la première fois
> on met à jour as distance depuis $s$ comme étant sa priorité, puis on enfile ses
> voisins avec la priorité comme ci-dessus, alors on visitera tous les sommets
> accessibles depuis $s$ et calculer leur distance la plus courte.

__Preuve :__ On montre par récurrence sur $1 \leq k \leq n$, avec $n$ la taille
du graphe que quand on a visité $k$ sommets, ce sont les $k$ sommets les plus
proches de $s$ et leurs distances sont correctes.\
Pour $k = 1$, $s$ est le sommet le plus proche de $s$ et $\text{dist}(s) = 0$.
Si la propriété est vérifiée pour $k - 1$ avec $2 \leq k \leq n$, tout chemin
qui part de $s$ est un chemin vers un sommet $r \in S$, puis nécessairement par
un sommet $u \in N$ (dans les voisins du sommet). Comme tous les arcs ont une
longueur supérieure à $0$, $u$ est au moins aussi proche de $s$ que $r$ l'est.\
Il existe donc un $k$-ième sommet plus proche de $s$ dans $N$.\
De même, pour tout $u \in N$, si un chemin de $s$ à $u$ passe par un sommet de
$R$, alors il passe par un autre sommet de $N$, et ce chemin sera plus court.\
Dans le plus court chemin de $s$ à un sommet encore non visité reste dans $V \cup N$,
et ne contient qu'un seul sommet de $N$.
Soit $(v_k)_k$ ce chemin, alors sa longueur est $\text{dist}(v_n) + d(v_n,u)$,
ce qui se vérifie par hypothèse de récurrence. Il s'agissait aussi bien de son
poids dans la file de priorité, et on peut donc conclure que récupérer les
sommets depuis la file de priorité donne bien les chemins les plus courts.

### Complexité
On s'assure que chaque sommet est visité au plus une fois, et que chaque arc
n'est suivi qu'une seule fois (et donc que les opérations associées ne sont
faites qu'une seule fois, soit quelque chose de linéaire en la taille de ces
opérations).\
Pour cela, on montre que dans le pire des cas, on retire autant d'éléments de la
file de priorité qu'on y a ajouté, soit $m + 1$. On fait l'hypothèse qu'on peut
obtenir avec un coût constant les listes de successeurs. Dans le pire cas, la
complexité est alors de $O(m \log m)$.

On peut améliorer cette complexité :
- On peut ajouter une opération pour diminuer la priorité d'un sommet dans la
  file de priorité, et la taille de la file est ainsi toujours majorée par $n$,
  avec au plus $n$ insertions et extractions. Avec cette implémentation, la
  modification est au minimum de complexité $\Theta(\log n)$, nous donnant une
  complexité $\Theta(m \log n)$.
- On peut utiliser des meilleures structures, comme les tas de Fibonacci ou les
  tas à paire, pour lesquels l'opération est respectivement de complexité $\Theta(1)$ (amorti)
  et $\Theta(\log n)$. Ainsi, la complexité dans le pire cas est de $\Theta(m + n \log m)$.
- La complexité moyenne est plus basse : en considérant les graphes aléatoires
  où les poids de toutes les arêtes entrantes pour chaque sommet sont mélangés
  uniformément au hasard de façon indépendante. Ici, la complexité moyenne sera
  alors $\Theta(m + n \log(\frac{m}{n}) \log(n))$.
- On peut ajouter de façon plus pratique une heuristique pour accélérer la
  recherche, de façon à favoriser certain chemin à l'essai, comme par exemple
  les plus proches à vol d'oiseau de l'arrivée.
