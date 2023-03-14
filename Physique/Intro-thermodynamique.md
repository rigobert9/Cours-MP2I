# Introduction à la thermodynamique
> Thermodynamique : Branche de la physique qui étudie la dépendance des propriétés
> des corps à la température ainsi que les échanges thermiques entre les corps.

Depuis le début du 19ème et les débuts de la machine à vapeur, la
thermodynamique a été étudiée. L'un des précurseurs est le polytechnicien Sadi
Carnot (pas le président), dans son court ouvrage "Réflexions sur la puissance
motrice du feu", où il fait une description macroscopique du problème.

## Systèmes thermodynamiques
La thermodynamique dispose beaucoup de son propre jargon.

### Définitions
> Un système thermodynamique est l'ensemble des entités se trouvant à l'intérieur
> d'un domaine de l'espace limité par une frontière (qui n'est pas forcément
> physique, c'est à nous de définir les bordures).

> Il y a trois types de système thermodynamiques :
> - Un système isolé est un système qui n'échange ni matière, ni transfert
>   thermique avec le milieu extérieur (on ne définira ce type de système que par
>   approximation, ou pour désigner tout l'univers). Un système isolé a des parois
>   athermanes/calorifugées.
> - Un système fermé est un système n'échangeant pas de matière mais pouvant
>   réaliser des transferts thermiques avec le milieu extérieur. Les parois sont
>   condutrices de chaleur, qu'on appelle diathermanes.
> - Un système ouvert est un système qui échange de la matière et de la chaleur.

### Taille des systèmes
> On distingue les tailles des différents systèmes étudiés :
> - Un système macroscopique contient une grande quantité de matière, de l'ordre
>   de la mole (un nombre d'Avogadro d'atomes, $6.022 \times 10^{23} \text{mol}^{-1}$).
>   Ce nombre d'atomes explique la difficulté à réaliser une simulation complète.
> - Un système microscopique contient des entités individuelles comme des atomes,
>   des ions, ou des molécules.
> - Un système mésoscopique, celui qu'on le plus souvent, est un système assez
>   grand pour contenir assez d'entités pour faire un traitement statistique
>   (plusieurs milliers), mais suffisamment petit pour être considéré comme
>   ponctuel par rapport à l'échelle macroscopique.

> Le libre parcours moyen d'une particule ($\ell$ ou $\lambda$) est le chemin
> moyen parcouru par un système entre deux chocs avec d'autres particules du
> système.

Pour un gaz, le libre parcours moyen des particules est de $\ell \approx 10^{-7} m$,
et pour un liquide, il est de $\ell \approx 10^{-10} m = 1 A°$ (1 Angström).
Pour le premier, on peut considérer qu'il y a très peu d'intéractions et
seulement des chocs de boules de billard, tandis que le modèle doit changer pour un liquide.

### Description
#### Variables d'état
> La pression, exprimée en unités SI en Pascal ($\text{Pa}$), ou parfois en Bar
> ($1 \text{bar} = 10^{5} \text{Pa}$). Elle correspond à la force pressante sur
> une surface, selon la formule $p = \frac{F}{S}$.

La pression est ainsi de dimension $\frac{ML^2T^{-2}}{L^2} = MT^{-2}$.

> La température est une grandeur liée au degré d'agitation thermique. Elle est
> mesurée en Kelvin ($K$) (avec un décalage de $-273.15$ avec le degrés Celsius).
> Sa dimension est $\Theta$, la température.

> Le volume est mesuré en $m^3$, de dimension $L^3$.

> La quantité de matière $n$ est mesurée en moles, selon le nombre d'atomes
> divisés par le nombre d'Avogadro. La quantité de matière est de dimension $N$.

> Les fractions massique $x_i$ sont des rapports entre la masse d'un objet $m_i$
> et la masse du système $m_\text{tot}$, de dimension $MM^{-1} = 1$.

> Les fractions massique $x_i$ sont des rapports entre la quantité de matière d'un objet $n_i$
> et la quantité de matière du système $n_\text{tot}$, de dimension $NN^{-1} = 1$.

#### Variables extensives
> Une grandeur extensive est une grandeur qui double lors de la réunion de deux
> systèmes identiques.

C'est le cas de la masse, du volume, ou de la quantité de matière.

#### Variables intensives
> Une grandeur intensive qui reste inchangée lors de la réunion de deux systèmes
> identiques.

C'est le cas de la température ou de la pression.

## Équilibre thermodynamique
### Définition
> Un système thermodynamique est dit à l'équilibre lorsque toutes ses variables
> d'état peuvent être définies et sont stationnaires (ne varient plus selon le
> temps), et que ses parois ne sont le lieu d'aucun échange avec l'extérieur
> avec le milieu extérieur.

## Équilibre mécanique
> Un système est à l'équilibre mécanique s'il n'y a pas de mouvement de matière à
> l'échelle du système.

Pour un système macroscopique ou mésoscopique, on ignore ainsi le mouvement des
atomes qui arrivera toujours.

> Un système thermodynamique est à l'équilibre mécanique au niveau d'une paroi
> libre de se déplacer si cette dernière est immobile, donc si la résultante des
> forces qui s'exerce sur elle est nulle.

Ainsi, l'équilibre mécanique n'est pas maintenant pour un piston qui se déplace.

### Équilibre thermique
> Un système thermodynamique est à l'équilibre thermique si sa température est
> constante.

> Lorsque l'équilibre thermique est atteint, la température $T$ du système est
> telle que $T$ est égale à la température extérieure $T_\text{ext}$ pour un
> système fermé.

### Variables nécessaires pour décrire un système à l'équilibre
> Un système est dit thermoélastique si la connaissance de sa quantité de matière
> $n$, son volume $V$, sa pression $P$, et sa température $T$, permet de
> déterminer totalement son état macroscopique à l'équilibre.

Les seules variables d'état nécessaires pour décrire l'état macroscopique d'un
système fermé à l'équilibre sont $T$, $P$, et $V$.

### Équation d'état
> Une équation d'état est une équation qui relie les variables d'état, c'est à
> dire une fonction $f(P,V,T) = 0$.

> Si un système thermoélastique fermé présente une équation d'état, seules deux
> variables d'état sont nécessaires pour le décrire.

## Fonction d'état
### Définition
> Une fonction d'état est une grandeur caractéristique d'un système
> thermodynamique qui peut s'exprimer à l'équilibre thermodynamique en fonction
> des variables du système.

C'est le cas de l'énergie interne du système ou encore de la formule des gaz
parfaits $P(n,V,T) = \frac{n R T}{V}$.

### Énergie interne $U$
Soit un système fermé de $N$ particules, avec des interactions qui dérivent d'un
potentiel (et sont donc conservatives).\
Son énergie cinétique, selon la vitesse $\overrightarrow{\rm v} = \overrightarrow{\rm v_\text{moyenne}} + \overrightarrow{\rm v_i}$,
avec la vitesse moyenne des particules si le système se déplace et la vitesse
d'une particule, est alors $E_c = \frac{1}{2} \sum\limits_{i = 1}^{N} m_i \lVert \overrightarrow{\rm v_\text{moyenne}} + \overrightarrow{\rm v_i} \rVert^2$,
qu'on développe comme $E_c = E_{c, \text{macro}} + E_{c, \text{micro}}$, avec
$E_{c, \text{macro}} = \frac{1}{2} \sum\limits_{i = 1}^{N} m \lVert \overrightarrow{\rm v_\text{moyenne}} \rVert^2$
et $E_{c, \text{micro}} = \frac{1}{2} \sum\limits_{i = 1}^{N} m \lVert \overrightarrow{\rm v_i} \rVert^2$
$+ m \overrightarrow{\rm v_{moyenne}} \cdot \sum\limits_{i = 1}^{N} \overrightarrow{\rm v_i}$.\
De même, on a $E_p = E_{p, \text{macro}} + E_{p, \text{micro}}$, séparant les
forces qui s'exerçent globalement sur le système et celles qui agissent sur la
particule.

> L'énergie interne $U$ est la somme $E_{C, \text{micro}} + E_{p, \text{micro}}$.

Définie sous ces hypothèses (particules ponctuelles et interaction dérivant
d'une énergie potentielle), l'énergie interne est une fonction d'état, donc sa
valeur ne dépend que de l'état du système et pas de la manière dont le système
atteint cet état.

### Enthalpie $H$
> L'enthalpie $H$ d'un système à l'équilibre de volume $V$ et de pression $P$ est
> définie comme $H = U + PV$. C'est une fonction d'état extensive.

Elle est homogène à une énergie et est donc mesurée en Joules.

### Capacités thermiques à volume et pression constants
> Dans un système thermoélastique fermé, la capacité thermique à volume constant
> est $C_V = \frac{\partial U}{\partial T}_V$.

On dérive uniquement selon la température on conservant le volume constant.

> Dans un système thermoélastique fermé, la capacité thermique à pression constante
> est $C_P = \frac{\partial H}{\partial V}_P$.

> Les capacités thermiques à pression ou à volume constants sont des grandeur
> intensives.

La capacité thermique massique à volume constant $c_V = \frac{C_V}{m}$
et à pression constante $c_P = \frac{C_P}{m}$, en $J \cdot K^{-1} \cdot kg^{-1}$,
et la capacité thermique molaire à volume constant $c_{V,n} = \frac{C_V}{n}$
et à pression constante $c_{P,n} = \frac{C_P}{n}$, en $J \cdot K^{-1} \cdot \text{mol}^{-1}$
sont parfois rencontrées.

> On a, par intégration, les relations $\Delta U = C_V \Delta T$ et $\Delta H = C_P \Delta T$.

## Description des gaz
### Approche historique
#### Lois phénoménologiques
> Loi de Boyle-Mariotte : $PV$ est constant (expérimental).

#### Échelle de température
Pour définir la température, il faut une température de référence $T_R$, à
partir de laquelle on définit $T = \frac{PV(T)}{PV(T_R)} T_R$.

### Modèle microscopique des gaz parfaits
#### Hypothèses du modèle
Le modèle microscopique utilisé a pour hypothèses :
- Les molécules sont considérées comme des points matériels, de taille
  négligeable devant la distance les séparant.
- On considère que les interactions entre les particules sont négligeables.
- On considère que les variables intensives sont les mêmes à l'échelle du gaz
  (Homogénéité). Cela se traduit statistiquement par des variables identiques en
  moyenne en tout point.
