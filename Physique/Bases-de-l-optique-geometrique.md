# Chapitre 1 : Bases de l'optique géométrique
## Lumières et sources lumineuses
### Lumière et ondes électromagnétique
> Un champ électromagnétique est créé par des particules chargées,
> généralement en mouvement

> On représente le rayonnement électromagnétique par une onde électromagnétique

Un rayonnement électromagnétique est caractérisé par une fréquence de vibrations
(notée $f$ ou $\nu$). Un rayonnement ne contenant qu'une seule fréquence est dit
monochromatique, ou polychromatique s'il en contient plusieurs.

> Dans le vide, une onde électromagnétique se propage à la vitesse de la lumière

La longueur d'onde dans le vide d'une onde électromagnétique de fréquence $\nu$
est définie par la relation $\lambda = \frac{c}{\nu}$ (avec la longueur d'onde
en mètres).

Le champ des ondes électromagnétiques visibles est situé entre 400 et 800
nanomètres de longueur d'onde. On a le spectre suivant.

Bornes     | Gamma   | Rayons X | Ultraviolets | Visible | Infrarouges | Micro-ondes | Autres | Radio
---        | ---     | ---      | ---          | ---     | ---         | ---         | ---    | ---
Plus petit | -       | 10 pico  | 10 nm        | 380 nm  | 780 nm      | 1 mm        | 30 cm  | 1 m
Plus grand | 10 pico | 10 nm    | 380 nm       | 780 nm  | 1 mm        | 30 cm       | 1 m    | -

> La lumière est une onde électromagnétique, qui correspond dans le vide
> approximativement au spectre de longueur d'onde 400 nanomètres (violet) et 800
> nanomètres (rouge)

#### Sources lumineuses
> Une source primaire de lumière est une source qui émet sa propre lumière.
> Une source secondaire est une source qui ne produit pas de lumière mais ne
> fait que la retransmettre.

##### Sources thermiques
> Tout corps ou objet de température non nulle (exprimée en Kelvin) émet des ondes électromagnétiques. Ces corps chauds sont historiquements appelés corps noirs.
> Le spectre d'émission d'un tel corps est appelé spectre d'émission du corps
> noir et on parle de source thermique.

Loi de Wien : $\lambda_{max} \cdot T = constante$

> Si l'objet est suffisamment chaud, l'essentiel du rayonnement est contenu dans
> le spectre visible et la lumière est alors perçue comme blanche par l'oeil.

##### Spectres ou lampes spectrales
> Le rayonnement d'un spectre est discret. Seules des raies, centrées autour de certaines longueurs d'ondes,
> sont émises

##### Lasers
> Laser signifie "Light Amplification by Stimulation Emission of Radiation"

Le rayonnement émis par un laser est proche d'un rayonnement monochromatique.

##### Bilan qualitatif
Les spectres d'analyses de chacun de ces rayonnements présentent des largeurs
différentes, de la plus large et étalée à la plus étroite et longiligne :
Thermique, Spectral, Laser, Monochromatique (seulement théorique).

### Indice optique
#### Définition
> L'indice optique ou indice de réfraction d'un milieu transparent est le
> rapport entre la vitesse de la lumière et la vitesse de la lumière dans le milieu

La formule est donc notée $n_{\text{milieu}} = \frac{c}{c_{\text{milieu}}}$

Valeurs courantes:
- $n_{\text{air}} = 1.00$ (commence à changer à partir de la quatrième décimale)
- $n_{\text{eau}} = 1.33$
- $n_{\text{verre}} = 1.5 \text{à} 1.8$

#### Milieu dispersif
La fréquence $\nu$ d'un onde électromagnétique est indépendante du milieu
qu'elle traverse (mais la vitesse peut changer).

> Un milieu est dit dispersif lorsque $c_{\text{milieu}}$ dépend de la fréquence $\nu$
> de l'onde électromagnétique le traversant. Dans ce cas, $n_{\text{milieu}}$ dépend
> aussi de $\nu$.

##### Exemple : le verre est un milieu dispersif, c'est pourquoi chaque couleur de la
lumière a une vitesse différente selon sa fréquence. On peut lier cette relation
par la loi de Cauchy, $n_{lambda} = A + \frac{B}{\lambda^2}$ (A et B déterminés
expérimentalement).

#### Conséquences sur les longueurs d'onde
$\nu = \frac{c}{\lambda} = \frac{c_{\text{milieu}}}{\lambda_{\text{milieu}}} \Leftrightarrow \lambda_{\text{milieu}} = \lambda \frac{c_{\text{milieu}}}{c}$
or $n_{\text{milieu}} = \frac{c}{c_{\text{milieu}}}$, donc $\lambda_{\text{milieu}} = \frac{\lambda}{n_{\text{milieu}}}$ 

Sa longueur d'onde $\lambda_{\text{milieu}}$ dans un milieu d'indice optique $n_{\text{indice milieu}}$ 

Propriété : $\lambda_{milieu} = \frac{\lambda_{onde}}{n_{milieu}}$

## Modèle de l'optique géométrique
### Notion de rayon lumineux
> Un rayon lumineux matérialise la propagation de la lumière. On le représente
> par un trait muni d'une flèche qui indique le sens de propagation de la lumière

### Cadre de l'optique géométrique
On suppose que les milieux traversés sont :
- Transparents
- Homogènes
- Isotropes (même propriétés dans toutes les directions)

#### Propagation en ligne droite
On ne tient pas compte du caractère ondulatoire de la lumière.
Tant que les rayons ne rencontrent pas d'obstacles, ils se propagent en ligne
droite (on ne constate pas de mirages chauds par exemple, puisque le milieu est
homogène).

#### Indépendance de la lumière
Il n'y a ni diffraction, ni interférences.

#### Retour inverse de la lumière
Si un point A éclaire un point B, alors une source de lumière placée en B
éclaire A.

### Limites du modèle
- Pas de description de la diffraction et des interférences
- Pas de description de la polarisation (fait que le champ électrique tourne
  dans l'espace)
- Pas de description des mirages (effets de milieux non homogènes)

## Loi de Snell-Descartes
### Énoncé des lois
> On appelle dioptre la surface de séparation entre deux milieux d'indices
> différent.

Par exemple, la surface de l'eau dans un environnement entre l'eau (d'indice
1,33) et l'air (d'indice 1) est un dioptre. Le dioptre n'est pas toujours une
ligne droite, puisqu'il consiste en une courbe pour une bulle de savon ou une
goutte d'eau.

> La normale à un dioptre en un point est la droite passant par ce point et
> perpendiculaire au plan local du dioptre.

__Énoncé des lois :__ Soit un dioptre entre un milieu d'indice $n_1$ et un autre
milieu d'indice $n_2$. Un rayon incident arrivant sur le dioptre est réfléchi
par le dioptre, et réfracté de l'autre côté du dioptre.
- Tous les rayons sont situés dans le même plan, contenant la normale au dioptre
  et le rayon incident : c'est le **plan d'incidence**.
- Le rayon réfléchi possède un angle opposé au rayon incident, donnant l'angle
  $r = -i_1$.
- L'angle du rayon réfracté vérifie $n_1 \sin i_1 = n_2 \sin i_2$.

### Première application
Avec une surface entre l'air (n = 1) et le verre (n = 1,5), et un rayon $i_1 = 40°$.
On peut trouver $i_2$ à l'aide de la troisième loi de Snell-Descartes : $n_\text{air} \sin i_1 = n_\text{verre} i_2$,
soit $\sin i_2 = \frac{n_\text{air}}{n_\text{verre}} \sin i_1 \Leftrightarrow i_2 = \arcsin(\frac{n_\text{air}}{n_\text{verre}}\sin i_1)$.
L'application numérique nous donne ainsi $i_2 \approx 25°$

### Angles limite
#### Angle de réfraction limite
$n_1 < n_2$, et $i_1 > i_2$. Avec l'angle maximal du rayon incident 90°, on a
avec la 3ème loi de Snell-Descartes $i_2 = \arcsin \frac{n_1}{n_2}$.

> Pour deux milieux d'indices $n_1$ et $n_2$, on dit que le milieu 1 est plus
> réfringent que le milieu 2 si $n_1 > n_2$.

> Pour une réfraction vers un milieu plus réfringent, l'angle de réfraction
> limite correspond à un angle d'incidence maximal et vérifie $i_{2\text{lim}} = \arcsin \frac{n_1}{n_2}$.

#### Phénomène de réflexion totale
Lorsque l'indice $n_1 > n_2$, $i_1 < i_2$. Lorsque $i_1 > i_{1\text{lim}}$,
les rayons réfléchis et réfractés sont confondus et tous deux réfléchis.

> L'angle d'incidence limite $i_1\text{lim}$ est l'angle d'incidence au delà
> duquel le rayon incident est totalement réfléchi. On parle de réflexion
> totale.

Ce phénomène se retrouve dans la brillance des diamants ou dans le
fonctionnement de la fibre optique.

### Principe de Fermat
> Pour relier deux points a et b, la lumière (le rayon lumineux) suit un chemin
> dont le temps de parcours est localement extrémal (maximal ou minimal).

Ce principe est un principe de moindre effort de la propagation des rayons
lumineux.

#### Propagation en ligne droite dans les milieux homogènes
Dans un milieu homogène, la lumière se déplace toujours à la même vitesse (car
l'indice optique est le même partout) et le chemin le plus rapide entre deux
points est le chemin le plus court (en termes de distance), soit une ligne
droite.

#### Principe de retour inverse de la lumière
Si un chemin est extrémal dans un sens de parcours, il l'est également dans
l'autre.

#### Lois de Descartes
Voir prochain TD

## Application : La fibre optique à saut d'indice
### Principe
Une fibre optique à saut d'indice est constituée d'un tube central, appelé cœur
transparent, d'indice optique $n_\text{cœur}$, entouré d'un gaine d'indice
optique $n_\text{gaine}$.

Il y a réflexion totale avec $n_\text{cœur} > n_\text{gaine}$.
On cherche à obtenir une condition sur $\Theta$ pour qu'il y ait réflexion
totale en I.
Pour avoir réflexion totale en I, il faut que $i > i_\text{lim}$, donc que
$\sin i_\text{lim} = \frac{n_\text{gaine}}{n_\text{cœur}}$.
On a $\Theta ' + i + \frac{\Pi}{2} = \Pi \Leftrightarrow i = \frac{\Pi}{2} - \Theta '$.
La condition $i > i_\text{lim}$ s'écrit $\frac{\Pi}{2} - \Theta' > i_\text{lim}$
$\Leftrightarrow \Theta' < \frac{\Pi}{2}i_\text{lim}$. $\sin(\Theta)$ est
croissant sur $[0; \frac{\Pi}{2}]$. De plus, on a
$\sin\Theta' < \cos i_\text{lim}$.
On à, d'après la loi de Descartes, $n_\text{air} \sin \Theta = n_\text{cœur} \sin\Theta'$.
Or, $n_\text{air} = 1.00$ donc $\sin\Theta = n_\text{cœur} \sin\Theta'$.
Or $\sin\Theta' < \cos i_\text{lim}$.
Donc $\sin\Theta < n_\text{cœur} \cos i_\text{lim}$.
Or $\sin i_\text{lim} = \frac{n_\text{gaine}}{n_\text{cœur}}$ et
$\cos^2 i_\text{lim} + \sin^2 i_\text{lim} = 1$
$\Leftrightarrow \cos^2 i_\text{lim} = 1 - \sin^2 i_\text{lim}$,
Donc $\cos^2 i_\text{lim} = 1 - (\frac{n_\text{gaine}}{n_\text{cœur}})^2$
$\Leftrightarrow \cos i_\text{lim} = \sqrt{1 - (\frac{n_\text{gaine}}{n_\text{cœur}})^2}$
Donc $\sin \Theta < n_\text{cœur} \sqrt{1 - (\frac{n_\text{gaine}}{n_\text{cœur}})^2}$
$\Leftrightarrow \sin \Theta < \sqrt{n_\text{cœur}^2 - n_\text{gaine}^2}$

Propriété : $\sin\Theta < \sqrt{n_\text{cœur}^2 - n_\text{gaine}^2}$.
On appelle cette valeur Ouverture Numérique, telle que
$O.N. = \sqrt{n_\text{cœur}^2 - n_\text{gaine}^2}$

### Dispersion intermodale
*Rayon le plus rapide* : $\Theta = 0$, le temps de parcours est alors
$T_1 = \frac{L}{c_\text{cœur}}$, aussi noté $T_1 = \frac{L n_\text{cœur}}{c}$

*Rayon le plus lent* : $\Theta = \Theta_\text{max}$, la longueur du parcours est
alors $L_2 = \frac{L}{\sin(i_\text{lim})}$, et $T_2 = \frac{L_2 n_\text{cœur}}{c}$
$= \frac{L n_\text{cœur}}{c \sin i_\text{lim}}$. Or, $\sin i_\text{lim} = \frac{n_\text{gaine}}{n_\text{cœur}}$,
donc $T_2 = \frac{L n_\text{cœur}^2}{c n_\text{gaine}}$.

*Différences des temps de parcours* : $\Delta T = T_2 - T_1$
$= \frac{L}{c} \frac{n_\text{cœur}^2}{n_\text{gaine}} - \frac{L}{c}n_\text{cœur}$
$= \frac{L}{c} \frac{n_\text{cœur} (n_\text{cœur} -n_\text{gaine})}{n_\text{gaine}}$.

On peut ainsi avoir les valeurs suivantes :
- $L = 10.0 km$
- $n_\text{cœur} = 1.62$
- $n_\text{gaine} = 1.52$
- $\Delta N = 0.560$
- $\Delta T = 3.53 microsecondes$

Le signal de la fibre optique peut ainsi se distordre et se décaler dans le
temps, posant de nombreux défis techniques.
