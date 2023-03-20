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

Si les poids sont $w_i = 2^{n-i}$, avec $i \in [\![1;n]\!]$,
alors si on arrive à l'objet $i$, le prendre apport $w_i$ et ne pas le prendre
rapporte au plus $w_i - 1 < w_i$, et il n'est alors jamais optimal de sauter un
objet que l'algorithme glouton prend.

On peut généraliser : dans le problème du sac à dos tel qu'usuellement décrit,
on se donne $n \in \mathbb{N}$, $c \in \mathbb{N}$, $(w_i)_{[\![1;n]\!]}$ des
poids et $(v_i)_{[\![1;n]\!]}$ des valeurs, avec $c \geq \text{max} (w_i)$.
On cherche un sous-ensemble $\{i_i\}_{[\![1;k]\!]}$ de $[\![1;n]\!]$
tel que $\sum\limits_{j = 1}^{k} w_{i_j} \leq c$ et $\sum\limits_{j = 1}^{k} v_{i_j}$ soit maximal.
- Si on trie les objets par $v_i$ décroissant, l'algo glouton est arbitrairement
  mauvais
- Si on trie selon $\frac{v_i}{w_i}$ par ordre décroissant, $\frac{v_\text{opt}}{v_\text{glouton}} = c - \frac{1}{2}$.

## Coloriage de graphe
Dans un graphe non-orienté $G = (S,E)$, on associe à chaque sommet une couleur, telle que
deux sommets reliés par une arête ne sont pas de la même couleur.
On appelle donc coloriage une fonction $S \to \mathbb{N}$ telle que $\forall s,t \in S$,
$\{s,t\} \in E \Rightarrow c(s) \neq c(t)$. On cherche $c$ tel que
$\text{max}_{s \in S}(c(s))$ est le plus petit possible. Le plus petit nombre de
couleurs possibles pour un coloriage est appelé nombre chromatique de $G$.

On peut utiliser une stratégie gloutonne pour trouver un coloriage. On parcourt
$S = [\![0;n-1]\!]$ et on définit $c\restriction_{[\![0;i]\!]}$ pour tout $i \in S$
ainsi. Soit $m_i = \text{max}_{j \in [\![0;i-1]\!]} c\restriction_{[\![0;i-1]\!]}(j)$
avec $m_0 = -1$. Si $\forall x \in [\![0;m_i]\!]$, $\exists j \text{ voisin de } i \mid j < i$
et $c\restriction_{[\![0;i-1]\!]}(j) = x$, alors on pose $c(i) = m_i + 1$.
Sinon, $c(i) = \text{min}(x \in [\![0;m_i]\!] \mid \forall j < i, c\restriction_{[\![0;i-1]\!]}(j) \neq x)$.
En particulier, dans ce second cas, $m_{i + 1} = m_i$.
Dans le pire des cas, on utilise $1 + \text{max}_{s \in S} d(s)$ couleurs.

Cette borne est atteinte, y compris sur certains graphes bipartis dont on sait
pourtant trouver un 2-coloriage via un DFS en temps linéaire.
