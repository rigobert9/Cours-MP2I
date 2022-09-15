# Chapitre 2 : Systèmes optiques
## Systèmes optiques et stigmatisme
### Systèmes optiques
> Un système optique est une succession de milieux transparents séparés par des
> dioptres ou des miroirs (un exemple avec deux lentilles serait la lunette
> astronomique).

Celui-ci comporte une face d'entrée et une face de sortie des rayons qui le
traversent.

Diagramme

> Un système optique est dit centré si tous ses composants présentent une
> symétrie de rotation autour d'un axe commun, nommé axe optique.

Image axe optique

Dans la réalité, les sources lumineuses sont étendues. Par la suite, on
travaillera avec des sources ponctuelles pour éviter de nombreux phénomènes.

> Un point source est une source lumineuse ponctuelle.

### Stigmatisme rigoureux
> Le point de croisement des prolongements des rayons entrants dans un système
> optique est **l'objet**. Il est considéré comme ponctuel.

> **Définition :** Un système optique est dit rigoureusement stigmatique si tous
> les rayons issus d'un objet ponctuel $A$ convergent en sortie vers un unique
> point $B$. Dans ce cas, le point $B$ est l'image conjuguée de $A$. Les points
> $A$ et $B$ sont dits conjugués.

> Pour un système optique stigmatique, le point de croisement des prolongements
> des rayons sortants du système optique est l'image.

> Un point source placé sur l'axe optique d'un système centré rigoureusement
> stigmatique donne une image placée sur l'axe.

> Les rayons provenant d'un objet situé à l'infini __sur__ l'axe optique arrivent
> sur le système optique parallèle entre eux.

> Les rayons provenant d'un objet situé à l'infini __hors de__ l'axe optique
> arrivent sur l'axe optique parallèles entre eux sur l'axe optique.

### Stigmatisme approché
Dans la pratique, il existe très peu de systèmes optiques rigoureusement
stigmatiques. Tout capteur optique (une pellicule, cellule CCD, rétine) à une
limite de résolution.

L'image d'un objet ponctuel sera alors net si sa taille sur le capteur est plus
petite que la taille d'une cellule. Tous les rayons qui arrivent vont alors
être captés comme une unité mesurée (un pixel par exemple).

> Un système optique vérifie un stigmatisme approché si les rayons image d'un
> objet ponctuel se concentrent sur une zone plus faible que la taille d'une
> cellule (donc que plusieurs rayons donnent un unique pixel).

### Aplanétisme
> Un objet vérifie un aplanétisme si l'image d'un objet perpendiculaire à l'axe optique
> est perpendiculaire à l'axe optique (bien qu'il puisse être renversé).

### Un système rigoureusement stigmatique : le miroir plan
Le miroir plan est un système rigoureusement stigmatique et aplanétique.

## Les lentilles miroir
### Définition et premières propriétés
> Une lentille est un bloc, généralement en verre ou autre matériau transparent,
> servant à faire converger ou diverger la lumière.

Une lentille est dite mince si ses dimensions (largeur, épaisseur), sont petites
devant les rayons de courbure des faces.

Représentations schématiques :

### Conditions de Gauss
Dans le cadre de l'approximation des conditions des Gauss, les rayons sont peu
inclinés et peu éloignés de l'axe optique. Ils sont dits paraxiaux.

### Caractère réel ou virtuel des objets ou des images
Voir image.

### Points particuliers
#### Centre optique
> Le centre optique est le centre de la lentille, noté $O$.

Un rayon passant par le centre optique n'est pas dévié.

#### Point focal de l'image
> Le point focal d'image ou foyer principal image ou foyer image est l'image
> conjuguée du point source, situé à l'infini sur l'axe optique. Il est noté
> $F'$.

Les rayons entrant parallèles à l'axe optique convergent en sortie vers le foyer
image $F'$.

#### Point focal objet
> Le point dont l'image conjuguée est à l'infini est appelé le point focal objet

Les rayons passant par le foyer objet émergent parallèlement à l'axe optique.

#### Symétrie de la lentille
$F$ et $F'$ sont symétriques par rapport à l'axe optique

### Aberrations
#### Aberrations géométriques
On observe des aberrations géométriques lorsqu'il y a un écart entre les rayons
paraxiaux et les rayons réels. On observe alors une tache floue au lieu d'une
image ponctuelle.

#### Aberrations chromatiques
Les aberrations chromatiques sont caractérisées par différentes taches floues
colorées qui dépendent de la longueur d'onde (à cause de l'entrée dans un milieu
dispersif).

### Les relations algébriques des lentilles
#### Les distances algébriques
On observe pour deux point $A, B$, si $AB$ est horizontal, la distance
algébrique $\overline{AB} = AB > 0$ si b est plus avancé sur l'axe optique, et
$\overline{AB} = -AB > 0$ sinon.
Pour $AB$ vertical, si B est plus haut au-dessus de l'axe optique $\overline{AB} = AB > 0$ et
$\overline{AB} = -AB > 0$ sinon.

Pour tous points $A$ et $B$, $\overline{AB} = -\overline{BA}$.
Pour tous points $A, B, C$, $\overline{AB} = \overline{AC} + \overline{CB}$ (sur
le même axe horizontal ou vertical).

#### Distance focale et vergence
La distance focale image (ou distance focale) vérifie $f' = \overline{OF'}$.
Comme $f'$ est une distance algébrique, son signe renseigne sur le type de la
lentille :
- Si $f' > 0$, c'est une lentille convergente
- Si $f' < 0$, c'est une lentille divergente

La vergence $V$ est l'inverse de la distance focale, mesurée en dioptrie $\delta$
($m^{-1}$), selon la relation $V = \frac{1}{f'}$.

#### Le grandissement
Le grandissement transversal $\gamma$, ou grandissement, est défini par
$\gamma = \frac{\overline{A'B'}}{\overline{AB}}$, et est sans unité.
- Si $|\gamma| < 1$, l'image est plus petite que l'objet
- Si $|\gamma| > 1$, l'image est plus grande que l'objet
- Si $\gamma < 0$, l'image est renversée

Avec le théorème de Thalès, $\gamma = \frac{\overline{A'B'}}{\overline{AB}} = \frac{\overline{OA'}}{\overline{OA}}$.

### Relation de conjugaison
#### Relation de conjugaison de Newton, dite "aux foyers"
$\overline{FA}\,\overline{F'A'} = -f'^2$

Ainsi, le grandissement peut s'exprimer sous la forme
$\gamma = \frac{-\overline{F'A'}}{f'} = \frac{f'}{\overline{FA}}$.

#### Relation de conjugaison de Descartes, dite "aux centres"
$\frac{1}{\overline{OA'}} - \frac{1}{\overline{OA}} = \frac{1}{f'}$

### Application : la loupe
Avec une loupe $f' = 5 cm$, $\overline{AB} = 1cm$ et $\overline{OA} = -3cm$.
L'image $\overline{A'B'}$ est agrandie, virtuelle, et de même sens que l'objet.
On a ainsi les mesures supplémentaires :
$\overline{A'B'} = 2.5cm$, $\overline{OA'} = 7.5cm$, $\overline{F'A'} = -12.5cm$, $\gamma = 2.5$.

On peut alors montrer $\overline{F'A'}$ à partir de la relation de conjugaison
de Newton, ainsi que $\gamma = 2.5$.

On peut non seulement calculer $\overline{OA'}$ par Thalès, mais aussi par la
relation de conjugaison de Descartes, qui nous donne :
$\frac{1}{\overline{OA'}} - \frac{1}{\overline{OA}} = \frac{1}{f'}$
$\Leftrightarrow \frac{1}{\overline{OA'}} = \frac{1}{\overline{OA}} + \frac{1}{f'}$
$\Leftrightarrow \frac{1}{\overline{OA'}} = \frac{\overline{OA} + f'}{\overline{OA} \times f'}$
$\Leftrightarrow \overline{OA'} = \frac{\overline{OA} \times f'}{\overline{OA} + f'}$
$\Leftrightarrow \overline{OA'} = \frac{-15}{2}$

### Condition expérimentale pour obtenir une image réelle à partir d'un objet réel
On doit, en prenant en compte la grandeur $D = \overline{AA'} > 0$ fixe,
déterminer $x = \overline{OA'} < 0$.

Voir TP : Méthode de Bessel.

D'après la relation de Descartes,
$\frac{1}{\overline{OA'}} - \frac{1}{\overline{OA}} = \frac{1}{f'}$.
Or, $\overline{OA'} = \overline{OA} + \overline{AA'} = x + D$,
donc $\frac{1}{x+D} - \frac{1}{x} = \frac{1}{f'}$.
Ainsi, on a $x = \frac{1}{x+ D} - \frac{1}{x} - \frac{1}{f'} = 0$.
On multiplie tout par $x(x+D)f'$, et on obtient le polynôme
$xf'- f'(x + D) - x(x + D) = 0$
$\Leftrightarrow x^2 + Dx + f'D = 0$. En obtenant le discriminant, on a
$\Delta = D^2 - 4Df' = D(D-4f') \geq 0$, donc $D \geq 4f'$

Pour former l'image réelle d'un objet réel, avec une lentille convergente de
focale $f'$, il faut que l'objet et l'écran soit séparés d'une distance $D \geq 4f'$

## Association de lentilles
### Association de deux lentilles convergentes
> $A_1, B_1$ est l'image intermédiaire de l'objet dans le système optique

##### Exemple
$f'_1 = f'_2 = 2cm$, $\overline{O_1 O_2} = 5cm$, $\overline{AB} = 1cm$, $\overline{O_1 A} = -4cm$.

### La lunette astronomique
La lunette astronomique est un système afocal.

> Un système optique est dit afocal si un objet à l'infini y donne une image à
> l'infini.

Le grossisement vérifie dans ce système $G = \frac{\alpha'}{\alpha}$, avec $\alpha$ le diamètre
apparente de l'œil, et $\alpha'$ le diamètre apparent à travers la lunette.

## Modélisation de l'œil
### Description sommaire
Modélisation : Le cristallin est représenté par une lentille convergente, la
rétine par un écran et l'iris avec la pupille par un diaphragme.

Attention : au cours de la vision, la distance entre la lentille et l'œil ne
change pas, la focale du cristallin varie par le système de diaphragme de l'iris
sans modifier la distance à la rétine qui est fixée par l'anatomie à environ 1.7
cm.

### Caractéristiques optiques
#### Champ visuel
> Le champ visuel d'un capteur optique décrit la portion d'espace visible pour
> le capteur. Il est défini comme l'angle entre les rayons extrêmes accessibles
> au capteur.

#### Pouvoir séparateur ou acuité visuelle
> Le pouvoir séparateur d'un capteur optique décrit sa capacité à pouvoir
> distinguer deux points très proches. Il est défini comme l'angle minimal que
> doivent former deux rayons pour pouvoir être interprétés comme provenant de
> deux points différents.

On exprime l'acuité visuelle comme $\alpha = 1 \text{minute d'arc} = (\frac{1}{60})° = 0.017° \approx 3 \times 10^{-4} \text{rad}$.

#### Limite de vision nette
> Le punctum proximum (PP) est le point le plus proche de l'œil qui est visible
> nettement.

> Le punctum remotum (PR) est le point le plus lointain de l'œil qui est visible
> nettement.

Un œil qui n'accommode pas voit au punctum remotum, qui se situe pour un œil
normal à l'infini.

Le punctum proximum d'un œil normal se trouve entre 20 et 25 cm.

### Défauts de la vision
#### Myopie
Le cristallin d'un myope est trop convergent, si bien que le punctum proximum
d'un myope se trouve plus près de l'œil que pour un œil normal. De plus, le
punctum remotum n'est pas à l'infini.

Les myopes se font corriger avec des lunettes, qui sont des lentilles
divergentes de dioptrie en général entre -1 et -2.

#### Hypermétropie
L'hypermétropie est l'opposé de la myopie.
Le cristallin d'un hypermétrope n'est pas assez convergent, si bien que le punctum proximum
d'un hypermétrope se trouve plus loin de l'œil que pour un œil normal.

Les hypermétropes se font corriger avec des lunettes, qui sont des lentilles
convergentes de dioptrie en général entre 1 et 2.

Un œil "normal" est appelé "emmetrope".

#### Astigmatie
Le cristallin d'un astigmate n'est plus parfaitement sphérique, mais a plutôt
une forme ovale (ballon de rugby). Le système n'est alors plus stigmatique et
les images qu'il forme sont entachées d'aberrations géométriques.

> "Vous avez des ballons de rugby dans les yeux."

#### Presbytie
La presbytie est un trouble de la vision qui rend difficile la vision de près.
Cela a pour conséquence d'éloigner le punctum proximum. Ce problème arrive
souvent en vieillissant, vers 40-45 ans, et est provoquée par le relâchement des
muscles de l'iris.
