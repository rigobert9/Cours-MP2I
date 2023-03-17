# Algorithmes gloutons
> Un algorithme glouton peut exister pour un problème qui, étant donné un ensemble
> $S$ d'objets et un ensemble $J$, cherche la fonction $f: S \to I$ qui minimise
> (ou maximise) une certaine mesure $W(f)$, tout en vérifiant $P(f)$. L'algorithme
> glouton consiste à parcourir $S$ dans un ordre arbitraire (ou fixé à l'avance),
> et pour chaque élément $s$, choisit $f(s)$ qui minimise (ou maximise) $W$ sur la
> restriction de $f$ aux éléments déjà rencontrés.

Un algorithme glouton fournit UNE solution, mais il n'est pas garanti
qu'elle soit optimale.

L'exemple le plus célèbre est le problème du sac à dos, où on dispose d'un sac
de capacité maximale $C$, et de $[\![1,n]\!]$ une collection d'objets de poids
$w_{[\![1,n]\!]}$. Si on suppose que ces poids sont ordonnés, on peut déterminer
un algorithme glouton en prenant l'objet disponible le plus lourd possible à
chaque fois. On peut voir que le résultat n'est pas mauvais, mais n'est pas
toujours le meilleur.
