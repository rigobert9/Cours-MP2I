# Structures de données séquentielles : Partie 1
## Structure de données abstraite et interface
Une structure de données est une façon d'organiser l'information pour la
traiter. Elle se caractérise par une structure de données abstraite qui spécifie
mathématiquement les opérations de cette structure, et une implémentation qui
traduit la SDA dans le langage.

Par exemple, on cherche à modéliser un tableau associatif de clés chaînes de caractères et de
valeurs entières (sorte de dictionnaire python réduit).
On veut pouvoir :
- créer un tableau associatif vide
- associer une valeur à une clé (en remplaçant la précédente le cas échéant)
- vérifier si une clé est présente
- lire la valeur associée à une clé présente
- supprimer une clé
- détruire un tableau associatif

Toutes ces opération vont alors constituer une interface : en C, il s'agit de la
déclaration de toutes les fonctions associées dans un fichier header (extension
.h) et de leur documentation.
La "barrière d'abstraction" signifie qu'il n'est ni nécessaire, ni souhaitable
d'avoir plus de détails sur l'implémentation (et donc que les interactions avec
cette structure de données ne doivent être faites que par les fonctions
proposées).

L'implémentation réalise cette interface, et l'utilisateur utilisera cette
interface (si l'implémentation change, l'interface ne change pas et est toujours
utilisable pareil).

En C, on fera ensuite `#include "mastructure.h"` dans le code client, et on
compilera ainsi notre code avec l'interface et son implémentation (en utilisant
une bibliothèque qui implémente l'interface, par exemple).

## Structures en C
Une structure est un "type" de L-value qui contient des champs de différents
types (des "cases" à l'intérieur de la structure). Par exemple :
```c
struct Fraction {
  int num;
  int den;
};
```

Les structures sont passées par valeur aux fonctions (si seul leur nom est
précisé comme type), soit en détail *tous les champs sont copiés dans la frame*.
On peut de même renvoyer une structure avec une fonction.

Dans la plupart des cas, on préfèrera allouer dynamiquement de l'espace pour une
structure avec `malloc` et passer des pointeurs vers la structure entre les
fonctions. De plus, la plupart des fonctions sur les structures vont soit les
lire (ce qui sera plus léger soit en passant les valeurs concernées, soit un
pointeur plutôt que toute la structure) soit les modifier (auquel cas on veut
bien agir directement sur la structure via sa référence avec une pointeur).

À cause de la lourde utilisation des pointeurs vers les structures, on utilise
l'opérateur "spaceship", avec `pointer->field` l'équivalent de l'indigeste
`(*pointer).field`.
