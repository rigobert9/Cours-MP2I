# Algorithmique sur les textes
Dans ce chapitre, on se donne pour chaque algorithme un ensemble de lettres
appelé alphabet. Un texte est une suite finie de lettres. La complexité d'un
algorithme peut dépendre à la fois de la taille de l'alphabet et du nombre de
lettres dans le texte, même si on néglige le temps nécessaire pour comparer deux
lettres.

## Compression de texte
> Étant donné un alphabet, on appelle fonction de compression une fonction
> injective qui prend en argument un texte de longueur $N$ et renvoie un couple
> (encode, texte compressé), tel que la taille de l'encodage (qui peut être sous
> des formes diverses) est borné uniquement en fonction de la taille de
> l'alphabet. Le texte compressé est une suite de $C$ bits. Si chaque lettre est
> encodée à l'origine sur $8$ bits, on dit que $\frac{8N}{C}$ est le taux de
> compression et $1 - \frac{C}{8N}$ l'économie d'espace.

On cherche, forcément, à maximiser pour tout $N$ la plus petite valeur de $E$
sur les textes de taille $N$. On considère ici la compression sans perte, pour
laquelle des théorèmes de théorie de l'information limitent la taille possible.
En pratique, on aimerait de plus que les fonctions de compression et de
décompression soient toutes deux faciles à calculer.

### Algorithme de Hoffman
On donne en entrée un alphabet d'au moins deux lettres et un texte sur cet
alphabet, et on veut obtenir un arbre binaire strictement non vide dont les
feuilles sont étiquetées chacune par une lettre différente de l'alphabet et dont
les nœuds internes n'ont pas d'étiquette, avec une suite de bits correspondant
au texte compressé.

#### Passage du texte au texte compressé et vice et versa
On suppose l'encodage connu, et à chaque lettre on associe la suite de bits qui
correspond au chemin de la racine jusqu'à la lettre ($0$ est le passage à gauche
te $1$ à droite). Aucune de ces suites n'est préfixe de l'autre : on parle de
code préfixe. Ainsi, les suites de bits peuvent être identifiées sans qu'on aie
besoin d'utiliser des lettres de taille connue d'avance, ou sans utiliser de
séparateurs.

Pour encoder plus efficacement, on utilise un algorithme prenant les fréquences
$(f_i)_i$ des lettres $(a_i)_i$ du texte, qui donne l'arbre binaire d'encodage.
On trie alors (ou crée une file de priorité) les fréquences.

> Soit $\mathcal{A}$ un alphabet de $n \geq 2$ lettres, et $A$ l'arbre de Hoffman
> d'un texte sur $\mathcal{A}$ et $A'$ un autre arbre binaire strict non vide dont
> les $n$ feuilles sont les éléments de $\mathcal{A}$. Alors $C$ la longueur du
> texte compressée avec $A$ est inférieure ou égale à $C'$ la longueur du texte
> compressé avec $A'$.

Ainsi, l'algorithme de Hoffman donne le meilleur code préfixe pour la
compression.

__Preuve :__ Pour le texte, $C = \sum\limits_{i = 1}^{n} p_i f_i$ où $p_i$
est la profondeur de $a_i$ dans $A$. On montre alors par récurrence que $C \leq C'$
sur $n$ la taille de l'arbre à partir de $2$.

Pour la complexité, on admet l'utilisation d'une file de priorité de taille
initiale $n$ sur laquelle on fait $n$ fois 2 extractions et 1 ajout.
La complexité sera donc de $\Theta(n \log n)$.

### Algorithme de Lempel-Ziv-Welch
Pour certains textes pourtant faciles à décrire brièvement, l'algorithme de
Hoffman est inefficace. LZW permet de découper en suites de lettres récurrentes
le texte. On peut d'ailleurs l'appliquer avant Hoffman.

On crée un dictionnaire de toutes les lettres, et on enregistre ensuite toutes
les suites de lettres pour la première lettre avec le premier entier disponible.
On encode alors ces suites par leur valeur, puis on recommence en ayant remplacé
dans le texte.

TODO

## Algorithmes de recherche dans un texte
On se donne dans les algorithmes de cette partie un texte $t$ de longueur $n$,
avec un motif $u$ de longueur $m$. On souhaite obtenir tous les indices dans
$[\![0;n - m]\!]$ où on peut retrouver le motif.

On est limité par une complexité de $m \times (n - m)$ comme on peut l'avoir
avec la recherche naïve qui passe sur chaque $i$ et compare jusqu'à échec de la
reconnaissance. Néanmoins, on peut trouver des algorithmes bien plus efficaces
dans des cas plus réalistes (bien qu'ils aient la même borne dans leurs cas
limite).

### Algorithme de Boyer-Moore (simplifié, au programme)
Étant donné un indice $i$, pour $j$ de $m - 1$ à $0$, on compare $u_j$ à $t_{i + j}$.
Si on arrive au bout, $i$ est un des indices qu'on cherche et on continue à $i + 1$;
sinon, soit $j$ le plus grand entier de $[\![0;m - 1]\!]$ tel que $u_j \neq t_{i+j}$
et $i'$ le plus petit entier de $[\![i+1;i+j]\!]$ tel que $u_{j - (i' - i)} = t_{i' + j - (i' - i)}$
$= t_{i+j}$. Si aucun tel $i'$ n'existe, alors on pose $i' = i + 1$. Dans tous
les cas, on recommence à chercher avec $i'$ à partir de $j = n - 1$.

L'algorithme est peu efficace et lance souvent des recherches qui semblent ne
jamais pouvoir aboutir. Dans le meilleur cas, la complexité de la recherche
est de $O(\frac{n}{m})$, sachant qu'un précalcul de $O(n^2)$ est nécessaire pour
faire le tableau des décalages selon les lettres.

### Algorithme de Rabin-Karp
On reprend $h$ la fonction de hachage utilisée dans les chapitres précédents. Il
suffit de vérifier pour chaque indice si le haché obtenu sur chaque sous-chaîne
est égal au haché de $u$. Cette stratégie est aussi inefficace que l'algorithme
naïf.

On va donc prendre avantage du calcul de la fonction de hachage qui est telle
que $h(a_0,a_1,\ldots,a_{m-1}) = \sum\limits_{j = 0}^{m - 1} b^{m - 1 - j} a_j [p]$,
avec $p$ un nombre premier tel que $p^2 \leq m$. On a alors le haché suivant $h(a_1,\ldots,a_m)$ qui
sera égal à $b h(a_0,\ldots,a_{m-1}) + a_m - b^n a_0 [p]$ par stabilité des
multiplications et additions modulo $p$. Ainsi, on peut calculer en temps
constant un haché à partir du précédent, donnant un coût total de $\Theta(n)$
(pour une comparaison de haché constante).
