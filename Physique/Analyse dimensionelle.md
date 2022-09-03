# Dimensions et unités
## Définitions
> Deux grandeurs physiques ont la même dimension si elles peuvent être comparées
> entre elles, ont dit alors qu'elles sont homogènes. Les grandeurs sont notées
> entre [].

> L'unité est une grandeur de référence qui se trouve après la valeur numérique.
> Ne pas se tromper avec les degrés et radians, qui sont des rapports, pas des
> unités, et n'ont ainsi pas d'unités.

> Une formule physique doit nécessairement être homogène, et les deux membres de
> l'égalité doivent être de même dimension

## Unités du système international (SI)
7 dimensions de base, associées à 7 unités de base

Dimension            | Symbole | Unité
---                  | ---     | ---
Temps                | T       | Seconde (s)
Longueur             | L       | Metre (m)
Masse                | M       | Kilogramme (kg)
Température          | $\rho$  | Kelvin (K)
Quantité de matière  | N       | Mole (mol)
Intensité électrique | I       | Ampère (A)
Intensité lumineuse  | J       | Candela (cd)

> La dimension de toute grandeur physique est un produit de ces 7 dimensions
> fondamentales avec éventuellement des coefficients en puissance.

> L'écriture de la dimension d'une grandeur physique se fait en fonction des 7 grandeurs
> de base du système international

> On apelle l'étude d'une relation physique en termes de dimensions "analyse
> dimensionelle"

Exemple : $e = mc^2$ donne $[E] = [m][c]^2$, qui donne la dimension
$M L^2 T^{-2}$, soit les unités $kg \cdot m^2 s^{-2}$
- Puissance, $E = P \delta T$ -> $M L^2 T^{-2} = [P] T$, donc $[P] = M L^2 T^{-3}$
- Résistance, $P = RI^2$ a une unité de $kg \cdot m^2 s^{-1} A ^ {-2}$

### Opérations mathématiques sur les grandeurs dimensionées
#### Somme et différence
> Tous les termes d'une somme ou d'une différence sont de même dimension; le
> résultat aussi

#### Produit et quotient
> On peut multiplier ou diviser des grandeurs de n'importe quelle dimension. La
> dimension d'un produit est le produit des dimensions, la dimension d'un
> quotient est le quotient des dimensions

#### Dérivation
> $[ \frac{dY}{dX} ] = \frac Y X$
Exemple : Force, $F = ma$ est de dimension $[\frac dv dt] = \frac LT^{-1} T$

#### Intégration
> Pour deux grandeurs Y et X, $[\int Y(x)dx] = [Y][x]$

#### Fonctions transcendantes
> En physique, une "fonction transcendante" englobe les exponentielles et
> logarithmes, ainsi que toutes les fonctions trigonométriques

> L'argument d'une fonction transcendante est sans dimension; Une fonction
> transcendante est sans dimension
Exemple : Décharge d'un condensateur : $U = E e^{\frac t \tau}$,  $\tau] = $

## Présentation d'un résultat numérique
### Calcul numérique et calcul littéral
> Commandement 1 : Tous les calculs sont d'abord effectués de façon littérale, ce qui signifie
que les seuls nombres qui apparaissent doivent être sans dimensions et que
les grandeurs qui apparaissent sont représentées par leur symbole (une lettre)

### Ordres de grandeur et chiffres significatifs
> Soit un résultat numérique correspondant au chiffre compté à partir du premier
> chiffre non nul en partant de la gauche, sans indication autre, le nombre de
> chiffres significatifs d'un résultat numérique doit correspondre à celui de la
> grandeur possédant le plus petit nombre de chiffres significatifs.

> Commandement 2 : Un résultat numérique sera systématiquement écrit en écriture
> scientifique en respectant le nombre de chiffres significatifs et en indiquant
> impérativement unité, si le résultat est dimensionné.

> L'ordre de grandeur d'un résultat numérique correspond à la puissance de 10 la plus
> proche de la valeur numérique dans une unité donnée.

Exemple : Pour C (vitesse de la lumière) $\approx 2.99792458 \times 10^8$,
l'ordre de grandeur est 10^8.

## Analyse dimensionelle comme outil de prédiction
### Principe
> Les grandeurs sont dites dimensionellement indépendantes si on ne peut pas
> construire de grandeur sans dimension à partir du produit de ces dernières ou
> portant au moins un exposant au milieu

Si une grandeur X est succeptible de dépendre d'un certain nombre de grandeurs
dimensionnées A, B, C et D, caractéristiques du problème et dimensionellement
indépendantes, alors X peut se mettre sous la forme $X = k A^{\alpha} B^{\beta} C^{\gamma} D^{\delta}$

### Applications
Méthode :
1. Déterminer la grandeur recherchée (X par exemple), ainsi que sa dimension en
   fonction de dimensions de base (voir plus haut)
2. Lister les grandeurs caractéristiques
3. "On suppose que X peut s'écrire sous la forme $X = k A^{\alpha} B^{\beta} C^{\gamma} D^{\delta}$"
4. Utiliser l'équation de dimension pour obtenir un système pour alpha, beta,
   gamma et delta, puis le résoudre
5. Conclure et déterminer k

Exemple : Vitesse dans une chute verticale (formule )
1. On cherche la vitesse v du corps (c'est une vitesse), de dimension $L T^{-1}$
2. g (attraction gravitationelle) (dimensions d'une accélération, donc $L \cdot T^{-2} )$
   et la hauteur de laquelle on lâche l'objet (dimension L), ainsi que sa masse (dimension M)
3. On suppose que v va s'écrire
   $v = k h^\alpha m^\beta g^\gamma$, de dimension
   $v = k L^\alpha M^\beta L^\gamma T^{-2\gamma}$
4. On obtient le système 
   $\left\{\begin{matrix} 1 = \alpha + \gamma \\ 0 = \beta \\ -1 = -2y \end{matrix}\right.$
   , qui se résout par 
   $\left\{\begin{matrix} \alpha = \frac{1}{2} \\ \gamma = \frac{-1}{2} \\ \beta = 0 \end{matrix}\right.$
5. Ainsi, $v = k \sqrt{gh}$ avec $k = \sqrt{2}$

Exemple : Période d'un pendule simple (formule $2\pi \sqrt{\frac{l}{g}}$)
1. On cherche la période $T_0$, de dimension $T$
2. g (attraction gravitationelle) (dimensions d'une accélération, donc $L \cdot T^{-2} )$
   et la longueur du fil (dimension L), ainsi que sa masse (dimension M)
3. On suppose que v va s'écrire
   $T_0 = k l^\alpha m^\beta g^\gamma$, de dimension
   $T_0 = k L^\alpha M^\beta L^\gamma T^{-2\gamma}$
4. On obtient le système $\left\{\begin{matrix} \alpha = 0 \\ \beta + \gamma = 0 \\ \delta = -2\gamma \end{matrix}\right.$
5. Ainsi, $T_0 = 2\pi \sqrt{\frac{l}{g}}$

Exemple : vitesse d'un satellite
1. On cherche la vitesse v, de dimension $L \cdot T^{-1}$
2. On considère les grandeurs suivantes : masse du satellite $M_s$ (dimension M),
   rayon de l'orbite R (dimension L), et la constante de gravitation universelle
   G (de dimension $M^{-1} L^{3} T^{-2}$) (voir formule d'attraction
   gravitationnelle, dont le résultat en N est de dimension $M L T^{-2}$)
3. On suppose qu'on a ainsi $v = k M_s^\alpha R^\beta G^\gamma$, de dimension
   $L T^{-1} = k M^\alpha L^\beta M^{-\gamma} L^{3\gamma} T^{-2\gamma}$
4. On obtient le système suivant :
   $\left\{\begin{matrix}  0 = \alpha - \gamma \\ 1 = \beta + 3\gamma \\ -1 = -2\gamma \end{matrix}\right.$
   $\left\{\begin{matrix}  \alpha = \frac{1}{2} \\ \beta = \frac{-1}{2} \\ \gamma = \frac{1}{2} \end{matrix}\right.$
5. On a donc $v = k \sqrt{\frac{G M_s}{R}}$, avec k = 1

Exemple : Rayon cyclotron
1. On cherche le rayon R de rotation de l'électron, de dimension L
2. On considère la charge de l'électron e (en coulons, soit une dimension de
   IT), la masse $m_e$ de l'électron (dimension M), la vitesse de l'électron
   $v_0$ (de dimension $L \cdot T^{-1}$), et le champ magnétique $B_0$, de
   dimension $M T^{-2} I^{-1}$
3. On suppose qu'on peut écrire $R = k e^{\alpha} m_e^\beta v_0^\gamma B_0^\delta$, de dimension
   $L = k I^\alpha T^\alpha M^\beta L^\gamma T^{-\gamma} M^\delta T^{-2\delta} I^{-\delta}$
4. On obtient le système suivant :
   $\left\{\begin{matrix} 0 = \beta + \gamma \\ 1 = \gamma \\ 0 = \alpha - \gamma -2\delta \\ 0 = \alpha - \delta \end{matrix}\right.$
5. $R = k \frac{m_e v_0}{e B_0}$ avec k = 1

### Limitations
#### Oubli de grandeurs caractéristiques
Si on oublie une grandeur caractéristique, l'équation en dimension n'admet
généralement pas de solutions

#### Grandeur caractéristique sans dimension
Si la valeur X recherchée dépend en outre de d'une grandeur sans dimension x,
cette dernière est invisible à l'analyse dimensionnelle.

Exemple : Dans le cas ou une grandeur dépend d'une fonction sans dimension
(comme dans le cas du balancement d'un pendule, celui-ci dépend de l'amplitude
angulaire $f(\theta)$ ).
