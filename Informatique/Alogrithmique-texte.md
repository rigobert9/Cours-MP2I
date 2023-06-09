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
