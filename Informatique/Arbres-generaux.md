# Arbres généraux
## Extension de la définition des structure inductives
On peut définir des structures mutuellement inductives, c'est-à-dire
que leurs constructeurs peuvent prendre des arguments de cette même structure ou
d'une autre structure.

Le théorème d'induction structurelle s'applique encore sur l'union de ces
structures mutuellement inductives et donc aussi sur chacune prise
individuellement.

On définit les arbres avec deux structures mutuellement inductives, les arbres
et les forêts :
- La forêt vide est une forêt
- `Noeud(x, F)`, où `x` est une étiquette et `F` une forêt, est un arbre.
- `a::F`, avec `a` un arbre, est une forêt

On peut réécrire la définition des forêts comme étant la forêt vide ou la forêt
formée de la racine d'un arbre, de la forêt de ses enfants, et de la forêt des
arbres suivants.

On obtient ainsi nue définition des forêts comme structure inductives (sans
référence aux arbres) avec un constructeur constant et un constructeur d'arité $2$,
typé par la type des arbres de la forêt. Il s'agit donc des arbres binaires à un
isomorphisme près.
Les arbres correspondent aux forêts à un seul élément, c'est-à-dire aux arbres
binaires dont le sous-arbre droit est vide.

Un arbre générique de hauteur $1$ peut avoir un nombre arbitrairement grand de
nœuds.

### Arbres préfixes
Les arbres binaires sont une implémentation des tableaux associatifs dont les clés
sont des chaînes de caractères, en utilisant les arbres.

Pour cela, on étiquette chaque nœud par un caractère, un booléen et un entier.
La racine est étiquetée par le caractère nul (ou alternativement en utilisant
une forêt préfixe plutôt qu'un arbre).

Pour rechercher une clé :
- si le caractère du nœud correspond à un caractère de la clé, alors on continue
  avec les enfant de ce nœud avec la clé amputée en 1er caractère
- sinon, on continue avec cette même clé vers le frère de l'arbre
- si notre recherche arrive à la forêt vide, la clé n'est pas dans le tableau
  associatif et on s'arrête
- si on réduit la clé à la chaîne vide, alors le booléen du nœud indique si la
  clé est dans le tableau associatif, et l'entier est la valeur associée

La complexité des opérations dans le pire cas est proportionnelle à la somme des
arités des nœuds rencontrés sur le chemin dans l'arbre binaire. Dans le pire
cas, $\Theta(ha)$, avec $h$ la hauteur à l'arité maximale d'un nœud, et
$\Omega(\log(n))$ en utilisant l'inégalité sur la hauteur de l'arbre binaire.

### Parcours d'arbres
On peut définir les parcours préfixes, infixes et suffixes sur tout arbre et sur
toute forêt, de la même façon que sur les arbres binaires :
- si $F$ est une forêt non vide, `f = a::f'`, le parcours préfixe de `f` est
  constitué du parcours préfixe de `a` puis de `f'`.
- le parcours de la forêt vide est l'ensemble vide.

> Soit $F$ une forêt et $A$ l'arbre binaire correspondant, alors le parcours
> préfixe de $F$ est le parcours préfixe de $A$, et de même pour le parcours
> suffixe.

__Preuve :__ On procède par induction structurelle sur les forêts.
On initialise sur la forêt vide qui correspond à l'arbre vide. Soit
`F = B::F2` une forêt non vide, on pose `B = Noeud(x,F1)`. On suppose la
propriété vraie pour `F1` et `F2`. On note `g` la fonction qui à chaque
forêt associe un arbre binaire en respectant la structure, et on a
`A = g(F) = Noeud(g(F1),x,g(F2))`. Le parcours préfixe de `A` est donc valable.
