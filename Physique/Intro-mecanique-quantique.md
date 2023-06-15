# Introduction à la mécanique quantique
Au début du XXème siècle, deux théories cohabitent : la mécanique Newtonienne
qui subsiste depuis le XVIIème siècle et l'électromagnétisme de Maxwell. Tout
semble bien se passer, mais certaines expériences restent inexpliquées.\
C'est le cas du problème du rayonnement du corps noir, pour lequel Max Planck
propose l'hypothèse des quantas en 1900, qui font tout marcher si on peut poser
$E = h \nu$. L'énergie serait alors discrète et non continue.\
Einstein explique l'effet photoélectrique à l'aide des quantas en leur donnant
un sens et obtient le prix Nobel en 1905.

En 1913, Bohr met au point un modèle de l'atome d'hydrogène, quantifiant le
moment cinétique et utilisant des niveaux d'énergie discrets au niveau
atomique.\
En 1924, Louis de Broglie (prononcer "de Breuille") exhibe la dualité entre onde
et corpuscule.\
En 1925, Schrödinger propose son équation quantique.\
En 1927, Heisenberg introduit le principe d'incertitude, qui empêche de
connaître la position exacte de certaines particules.

## Aspect corpusculaire
### Rayonnement du corps noir
Le corps noir est un objet idéal qui absorberait l'énergie électromagnétique
sans en émettre ou en réfléchir. Le rayonnement ne dépend alors que de la température.
L'intensité de la lumière renvoyée est différente de celle prédite par la
théorie classique proposée par Rayleigh-Jeans.

### Effet photoélectrique
#### Observations
Certains métaux (comme le silicium, le sodium, le césium) émettent des électrons
quand ils sont exposés à la lumière. L'expérience se déroule avec deux
électrodes (un émetteur et un collecteur) dans un tube à vide avec une lumière
incidente sur l'émetteur. Un courant se crée, ce qui n'était pas prévu à
l'époque.

#### Le photon pour expliquer l'effet photoélectrique
Pour expliquer l'expérience, Einstein aboutit à la théorie du photon. Il fait
l'hypothèse que la lumière est composée de particules (les photons), d'énergie
$E = h \nu$, avec $h$ la constante de Planck ($6,62 \times 10^{-34} J \cdot s$),
et il pose un $W_\text{ext}$ l'énergie nécessaire à extraire un électron.
On trouve $h \nu = W_\text{ext} + \frac{1}{2} m v^2$, et comme
$W_\text{ext} = h \nu_0$ avec $\nu_0$ la fréquence seuil, on a
$h (\nu - \nu_0) = \frac{1}{2} m v^2$.

Einstein obtient le prix Nobel pour cette théorie en 1921.

### Effet Compton
En éclairant une cellule de carbone avec des rayons X pour une longueur d'onde
de 71 picometres, on observe un rayonnement de longueur d'onde différente que
celle donnée expérimentalement.

Compton repère ainsi deux ondes, une de la même longueur que celle qu'il a émis
et l'autre différente. En faisant les hypothèses $E = h \nu = \frac{h c}{\lambda}$
et $p = \frac{h}{\lambda}$. On modélise ainsi la réaction comme une électron qui
est frappé du rayon X et réfléchit le rayon tout en émettant une nouvelle
particule.

### Le photon
Le photon est théorisé comme étant une particule sans masse, allant à la vitesse
de la lumière, et d'énergie $h \nu$. En impulsion, la quantité de mouvement est
de $\overrightarrow{\rm p} = \frac{h}{\nu} \overrightarrow{\rm u}$. On note
souvent le tout avec la constante réduite de Planck $\hbar = \frac{h}{2 \pi}$,
nous amenant à des expressions plus ondulatoires des formules précédentes (avec
$\omega = 2 \pi \nu$ et $k = \frac{2 \pi}{\lambda}$).

## Aspect ondulatoire de la lumière
### Expérience de diffraction ed Davisson et Germer
En 1927, les deux scientifiques obtiennent une figure de diffraction en
bombardant une cible de zinc. On peut ainsi constater que la lumière pout bien
se comporter comme une onde.

### Interférences
#### Retour sur les fentes de Young
Nous savons déjà interpréter les fentes d'Young ondulatoirement, mais en
étudiant des particules quantiques envoyées dans ce type de fente, on obtient
des résultats identiques à la lumière plutôt qu'une figure avec seulement deux
impacts (comme on pourrait attendre d'une particule solide).

De plus, si on mesure par quelle fente passent les particules, on les retrouve à
nouveau se comportant comme des particules classiques.

Des expériences concrètes ont été conduites avec des électrons en 1956, des
atomes froids en 1992, du Fullérène en 1999, et même certaines protéines en
2011.

### Dualité onde-corpuscule
En 1924, Louis de Broglie établit qu'on peut attribuer à une particule quantique
d'énergie $E = h \nu$ et de quantité de mouvement $p$ suit un comportement
ondulatoire de longueur d'onde $\lambda = \frac{h}{p}$. Il remarque de plus que
la quantité de mouvement est mieux approchée par $p = \gamma m v$,
avec $\gamma = \frac{1}{\sqrt{1 - \frac{v^2}{c^2}}}$, ce qui change les calculs
pour les particules à des vitesses proches de la lumière.

### Quand utiliser la mécanique quantique ?
Les phénomènes quantiques apparaissent, comme montré plus haut, à des vitesses
proches de la vitesse de la lumière ou plus généralement quand la dimension
caractéristique des données est plus grande que $\lambda = \frac{h}{p}$.

## Interprétation probabiliste
### Amplitude de probabilité
À priori, on considère que la position d'une particule est parfaitement définie
par une fonction d'onde $\underline{\psi(M,t)}$ qui représente l'amplitude de
probabilité. On mesure en général la probabilité de présence, qui est
proportionnelle à l'amplitude de probabilité au carré.

La probabilité qu'un objet quantique se trouve dans un volume $dV$ autour du
point $M$ à l'instant $t$ est alors $dP = |\underline{\psi}(M,t)|^2 dV$. De
plus, on réalise une condition de normalisation : la particule est quelque part,
et $\iiint |\underline{\psi}(M,t)|^2 dV = 1$.

### Interprétation
Soit $\underline{\psi_1}$ l'amplitude de probabilité correspondant au passage
par la fente 1 et $\underline{\psi_2}$ celle de passage par la fente 2 dans
l'expérience d'Young, les impacts suivent la probabilité $P$, proportionnelle
$|\underline{\psi_1} + \underline{\psi_2}|^2$ quand les chemin ne sont pas
discernés, et à $|\underline{\psi_1}|^2 + |\underline{\psi_2}|^2$ quand ils le
sont.

## Principe d'incertitude de Heisenberg
La nature quantique d'un objet nous empêche de connaître précisément à la fois
sa position et sa vitesse.

> La mesure à un instant donné de la position $x$ et de l'impulsion $p_x$
> est contrainte par les indéterminations fondamentales $\Delta x$ et $\Delta p_x$,
> vérifiant $\Delta x \cdot \Delta y \geq \frac{\hbar}{2}$.

La moyenne de $x$ est reliée à l'écart-type $\Delta x$ par $\Delta x = \sqrt{<x^2> - <x>^2}$.

## Un modèle historique, le modèle de Bohr
On se place dans le référentiel supposé galiléen protocentrique, dans lequel on
considère l'électron gravitant autour du proton sur lequel agit la force
électrostatique. On obtient par résultats sur les forces centrales
que la particule reste dans un même plan, et possède une énergie cinétique
de $E_c = \frac{e^2}{8 \pi \varepsilon_0 r}$.

Bohr a fait l'hypothèse de la possibilité de quantifier le moment cinétique de
l'électron comme $n \hbar$, avec $n$ le "nombre quantique principal".
On obtient finalement une énergie associée à chaque orbite dont les possibilités
sont discrètes, de la forme $E_n = - \frac{m e^{4}}{8 \varepsilon_0^2 h^2 n^2} = \frac{- E_0}{n^2}$.
Ce modèle a bien permis de retrouver les raies spectrales obtenues lors des
expériences faites pour l'atome d'hydrogène. En réalité, le modèle est plus
compliqué, voire échoue, pour d'autres atomes, et pour les ions
multiélectroniques.

De plus, si les électrons étaient en rotation, les atomes devraient émettre de
la lumière jusqu'à ce que l'électron tombe finalement dans le noyau.

Le modèle, malgré son intérêt historique, a été largement supplanté.

## L'équation de Schrödinger
### Énoncé de l'équation
L'onde associée à une particule quantique libre se propageant selon la direction
$\overrightarrow{\rm u_x}$, on pose la fonction quantique
$\underline{\Psi} = \Psi_0 e^{i (kx - \omega t)}$, avec $\omega = 2 \pi \nu$,
$k = \frac{2 \pi}{\lambda}$ et $h \nu$, donnant
$\underline{\Psi} = \Psi_{0} e^{i (\frac{p x}{\hbar} - \frac{E t}{\hbar})}$.

On a l'équation de Schrödinger qui est $- \frac{\hbar^2}{2m} \Delta \underline{\Psi} + V \underline{\Psi} = i \hbar \frac{\partial \underline{\Psi}}{\partial t}$,
avec $V$ le potentiel d'interaction associée aux forces conservatives
s'appliquant sur l'objet quantique, et
$\Delta$ est l'opérateur différentiel Laplacien
$\frac{\partial^2}{\partial x^2} + \frac{\partial^2}{\partial y^2} + \frac{\partial^2}{\partial z^2}$.
Sur une unique dimension, on peut simplifier à $\frac{- \hbar^2}{2 m} \frac{d^2 \underline{\Psi}}{dx^2} + V \underline{\Psi} = i \hbar \frac{\partial \underline{\Psi}}{\partial t}$.

### Quantification de l'énergie d'une particule libre confinée à une dimension
On prend une particule qui ne peut se déplacer que dans un sens. On a
alors $V = 0$ sur cette dimension, et $V = +\infty$ au-delà.
On sépare les variables d'espace et de temps $\underline{\Psi}(x,t) = \varphi(x) e^{- i \omega t}$.
En remplaçant dans l'équation de Schrödinger,
donnant $\hbar \omega \varphi(x) = - \frac{\hbar^2}{2m} \frac{d^2 \varphi(x)}{dx^2} + V \varphi(x)$,
et en appliquant $E = \hbar \omega$,
$E \varphi(x) = - \frac{\hbar^2}{2m} \frac{d^2 \varphi(x)}{dx^2} + V \varphi(x)$.
Entre $0$ et $L$, $V = 0$, donnant l'équation différentielle
$\frac{d^2 \varphi(x)}{dx^2} + k^2 \varphi(x) = 0$,
avec $k = \frac{\sqrt{2 m E}}{\hbar}$,
donnant les solutions $\varphi(x) = A \cos(k x) + B \sin(k x)$,
et les conditions aux limites donnent
$\varphi(x) = B \sin(\frac{n \pi x}{L})$.

Pour terminer l'équation, on utilise la condition de normalisation,
qui pose ici $B^2 \int\limits_{0}^{L} \sin^2(\frac{n \pi x}{L}) dx = 1$,
soit $1 = B^2 \int\limits_{0}^{L} \frac{1 - \cos(\frac{2 n \pi x}{L})}{2} dx$
$= \frac{B^2}{2} L - \frac{L B^2}{2 n \pi L} [\sin(\frac{2n \pi x}{L})]_0^L$
$= \frac{B^2}{2} L - \frac{L B^2}{2 n \pi L} [\sin(\frac{2n \pi x}{L})]_0^L$
$= \frac{B^2 L}{2}$, donnant finalement
$\varphi(x) = I \sqrt{\frac{2}{L}} \sin(\frac{n \pi x}{L})$.
L'équation de Schrödinger donne ainsi $E_n = \frac{h^2}{8 m L^2} n^2$.
