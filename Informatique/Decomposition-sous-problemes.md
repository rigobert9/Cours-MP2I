# Chapitre 11 : Décomposition d'un problème en sous-problèmes
## Diviser pour régner
Il s'agit de l'appellation des algorithmes récursifs où on divise le problème en
$k \geq 1$ problèmes qu'on résout indépendamment tant qu'on arrive pas au cas de base,
puis qu'on résout par $k$ appels récursifs les sous-problèmes, et enfin on les
rassemble en remontant les apples récursifs.

Si les étapes diviser et rassembler ont ensemble une complexité $f(n)$, alors la
complexité, alors la complexité de notre algorithme vérifiera
$\forall n, C(n) \leq kC(\left\lfloor qn \right\rfloor) ) f(n)$.

Par exemple :
- $C(n) = 2 C(\left\lfloor \frac{n}{2} \right\rfloor) + \Theta(n) \Rightarrow C(n) = \Theta(n \log n)$
- $C(n) = C(\left\lfloor \frac{n}{2} \right\rfloor) + \Theta(1) \Rightarrow C(n) = \Theta(\log n)$
- $C(n) = 2 C(\left\lfloor \frac{n}{2} \right\rfloor) + o(n) \Rightarrow C(n) = \Theta(n)$

## Exemples simples déjà connus
### Recherche dichotomique
On cherche à trouver des éléments dans un ensemble trié. On n'engendre à chaque
fois qu'un seul problème, de la taille de la moitié de la taille actuelle.
Dans le cas de base, on revoie simplement l'indice. On recherche donc dans ce
cas dans 0 ou 1 indices.

### Exponentiation rapide
- Problème : calculer $a^n$
- Cas de base : $n = 0$
- Diviser : calculer $a^{\left\lfloor \frac{n}{2} \right\rfloor}$
- Régner : 1 appel récursif
- Rassembler : Une ou deux multiplications
- Forme du problème : $C(n) = C(\left\lfloor \frac{n}{2} \right\rfloor) + \Theta(1)$

On suppose $\exists K_1,K_2 > 0, \forall n \geq 2, 2 C(\left\lfloor \frac{n}{2} \right\rfloor) + K_1 n \leq C(n) \leq 2 C(\left\lfloor \frac{n}{2} \right\rfloor) + K_2 n$.
On montre par récurrence sur $n$ que $\forall n \geq 2, K_3 n \log(n) \leq C(n) \leq K_4 n \log(n) = P(n)$,
avec $K_3 = \text{min}(\frac{C(2)}{2}, \frac{C(3)}{3 \log(3)}, \frac{K_1}{\frac{3}{2} + \log(\frac{3}{2})})$
et $K_4 = \text{max}(\frac{C(2)}{2}, \frac{C(3)}{3 \log(3)}, K_2)$.

Initialisation : $K_3 2 \log(2) \leq C(2)$, car $K_3 \leq \frac{C(2)}{2}$.
$C(2) \leq K_4 2 \log(2)$ car $K_4 \geq \frac{C(2)}{2}$.
$K_3 3 \log(3) \leq C(3)$ et $K_4 \geq \frac{C(3)}{3 \log(3)}$.

Hérédité : Soit $n \geq 4$. On suppose $\forall k \in [\![2, n - 1]\!], P(k)$.
Alors $\left\lfloor \frac{n}{2} \right\rfloor \in [\![2,n-1]\!]$, donc
$K_3 \left\lfloor \frac{n}{2} \right\rfloor \log(\left\lfloor \frac{n}{2} \right\rfloor) \leq C(\left\lfloor \frac{n}{2} \right\rfloor)$
$\leq K_4 \left\lfloor \frac{n}{2} \right\rfloor \log(\left\lfloor \frac{n}{2} \right\rfloor)$.
De plus, $K_1 n + 2 C(\left\lfloor \frac{n}{2} \right\rfloor) \leq C(n) \leq 2 C(\left\lfloor \frac{n}{2} \right\rfloor) + K_2 n$,
donc $K_1 n + 2 K_3 \left\lfloor \frac{n}{2} \right\rfloor \log(\left\lfloor \frac{n}{2} \right\rfloor) \leq C(n) \leq 2 K_4 \left\lfloor \frac{n}{2} \right\rfloor \log(\left\lfloor \frac{n}{2} \right\rfloor) + K_2 n$.
Puisque $\frac{n-1}{2} \leq \left\lfloor \frac{n}{2} \right\rfloor \leq \frac{n}{2}$,
$K_1 n + K_3 (n-1) \log(n-1) \leq C(n) \leq K_4 n \log(\frac{n}{2}) + K_2 n$
$\Leftrightarrow K_1 n - K_3 \log(\frac{n-1}{2}) + K_3 n [\log(n) - \log(\frac{n}{n-1}) - 1] \leq C(n) \leq K_4 n \log(n)$.

### Exemples avec le merge sort et le quick sort
- Problème : trier $n$ indices consécutifs d'un tableau
- Cas de base : Tableau à $1$ ou $0$ éléments (rien à trier)

### Merge sort
- Diviser : On coupe l'ensemble des indices à trier en deux moitiés égales à $1$
  près
- Régner : 2 appels récursifs
- Complexité : Soit $n = \text{fin} - \text{deb}$, on étudie la complexité dans
  le pire cas du tri fusion. Si $n \leq 1$, la complexité du programme est de 2.
  Sinon, la division a une complexité constante, le règne se fait en une
  complexité $C(\left\lfloor \frac{n}{2} \right\rfloor) + C(\left\lceil \frac{n}{2} \right\rceil )$,
  et le rassemblement se fait en une complexité $n$.

$\forall n \geq 2, C(n) = C(\left\lfloor \frac{n}{2} \right\rfloor) + C(\left\lceil \frac{n}{2} \right\rceil) + \Theta(n)$.
$\exists K_1,K_2, \forall n \geq 2, C(n) \leq C(\left\lfloor \frac{n}{2} \right\rfloor) + C(\left\lceil \frac{n}{2} \right\rceil) + K_2 n$
et $C(n) \geq C(\left\lfloor \frac{n}{2} \right\rfloor) + C(\left\lceil \frac{n}{2} \right\rceil) + K_1 n$.

Montrons par récurrence sur $n$ que $\forall n \geq 1, C(n) \geq K_3 n \log(n)$.
- Initialisation : $K_3 \times 1 \times \log(1) = 0$, donc $C(1) \geq K_3 \times 1 \times \log(1)$.
- Hérédité : Soit $n \geq 2$, on suppose $\forall k \in [\![1,n-1]\!], C(k) \geq K_3 k \log(k)$.
  $n \geq 2$ donc $\left\lfloor \frac{n}{2} \right\rfloor \geq 1, \left\lceil \frac{n}{2} \right\rceil, \left\lfloor \frac{n}{2} \right\rfloor \geq 1$,
  $\left\lfloor \frac{n}{2} \right\rfloor \leq \frac{n}{2} \leq n$ et
  $\left\lceil \frac{n}{2} \right\rceil \leq \frac{n+1}{2} \leq n$.\
  On va donc appliquer l'hypothèse de récurrence à $\left\lfloor \frac{n}{2} \right\rfloor$
  et à $\left\lceil \frac{n}{2} \right\rceil$, donnant
  $C(n) \geq C(\left\lfloor \frac{n}{2} \right\rfloor) + C(\left\lceil \frac{n}{2} \right\rceil) + K_2 n$
  $\geq K_3 \left\lfloor \frac{n}{2} \right\rfloor \log(\left\lfloor \frac{n}{2} \right\rfloor) + K_3 \left\lceil \frac{n}{2} \right\rceil \log(\left\lceil \frac{n}{2} \right\rceil) + K_1 n$\
  $\geq K_3 \frac{n-1}{2} \log(\frac{n-1}{2}) + K_3 \frac{n}{2} \log(\frac{n}{2}) + K_1 n$\
  $\geq K_3 \frac{n}{2} \log(\frac{n}{2}) - K_3 \frac{n}{2} \log(\frac{n}{n-1}) - \frac{K_3}{2} \log(\frac{n-1}{2}) + K_3 \frac{n}{2} \log(\frac{n}{2}) + K_1 n$\
  $\geq K_3 n \log(n) - K_3 n + K_1 n - K_1 \frac{n}{2} - \frac{K_3 n}{4}$\
  Or, $K_1 \geq K_3 + \frac{K_3}{2} + \frac{K_3}{4}$, donc
  $-K_3 n + K_1 n - K_3 \frac{n}{2} - K_3 \frac{n}{4} \geq 0$,
  donc $C(n) \geq K_3 n \log(n)$.

On montre ensuite par récurrence sur $n$ que $\forall n \geq 2, C(n) \leq K_4 n \log(n)$.
- Initialisation : Pour $n = 2$, $C(2) \leq K_4 2 \log(2)$ car $K_4 \geq \frac{C(2)}{2}$.
  Pour $n = 3$, $C(3) \leq K_4 3 \log(3)$ car $K_4 \geq \frac{C(3)}{3 \log(3)}$.
- Hérédité : Soit $n \geq 4$, on suppose $\forall k \in [\![2,n-1]\!], C(k) \leq K_4 k \log(k)$,
  $C(n) \leq C(\left\lfloor \frac{n}{2} \right\rfloor)) + C(\left\lceil \frac{n}{2} \right\rceil) + K_2 n$.
  Or, $\left\lfloor \frac{n}{2} \right\rfloor \geq \left\lfloor \frac{4}{2} \right\rfloor = 2$,
  $\left\lceil \frac{n}{2} \right\rceil \leq 2$, et
  $\left\lceil \frac{n}{2} \right\rceil \leq \left\lceil \frac{n}{2} \right\rceil \leq \frac{n-1}{2} \leq n$.\
  On peut donc appliquer l'hypothèse de récurrence :\
  $C(n) \leq K_4 \left\lfloor \frac{n}{2} \right\rfloor \log(\left\lfloor \frac{n}{2} \right\rfloor) + K_4 \left\lceil \frac{n}{2} \right\rceil \log(\left\lceil \frac{n}{2} \right\rceil) + K_2 n$\
  $\leq K_4 \frac{n}{2} \log(\frac{n}{2}) + K_4 \frac{n+1}{2} \log(\frac{n+1}{2}) + K_2 n$\
  $\leq K_4 \frac{n}{2} \log(\frac{n}{2}) + K_4 \frac{n}{2} \log(\frac{n}{2}) + K_4 \frac{n}{2} \log(\frac{n+1}{n}) + \frac{K_2}{2} \log(\frac{n+1}{2}) + K_2 n$\
  $\leq K_4 n \log(n) - K_4 n + K_4 \frac{n}{2} + \frac{K_2}{4} n + K_2 n$\
  Or, $-K_4 + \frac{K_4}{2} + \frac{K_4}{4} + K_2 = \frac{-K}{4} + K_2 \leq 0$
  car $K_4 \geq 4 K_2$, donc $C(n) \leq K_4 n \log(n)$.

Enfin, on prouve par récurrence sur la taille du tableau la correction et la
terminaison du tri fusion.
- Initialisation : si $n = 1$ ou $n = 1$, il n'y a plus rien à trier,
  l'algorithme se vide et le tri est correct.
- Hérédité : Soi $n \geq 2$, et $t$ un tableau d'éléments, on suppose que
  l'algorithme est correct sur tout les tableaux de taille $k \leq n-1$, donc
  en particulier sur les sous-tableaux (phase régner). On montre l'invariant de
  boucle suivant sur la phase rassembler : pour l'indice $i$ dans la boucle, $\text{aux}[0 \ldots i]$
  contient dans l'ordre les $i$ plus petits éléments du tableau $\text{t}[\text{deb} \ldots \text{fin} - 1]$.
  - Initialisation : pour $i = 0$, après le passage, $\text{aux}[0] = \text{min}(\text{t}[\text{deb}], \text{t}[m])$.
    Or, par hypothèse de récurrence, $\text{t}[\text{deb}] = \text{min}(\text{t}[\text{deb} \ldots \text{fin} - 1])$,
    et $\text{t}[m] = \text{min}(\text{t}[m \ldots \text{fin} - 1])$. Ainsi, $\text{aux}[0]$
    $= \text{min}(\text{t}[\text{deb} \ldots \text{fin} - 1])$.
  - Hérédité : On suppose que dans $\text{aux}[0 \ldots i - 1]$ sont les valeurs
    attendues. Soit $j$ tel que $\text{min}(i) = \text{t}[j]$. Par hypothèse de
    récurrence, $\text{t}[j]$ est plus grand que toutes les valeurs prises dans
    le même sous-tableau, et est plus petit que toutes les autres valeurs des
    mêmes sous-tableaux.
    Soit $\text{aux}[i \ldots 1]$ est dans le même sous-tableau que $\text{t}[j]$,
    alors par hypothèse de récurrence, tous les éléments de $\text{aux}[0 \ldots i - 1]$
    sont plus petits que $\text{aux}[i-1]$, donc plus petits que $\text{t}[j] = \text{aux}[i]$.
    De même dans l'autre cas.

On a donc prouvé l'invariant de boucle, donc à la fin de la phase rassembler, le
tableau est trié. L'algorithme est donc correct sur tous les tableaux.

## Tri rapide
- Diviser : On prend une case de la partie à trier, puis on répartit les valeurs
  restantes selon la comparaison avec ce point.
- Régner : Soit $n$ le nouvel indice du point, on trie récursivement
  $\text{t}[\text{deb} \ldots (n-1)]$ et $\text{t}[(n+1) \ldots \text{fin}]$
- Rassembler : rien à faire.
- Complexité : la division est de complexité $\Theta(n)$. Dans le cas ou le
  pivot est toujours le plus petit, on a $C(n) = \Theta(n) + C(n-1) = \Theta(n^2)$.
  Si le pivot est toujours le plus grand élément, on se retrouve dans le même
  cas. Si le pivot se retrouve toujours à être la médiane, alors la complexité
  $\Theta(n \log(n))$.

## Plus proches paire parmi $n$ points du plan
- Problème : On cherche à déterminer parmi un ensemble de points d'un plan
  orthonormé (dont on possède les coordonnées) la paire ayant la plus petite
  distance possible.
- Algo naïf : On teste les distances entre tous les points et on retient le
  score minimal, en plus des points permettant de l'atteindre. L'idée donne un
  raisonnement de complexité $\Theta(n^2)$.
- Précalcul : On prépare deux tableaux, l'un des points triés par abscisse et
  l'autre des points triés par ordonnée
- Cas de base : Lorsqu'il ne reste plus que deux points, alors la distance
  entre ces deux points est la distance minimale
- Division : On sépare l'ensemble des points du plan selon la médiane des
  points de l'ensemble, et on appelle récursivement sur ces deux divisions.
  On obtient le minimum de la distance des deux côtés, et on vérifie s'il
  existe une paire dans un bandeau de deux fois cette longueur autour de la
  ligne de séparation...
- Complexité : la formule de la complexité est la même que pour celle du tri fusion

## Master Theorem
Soit $a,b \in \mathbb{N}^{\ast}$, $c \in \mathbb{R}_{+}$,
$h_1,h_2,\ldots,h_n \in \mathbb{N} \setminus \{0,1\} \to \mathbb{R}$ telles que
$h_i(n) = O(\frac{n}{\log^2(n)})$.
Soit $\begin{aligned} f: \mathbb{N}^{\ast} &\to \mathbb{N}^{\ast} \\ \forall n \geq n_0, f(n) = (\sum\limits_{i = 1}^{b} f(\frac{n}{a} + h_i(n))) + \Theta(n^c) .\end{aligned}$.

Ainsi, il s'agit d'un algorithme quelconque tel que :
- Division : on coupe en sous-problèmes de taille $\frac{n}{a}$ (à la correction
  $h_i(n)$ près).
- Règne : On appelle $b$ fois la fonction récursivement sur les sous-problèmes.
- Rassemblement : On effectue des opérations de coût total $\Theta(n^c)$.

Dans ce cas, on a :
- si $\log_a(b) < c, f(n) = \Theta(n^c)$
- si $\log_a(b) > c, f(n) = \Theta(n^{\log_a(b)})$
- si $\log_a(b) = c, f(n) = \Theta(n^c \log^n)$

## Rencontre au milieu
La "rencontre" au milieu consiste à prendre un problème que l'on résout par
recherche exhaustive dans un certain ensemble, et couper le problème en deux ce
qui fait que la taille de l'ensemble où on cherche diminue.

Cependant, les sous-problèmes sont alors de nature différente, et on en peut pas
utiliser cette méthode de façon récursive comme pour la méthode diviser pour
régner.

Si la taille de l'ensemble où on cherche est $O(n^k)$, où $n$ est la taille du
problème, et $k$ un entier, alors la taille des deux ensembles correspondent aux
sous-problèmes est $O(\frac{n^k}{2^k})$, soit $O(n^k)$.

On n'a alors rien gagné sur l'ordre de grandeur de la complexité. La rencontre
au milieu ne s'applique donc qu'à des problèmes où l'espace de recherche est
plus que polynomial (typiquement, $\Theta(2^k)$).

Les sous-problèmes sont d'une nature différente du problème initial :
- Dans le problème initial, on cherche parmi les $x \in E$ celui qui vérifie une
  propriété $P(x,E)$.
- Dans les sous-problèmes, pour chaque $x_1 \in E_1, x_2 \in E_2$, on calcule
  une valeur $f(x_1)$ ou $g(x_2)$.
  On va dans un second temps retrouver $x$ à partir de $\{f(x_1)\}_{x_1 \in E_1}$
  et $\{g(x_2)\}_{x_2 \in E_2}$.

Si $E$ est de taille $\Theta(2^k)$, alors construire $\{f(x_1)\}_{x_1 \in E}$
et $\{g(x_2)\}_{x_2 \in E}$ coûte $\Theta(2^{\frac{n}{2}})$ opérations (en
supposant que $f$ et $g$ soient de complexité constante), et $\Theta(n^{\frac{n}{2}})$
mémoire. La seconde partie ne peut pas être une recherche exhaustive sur
$E_1 \times E$ car alors on retrouve un coût $\Theta(n^{\frac{n}{2} n^2})$
soit $\Theta(2^k)$.
Il fait utiliser la structure du problème pour trouver un algorithme plus
efficace.

La rencontre au milieu est une concession de beaucoup de mémoire pour un gain en
vitesse d'exécution. En effet, l'algorithme naïf parcourt $E$ et cherche le bon
$x$ ne nécessite en général qu'une mémoire logarithmique en la taille de $E$
($\Theta(n)$ dans l'exemple précédent).

### Recherche de la plus grand somme majorée

```ocaml
let puiss_2 n = 1 lsl n (* puissances de 2 *)

let plus_grande_somme_majoree t m =
  (* 
    Renvoie les plus grande somme d'éléments de t qui est
    inférieure ou égale à m.
    Tous les éléments de t sont des entiers positifs.
  *) 
  let n = Array.length t in


  (*
     Rencontre au milieu : on liste les 2^(n/2) sommes de la partie gauche,
     et les 2^((n+1)/2) sommes de la partie droite
  *)
  let sommes_g = Array.make (puiss_2 (n / 2)) 0 in
  let sommes_d = Array.make (puiss_2 ((n + 1) / 2)) 0 in (* (n+1)/2 est la partie entière supérieure de n/2 *)
  
  let rec tableau_sommes sommes i deb fin ajout =
    (* 
      Met dans le tableau "sommes", à partir de l'indice i,
      toutes les sommes constituées d'éléments de t
      dont l'indice est entre deb et fin (fin exclus).
      On ajoute "ajout" à chacune de ces sommes.
      La fonction renvoie le premier indice non modifié de "sommes".
    *)
    if deb >= fin then (sommes.(i) <- ajout; i + 1)
    (* il n'y a que la somme de l'ensemble vide, elle est nulle *)
    else
      let j = tableau_sommes sommes i (deb + 1) fin ajout in
      tableau_sommes sommes j (deb + 1) fin (ajout + t.(deb))
  in
      
  let _ = tableau_sommes sommes_g 0 0 (n / 2) 0 in
  let _ = tableau_sommes sommes_d 0 (n / 2) n 0 in
  

  (* On trie l'un des tableaux de sommes *)
  Array.sort compare sommes_g;


  (*
    On utilise une recherche dichotomique dans sommes_g,
    pour chaque élément de sommes_d
  *)
  let rec recherche_xg x_d deb fin =
    (* 
      Trouve le plus grand x_g dans sommes_g 
      (entre deb inclus et fin exclus) tel que x_d + x_g <= m
      Renvoie la somme x_d + x_g. 
    *)
    assert (deb < fin); (* 0 vérifie toujours x_d + 0 <= m *)
    if deb = fin - 1 then x_d + sommes_g.(deb)
    else 
      let mid = (deb + fin) / 2 in
      if x_d + sommes_g.(mid) > m then recherche_xg x_d deb mid
      else recherche_xg x_d mid fin
  in


  let rec recherche_xd deb =
    (* 
       Trouve le x_d dans sommes_d (pour des indices >= deb) 
       qui participe à la plus grande somme.
       Renvoie cette somme,
       ou renvoie -1 si aucun élément dans cet ensemble n'est <= m.
    *)
    if deb >= puiss_2 ((n + 1) / 2) then -1
    else
      if sommes_d.(deb) > m then recherche_xd (deb + 1)
      else max (recherche_xg sommes_d.(deb) 0 (puiss_2 (n / 2)))
               (recherche_xd (deb + 1))
  in


  recherche_xd 0
```

#### Complexité
##### Complexité de tableau_sommes
Soit $m = \text{Fin_deb}$, soi toutes les opérations hors appels récursifs de
coût au plus constant, $C(m) = 2C(m - 1) + \Theta(1)$
(pour $m \geq 1$). $(C(n))$ est donc encadrée par deux suites
arithmético-géométriques positives de raison $2$, donc
$C(m) = \Theta(2^{m})$.

Ainsi, on effectue aux lignes 34 et 35 des opérations de coût total
$\Theta(2^{\frac{n}{2}})$.

La ligne $38$ a pour complexité $\Theta(k \log k)$ où $k$ est la taille
de $\text{sommet_g}$, $k = 2^{\left\lfloor \frac{n}{2} \right\rfloor}$,
donc la complexité est $\Theta(2^{\frac{n}{2}} \frac{n}{2})$,
soit $\Theta(n 2^{\frac{n}{2}})$.

##### Complexité de `recherche_xg`
Il s'agit d'une variante de la recherche dichotomique, de complexité
$\Theta(\log m)$ avec $m = \text{Fin_deb}$.

##### Complexité de `recherche_xd`
Cette fonction utilise un appel à `recherche_xg`.
