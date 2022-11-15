# Chapitre 7 : Complexité
## Définition, profils de complexité
> La complexité en temps (ou temporelle) d'un algorithme est le nombre
> d'opérations atomiques réalisées par l'algorithme en fonction d'une ou plusieurs grandeurs qui
> caractérise l'entrée.

> La complexité en espace (ou spatiale) d'un algorithme est la quantité de
> mémoire utilisée (au plus) lors de son exécution, en fonction d'une ou plusieurs grandeurs qui
> caractérise l'entrée.

Par défaut, on calcule la complexité dans le pire cas, c'est à dire qu'on
suppose que l'entrée set celle qui nécessite le plus d'opérations (ou le plus de
mémoire) parmi les entrées décrites par la grandeur (par exemple, parmi les
tableaux d'entiers de taille n).

Comme la définition précise d'une opération atomique peut dépendre du système, et
comme le comptage exact peut être fastidieux, on donnera un ordre de grandeur à
coefficient multiplicatif près de la complexité.

### Notations de Landau
Soient $f,g$ deux fonction $\mathbb{N}^{\ast} \to \mathbb{N}^{\ast}$ :
- Si $\exists C \in \mathbb{R}^{\ast}_{+}$ tel que
  $\forall n \in \mathbb{N}, f(n) \leq C g(n)$, on note $f(n) = O(g(n))$
- Si $\exists C \in \mathbb{R}^{\ast}_{+} \mid \forall n \in \mathbb{N}^{\ast}$,
  $f(n) \geq C g(n)$, on note $f(n) = \Omega(g(n))$.
  On a ainsi $f(n) = \Omega(g(n)) \Leftrightarrow g(n) = O(f(n))$.
- Si $\exists C_1, C_2 \in \mathbb{R}^{\ast}_{+} \mid \forall n \in \mathbb{N}^{\ast}$,
  $C_1 g(n) \leq f(n) \leq C_2 g(n)$, alors on note
  $f(n) = \Theta(g(n))$.
- Si $\lim\limits_{n \to + \infty} \frac{f(n)}{g(n)} = 0$, alors on note $f(n) = O(g(n))$.
  (voir preuve ci-dessous).
- Si $\lim\limits_{n \to + \infty} \frac{f(n)}{g(n)} \leq 1$, alors
  on note $f(n) ~_{n \to +\infty} g(n)$. On a ainsi
  $f(n) ~_{n \to +\infty} g(n) \Rightarrow f(n) = \Theta(g(h))$

Si on a $f(n) = \Theta(g(n)) \Leftrightarrow f(n) = O(g(n)) \land f(n) = \Omega(g(n))$

##### Preuve
Si $\frac{f(n)}{g(n)} \to_{n \to  +\infty} 0$, alors
$\exists N \in \mathbb{N} \mid \forall n \geq N, \frac{f(n)}{g(n)} \leq 1$.
Soit $C = max(1, \text{max}_{n \in [1, N-1]_{\mathbb{N}}}(\frac{f(n)}{g(n)}))$.
Donc $\forall n \in \mathbb{N}, \frac{f(n)}{g(n)} \leq C$, donc
$f(n) = O(g(n))$.

### Ordres de complexité
On parle de complexité :
- constante si $C(n) = O(1)$
- logarithmique si $C(n) = O(\log n)$
- polylogarithmique si $C(n) = O(\log^k n)$ (pour $k \in \mathbb{N}^{\ast}$)
- linéaire si $C(n) = O(n)$
- quasi-linéaire si $C(n) = O(n \log^k n)$
- quadratique si $C(n) = O(n^2)$
- polynomiale si $C(n) = O(n^k)$
- exponentielle si $C(n) = O(k^n) = 2^{O(n)}$

Si la fonction n'est pas récursive :
- on compte le nombre d'itérations de chaque boucle (facile pour les for,
  nécessite de regarder le variant de boucle pour les while)
- on marque les multiplicateurs sur les corps de boucle
- on obtient un ordre de grandeur de la complexité

Si la fonction est récursive, on obtient une définition par récurrence d'une
majoration de la complexité dans le pire cas. Il faut ensuite en tirer une
majorité en fonction de n.

##### Preuve de la complexité de l'exponentiation rapide
On montre par récurrence sur $n \geq 1$ que $C(n) \leq 6 \left\lfloor \log n \right\rfloor + 8$ :
- Initialisation : On a $C(1) = 8$ dans l'implémentation donnée (facile à
  déterminer par simple comptage).
- Hérédité : Soit $n \geq 2$, on suppose $\forall k \in [1, n-1]_{\mathbb{N}}, C(k) \leq 6 \left\lfloor \log k \right\rfloor + 8$.
  Soit $i = \left\lfloor \log n \right\rfloor$ le plus grand entier tel que $2^i \leq n$, on
  a donc $2^{i-1} \leq \frac{n}{2} < 2^i$. Comme $2^{i-1}$ est entier,
  $2^{i-1} \leq \left\lfloor \frac{n}{2} \right\rfloor < 2^i$.
  Ainsi, $i-1 = \left\lfloor \log \frac{n}{2} \right\rfloor$, donc
  $C(\left\lfloor \frac{n}{2} \right\rfloor) \leq 6 \left\lfloor \log \frac{n}{2} \right\rfloor + 8$
  par hypothèse de récurrence et donc
  $C(\left\lfloor \frac{n}{2} \right\rfloor) \leq 6 (\left\lfloor \log n \right\rfloor + 1) + 8$.
  Or $C(n) \leq C(\left\lfloor \frac{n}{2} \right\rfloor) + 6$,
  donc $C(n) \leq 6 \left\lfloor \log n \right\rfloor + 8$.

On remarque d'ailleurs que $\left\lfloor \frac{n}{2} \right\rfloor < n$ et
$n \geq 2$, donc $\frac{n}{2} \geq 1$, donc
$\left\lfloor \frac{n}{2} \right\rfloor \geq 1$.

Ainsi, $C(n) = O(\log n)$.

#### Propriétés
Soient $f, g, h, k \in \mathbb{N}^{\ast} \to \mathbb{R}^{\ast}_{+}$.
- Si $f(n) = O(g(n))$ et $h(n) = O(k(n))$ alors $f(n)h(n) = O(g(n)k(n))$
- Si $f(n) = O(g(n))$ et $g(n) = O(k(n))$ et $h(n) = O(k(n))$ alors $f(n) + h(n) = O(k(n))$
- Si $f(n) = O(g(n))$ et $g(n) = O(k(n))$ alors $f(n) = O(k(n))$
- Si $f(n) = \Omega(g(n))$ et $h(n) = \Omega(k(n))$ alors $f(n)h(n) = \Omega(g(n)k(n))$
- Si $f(n) = \Omega(g(n))$, alors $f(n) + h(n) = \Omega(g(n))$
- Si $f(n) = \Omega(g(n))$ et $g(n) = \Omega(k(n))$ alors $f(n) = \Omega(k(n))$

On en déduit les propriétés sur $\Theta$ en utilisant
que $f(n) = \Theta(g(n)) \Leftrightarrow \left\{\begin{matrix} f(n) = O(g(n)) \\ f(n) = \Omega(g(n)) \end{matrix}\right.$.

##### Preuve
Troisième assertion : $\exists C_1 > 0, \forall n \in \mathbb{N}^{\ast}, f(n) \leq C_1 g(n)$ et
$\exists C_2 > 0, \forall n \in \mathbb{N}^{\ast}, g(n) \leq C_2 h(n)$. Soit
$C = C_1 C_2 > 0, n  \in \mathbb{N}^{\ast}$, alors
$f(n) \leq C_1 g(n) \leq C_1 (C_2 h(n)) \leq C h(n)$, donc
$f(n) = O(h(n))$.

## Complexité des opérations sur les structures de données séquentielles
### Les tableaux
- Créer/détruire : on ne précise pas de complexité car ces opérations ne sont
  faites qu'une seule fois sur ces structures. En pratique, $O(n)$ ou souvent
  $O(1)$.
- Accéder/modifier une valeur d'un indice i : C est usuellement constant de
  valeur $1$. Il suffit d'aller à l'emplacement d'adresse $t + taille \times i$
- Longueur des tableaux : Coût constant si l'implémentation le permet. En C, il
  fait donc retenir la taille du tableau.

### Listes chaînées
- Créer/détruire : $\Theta(1)$
- Renvoyer/modifier la queue de la liste : $\Theta(1)$
- Renvoyer la queue de la liste (depuis une structure de contrôle qui la
  conserve, si tel est le cas) : $\Theta(1)$

Les listes chaînées sont conçues pour que l'opération de base soit de passer au
maillon suivant ou de faire un nouveau maillon pointant vers un maillon
existant. Toutes ces opérations doivent donc avoir un coût constant.

Avec $n$ la taille de la liste, ces opérations complexes sont :
- Obtenir la longueur d'un liste (sauf dans le cas constant d'un liste qui
  conserverait la longueur de la liste) : $\Theta(n)$
- Suppression d'une liste : $\Theta(n)$

Ces opérations nécessitant de parcourir tous les maillons de la liste, leur
complexité est linéaire de la longueur de la liste.

Soit $i$ un indice dans la liste (c'est à dire plus petit que la longueur de la
liste) :
- Accès au $i$-ème élément : $\Theta(i)$
- Insertion au rang $i$ : $\Theta(i)$
- Suppression du $i$-ème élément : $\Theta(i)$
- Concaténation de deux listes (ou $\Theta(1)$, il s'agit de la même complexité
  que celle de l'obtention de la queue de la liste) : $\Theta(n)$

Ces deux opérations au milieu de la liste prennent seulement $\Theta(1)$ pour une
implémentation de la liste chaînée sur un tableau dynamique, mais la
concaténation demande des besoins particulièrement différents.
Le fait que le coût marginal de la suppression et de l'insertion dans un
parcours soit constant permet, par exemple, de parcourir une liste chaînée triée
en supprimant les doublons en temps $\Theta(n)$.

### Les tableaux dynamiques
- Créer, détruire, accéder et modifier : comme un tableau simple.
- Changer la taille : $\Theta(n)$
- Push (ajouter un élément à la fin de la liste) : $\Theta(1)$ (en coût amorti,
  seulement si on n'a pas besoin de faire grandir le tableau).

> La complexité amortie d'une opération sur une structure est la limite
> $\lim\limits_{k \to + \infty} \frac{C_k(n)}{k}$ où $C_k(n)$ est le coût de
> répéter $k$ fois l'opération sur une structure de taille n.

##### Preuve du coût amorti du push sur les tableaux dynamiques
Soit T un tableau dynamique de taille initiale $n_0 > 0$ et de capacité initiale
$c_0 \geq n_0$. Si on effectue $k$ push successifs sur T, à chaque push la
taille augmente de 1 et est donc inférieure à 2 fois la capacité.
Donc les capacités successives de T seront de $c_0, 2c_0, \ldots, 2^n c_0$.
Ainsi, $\frac{C_k(n)}{k} = \frac{1}{k} \sum\limits_{i = 1}^{k} \text{coût du i-ème push}$,
avec le coût du i-ème push de $\Theta(n_0 + i)$ si $n_0 + i = 2^j c_0 + 1$ (pour
un certain $j \in \mathbb{N}$) et $\Theta(1)$ sinon.

Ainsi, le coût du i-ème push est majoré, avec un certain $K > 0$, par
$K(n_0 + i)$ dans le premier cas et $K$ sinon.
On obtient ainsi $\frac{C_k(n)}{k} \leq \frac{1}{k} (\sum\limits_{i = 1}^{k} K + \sum\limits_{j = 0}^{r} K 2^j c_0)$
$\leq K + \frac{1}{k} K c_0 2^{r + 1}$.
Or, la taille finale de T est $n_0 + k$, donc $r$ est le plus petit entier tel
que $2^r c_0 \geq n_0 + k$, soit $r = \left\lceil \log_2 \frac{(n_0 + k)}{c_0} \right\rceil$.

$\frac{C_k(n)}{k} \leq K + \frac{K_{c_0}}{k} 2^{\log_2 \frac{n_0 + k}{c_0} + 2}$\
$\leq K + \frac{4K_{c_0} (n_0 + k)}{k c_0}$\
$\leq 5K + \frac{4K_{n_0}}{k}$\
$\to_{k \to +\infty} 5K$\
On a donc bien que la complexité amortie du push est $O(1)$ (une constante).
Comme chaque push coûte plus d'une opération, $\frac{C_k(n)}{k} \geq 1$, donc la
complexité amortie est $\Theta(1)$.

## Complexité autre que dans le pire cas
### Complexité dans le meilleur cas :
- Regarder la complexité dans le meilleur cas pour une entrée de taille donnée
  permet de savoir si l'algorithme gâche des opérations sur le pire cas. Il
  est parfois possible de le réécrire de façon à équilibrer les coûts.
- Si les ordres de grandeur des complexités dans le pire et le meilleur cas
  sont différents, il peut être pertinent de s'intéresser au cas moyen, ou à
  la complexité amortie dans le cas d'une structure.

### Complexité amortie
Voir définition ci-dessus.

### Complexité moyenne
#### Moyenne sur toutes les entrées de taille n
Si et seulement si cet ensemble est "gérable".

##### Exemple
Pour choisir T au hasard parmi les tableaux avec $k$ "1" et $n-k$ "0", on tire
$i_1,\ldots, i_k$ des indices dépendants qui contiennent les "1". Chaque indice
$i_j$ suit une loi uniforme sur $[0, n-1]_{\mathbb{N}}$ si on ne conditionne pas
pas sur les autres.
Comme chaque valeur est échangée au plus une fois lors du tri, le nombre
d'échanges est le nombre de "1" mal placés. Soit $X$ cette quantité,
$E(X) = E(\sum\limits_{j = 1}^{k} 1_{i_j < n-k})$ (somme d'indicatrices).
On a alors par linéarité de l'espérance
$E(X) = \sum\limits_{j = 1}^{j} E(1_{i_j < n-k})$\
$= \sum\limits_{j = 1}^{k} P(i_j < n-k)$\
$= \sum\limits_{j = 1}^{k} \frac{n-k}{n}$\
$= \frac{k (n-k)}{n}$

#### Modèle des tableaux aléatoires
Si un algorithme prend en entrée un tableau quelconque et que la complexité ne
dépend que des comparaisons entre valeurs, plutôt que de raisonner sur tous les
tableaux de taille n représentables par la machine, on se donne un tableau dont
les valeur sont muette, qu'on suppose ordonné selon un des $n!$ ordres
possibles tirés au hasard.

#### Moyenne sur l'aléa
Dans le cas d'un algorithme randomisé (qui utilise une source de hasard), on
fait l'espérance de la complexité pour chaque cas, puis on prend la pire des
espérances.
