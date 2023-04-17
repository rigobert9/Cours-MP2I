# Programmation dynamique
On observe le problème de la pyramide d'entiers, où on cherche le chemin avec la
plus grande valeur en partant du sommet d'une planche de Galton.
Il n'y a pas de condition d'échec, donc on ne peut pas faire de backtracking, et
l'algorithme glouton est arbitrairement mauvais.

On risque d'être forcé à tout tester. L'algorithme diviser pour régner est
l'algorithme naïf, mais on visite plusieurs fois les mêmes endroits : les
sous-problèmes se chevauchent.

La programmation dynamique permet, à la façon du calcul de la suite de
Fibonacci, de réutiliser des résultats tous ensemble pour résoudre un problème
général. En particulier, on résout ici tous les sous-problèmes de façon optimale
et on les rassemble pour obtenir les problèmes au-dessus de façon optimale.
On doit donc avoir un problème dont la solution optimale peut être obtenue par
des sous-solutions optimales.

En prenant $S$ l'ensemble des sous-problèmes, on peut définir un graphe orienté
acyclique de sommets $S$, tels que $u \to v$ si $v$ est un des sous-problèmes
que l'on doit résoudre pour obtenir la solution optimale de $u$. On parcourt en
profondeur ce graphe, et on marque comme visité chaque noeud après l'avoir
résolu (OK car il n'y a pas de cycles), et en le marquant (conceptuellement), on
inscrit son résultat dans un cache (concrètement). Ainsi, le parcours en
profondeur se finit et ne visite pas deux fois un même nœud.

Si le calcul d'une solution en fonction des solutions de ses sous-problèmes est
$O(s)$, avec $s$ le nombre de sous-problèmes, alors la complexité en temps de
l'algorithme mémoïsé est $O(\text{Card}(A))$ avec $A$ les arêtes du graphe.
Si la complexité du calcul d'une solution en fonction des solutions des
sous-problèmes est plus grande, alors la complexité est plus grande de façon
similaire.

En espace, la complexité est $O(\text{Card}(S))$ avec $S$ les sommets du graphe.
En général, la partie de l'algorithme naïf hors appels récursifs n'utilise pas
des grandes quantités de mémoire. Dans un DFS, il n'y a jamais de frames
empilées que de sommets dans le graphe.

## Programmation dynamique de bas en haut (bottom-up)
L'idée est d'organiser le graphe $(S,A)$ en étages de $0$ à $n$,
tels que l'étage $0$ n'ait pas de successeur et $n$ pas de prédécesseur.
Pour toute étape $i$, tous les prédécesseurs sont à l'étape $i$ ou $i + 1$.

Ceci signifie que pour $i \geq 1$, une fais que l'étape $i$ du cache est rempli,
on n'a plus besoin des étape $ \leq i - 1$. On utilise ainsi moins de mémoire.
En revanche, selon les problèmes (à quel point les sous-problèmes "s'empilent"),
on peut avoir du mal à formuler des étages ou de faire des calculs efficaces,
et on peut se retrouver à résoudre des problèmes dont on avait pas besoin.

### Passer de calcul de la valeur de la meilleure solution au calcul de la meilleure solution
Souvent la meilleure solution d'un problème se calcule de la façon suivante :
- Calculer les meilleures solutions de chaque sous-problème
- Calculer les valeurs de chacune de ces solutions
- Choisir le sous-problème avec la meilleure valeur, et calculer à partir de sa
  meilleure solution la meilleure solution du problème

Ainsi, on préfère mettre dans le cache les solutions et leurs valeurs.
