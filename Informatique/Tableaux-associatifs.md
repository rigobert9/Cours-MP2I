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

## Table de hachage
Une table de hachage consiste à utiliser une fonction de hachage prenant une clé
en entrée et renvoyant un entier, puis à mettre dans chaque coupe $(c,v)$ du
tableau associatif dans la case `h(c) % m` d'un tableau de $m$ cases.

Le principal problème est que $h$ n'est pas nécessairement injective, et donc
que deux éléments peuvent avoir le même hachage ou occuper la même case en étant
équivalente au modulo $m$.

Pour cela, on dispose de deux solutions : on peut mettre les entrées les une à
la suite des autres en listes chaînées, ou on peut utiliser l'adressage ouvert.

Dans les deux cas, le coût pour obtenir l'association $(c,v)$ dans $t$ à partir
de $h(t)$ est proportionnel (dans le pire cas et en moyenne) au nombre de clés
$c'$ dans $t$ telles que `h(c') % m == h(c) % m`. Il est donc important pour
maintenir l'accès en coût constant que $h$ ait peu de collisions et $m$ soit
assez grand.

On détermine le choix de $m$ par le principe des tiroirs. Si on met $n$ clés
dans $t$, il existe un seau $b \in [\![0,n-1]\!]$ tel que $b$ contient au moins
$\left\lceil \frac{n}{m} \right\rceil$ associations. $m$ doit donc au minimum
rester de l'ordre de grandeur de $n$. Cependant, prendre $m$ grand signifie
qu'on occupe plus de place en mémoire (un mot mémoire pour le tableau), donc on
veut éviter de la choisir beaucoup plus grand.

De plus si $n$ est une puissance de $2$, alors prendre `h(c) % m` revient à
faire le ET bitwise de `h(c)` et $m-1$. Cette opération peut être vue comme
étant de coût constant, contrairement à la division euclidienne.

Pour choisir $h$, on veut que les images des clés par $h$ soient suffisamment
dispersées. En particulier, si $C$ est l'ensemble des clés, utiliser la longueur
des chaînes de caractères est une mauvaise idée (trop petites valeurs, trop de
collisions). La somme des bits de la clé n'est pas une bonne idée non plus, et
idem pour le produit (ils sont tous deux stables par permutation). On propose
donc, sur les chaînes de caractères, $h(c) = \sum\limits_{j = 0}^{k} b^{k-j} \,\text{code}$,
avec $k$ la longueur de la chaîne, et b assez grand pour éviter les collisions
sur les clés courantes (par exemple, $b \geq 26$ pour les lettres minuscules).

On choisit de plus $b$ impair pour éviter que lorsqu'on prend le reste module
$2^{64}$.

## Serialisation
Pour faire une table de hachage avec d'autres types que les chaînes de
caractères, on peut décider de représenter les objets comme des chaînes de
caractères. On peut naïvement choisir une représentation "humaine", ou sous
forme de code, ou encore sous la forme de JSON.

On peut cependant améliorer la chaîne de caractère, en choisissant un format
plus "machine". Pour un arbre, on pourrait par exemple utiliser le parcours
préfixe, qui est injectif des arbres binaires dans le chaînes de caractères.

On peut encore mieux faire en jouant sur la représentation des entiers. Par
exemple, sur 256 caractères, on peut en utiliser 200 pour écrire les entiers en
base 100 en utilisant des jeux de caractères différents pour le parcours infixe
et les caractère restants pour éviter les parenthèses.

On appelle fonction de serialisation une fonction injective d'un type vers les
chaînes de caractères. La chaîne sérialisée comporte un préfixe qui décrit le
type.

En OCaML, `Marshall.to_string` permet de sérialiser, et on peut obtenir la
donnée à partir de `Marshall.of_string`.

On ne peut pas vraiment le faire pour une fonction, on ne peut qu'indiquer
l'endroit dans le programme, avec l'environnement local, où se trouve cette
fonction. Une fonction ne peut donc être sérialisée que si elle doit être
réutilisée par le même programme.
