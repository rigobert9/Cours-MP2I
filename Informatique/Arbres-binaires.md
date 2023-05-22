# Arbres binaires
> Un arbre binaire est soit :
> - Un arbre vide (souvent `NULL`)
> - Une valeur, associée à deux autres arbres (le fils droit et le fils gauche)

Un arbre quelconque pris à part, que l'on utilise par comme racine d'un arbre,
est appelé nœud.

Un nœud dont les deux sous-arbres sont vides est appelé feuille. Les autres sont
appelé nœuds internes.

> Pour tout arbre avec $n \geq 0$ nœuds, l'arbre a $n+1$ sous-arbres vides.

__Preuve :__ On cherche à montrer par récurrence sur $n \geq 0$
la définition ci-dessus.
- Initialisation : Si $n = 0$, alors $A$ est l'arbre vide. Il a donc
  $0 + 1$ (lui-même) sous-arbres vides.
- Hérédité : Soit $m < n$ le nombre de nœuds de $A_g$. $A_d$ a $n-m-1$ nœuds, donc par
  hypothèse de récurrence, $A_g$ a $m + 1$ sous-arbres vides. Ainsi, l'arbre a
  $n+1$ sous-arbres vides.

> Soit $A$ un arbre binaire de $n$ nœuds et de hauteur $h$, alors $k + 1 \leq n \leq 2^{k+1} - 1$.
> De plus, pour tout $k \geq -1$, il existe $A_\text{min}$ et $A_\text{max}$ de
> hauteur $h$ qui atteignent ces bornes.

Un arbre $A$ de hauteur $H$ tel que toutes ses feuilles sont de profondeur $h$
(donc $n = 2^{k-1} - 1$) est dit parfait.

Un arbre dont toutes les feuilles sont de profondeur $h$ ou $h-1$ et dont les
feuilles de profondeur $h - 1$ sont toutes à droite des nœuds internes de même
profondeur sont dits complets.

Soit $n$ un nœud, on appelle enfant gauche (droit) la racine de son sous-arbre
gauche (droit) si ce sous-arbre n'est pas vide. On appelle parent de $n$ un
nœud tel que $n$ est un enfant droit ou gauche de ce nœud. La racine est le seul
nœud sans parent dans l'arbre $A$.

## Implémentation
En OCaML, on utilisera des unions disjointes entre l'arbre vide et un produit
cartésien. En C, on utilisera des structures récursives.

Si on sait que l'arbre qu'on manipule aura toujours le même nœud racine
(l'étiquette peut néanmoins changer), qu'il en sera de même de ses sous-arbres
tant qu'ils sont non vides, et qu'il sera toujours complet, alors on peut
implémenter les arbres binaire sur des tableaux dynamiques :
- `t[0]` contient le nombre de nœuds
- `t[2^p]` à `t[2^{p+1} - 1]` contiennent les étiquettes des nœuds de profondeur
  $p$ en partant de la gauche.

On peut dans cette implémentation modifier les étiquettes et ajouter des nœuds
tel que l'arbre reste complet. On ne peut pas faire un appel récursif sur un
sous-arbre en gardant le même modèle, car calculer le tableau d'un sous-arbre
prend un temps linéaire.

## Données stockées
- L'arbre contient des données entrées de façon désordonnée et les organise de
  façon à respecter une propriété sur les étiquettes des sous-arbres par rapport à
  la racine, récursivement. Ceci permet normalement un accès plus efficace aux
  données ou bien de calculer une fonction des données. C'est le cas des arbres
  binaires de recherche et des files de priorité avec des tas binaires. On
  manipulera alors l'arbre avec des fonctions récursives qui ne sélectionnent
  qu'un seul des sous-arbres.
- L'arbre correspond à une partie d'un arbre ou' d'un graphe qu'on n'explicite
  pas. Chaque nœud correspond donc à un certain object mathématique et son
  étiquette se rapporte à cet objet. Les algorithmes effectués sur l'arbre sont
  alors dépendants de l'objet mathématique effectué. C'est le cas des arbres
  couvrants d'un graphe ou des arbres radix.
- L'arbre représente une hiérarchie des données. Les algorithmes sur ces arbres
  vont parcourir l'arbre en profondeur (en général de façon récursive avec 2
  appels récursifs) afin d'exploiter cette hiérarchie. On a ainsi chaque appel
  (hors celui initial sur la racine) qui est fait depuis l'appel sur le nœud
  parent, auquel on peut faire référence.

## Parcours d'arbres
On appelle parcours un algorithme qui visite tous les nœuds d'un arbre.

### Parcours en profondeur d'abord - DFS
Un parcours en profondeur d'abord consiste à prendre à chaque nœud d'abord ses
descendants, c'est à dire les nœuds les plus profond avant de regarder les
autres pas encore visités.

Par convention, on visitera alors le sous-arbre gauche avant le droit. On peut
de plus traiter l'étiquette avant, au milieu des deux ou après, donnant un
ordonnancement de résultat différent à chaque fois (voir l'exemple sur les BST).
Le parcours infixe correspond à l'ordre des étiquettes de gauche à droite. On
perd l'information qui permettrait de reconstruire l'arbre si on ne note pas les
arbres vides.

### Complexités
Dans un arbre binaire de recherche de hauteur $h$, on peut :
- rechercher si une étiquette est présente en temps $O(h)$
- ajouter une étiquette ou calculer un ABR avec des étiquettes en plus valide en
  maintenant la propriété d'ABR en temps $O(h)$
- retirer une étiquette (ou calculer un ABR sans certaines étiquettes) en temps
  $O(h)$

En général, on imposera que les étiquettes d'un ABR soit deux à deux
distinctes.

Si l'arbre binaire est équilibré, $h = \Theta(\log n)$. Les ABR sont donc un
choix généraliste décent pour les ensemble ou les tableaux associatifs.

Si on ajoute $n$ éléments dans un ordre uniformément aléatoire dans un ABR
vide, l'ABR qui en résulte a en moyenne une hauteur $2 \log(n)$.

Ceci ne suffit pas, car en général l'ordre d'insertion n'est pas aléatoire, et
les arbres se déséquilibrent très vite.

## ABR équilibrés : exemple des arbres rouge-noir
> Une structure d'ABR équilibré est une structure pour laquelle :
> - Tout élément de la structure est un ABR
> - On a les opérations d'insertion et de suppression qui maintiennent la
>   structure
> - $\exists C \geq 1$ tel que $\forall n \in \mathbb{N},\forall A$ un élément de
>   la structure avec $n$ étiquettes, la hauteur de $A$ est $\leq C \log(n)$.

> Soit $A = (x,A_1, (y, A_2, A_3))$ un ABR, on appelle rotation à gauche de $A$ l'arbre
> $(y,(x,A_1,A_2),A_3)$, et rotation à droite l'opération inverse.

Par convention, si $A$ est vide ou son sous-arbre droit est vide, sa rotation à
gauche est lui-même, et si $A$ est vide ou son sous-arbre gauche est vide, sa
rotation à droite est lui-même. Dans ces cas particuliers, les opérations ne
sont plus réciproques l'une de l'autre.

> La rotation gauche et droite d'un ABR $A$ sont des ABR, et si $A'$ est un
> sous-arbre, le remplacer par l'une de ses rotations conserve la propriété d'ABR.

> On appelle arbre rouge-noir un ABR où chaque nœud possède une couleur (rouge ou
> noir ici), avec les propriétés suivantes qui doivent être conservées :
> - tout nœud non racine qui est rouge a un parent noir
> - il existe $b(A) \in \mathbb{N}$ tel que tout chemin de la racine de $A$ à une
>   feuille de $A$ passe par $b(A)$ nœuds noirs

On peut remarquer que si $A$ est rouge-noir, ses sous-arbres gauche et droit
sont aussi des arbres rouge-noir (ce qui permet de raisonner par induction
dessus facilement). La réciproque est fausse (il faut ajouter la condition
$b(A_g) = b(A_d)$, et s'assurer que la racine est noire ou que les racines des
deux sous-arbres soient noires).

On peut toujours colorier en noir la racine d'un arbre rouge-noir, mais on ne le
met pas dans la définition pour garder la propriété d'hérédité.

Soit $A$ un arbre rouge-noir avec $n$ nœuds de hauteur $h$, avec $b(A)$ nœuds
noirs sur tout chemin de la racine à un sous-arbre vide, alors $n \geq 2^{b(A)} - 1$
et $h \leq 2 b(A)$. Ainsi, soit $A$ un arbre rouge-noir, de hauteur $h$ avec $n$
nœuds, on a $h \leq 2 \log(n + 1)$.

__Preuve :__ TODO

### Insertion dans un arbre rouge-noir
On insère comme dans un ABR, puis on colorie en rouge le nœud inséré. Le
résultat est un ABR qui viole au plus une fois la propriété sur la parenté des
nœuds rouges, et respecte la propriété de la profondeur noire ($b(A)$ reste
inchangé).

Si la propriété est bien respectée, il n'y a rien à faire. Sinon, on a la
procédure de réparation générale, qu'on opère jusqu'à réparation :
Soit, avec $x$ et $y$ des nœuds rouges, l'arbre (avec $y$ fils gauche sans
perte de généralité, on pourrait le mettre à droite) $(x,(y,A_2,A_3),A_1)$.
- Si ce sous-arbre est $A$ tout entier, on colorie $x$ en noir
- Sinon, soit l'arbre $(w,(x,(y,A_1,A_2),A_3),A_4)$, avec $x$ et $y$ rouges et
  $w$ noir, on effectue la rotation
  vers la droite de cet arbre, en coloriant $y$ en noir, et on effectue la
  procédure sur l'arbre au-dessus
- Dans le dernier cas où $y$ est le fils de $x$ de l'autre côté que $x$ est fils
  de $w$, on fait une rotation à droite pour se ramener au cas précédent
