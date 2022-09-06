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

Bornes     | Rayons gamma | Rayons X | Ultraviolets | Visible  | Infrarouges | Micro-ondes | Autres | Ondes radio
Plus petit | -            | 10 pico  | 10 nano      | 380 nano | 780 nano    | 1 mm        | 30 cm  | 1 m
Plus grand | 10 pico      | 10 nano  | 380 nano     | 780 nano | 1 mm        | 30 cm       | 1 m    | -

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

Exemple : le verre est un milieu dispersif, c'est pourquoi chaque couleur de la
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
> par un trait muni d'un flèche qui indique le sens de propagation de la lumière

### Cadre de l'optique géométrique
On suppose que les milieux traversés sont :
- Transparents
- Homogènes
- Isotrope (même propriétés dans toutes les directions)

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
