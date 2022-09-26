# Chapitre 4 : Discipline de programmation, validation, test
## Intéraction du programme avec son environnement
La fonction main donne le point d'entrée de l'exécution du programme.
Si l'environment passe des arguments au programme, alors ils donnent les
arguments de main.

```c
int main(int argc, char * argv[])
```

Les arguments de main sont :
- argc : compteur du nombre d'arguments du programme, avec le nom du programme
  comme premier argument.
- argv : de longueur argc, un tableau de chaînes de caractères qui contient les
  arguments du programme.

Lorsque le programme se termine, il informe l'environnement selon si son
exécution a fait ce qui est attendu ou pas :
- EXIT_SUCCESS (constante 0 sur Linux et les systèmes POSIX) tout s'est bien
  passé
- EXIT_FAILURE (constante 1 sur Linux et les systèmes POSIX) tout s'est bien
  passé

La valeur entière renvoyée par main est le statut de terminaison que le
programme transmet à l'environnement.

Si on ne l'écrit pas, la fonction main renvoie EXIT_SUCCESS par défaut.

## Spécification et commentaires
Quand on écrit une fonction, même avec un nom descriptif (fortement recommandé),
il peut ne pas être évident à la lecture de savoir ce que sont les arguments, ou
ce que fait précisément la fonction.
On écrit donc 2 lignes de commentaire :
- l'entrée de la fonction, qui précise les valeurs autorisées pour les arguments
  et leurs éventuelles relations
- la sortie qui précise la relation entre la valeur éventuellement renvoyée et
  les arguments ainsi que les éventuels changements effectués dans la mémoire

## Programmation défensive
Au cours du développement d'un programme, on commet souvent des erreurs ne ne
respectant pas la spécification des fonctions. On peut donc utiliser des
assertions afin de provoquer une erreur lors de l'exécution si :
- des arguments ne respectent pas la spécification
- un invariant de boucle n'est pas respecté

Une assertion (`#include <assert.h>`) est formée des mots-clés assert suivi
d'une expression à évaluer comme booléen. Si c'est faux, le programme
s'interrompt.

On peut d'ailleurs lever un message plus explicatif en utilisant l'opérateur
virgule, sous la forme :
```c
#include <assert.h>
int main() {
  assert(("Les mathématiques sont fausses", 1 == 1));
  assert(("POSIX est faux", 1 == 0));
  return 0;
}
```

On peut désactiver les assertions en déclarant la macro NDEBUG avec la directive
`#define NDEBUG`. On peut faire de même en passant au compilateur l'option `-DNDEBUG`.

## Tests
Au fur et à mesure du développement d'un programme on doit tester ses fonctions.
Pour s'assurer de rencontrer tous les cas, on utilise souvent des cas
particuliers, rassemblés dans un fichier séparé qui contient un jeu de test (ou
le génère) et, avec des assertions, vérifie que la sortie de chaque fonction en
prenant en argument un élément du jeu de tests, est conforme à la spécification.

Si ce n'est pas le cas, on utilise d'autres moyens de debugging (GDB, un IDE,
etc.).

Pour compiler les deux fichiers test.c (qui contient main avec les assertions)
et programme.c (qui contient les fonctions à tester) ensemble.
