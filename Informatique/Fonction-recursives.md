# Chapitre 3 : Fonctions récursives
## Définition, preuve de terminaison et de correction

> Une fonction récursive est une fonction dont la définition contient un appel à
> elle-même. Elle doit contenir un branchement tel que pour certaines valours de
> ses arguments, l'exécution de la fonction ne fasse pas appel à elle-même. On
> appelle ceci le cas de base.

Pour toute fonction récursive, il faut prouver par une récurrence que quels que
soient ses arguments la fonction termine (on arrive à un cas de base en un
nombre fini d'appels) et renvoie le bon résultat.

##### Exemples : Factorielle
Soit $n \geq 0$, par récurrence :
- Initialisation : si $n = 0$, $0! = 1$ par définition et factorielle(0) renvoie 1
- Hérédité : Soit $n \geq 1$, supposons que $\forall x \in [0,n-1]\_{\mathbb{N}}$, factorielle(k)
  renvoie k!, alors factorielle renvoie $n \times \text{factorielle(n-1)} = n \times (n-1)! = n!$ par définition.

  Donc la fonction factorielle termine et renvoie le bon résultat par $n \geq 0$.

##### Exemple : Algorithme d'Euclide
```c
int pgcd(int a, int b) {
  if (a == 0) return abs(b);
  else if (b == 0) return abs(a);
  else if (abs(a) >= abs(b)) return pgcd(b, a%b);
  else return pgcd(b, a%b);
}
```

On montre par récurrence sur $n \geq 0$ que $\text{pgcd}(a, b)$ termine et donne
le résultat correct pour $|a| + |b| = N, \forall N \geq 0$.
- Initialisation : $N = 0$, donc $a = b = 0$. $\text{pgcd}(0,0)$ retourne 0, ce
  qui est le résultat attendu
- Hérédité : soit $N \geq 1$, on suppose la propriété vraie pour tout $0 \leq k < N$.
  On suppose $|a| \geq |b|$ sans perte de généralité. On a la disjonction de
  cas :
  - b = 0, alors $\text{pgcd}(a,b)$ renvoie $|a|$, ce qui est la valeur attendue
  - $|b| > 0$, alors $\text{pgcd}(a,b)$ renvoie $\text{pgcd}(b,r)$, où $r$ est
    le reste de la division euclidienne de a par b.
    ........

##### Exponentiation rapide
```c
long int exp_rapide(int a, unsigned b){
  if (b == 0) return 1;
  else if (b%2 == 0){
    long int x = exp_rapide(a, b / 2);
    return x *x;
  } else {
    long int x = exp_rapide(a, b / 2);
    return a * x * x;
  }
}
```

On montre par récurrence sur $b \geq 0$ que $\forall a \in \mathbb{Z}, \text{exprapide(a,b)} = a^b$
- Initialisation : si $b = 0, \text{exprapide}(a,0) = 1 = a^0$
- Hérédité : Soit $b \geq 1$. Supposons $\forall k  \in \[0, b-1\]\_{\mathbb{N}}$,
  $\text{exprapide}(a,k) = a^k$. Par disjonction de cas :
  - b est pair. Dans ce cas, $\text{exprapide}(a,b) = \text{exprapide}(a,\frac{b}{2})^2$.
    Or par hypothèse de récurrence, $\text{exprapide}(a, \frac{b}{2}) = a^{(\frac{b}{2})}$.
    Donc $\text{exprapide}(a, b) = a^b$.
  - b est impair, alors $\text{exprapide}(a,b) = a \times \,\text{exprapide}(a, \frac{b-1}{2})^2$.
    De même, on a alors $\text{explapide}(a,\frac{b-1}{2})^2 = a^{b-1}$, et
    donc $a \times \text{exprapide}(a,\frac{b-1}{2})^2 = a \times a^{b-1} = a^b$

## Pile d'appels
Chaque appel de fonction lors de l'exécution d'un programme crée dans la mémoire
une frame correspondant à l'environnement de la fonction. La frame contient
toutes les variables locales (y compris l'argument), mais aussi un endroit
spécifique pour la valeur de retour, un pointeur vers l'instruction dont on est
parti (qui est en quelque sorte mise en pause). 
Une instruction return charge le résultat dans la valeur de retour, puis quitte
la frame pour revenir à celle depuis laquelle on a appelé la fonction et à
l'instruction d'appel (Instruction Register/Program Counter).
L'instruction utilisant le résultat de la fonction retrouve le résultat à un
endroit spécifié "au-dessus" de la frame courante.

Si une fonction récursive fait trop d'appels imbriqués, on peut avoir des
problèmes de mémoire.
On va donc faire l'arbre des appels et compter en fonction des arguments :
- le nombre total d'appels (la taille de l'arbre)
- le nombre d'appels imbriqués (sa profondeur)

À même type d'appels, on peut compter le nombre d'appels récursifs afin de
commencer à approcher la notion de complexité algorithmique.

Une fonction récursive (sauf récursion terminale, voir plus tard), utilise un
nombre de frames dans la mémoire égal à la profondeur de son arbre d'appel.
Il faut donc prendre garde lorsque cette fonction n'a pas par ailleurs de raison
d'utiliser beaucoup de mémoire.

Il faut prendre garde de ne pas faire d'appels récursifs inutiles car ceux-ci
peuvent faire exploser le nombre total d'appels et le temps d'exécution de la
fonction.

## Dérécursification
Quitte à implémenter de façon itérative la pile (comme un tableau alloué
dynamiquement) et à simuler les appels récursifs tant que la pile n'est pas
vide, on peut décrire un équivalent itératif de toute fonction récursive.
Le résultat de ce processus est en général illisible.

Parfois, il est possible de dérécursiver de façon plus élégante en étudiant
l'arbre des appels. Par exemple, on peut écrire l'exponentiation rapide comme
une boucle for ou while. Encore plus efficacement, on peut constater que cette
fonction ne multiplie par a à la profondeur i que le bit de poids $2^i$ de b est 1.
En effet, le résultat de profondeur i est élevé i fois au carré. Ce a devient
ainsi $a^{2^{2 \ldots^2}} = a^{2i}$.

On peut donc directement écrire b en binaire et multiplier un accumulateur par
$a^{2i}$ quand le i-ème bit est un 1.

```c
#include <stdio.h>
#include <stdint.h>

long int exp_rapide(int a, uint32_t b) {
  long int resultat = 1;
  int8_t bit_b = b%2;
  long int puissance = a;
  for (int i = 0; i < 32; i++) {
    if (bit_b == 1) {
      resultat *= puissance;
    }
    b = b / 2;
    bit_b = b%2;
    puissance = puissance * puissance;
  }
  return resultat;
}
```

## Récursivité croisée
> Plusieurs fonctions qui forment un ensemble sont dites mutuellement récursives
> si il existe un cycle $f1 \to f2 \to \ldots \to fn \to f1$ de fonction de cet
> ensemble telle que chaque fonction appelle la suivante dans le cycle dans sa
> définition.

##### Exemple
```c
bool impair(int);
bool pair(int n) { return n == 0 || impair(n-1); }
bool impair(int n) { return n !=0 && pair(n-1); }
```

En C, il faut déclarer les fonctions avant de les utiliser dans une autre
définition de fonction. On peut déclarer une fonction sans la définir.
On peut déclarer une fonction sans la définir, ce qui est nécessaire pour des
fonctions mutuellement récursives.

##### Exemple : décision du vainqueur aux échecs depuis une position
On est au tour du joueur rouge. On souhaite vérifier si le joueur rouge va
gagner.
Pour cela, on peut appeler une fonction potentielle "rouge_joue_et_gagne" qui
renvoie si pour tout coup légal de rouge, tous les coups de bleu l'amènent à
perdre, et sinon renvoie faux lorsqu'il n'y a pas de coup légal.
Pour cela, on utilise donc une fonction "bleu_joue_et_perd" qui essaie tous les
coups de légaux de bleu, et vérifie si rouge gagne à ce coup.

Ces deux fonctions vont donc s'entre-appeler, afin de déterminer le vainqueur.

On peut toujours (bien que ça ne clarifie pas nécessairement le code) écrire n
fonctions mutuellement récursives comme une seule fonction récursive avec switch
... case.
