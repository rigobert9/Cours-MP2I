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
> arrivent sur l'axe optique parallèles entre eux sur l'axe optique, et formant

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

Pour tous points $A$ et $B$, $\overline{AB = -\overline{BA}}$.
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
$\overline{FA}\overline{F'A'} = -f'^2$

Ainsi, le grandissement peut s'exprimer sous la forme
$\gamma = \frac{-\overline{F'A'}}{f'} = \frac{f'}{\overline{FA}}$.

#### Relation de conjugaison de Descartes, dite "aux centres"
$\frac{1}{\overline{OA'}} - \frac{1}{\overline{OA}} = \frac{1}{f'}$
