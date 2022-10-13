# Chapitre 5 : Cinématique du point matériel
La cinématique étudie le mouvement d'un point matériel indépendamment des causes
qui lui donnent naissance. Elle repose sur une description Euclidienne de
l'espace et d'un temps absolu.

## Temps et espace
### Le temps
Le temps est une notion difficile à définir. On réduit le temps à différents
attributs : seconde, durée, instant, chronologie, présent, passé, futur, flèche
des temps...
Il faut attendre la 17ème siècle et les premières descriptions mathématiques de
la physique, notamment par les travaux de Galilée et de Newton.

> Dans le cadre de la mécanique Newtonienne, le temps est une variable scalaire
> (à une dimension) qui croît continument, ceci indépendamment de tout
> observateur et de tout phénomène.

En 1905, Einstein (et Planck quelques mois avant) (et avec l'aide de sa femme,
inspirée par Poincaré) remet entièrement en question ce modèle par le concept de
relativité restreinte dans 3 articles. Le concept de temps n'est alors plus
absolu, et la simultanéité et la chronologie deviennent relatives à
l'observateur, et même son irréversibilité est remise en question, et la
question est toujours ouverte pour de nombreux physiciens. Le concept d'entropie
est aussi étudié pour modéliser notre monde.

> Postulat : Principe de causalité : la cause est, pour tout observateur, antérieure à
> l'effet qu'elle produit. De manière plus générale, la chronologie de deux
> évènements reliés causalement est toujours la même, quelque soit
> l'observateur.

> Par définition, la seconde est la durée de 9 192 631 770 périodes de la
> radiation correspondante à la transition entre deux niveaux hyperfins de
> l'atome de césium 133.

### L'espace
Dans le cadre de la mécanique Newtonienne, l'espace est supposé à trois
dimensions, euclidien, homogène et isotrope.
Cet espace est absolu, et ses propriétés sont indépendantes de la matière qui
s'y trouve.

> Par définition, le mètre est la longueur du trajet parcouru par la lumière
> dans le vide pendant une durée de 1/299 792 458 de seconde.

## Référentiel
### Définition
> Le référentiel est la cadre spatio-temporel de l'étude.

Pour le définir, on a besoin d'un repère d'espace et d'un repère de temps. 

### Repère de temps
Pour dater un évènement, on utilise un repère de temps, constitué d'une mesure
de temps défini par unité de durée (la seconde) et d'une origine des temps.

> Un instant est un point de la flèche du temps.

> L'origine des dates est un instant particulier choisi comme instant 0 de façon
> arbitraire.

> Une date repère la position d'un instant sur la flèche du temps. C'est la
> durée séparant cet instant de l'origine des dates.

> Une durée $\Delta t = (t_2 - t_1)$ est la largeur d'un intervalle de temps entre des dates
> $t_1$ et $t_2$.

### Repère de l'espace
Pour repérer un point dans l'espace, on a besoin :
- d'une mesure d'espace, définie par unité de longueur (le mètre);
- d'une origine d'espace, un point fixe dans le référentiel d'étude;
- de trois directions orthogonales fixes

### Exemple de référentiels
#### Référentiel terrestre
Le référentiel terrestre est centré en un point de la Terre, et ses axes sont
liés à la rotation terrestre.

#### Référentiel géocentrique
Le référentiel géocentrique a pour origine le centre de masse de la Terre, et
ses axes sont définis par rapport à trois étoiles suffisamment lointaines pour
sembler immobiles. L'étoile polaire est souvent un des astres choisis.

#### Référentiel héliocentrique
Le référentiel héliocentrique a pour origine le centre de masse du soleil, et
ses axes sont définis par rapport à trois étoiles suffisamment lointaines pour
sembler immobiles.

### Relativité du mouvement
La description du mouvement dépend du référentiel dans lequel on l'étudie. Pour
une étude mécanique, il faut systématiquement préciser le référentiel d'étude
(important !).

### Limites de la description classique
Lorsque la vitesse d'un objet s'approche de celle de la lumière, on observe un
phénomène de dilatation des durées et contraction de la longueur (notamment)
pour une particule.

## Vecteur position
> Par définition, le vecteur position est le vecteur $\overrightarrow{\rm r}(t) = \overrightarrow{\rm OM}(t)$.

### Vecteur position en coordonnées cartésiennes
En plaçant un point $M$ dans le repère, on a le vecteur $\overrightarrow{\rm OM}$ le vecteur de l'origine vers ce point.
Puisque le repère est défini comme $(O, \overrightarrow{\rm e_x}, \overrightarrow{\rm e_y}, \overrightarrow{\rm e_z})$,
on définit $\overrightarrow{\rm OM}$ sous la forme $\overrightarrow{\rm OM}$
$= x \overrightarrow{\rm e_x} + y \overrightarrow{\rm e_y} + z \overrightarrow{\rm e_z}$,
et on a donc le vecteur $\overrightarrow{\rm OM}$ sous la forme d'une équation
horaire $\overrightarrow{\rm OM} \left|\begin{matrix} x(t) \\ y(t) \\ z(t) \end{matrix}\right.$.

##### Exemple
$\overrightarrow{\rm OM} \left\{\begin{matrix} x(t) = R \cos(\omega t) \\ y(t) = R \sin(\omega t) \end{matrix}\right .$ (où $\omega$ est une constante).
On a $\lVert \overrightarrow{\rm OM} \rVert^2 = x^2 + y^2 = R^2$ (l'équation
d'un cercle de rayon R).

### Vecteur position en coordonnées polaires
On peut aussi noter le vecteur position sous la forme $\overrightarrow{\rm r} = \lVert \overrightarrow{\rm r} \rVert \overrightarrow{\rm u_r}$,
avec $\overrightarrow{\rm u_r}$ un vecteur unitaire orienté à un angle $\Theta$
par rapport à $\overrightarrow{\rm u_x}$ en deux dimensions.

### Vecteur position en coordonnées cylindriques
De la même façon que pour les coordonnées polaires, on définit le vecteur
position comme $\overrightarrow{\rm OM} = r \overrightarrow{\rm u_r} + z \overrightarrow{\rm u_z}$,
avec $\overrightarrow{\rm u_r}$ un vecteur unitaire orienté d'un angle $\Theta$
avec l'axe $\overrightarrow{\rm u_x}$, et $u_z$ l'un des vecteurs unitaire de la
base (en général celui de la hauteur).

### Vecteur position en coordonnées sphériques
On définit cette position comme les coordonnées polaires deux fois, donc avec
$\overrightarrow{\rm OM} = r \overrightarrow{\rm u_r}$, avec $\overrightarrow{\rm u_r}$
un vecteur unitaire orienté d'un angle $\varphi$ avec $\overrightarrow{\rm u_x}$
et d'un angle $\Theta$ avec $\overrightarrow{\rm u_z}$.

### Abscisse curviligne
On représente par une mesure algébrique de la distance la position, sur une
courbe. Il s'agit donc de l'équation paramétrique du point, qu'on a sous la
forme $s(t) = \stackrel{\frown}{M_0 M}(t)$. La valeur trouvée est donc la distance d'arc
$\stackrel{\frown}{M_0 M}(t)$.

## Vitesse d'un point
### Définition
On appelle vecteur vitesse instantané du point $M$ par rapport au référentiel $R$
le vecteur $\overrightarrow{\rm v} = \lim\limits_{\Delta t \to + \infty} \frac{\overrightarrow{\rm OM}(t + \Delta t) - \overrightarrow{\rm OM}(t)}{\frac{d \overrightarrow{\rm OM}}{dt}}$
(il s'agit d'un taux de variation, donc de la dérivée de la position).

### Expression du vecteur vitesse en coordonnées cartésiennes
$\overrightarrow{\rm v} = \frac{d \overrightarrow{\rm OM}}{dt}$
$= \frac{d x}{dt} \overrightarrow{\rm e_x} +  x \frac{d \overrightarrow{\rm e_x}}{dt} + \frac{dy}{dt} \overrightarrow{\rm e_y} + y \frac{d \overrightarrow{\rm e_y}}{dt} + \frac{dz}{dt} \overrightarrow{\rm e_z} + z \frac{d \overrightarrow{\rm e_z}}{dt}$
Puisque les vecteurs $\frac{d \overrightarrow{\rm v_x}}{dt}$, $\frac{d \overrightarrow{\rm v_y}}{dt}$, $\frac{d \overrightarrow{\rm v_z}}{dt}$ sont constants, leur dérivée est nulle.

Ainsi, on obtient $\overrightarrow{\rm v} = \frac{d x}{dt} \overrightarrow{\rm u_x} + \frac{d y}{dt} \overrightarrow{\rm u_y} + \frac{d z}{dt} \overrightarrow{\rm u_z}$.
On pose $\dot{x} = \frac{d x}{dt}$, $\dot{y} = \frac{d y}{dt}$ et $\dot{z} = \frac{d z}{dt}$, et ainsi l'équation paramétrique $\overrightarrow{\rm v} \left|\begin{matrix} \dot{x}(t) \\ \dot{y}(t) \end{matrix}\right.$.

##### Exemple
$\overrightarrow{\rm OM} \left|\begin{matrix} x(t) = R \cos(\omega t) \\ y(t) = \sin(\omega t) \end{matrix}\right.$ (avec $\omega$ une constante)

$\overrightarrow{\rm v} \left|\begin{matrix} \dot{x}(t) = -R \omega \sin(\omega t) \\ \dot{y}(t) = R \omega \cos(\omega t) \end{matrix}\right.$

$\lVert \overrightarrow{\rm v} \rVert = R \omega$ (une constante).

### Vecteur vitesse en coordonnées polaires
$\overrightarrow{\rm r} = r \overrightarrow{\rm  u_t}$, et on a ainsi
$\overrightarrow{\rm v} = \frac{dr}{dt} \overrightarrow{\rm u_r} + r \frac{d}{dt} [\overrightarrow{\rm u_r}]$,
or $\frac{d [\overrightarrow{\rm u_r}]}{dt} = \frac{d \Theta}{dt} \times \frac{d}{d \Theta} [\overrightarrow{\rm u_r}]$.

On verra par le TD les étapes intermédiaires, et on a
$\frac{d}{d \Theta} [\overrightarrow{\rm u_r}] = \frac{d}{d \Theta} = \dot{\Theta} \overrightarrow{\rm u_\Theta}$
et $\frac{d}{d \Theta} [\overrightarrow{\rm u_\Theta}] = -\dot{\Theta} \overrightarrow{\rm u_r}$.
On obtient finalement $\overrightarrow{\rm v} = \frac{d r}{dt} \overrightarrow{\rm u_r} + r \frac{d \Theta}{dt} \overrightarrow{\rm u_\Theta} = \dot{r} \overrightarrow{\rm  u_r} + r \dot{\Theta} \overrightarrow{\rm u_\Theta}$.

On peut ainsi poser les équations horaires
$\overrightarrow{\rm v} \left|\begin{matrix} v_r(t) = \dot{r} \\ v_\Theta(t) = r \dot{\Theta} \end{matrix}\right. $

### Vecteur vitesse dans la base de Frenet
En définissant une tangent et sa normale à la courbe $\overrightarrow{\rm v} = \frac{d s}{dt} \overrightarrow{\rm t}$.
