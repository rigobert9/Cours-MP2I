# Champ magnétique
## Champ magnétique et lignes de champ
### Notion de champ
> Un champ est une fonction $\mathbb{R}^3 \times \mathbb{R} \to E$, qui à chaque point $M$
> de l'espace et pour chaque instant $t$ associe la valeur d'une grandeur
> physique. Cette grandeur physique peut être scalaire ou vectorielle.

La carte météo présente un champ scalaire, et le champ gravitationnel constitue
un champ vectoriel (de formule $\overrightarrow{\rm F_{m_0 \to m}} = - G \frac{m_0 m}{\lVert \overrightarrow{\rm OM} \rVert^3} \overrightarrow{\rm OM} = m \overrightarrow{\rm g}$,
où $g$ est le champ exercé par $m_0$).

### Champ magnétique $\overrightarrow{\rm B}$
Le champ magnétique est un champ vectoriel généré soit par un aimant permanents
soit par un courant électrique, et se mesure en $T$ (Tesla).

> Le champ magnétique est un champ vectoriel défini en tout point de l'espace et à
> tout instant, permettant de modéliser les effets magnétiques des courants
> électriques ou des matériaux magnétiques comme les aimants permanents.

Le champ magnétique est dit stationnaire s'il ne dépend pas du temps, uniforme
s'il ne dépend pas de la position dans l'espace, et constant s'il ne dépend ni de
l'espace ni du temps.

### Lignes de champ
> Une ligne de champ est un courbe orientée $\mathcal{C}$ pour laquelle le champ magnétique
> y est tangent en chaque point $M$ et à chaque instant $T$. On a donc
> $\forall t, \forall m \in \mathcal{C}, \overrightarrow{\rm B}(M,t) \wedge d \overrightarrow{\rm r}(M,t) = \overrightarrow{\rm 0}$

## Origine du champ magnétique
### Les aimants permanents
Dès l'antiquité les grecs avaient remarqué que la magnétite ($Fe_3 O_4$)
était magnétique sans comprendre le phénomène, et les chinois ont compris que
l'alliage de Néodyme, Fer, et Bore, permettait de faire une boussole.

#### Aimant droit
Un grand nombre d'aimants possède deux pôles opposés sur une même barre
métallique. On peut utiliser ce même modèle pour le champ magnétique terrestre
avec un aimant orienté sur l'axe du nord et du sud magnétique de la Terre
(environ 10 degrés de différence avec le nord géographique).

Par convention, pour tous les aimants, on fait aller les flèches du nord au sud
magnétique d'un aimant.

#### Aimant en U
Entre les deux pattes d'un aimant en $U$ règne un champ magnétique constant
d'une patte à l'autre, et les deux pattes sont de polarité opposée.

### Le courant électrique
Ce phénomène a été pour la première fois observé par Orsted en 1820 à l'aide
d'un fil électrique au-dessus d'une boussole, qui oscille alors entre la
direction du champ magnétique terrestre et la direction perpendiculaire au fil.

#### Spire circulaire
Une spire qu'on soumet à un courant électrique va générer un champ magnétique
circulaire perpendiculaire autour de la spire.

#### Fil infini
En prenant un fil électrique, il génère un champ magnétique circulaire autour du
fil.

#### Solénoïde
Un solénoïde est un fil en forme de ressort fini : un champ magnétique uniforme
et rectiligne est généré au milieu des boucles, et le reste du champ s'enroule
sur les côtés du solénoïde.

### Propriétés générales
- Si les lignes de champ sont parallèles entre elles et régulièrement espacées,
  alors le champ est uniforme.
- Les lignes de champ sont toujours des courbes fermées.
- Lorsque les lignes de champ sont plus resserrées, le champ est plus intense.
- Les zones où le champ est le plus intense se trouvent au voisinage de la
  source du champ magnétique.

### Lien entre deux sources de magnétisme
Soit un boucle de courant qui va dans le sens trigonométrique
qui forme un cercle de surface $S = \pi R^2$, avec un vecteur normal $\overrightarrow{\rm n}$,
on définit le moment magnétique comme $\overrightarrow{\rm \mathcal{M}} = i \overrightarrow{\rm S}$
où $\overrightarrow{\rm S} = S \overrightarrow{\rm n}$.

Dans les aimants, on considère qu'on a ces surfaces qui s'orientent vers les
pôles nord.

L'origine du champ magnétique est le déplacement de particules chargées,
c'est-à-dire un courant. Ce mouvement correspond à un moment magnétique, qui
peut être considéré également comme l'origine du champ magnétique.

## Champ magnétique pour quelques systèmes
### Spire circulaire
Il s'agit d'un spire circulaire dans laquelle passe un courant $i$ dans le sens
trigonométrique, de rayon $R$ et d'axe $(Oz)$.

On a $\overrightarrow{\rm B} = \frac{\mu_0 i}{2R} \sin^3(\alpha) \overrightarrow{\rm e_z}$\
$= \frac{\mu_0 i}{2 R (1 + (\frac{z}{R})^2)^{\frac{3}{2}}} \overrightarrow{\rm e_z}$,
avec $\mu_0$ la perméabilité du vide ($4 \pi \times 10^{-7} H \cdot m^{-1}$).

### Solénoïde infini
Pour un solénoïde fini en longueur mais avec un nombre de spires infini,
on a $\overrightarrow{\rm B} = \mu_0 n i \overrightarrow{\rm e_z}$ (il s'agit du
cas $L \gg R$), avec $n = \frac{N}{L}$, pour $N$ le nombre de spires et $L$ la
longueur du solénoïde.

### Fil infini
Pour un fil infini, avec $\overrightarrow{\rm e_\theta}$ un vecteur
perpendiculaire au champ orienté dans le sens trigonométrique quand on oriente
le courant vers le haut.

On obtient $\overrightarrow{\rm B} = \frac{\mu_0 i}{2 \pi R} \overrightarrow{\rm e_\theta}$.

### Moment magnétique
Si la taille de la source du moment magnétique $L$ est négligeable devant la
distance à la source $r$, on obtient $\overrightarrow{\rm B} = \frac{\mu_0 \mathcal{M}}{4 \pi r^3} (2 \cos \theta \overrightarrow{\rm e_r} + \sin \theta \overrightarrow{\rm e_\theta})$.

Vue de loin, toute les sources de champ magnétique peuvent être assimilées à un
moment magnétique.

Par exemple, pour une bobine d'axe $(Oz)$ de rayon $R$ et avec $N$ spires,
on a $\overrightarrow{\rm \mathcal{M}} = I \overrightarrow{\rm S} = N i \overrightarrow{\rm S}$
$= N i \pi R^2 \overrightarrow{\rm e_z}$, donnant
$\overrightarrow{\rm B}(M) = \frac{\mu_0 N i \pi R^2}{4 \pi r^3} (2 \cos \theta \overrightarrow{\rm e_r} + \sin \theta \overrightarrow{\rm e_\theta})$.
Pour un point $M$ de l'axe avec $\theta = 0$ et $r = z$, on a donc
$\overrightarrow{\rm B}(M) \approx \frac{\mu_0 N i R^2}{2 z^3} \overrightarrow{\rm e_r}$.
On retrouve ainsi un résultat similaire à la formule de la spire avec $z \gg R$.

### Ordres de grandeur

Dispositif | Ordre de grandeur de $B$ | Ordre de grandeur de $\mathcal{M}$
---|---|---
Spire circulaire | $10^{-5} T$ | $10^{-2} A \cdot m^2$
Solénoïde | $10^{-2} T$ sur l'axe | $10 A \cdot m^2$
Terre | $5 \times 10^{-5} T = 0,5 G$ | $10^{23} A \cdot m^2$
Aimant permanent usuel | $0,1$ à $1 T$ | $\approx 10^{6} A \cdot m^2$
Aimant permanent conducteur | $1$ à $100 T$ | -
Étoile à neutrons | $10^{7} T$ | -
