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
