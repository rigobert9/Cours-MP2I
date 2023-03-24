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

L'algorithme glouton parcours $G'$ en DFS comme $G$ dans l'ordre des sommets. Le
sommet $2n$ va recevoir la couleur $1$, et tous les sommets $2n + 1$ la couleur
$0$. Ceci ne change donc pas les couleurs attribuées par l'algo glouton aux
sommets de $0$ à $2n - 1$. L'algorithme utilise encore $n$ couleurs.

## Rendu de monnaie
Soit $n \in \mathbb{N}^{\ast}$, $1 = v_1 < v_2 < \ldots < v_n$ des entiers, et
$s \in \mathbb{N}^{\ast}$. On cherche $(x_i)_{[\![1;n]\!]} \in \mathbb{N}^n$
tel que $\sum\limits_{i = 1}^{n} x_i v_i = S$ en minimisant
$\chi(x_i) = \sum\limits_{i = 1}^{n} x_i$.

Dans le représentation à laquelle correspond le nom du problème, on essaie de
rendre un somme $n$ avec des pièces de valeurs $(v_i)$, tout en minimisant le
nombre de pièces rendues.

On ne peut pas vraiment strictement décrire un algorithme glouton pour ce
problème, puisqu'on ne peut pas définir de solutions partielles vérifiant la
contrainte (rendre la bonne somme de monnaie).
On choisit donc la contrainte de rendre moins ou autant que la monnaie (dans la
plupart des cas, on fait à la fin l'appoint avec des petites pièces, mais dans
certains cas on ne trouvera pas de solution). On définit $\chi$ et $\chi'$
deux objectifs qui ramènent au problème d'origine :
- $\chi(x_i)$ est minimal quand $\sum\limits_{i = 1}^{n} x_i v_i = s$ et que
  parmi ces valeurs $\sum\limits_{i = 1}^{n} x_i$ est minimal
- $\chi'$ est strictement croissante en tous les $x_i$ car $2 v_i - 1 > 0$,
  donc si $\chi'(x_i)$ est maximal alors on a atteint $\sum\limits_{i = 1}^{n} x_i v_i = S$.
  Ainsi, on prend $\chi'(x_i) = 2 s - \sum\limits_{i = 1}^{n} x_i$.

On définit ainsi l'algorithme glouton : une solution partielle est constituée de
$k$ pièces, pour $k \in \mathbb{N}$, $k = \sum\limits_{i = 1}^{n} x_i = k$.
Étant donnée une solution partielle à $k$ pièces, on cherche la solution
partielle à $k + 1$ pièces (ou $k$ si on avait déjà fini) qui minimise $\chi$
(ou maximise $\chi'$). Dans les deux cas, soit $(x_i)_{[\![1;n]\!]}$,
une solution partielle à $k$ pièces, et $i$ le plus grand entier tel que $v_i \leq s - \sum\limits_{j = 1}^{n} x_j v_j$.
Aucune pièce $i' > i$ ne peut être ajoutée à la solution car on avait $\sum\limits_{j = 1}^{n} x_j v_j + v_{i'} > s$.\
Pour tout $i' < i$, $v_{i'} < v_i$, donc $s - \sum\limits_{j = 1}^{n} x_j v_j - v_{i'}$
$> \sum\limits_{j = 1}^{n} x_j v_j - x_i$. Ainsi, $i$ est la pièce à ajouter
pour minimiser $\chi$ sur une solution à $k + 1$ pièces. (Dans ce même cas, on a
$\sum\limits_{j = 1}^{n} x_j (2 v_j - 1) + (2 v_i - 1) < \sum\limits_{j = 1}^{n} x_j (2 v_j - 1) + 2 v_j - 1$,
donnant que $i$ est la pièce a ajouter pour maximiser $\chi'$ sur une solution à
$k + 1$ pièces).

On a donc défini l'algorithme glouton pour le rendu de monnaie. Tant que le
reste à rendre de $s - \sum\limits_{j = 1}^{n} x_j v_j > 0$. Soit $i$ le plus
grand entier tel que $v_i \leq \text{Reste}$, on incrémente $x_i$ de $1$.

> On appelle système canonique pour le rendu de monnaie des entiers $1 = v_1 < \ldots < v_n$,
> tels que l'algorithme glouton fournisse une solution optimale un problème de
> rendu de monnaie pour tout $s \in \mathbb{N}$.

Le système d'euros en centimes (1,2,5,10,20,50,100,200,500,1000,2000,5000,10000,20000)
et de dollars en cents (1,5,10,25,100,500,1000,2000,5000,10000) sont canoniques.

Contre-exemples : (1,3,4) n'est pas canonique (voir le rendu de 6, pour lequel
l'algo choisit 2,0,1 et le rendu optimal est 0,2,0) et le système anglais
pré-réforme qui donnait 1,2,4,12,24,48,96,120,250,960,1920,4800,9600,19200,48000,
dans lequel des pauvres gens avaient 49 pence = 196 farthings.


__Preuve :__ On suppose prouvée l'affirmation
"si $(x_i)_{[\![1;n]\!]}$ est une solution optimale pour $s$ quelconque, alors
$\forall i \in [\![1;n]\!]$, $\sum\limits_{j = 1}^{i - 1} x_j v_j < v_i$".\
Soit $(y_i)_{[\![1;n]\!]}$ la solution gloutonne pour $s \in \mathbb{N}$,
et $(x_i)$ une solution optimale. On montre par récurrence sur $i \in [\![0,n-1]\!]$ que $x_{n-i}$
$= y_{n - i}$.
Soit $i \in [\![0;n-1]\!]$, on suppose $\forall j \in [\![n-i+1;n]\!], x_j = y_j$
(supposition qui est valide si $i = 0$). Alors
$\sum\limits_{j = 1}^{n-i} x_j v_j = s - \sum\limits_{j = n-i+1}^{n} x_j v_j$
$= s - \sum\limits_{j = n-i+1}^{n} y_j v_j$ par hypothèse de récurrence,
et $\sum\limits_{j = 1}^{n-i} x_j v_j < v_{n - i + 1}$ (si cette quantité
existe, quand $i > 0$).\
Donc si $i > 0$, on se ramène au problème de rendre
$s - \sum\limits_{j = n - i + 1}^{n} x_j v_j$ avec les
$(v_i)_{[\![1;n+1]\!]}$. En effet, aucune autre pièce n'est utilisable car $s < v_{n-i+1}$,
et comme $y_{n-i}$ est choisi de façon gloutonne $y_{n-i} = \left\lfloor \frac{s - \sum\limits_{j = n - i}^{n} x_j v_j}{v_{n-1}} \right\rfloor$
il est impossible que $x_{n-i} > y_{n-1}$ (sinon on dépasse $s$). On suppose par
l'absurde que $x_{n-i} < y_{n-i}$, ce qui implique que
$\sum\limits_{j = 1}^{n - i + 1} x_j v_j = \sum\limits_{j = 1}^{n - i + 1} y_j v_j + (y_{n-i} - x_{n-i}) v_{n-i}$,
or $(y_{n-i} - x_{n-i}) v_{n-i} \geq v_{n-i}$, donnant
$\sum\limits_{j = 1}^{n-i+1} x_j v_j \geq v_{n-i}$, ce qui est contradictoire.\
On a ainsi prouvé l'hérédité, donc en particulier toutes les quantités de pièces
de la solution gloutonne sont égales à celles de la solution optimale : les deux
solutions sont identiques.
