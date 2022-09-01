# Dimensions et unités
## Définitions
> Deux grandeurs physiques ont la même dimension si elles peuvent être comparées
> entre elles, ont dit alors qu'elles sont homogènes. Les grandeurs sont notées
> entre [].

> L'unité est une grandeur de référence qui se trouve après la valeur numérique.
> Ne pas se tromper avec les degrés et radians, qui sont des rapports, pas des
> unités, et n'ont ainsi pas d'unités.

> Une formule physique doit nécessairement être homogène, et les deux membres de
> l'égalité douivent être de même dimension

## Unités du système international (SI)
7 dimensions de base, associées à 7 unités de base

Dimension            | Symbole    | Unité
---                  | ---        | ---
Temps                | T          | Seconde (s)
Longueur             | L          | Metre (m)
Masse                | M          | Kilogramme (kg)
Température          | \( \rho \) | Kelvin (K)
Quantité de matière  | N          | Mole (mol)
Intensité électrique | I          | Ampère (A)
Intensité lumineuse  | J          | Candela (cd)

> La dimension de toute grandeur physique est un produit de ces 7 dimensions
> fondamentales avec éventuellement des coefficients en puissance.

> L'écriture de la dimension d'une gradeur physique en fonction des 7 grandeurs
> de base du système international

> On apelle l'étude d'une relation physique en termes de dimensions "analyse
> dimensionelle"
Exemple : \( e = mc^2 \) donne \( [E] = [m][c]^2 \), qui donne la dimension
\( M L^2 T^{-2} \), soit les unités \( kg \cdot m^2 s^{-2} \)
Puissance, \( E = P \delta T \) -> \( M L^2 T^{-2} = [P] T \) a une unité de ...
Résistance, \( P = RI^2 \) a une unité de \( kg \cdot m^2 s^{-1} A ^ {-2} \)

### Opérations mathématiques sur les grandeurs dimensionées
#### Somme et différence
> Tous les termes d'une somme ou d'une différence sont de même dimension; le
> résultat aussi

#### Produit et quotient
> On peut multiplier ou diviser des grandeurs de n'importe quelle dimension. La
> dimension d'un produit est le produit des dimensions, la dimension d'un
> quotient est le quotient des dimensions

#### Dérivation
> \( [\frac{dY}{dX}] = \frac Y X \)
Exemple : Force, \( F = ma \) est de dimension \( [\frac dv dt] = \frac LT^{-1} T \)

#### Intégration
> Pour deux grandeurs Y et X, \( [\int Y(x)dx] = [Y][x] \)

#### Fonctions transcendantes
> En physique, une "fonction transcendante" englobe les exponentielles et
> logarithmes, ainsi que toutes les fonctions trigonométriques

> L'argument d'une fonction transcendante est sans dimension; Une fonction
> transcendante est sans dimension
Exemple : Décharge d'un condensateur : \( U = E e^{\frac t \tau} \),  $[\tau] = T$

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

Exemple : Pour C (vitesse de la lumière) \( \approx 2.99792458 \times 10^8 \),
l'ordre de grandeur est 10^8.

## Analyse dimensionelle comme outil de prédiction
### Principe
> Les grandeurs sont dites dimensionellement indépendantes si on ne peut pas
> construire de grandeur sans dimension à partir du produit de ces dernières ou
> portant au moins un exposant au milieu

Si une grandeur X est succeptible de dépendre d'un certain nombre de grandeurs
dimensionnées A, B, C et D, caractéristiques du problème et dimensionellement
indépendantes, alors X peut se mettre sous la forme \( X = k A^{\alpha} B^{\beta} C^{\gamma} D^{\delta} \)

### Applications
Méthode :
1. Déterminer la grandeur recherchée (X par exemple), ainsi que sa dimension en
   fonction de dimensions de base (voir plus haut)
2. Lister les grandeurs caractéristiques
3. "On suppose que X peut s'écrire sous la forme \( X = k A^{\alpha} B^{\beta} C^{\gamma} D^{\delta} \)"
4. Utiliser l'équation de dimension pour obtenir un système pour alpha, beta,
   gamma et delta, puis le résoudre
5. Conclure et déterminer k

Exemple : Vitesse dans une chute verticale (formule )
1. On cherche la vitesse v du corps (c'est une vitesse), de dimension \( L T^{-1} \)
2. g (attraction gravitationelle) (dimensions d'une accélération, donc \( L \cdot T^{-2} ) \) 
   et la hauteur de laquelle on lâche l'objet (dimension L), ainsi que sa masse (dimension M)
3. On suppose que v va s'écrire
   \( v = k h^\alpha m^\beta g^\gamma \), de dimension
   \( v = k L^\alpha M^\beta L^\gamma T^{-2\gamma} \)
4. On obtient le système \( { 1 = \alpha + \gamma ; 0 = \beta ; -1 = -2y \), qui
   se résout par \( \begin{cases} \gamma = \frac{-1}{2} \\ \beta = 0 \\ \alpha = \frac{1}{2} \end{cases} \)
5. Ainsi, \( v = k \sqrt{gh} \) avec \( k = \sqrt{2} \)


Exemple : Période d'un pendule simple (formule \( 2\pi \sqrt{\frac{l}{g}} \))
1. On cherche la période \( T_0 \), de dimension \( T \)
2. g (attraction gravitationelle) (dimensions d'une accélération, donc \( L \cdot T^{-2} ) \)
   et la longueur du fil (dimension L), ainsi que sa masse (dimension M)
3. On suppose que v va s'écrire
   \( T_0 = k l^\alpha m^\beta g^\gamma \), de dimension
   \( T_0 = k L^\alpha M^\beta L^\gamma T^{-2\gamma} \)
4. On obtient le système \( \begin{cases} \alpha = 0 \\ \beta + \gamma = 0 \\ \delta = -2\gamma \end{cases}\)
5. Ainsi, \( T_0 = 2\pi \sqrt{\frac{l}{g}} \)
