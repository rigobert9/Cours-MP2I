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

## Exemples de structures séquentielles
### Tableau
La structure la plus simple, car l'architecture de la mémoire est déjà l'implémentation d'un tableau.
Les opérations disponibles doivent être :
- La création d'un tableau de taille donnée
- Le destruction d'un tableau
- L'accès à un élément à un certain indice i, avec $0 \leq i < n$
- Accéder à la taille du tableau (optionnel)

### Tableau dynamique
Tableau contenu dans une structure avec des informations supplémentaires. Elles allouent
de l'espace supplémentaire quand nécessaire.

### Listes chaînées
Il s'agit d'une structure chaînée, composée de nœuds contenant chacun une valeur et
un (ou plusieurs) pointeurs vers d'autres nœuds qui le suivent. On la navigue ainsi avec une opération
qui permet de passer à l'élément suivant. On y implémente les opérations :
- Créer une liste vide / Détruire une liste
- Vérifier si une liste chaînée et non vide
- Accéder à la valeur de tête d'une liste
- Accéder à la liste chaînée qui commence par le maillon suivant
- Ajouter une valeur dans un maillon en tête de liste (où supprimer un maillon de tête)

Et aussi les opérations plus coûteuses :
- Accéder à la longueur d'une liste
- Concaténer deux listes
- Accéder à la valeur d'un rang i
- Insérer une valeur au rang i
- Supprimer la maillon au rang i

Telle que la SDA a été décrite, on pourrait implémenter une liste chaînée dans
un tableau dynamique.
On stockerait alors la suite avec la tête vers la fin du tableau. On peut
facilement accéder à la tête du tableau (`tab[n-1]`), retirer la tête, modifier
les éléments de tout rang très rapidement. Néanmoins, cette approche rend
extrêmement coûteux d'insérer ou de retirer un élément, puisqu'il faut alors
décaler tous les autres éléments. De plus, l'augmentation de la taille d'un
tableau dynamique est assez coûteuse.
En comparaison, l'insertion dans une liste chaînée normale équivaut seulement à
la création d'un maillon et à un changement de pointeur.

Ainsi, on ne peut pas définir une SDA sans s'intéresser au coût (en temps ou en
mémoire) des opérations définies sur la structure.
