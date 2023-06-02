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
simples, puis on pet les comparer un par un.
