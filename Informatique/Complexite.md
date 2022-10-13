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
- Si $\lim\limits_{n \to + \infty} \frac{f(n)}{g(n)}$, alors on note $f(n) = O(g(n))$.
  On a ainsi $f(n) = o(g(n)) \Rightarrow f(n) = O(g(n))$ (voir preuve ci-dessous).
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
