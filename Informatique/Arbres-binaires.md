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

__Preuve :__ On montre par récurrence sur $k \geq 0$ que pour tout $A$ un arbre
rouge-noir tel que $b(A) = k$, on a $n \geq 2^k - 1$ et $h \leq 2k$.
L'initialisation est triviale. On procède ensuite par récurrence forte,
et alors pour $A$ tel que $b(A) = k$.
- Si $A$ a une racine noire, avec la hauteur noire de ses deux enfants qui est
  égale, on a par hypothèse de récurrence $n(A_g), n(A_d) \geq 2^{k - 1} - 1$,
  donc $n(A) \geq 2 \times (2^{k - 1} - 1) + 1$. De même, $h(A) =
  \text{max}(A_g, A_d) + 1 \leq 2k - 2 + 1 < 2 k$.
- Si $A$ a une racine rouge, on fait les mêmes opérations et conclusions.

> Les arbres rouge-noir sont des ABR équilibrés, et la recherche, l'insertion, et
> la suppression dans un ABR à $n$ éléments est de coût $\Theta(\log n)$ dans le
> pire cas.

De plus, si les arbres sont mutables, le nombre d'écritures pour toute opération
est constante en complexité amortie.

### Insertion dans un arbre rouge-noir
On insère comme dans un ABR, puis on colorie en rouge le nœud inséré. Le
résultat est un ABR qui viole au plus une fois la propriété sur la parenté des
nœuds rouges, et respecte la propriété de la profondeur noire ($b(A)$ reste
inchangé).

Si la propriété est bien respectée, il n'y a rien à faire. Sinon, on a la
procédure de réparation générale, qu'on opère jusqu'à réparation :

À RÉÉCRIRE

Soit, avec $x$ et $y$ des nœuds rouges, l'arbre (avec $y$ fils gauche sans
perte de généralité, on pourrait le mettre à droite) $(x,(y,A_2,A_3),A_1)$.
- Si ce sous-arbre est $A$ tout entier, on colorie $x$ en noir
- Sinon, soit l'arbre $(w,(x,(y,A_1,A_2),A_3),A_4)$, avec $x$ et $y$ rouges et
  $w$ noir, on effectue la rotation
  vers la droite de cet arbre, en coloriant $y$ en noir, et on effectue la
  procédure sur l'arbre au-dessus
- Dans le dernier cas où $y$ est le fils de $x$ de l'autre côté que $x$ est fils
  de $w$, on fait une rotation à droite pour se ramener au cas précédent

## Les tas (heaps) et files de priorité
Une file de priorité sur $(E,F)$ avec $E$ totalement ordonné et $F$ un ensemble
est un structure de données abstraites qui représente un multiensemble
d'éléments de $E \times F$.

On dispose des opérations de base suivantes :
- créer un file de priorité
- déterminer si une FP est non vide
- ajouter un couple $(k,v)$ à une FP
- retirer et renvoyer un des couples $(k,v)$ de la FP qui minimise $k$

On peut aussi parler de la "max-heap", la version dans laquelle l'opération
élémentaire est d'obtenir l'élément maximisant $k$.

On peut faire ce travail avec les arbres binaires de recherche (en allant
chercher au plus à droite ou à gauche). La complexité des opérations est alors
de $\Theta(\log n)$ en utilisant des ABR équilibrés.

En pratique, on peut utiliser une autre structure qui donnera des opérations
légèrement plus rapides (mais toujours de même complexité). Ces structures
permettent néanmoins de créer un tas en temps $\Theta(n)$ plutôt que $\Theta(n \log n)$.

> Soit $A$ un arbre (binaire dans notre cas) étiquetté par $E$ totalement ordonné,
> on dit que A est un tas si tout nœud a une étiquette inférieure (respectivement
> supérieure dans une max-heap) à celle de ses enfants.

> Un tas binaire est un arbre binaire complet qui est un tas.

Pour insérer dans un tas binaire, on insère au seul endroit possible pour
conserver la complétude du tas, puis on fait remonter l'élément tant que des
éléments plus petits sont au-dessus de lui par échange. Cet algorithme dit de
tamisage (sift-up) est de complexité $\Theta(h) = \Theta(\log n)$.

Pour supprimer un élément, on remplace l'élément par le dernier élément du tas,
qu'on fait ensuite redescendre.

On peut facilement prouver la correction de ces algorithmes, et l'insertion de
$n$ éléments ou la suppression du nœud minimal d'un tas ("pop") se font en temps
$O(\log n)$ et en espace $O(1)$.

Pour construire un tas de $n$ éléments connus, on peut procéder naïvement par
$n$ insertions, donnant une complexité de l'ordre de $\sum\limits_{k = 1}^{n} \log(k) = \log((n - 1) !)$
$\sim n \log(n)$ (Stirling).\
Pour obtenir une meilleure complexité, on peut construire un tas binaire de $n$
éléments avec $-\infty$ dans chaque nœud ($O(n)$), puis on remplace les éléments
par nos éléments, qu'on fait ensuite sift down. Pour $m = 2^{\left\lfloor \log(n) \right\rfloor + 1} - 1 \leq 2n$
éléments (un arbre parfait de même hauteur),
remplir la couche de profondeur $h$ coûte au plus $K \frac{n}{2}$ car cette
couche contient $\frac{m + 1}{2}$ éléments. Pour celles en-dessous,
les remplir coûte au plus $\frac{m K k}{2^{k + 1}}$ pour la couche de hauteur $h - k$.
Le coût total est donc majoré par au plus $K \sum\limits_{k = 0}^{\left\lfloor \log(n) \right\rfloor} \frac{k m}{2^k}$
$\leq 2 K n \times \sum\limits_{k \geq 0} \frac{k + 1}{2^k}$.
La série converge, donc le coût de l'opération est bien $O(n)$.

### Tri par tas
Étant donné un tableau de taille $n$, on sait mettre ses éléments dans un tas
binaire. En stockant les éléments en commençant par la fin du tableau, on peut
créer un tas en place. Il suffit alors de réorganiser en un tas maximal, puis
de mettre les éléments retirés à la fin du tableau à chaque étape.
