# Tableaux associatifs
## Définition de la structure de données abstraites
On se donne $C$ un ensemble de clés et $V$ un ensemble de valeurs.
On suppose que la "taille" de chaque clé utilisée set petite par rapport au
nombre de clés utilisées parmi l'ensemble des clés.

On dispose des opérations suivantes sur un tableau associatif avec $n$
associations :
- Créer un tableau associatif vide, de capacité initiale $m$, en temps $O(m)$
- Pour $(c,v) \in C \times V$, on peut ajouter ou modifier un clé (chaque clé
  est associée une unique valeur, sinon on la remplace), en temps $O(1)$
- Pour $c \in C$, vérifier si $\exists v \in V \mid (c,v) \in \,\text{tableau}$,
  en temps $O(1)$
- Obtenir la valeur associée à une clé en temps $O(1)$
- Retirer une association en temps $O(1)$
- Libérer la mémoire occupée en temps $O(n + m)$

Les complexités constantes sont des approximations empiriques, et dans le cas de
l'ajout sont des complexités amorties qui :
- négligent la taille de la clé
- supposent qu'on maintienne une capacité $m$ dans le tableau
  associatif à l'ordre de grandeur de $n$

On néglige la taille de la clé (à priori de l'ordre de $\log(n)$), car les
opérations de manipulation de la clé, même plus nombreuses, sont moins
coûteuses que les opérations de déréférencement que l'on va réaliser et qui
restent en nombre majoré par une constante.

Toutes les opérations se font par rapport à la clé. Chercher une valeur sans sa
clé est extrêmement inefficace.

Si $C = [\![0, n-1]\!]$, on a juste un tableau. Si $C = \mathbb{N}$, on a un
tableau dynamique. Le cas le plus courant pour un tableau associatif
est $C$ étant des chaînes de caractères. Dans l'implémentation, on va donc
devoir transformer chaque clé en un entier pour se ramener au cas d'un tableau.
