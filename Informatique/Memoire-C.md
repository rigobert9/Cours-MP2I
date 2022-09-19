# Representation des données en mémoire en C

## Les types prédéfinis

Le C est un langage typé.
Cela signifie en particulier que toute variable, constante ou fonction, est d'un type precis.
Le type d'un objet définit la façon dont il est représente en mémoire.

La mémoire de l'ordinateur est une suite continue d'octets.
Chaque octet est caractérise par son adresse, un entier. Quand une variable est définie, une adresse lui est attribuée.
Les variables correspondent a des zones mémoire dont la longueur est fixée par leur type.

Les caractères (`char`) sont codes sur un octet, en utilisant le codage ASCII (7 bits, bit de poids fort 0). Les caractères Unicode sont codes par plusieurs octets precedes d'un caractère d'échappement (bit de poids fort 1).
En C, le type char peut être utilise dans toute expression utilisant des objets de type entier.
Un objet de type int est représenté sur 32 bits, on peut utiliser un attribut de precision (short int: 16 bits, long int: 64 bits) ou un attribut de representation (`unsigned`).
On peut utiliser le mot-clé `sizeof` pour connaître la longueur d'un objet.

Par défaut, la taille mémoire des types depend de la machine ou du compilateur, le header `<stdint.h>` ajoute des types qui en sont indépendants.

Par défaut, les types entiers peuvent coder autant (à une près) de valeurs strictement positives que strictement negatives, le bit de poids fort indiquant le signe de l'entier.
On peut travailler avec des valeurs non signées a l'aide de `unsigned`.

Pour représenter un entier négatif, on utilise le "complément a 2", c'est-à-dire:
- Le bit de poids fort correspond au signe : 0 pour un entier positif, 1 pour un entier négatif.
- Pour un entier négatif N, les n-1 bits suivants sont calcules ainsi :
  - On représente abs(N) en binaire
  - On prend le **complément a 1** de cette representation en inversant tous les bits
  - On ajoute 1 au complement a 1. Ceci donne le **complément a 2**.

Si le résultat est dans $[-2^{(n-1)} ; 2^{(n-1)}-1]$, les additions et soustractions des entiers avec cette representation peuvent se faire comme s'il s'agissait d'une addition d'entiers positifs représentes en binaire. Il faut pour cela ignorer l'éventuelle retenue sur le (n+1)-ème bit.

Lemme: Soit $N$ dans $[-2^{(n-1)} ; 0]$
Alors la representation en complement a 2 de $N$ est formée de 1 subis des $n-1$ bits représentant $2^{(n-1)}+N$ en binaire.

Lemme 2: Si $N+M$ dans $[-2^{(n-1)} ; 2^{(n-1)}-1]$\
et $N,M \geq 0$, alors $N+M$ dans [...]\
et $N \geq 0$, $M<0$, alors $2^{(n-1)}+N+M$ dans $[-2^n ; 2^{n}-1]$\
et $N < 0$, $M < 0$, alors $2^{n}+N+M$ dans $[-2^n ; 2^{n}-1]$

Les types flottants représentent des nombres a virgule flottante (float: 32 bits, double: 64 bits, long double: 128 bits)

## Adresses et pointeurs

On appelle "Lvalue" (left value) toute expression pouvant être place a gauche d'un opérateur d'affectation (pour l'instant, un nom de variable)
Elle est caractérisée par :
- son adresse (l'adresse mémoire ou l'objet est stocke)
- sa valeur (ce qui y est stocke)

L'adresse d'une Lvalue étant le numéro d'un octet de la mémoire, il s'agit d'un entier (actuellement sur 64 bits).
Le format d'une adresse de l'architecture, meme si il est généralement en 64 bits : il est donc plus correct d'utiliser %p que %lx.

L'opérateur & permet d'accéder a l'adresse d'une variable.
Ceci permet notamment le passage par adresse de la fonction `scanf`.

Attention : si i est une variable, &i n'est pas une Lvalue mais une constante, on ne peut pas faire figurer &i a gauche d'une operation d'affectation.
Pour pouvoir manipuler les adresses, on doit donc recourir aux **pointeurs**.

Deux variables i et j ont des adresses différentes, l'affectation i=j; ne change que les valeurs des variables.

Un pointeur est une Lvalue dont la value est égale a l'adresse d'un autre objet. Comme pour n'importe quelle Lvalue, sa valeur est modifiable.
On declare un pointeur via `type *nom_du_pointeur`. L'identificateur est ici, en quelque sorte, un identificateur d'adresse.

Meme si la valeur d'un pointeur est toujours un entier, le type d'un pointeur depend du type de l'objet vers lequel il pointe.
Un pointeur de type int* ne peut pas être converti en un pointeur de type float*.
Si la variable pointée prend plusieurs octets, la valeur du pointeur est celle de l'adresse du premier octet de la variable.

L'opérateur unaire d indirection `*`, aussi appelle opérateur de déréférencement, permet d'accéder directement a la valeur de l'objet pointe.
Si p est un pointeur vers un entier `*i`,`*p` désigne la valeur de i.

## Les tableaux de taille fixe

`type nom_du_tableau[nombre_elements];`
Un tableau est un ensemble fini d'éléments de meme type, stockes en mémoire a des adresses contigües.
`nombre_elements` doit être une expression constante, entière, et positive.
On accede a la case d'indice i du tableau avec `nom_du_tableau[i]`, avec $0 \leq i \leq \,\text{nombre_elements}-1$

Une allocation **statique** de mémoire est effectuée : la valeur entre les crochets doit donc être une constante.
Le compilateur **peut** accepter une instruction telle que `int tab[n];`, mais ce n'est pas garanti par la norme et peut réduire la performance.
(il est preferable d'utiliser des variables constantes `#define` au lieu de valeurs hardcodées)

Un tableau correspond a un pointeur constant vers le premier element du tableau.
Par consequent, aucune operation globale n'est autorisée, un tableau n'est pas une Lvalue.
Pour faire une copie d'un tableau, il faut copier les cases individuellement, a l'aide d'une boucle par exemple.

`type nom_du_tableau[N] = {var1, var2, ..., varN};` (ou `const` ?)
On peut utiliser cette syntaxe pour initialiser un tableau au moment de sa declaration.

Un tableau est un pointeur constant vers son expression d'un indice 0.
Cette expression est une Lvalue, on peut donc indirectement pointer vers le tableau.
Si p est un pointeur, `p[i]` accede a l'élément stocke a l'adresse `p+i*sizeof(p[0])`
L'expression `p[i]` est équivalente a l'expression `*(p+i)`.
Il n'est pas nécessaire de preciser le nombre d'octets dont on doit se décaler : on connaît deja le type des variables.

Attention ! Accéder a `p[i]` avec i trop grand n'est pas interdit ! On aura alors au mieux une erreur de segmentation, si le programme tente d'accéder a une partie a une partie de la mémoire qui ne lui est pas attribuée, et au pire un comportement non défini.

L'identifiant d'un tableau se comporte comme un pointeur sauf les situations ou on demande sa taille, avec `sizeof` ou avec de l'arithmétique des pointeurs (par exemple `&tab + 1`).
Dans ces deux cas, le compilateur traite le tableau comme un unique bloc de la taille appropriée.

Un tableau de caractères peut être initialisé par une liste de caractères, mais aussi par une chaîne de caractères littérale.
Le compilateur rajoute a la fin de toute chaîne de caractères une caractère special, appellé caractère nul (`'\0'`). Il faudra donc que le tableau ait un nombre d'éléments plus grand de 1 que le nombre de caractères.
On peut obtenir la longueur d'une chaîne de caractères avec `sizeof(chaine) / sizeof(char)`.

`type nom_du_tableau[lignes][colonnes];`
On peut également declarer un tableau a plusieurs dimensions, la syntaxe ci-dessus declare par exemple un tableau a deux dimensions.
Le tableau `tab` (`int tab[5][3];`) est par exemple un pointeur vers `tab[0][0]`, il a donc pour type `int**`, on peut aussi accéder à `tab[0][0]` avec `**tab`.

## Allocation dynamique de tableaux

Tels qu'ils sont définis en C, les tableaux présentent plusieurs problèmes :
- on ne peut définir qu'un tableau de taille connue a l'avance
- une fonction ne peut pas renvoyer un tableau défini localement
- une fonction ne peut pas renvoyer plusieurs objets

Au lieu de retourner un tableau, la fonction suivante retourne un pointeur NULL.
```c
int* fonction() {
	int tab[2] = {4, 2};
	return tab;
}
```

L' **allocation dynamique** permet de définir un tableau de taille variable et arbitraire, dont la portée n'est pas limitée a la fonction qui l'a crée.
Les **structures** permettent de définir des "tableaux" contenant différents types, et sont des Lvalue donc peuvent être renvoyées par une fonction. Leur taille doit néanmoins être constante. Elles seront détaillées dans un chapitre ultérieur !

Avant de manipuler un pointeur, et notamment de lui appliquer l'opérateur de déréférencement `*`, il faut l'initialiser vers une adresse mémoire.
Si on ne connaît pas encore son adresse, il est preferable de l'initialiser avec NULL (qui vaut généralement 0). On peut faire (p == NULL) pour voir si un pointeur est défini.
Il n'est pas nécessaire que l'adresse pointée par p contienne deja une variable. On peut alors directement manipuler `*p`, mais en ayant d'abord alloué un espace mémoire de taille adequate.

`void* malloc(size_t nombre_octets)`
Cette operation se fait en C via la fonction `malloc` du header `<stdlib.h>`. Le type `size_t` est utilise pour décrire une taille en mémoire, on peut l'obtenir avec `sizeof`.
Puisque `malloc` renvoie des adresses de types différents selon la situation (`int*`, `double*`, `char*`, ...), son type de retour est `void*` : ce type joue un role special et le type de la valeur de retour s'adaptera au type de pointeur vers lequel on affecte.

```c
#include <stdlib.h>

int *p;
p = malloc(sizeof(int));
```

Ici, on aurait pu écrire `p = malloc(4)`, mais on préfère utiliser `sizeof` qui crée un code portable (et plus lisible).

`malloc` permet également de stocker plusieurs objets contigus en mémoire, un peu comme un tableau.
Il ne faut pas oublier de libérer l'espace mémoire avec free pour ne pas provoquer de fuites de mémoire.
```c
p = malloc(2 * sizeof(int));
p[0] = 1;
p[1] = 2;
free(p);
```
