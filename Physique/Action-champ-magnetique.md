# Action d'un champ magnétique
## Force de Laplace
### Expression
On représente un conducteur par une courbe $\mathcal{C}$ de $D$ à $F$,
parcourue par le courant $i$, et qui en chaque point $M$ possède ainsi un
déplacement infinitésimal $d \overrightarrow{\rm l}$.

On définit la force de Laplace par sa différentielle.

> $d \overrightarrow{\rm F_L} = i d \overrightarrow{\rm l} \wedge \overrightarrow{\rm B}$

On a donc $\overrightarrow{\rm F_L} = \int\limits_\mathcal{C} i d \overrightarrow{\rm l} \wedge \overrightarrow{\rm B}$,
ou encore $\overrightarrow{\rm F_L}(t) = i(t) \int\limits_\mathcal{C} d \overrightarrow{\rm l}(M,t) \wedge \overrightarrow{\rm B}(M,t)$.
Si $\overrightarrow{\rm B}$ est uniforme on peut simplifier en
$\overrightarrow{\rm F_L}(t) = i(t) \overrightarrow{\rm B} \wedge \int\limits_{D}^{F} d \overrightarrow{\rm OM} = i \overrightarrow{\rm DF} \wedge \overrightarrow{\rm B}$.

##### Exemple : Pendule pesant
Soit un pendule pesant de longueur $L$, tournant autour d'une liaison pivot
parfaite, tenant à une ligne conductrice parcourue par $i$, nous donnant $d \overrightarrow{\rm F_L} = i d \overrightarrow{\rm l} \wedge \overrightarrow{\rm B}$
$= - i d r B \overrightarrow{\rm e_\theta}$,
donc $\overrightarrow{\rm F_L} = - i B \int\limits_{0}^{L} d \overrightarrow{\rm r} \overrightarrow{\rm e_\theta}$
$= - i B L \overrightarrow{\rm e_\theta}$.

##### Exemple : Rails de Laplace
On prend des rails placés en U, traversés par une tension $u$ et à une distance
$L$ l'un de l'autre. Une tige ferme le circuit et est posée sur le circuit.
On peut mesure un champ magnétique $\overrightarrow{\rm B}$ uniforme vers l'intérieur du
circuit sur l'axe $\overrightarrow{\rm e_z}$ pour la tension allant dans le sens horaire.

La force de Laplace élémentaire est $d \overrightarrow{\rm F_L} = i d \overrightarrow{\rm l} \wedge \overrightarrow{\rm B}$.
On s'intéresse au mouvement élémentaire dans la barre, qui est donc orienté
selon $\overrightarrow{\rm e_y}$, donnant $d \overrightarrow{\rm F_L} = i B d y \overrightarrow{\rm e_x}$.
On a enfin en intégrant $\overrightarrow{\rm F_L} = - i B L \overrightarrow{\rm e_x}$

### Moment de la force de Laplace
> Le moment élémentaire en $O$ exercé par la force de Laplace élémentaire en un
> point $M$ du conducteur $\mathcal{C}$ est $d \overrightarrow{\rm \mathcal{M}_O} = \overrightarrow{\rm OM} \wedge d \overrightarrow{\rm F_L}$

> Le moment en $O$ exercé par la force de Laplace sur tout le conducteur $\mathcal{C}$
> correspond à l'intégrale des moments en $O$ sur la courbe $\mathcal{C}$.

> S'il existe un point $P$ tel que $\overrightarrow{\rm \mathcal{M}_P} = 0$, la
> force de Laplace exercée sur un conducteur est équivalente à une force unique
> $\overrightarrow{\rm F_L}$ appliquée en $P$, et on a $\overrightarrow{\rm \mathcal{M}_O} = \overrightarrow{\rm OP} \wedge \overrightarrow{\rm F_L}$.

##### Exemple : Tige oscillante
On prend $G$ le milieu de la tige, et on a donc
$\overrightarrow{\rm \mathcal{M}_G}(\overrightarrow{\rm F_L}) = \int \overrightarrow{\rm GM} \wedge d \overrightarrow{\rm F_L}$\
$= \int \overrightarrow{\rm GO} \wedge d \overrightarrow{\rm F_L} + \int \overrightarrow{\rm OM} \wedge d \overrightarrow{\rm F_L}$\
$= \overrightarrow{\rm GO} \wedge \int d \overrightarrow{\rm F_L} + \int \overrightarrow{\rm OM} \wedge \overrightarrow{\rm F_L}$\
On a montré que $d \overrightarrow{\rm F_L} = - i B dr \overrightarrow{\rm e_\theta}$, donnant
$\overrightarrow{\rm \mathcal{M}_G}(\overrightarrow{\rm F_L}) = (\frac{-L}{2} \overrightarrow{\rm e_r}) \wedge \int\limits_{\frac{-L}{2}}^{\frac{L}{2}} (-i B dr \overrightarrow{\rm e_\theta}) + \int\limits_{\frac{-L}{2}}^{\frac{L}{2}} (r \overrightarrow{\rm e_r}) \wedge (-i B dr \overrightarrow{\rm e_\theta})$\
$= + i \frac{L^2}{2} B \overrightarrow{\rm e_z} - i \frac{L^2}{2} B \overrightarrow{\rm e_z} = \overrightarrow{\rm 0}$\
Ainsi, $\overrightarrow{\rm \mathcal{M}_O} = \overrightarrow{\rm OG} \wedge \overrightarrow{\rm F_L}$\
$= (\frac{L}{2} \overrightarrow{\rm e_r}) \wedge (-i B L \overrightarrow{\rm e_\theta})$\
$= i \frac{L^2}{2} B \overrightarrow{\rm e_z}$

## Équations de la dynamique
### Principe fondamental de la dynamique
On prend le système du conducteur, dans un référentiel terrestre supposé
galiléen. Les forces s'exerçant sur le conducteur sont les forces extérieures
$\overrightarrow{\rm F_\text{ext}}$ et la force de Laplace $\overrightarrow{\rm F_L}$.\
Le PFD nous donne $m \overrightarrow{\rm a_G} = \overrightarrow{\rm F_\text{ext}} + \overrightarrow{\rm F_L}$.

##### Exemple : Rails de Laplace
On reprend l'exemple précédent, avec $G$ un point au milieu de la tige posée sur les
rails, un point $O$ entre les barres, et un axe $x$ entre $O$ et $G$ avec pour
origine $O$, soit $\overrightarrow{\rm OG} = x \overrightarrow{\rm e_x}$. On
néglige les frottements et on obtient en projetant le PDF sur l'axe $(Ox)$,
$m \ddot{x} = - i B L$.

### Théorème du moment cinétique
On prend $O$ un point fixe, et $\overrightarrow{\rm \sigma_O}$ le moment
cinétique au point $O$. On a $\frac{d \overrightarrow{\rm \sigma_O}}{dt} = \overrightarrow{\rm \mathcal{M}_O}(\overrightarrow{\rm F_\text{ext}})$.

##### Exemple : Tige en rotation
On reprend l'exemple, avec une liaison pivot parfaite et une tige indéformable.
On a $\overrightarrow{\rm P} = m \overrightarrow{\rm g}$, donnant un moment
cinétique selon $(Oz)$ $\sigma_{Oz} = J_{Oz} \omega$.\
D'après le TMC selon $(Oz)$, $J_{Oz} \ddot{\theta} = \mathcal{M}_{Oz}(\overrightarrow{\rm F_\text{liaison}}) + \mathcal{M}_{Oz}(\overrightarrow{\rm P}) + \mathcal{M}_{Oz}(\overrightarrow{\rm F_L})$\
$= 0 - m g \sin(\theta) \times \frac{L}{2} - i \frac{L^2}{2} B$

### Théorème de la puissance cinétique
On peut applique le TPC, donnant $\frac{d E_c}{dt} = P_\text{ext} +
P_\text{int}$. Pour un solide indéformable, cette puissance intérieure sera
nulle.

On calcule la puissance de la force de Laplace, $P_L = \int\limits_{\mathcal{C}} d \overrightarrow{\rm F_L} \cdot \overrightarrow{\rm v}$.
- Si le solide est en translation rectiligne à la vitesse $\overrightarrow{\rm v_G}$, on réduit la formule à
  $P_L = \overrightarrow{\rm F_L} \cdot \overrightarrow{\rm v_G}$.
- Si le solide est en rotation autour d'un axe $(Oz)$ à la vitesse angulaire $\overrightarrow{\rm \omega} = \omega \overrightarrow{\rm e_z}$,
  on réduit la formule à $P_L = \mathcal{M}_{Oz}(\overrightarrow{\rm F_L}) \times \omega$.

## Spire rectangulaire en rotation autour d'un axe fixe
On prend un circuit rectangulaire aux angles (dans le sens trigo, en partant du
haut à droite) ABCD, avec des point $M_{i \in [\![1;4]\!]}$ entre chaque circuit
dans ce même ordre. On a les longueurs $AD = BC = L$ et $AB = CD = d$. Un champ
magnétique $\overrightarrow{\rm B}$ est induit. Le vecteur $\overrightarrow{\rm n}$ pointe vers le haut.\
On pose un tige rectiligne sur les points $M_1$ et $M_3$, de centre $O$, que
tourne selon un axe $(Oz)$ avec une vitesse angulaire $\omega = \dot{\theta}$.\
En observant face à l'axe $(Oz)$, la position de la tige forme un angle $\theta$
avec $\overrightarrow{\rm n}$, qui est orienté dans le sens de $\overrightarrow{\rm e_r}$.

### Calcul de la force de Laplace
Comme le pourtour est fermé, on note $\overrightarrow{\rm F_L} = \oint d \overrightarrow{\rm F_l}$.
On obtient donc $\overrightarrow{\rm F_L} = \oint i d \overrightarrow{\rm l} \wedge \overrightarrow{\rm B} = i (\oint d \overrightarrow{\rm l}) \wedge B = \overrightarrow{\rm 0}$.

### Calcul du couple de Laplace
- Sur $AB$, $\overrightarrow{\rm F_L^{AB}} = i \overrightarrow{\rm AB} \wedge \overrightarrow{\rm B} = F_L^{AB} \overrightarrow{\rm e_z}$,
  et $\overrightarrow{\rm \mathcal{M}_O}(\overrightarrow{\rm F_L^{AB}}) = \overrightarrow{\rm OM_1} \wedge \overrightarrow{\rm F_L^{AB}} = \overrightarrow{\rm 0}$.
- Sur $CD$, on obtient $\overrightarrow{\rm F_L^{CD}} = F_L^{CD} \overrightarrow{\rm e_z}$, donnant aussi un moment nul.
- Sur $DA$, $\overrightarrow{\rm F_L^{DA}} = i L B \overrightarrow{\rm e_y}$, et
  $\overrightarrow{\rm \mathcal{M}_O}(\overrightarrow{\rm F_L^{DA}}) = \overrightarrow{\rm OM_4} \wedge \overrightarrow{\rm F_L^{DA}}$
  $= (\frac{d}{2} \overrightarrow{\rm e_\theta}) \wedge (i L B \overrightarrow{\rm e_y})$
  $= i L \frac{d}{2} B \sin \theta \overrightarrow{\rm e_z}$.
- Sur $BC$, $\overrightarrow{\rm F_L^{BC}} = -i L B \overrightarrow{\rm e_y}$,
  donnant de même $\overrightarrow{\rm \mathcal{M}_O}(\overrightarrow{\rm F_D^{BC}}) = -i L \frac{d}{2} B \sin \theta \overrightarrow{\rm e_z}$.

On a donc un couple $\overrightarrow{\rm \Gamma_L} = \overrightarrow{\rm \mathcal{M}_O}(\overrightarrow{\rm F_L})$
$= -i L B \sin(\theta) d \overrightarrow{\rm e_z}$.
On a la spire $S = L d$, et on a le moment magnétique $\mathcal{M} = i S \overrightarrow{\rm n}$,
donc $\overrightarrow{\rm \Gamma_L} = \overrightarrow{\rm \mathcal{M}} \wedge \overrightarrow{\rm B}$.

### Énergie potentielle
Soit une spire en rotation autour de $(Oz)$, $P_L = \mathcal{M}_{Oz}(\overrightarrow{\rm F_L}) \cdot \omega = -i S B \dot{\theta} \sin \theta$,
donnant $\delta W(\overrightarrow{\rm P_L}) = P_L \cdot dt = -i S B \sin(\theta) d \theta$.\
La force de Laplace est conservative, et on a $d E_p = i S B \sin \theta d \theta$,
donc $E_p = - i S B \cos(\theta) + C$ avec $C$ une constante, ce qui nous
permet de conclure $E_p = - \overrightarrow{\rm \mathcal{M}} \cdot \overrightarrow{\rm B}$.

### Généralisation
Soit un moment $\overrightarrow{\rm \mathcal{M}}$ immergé dans un champ $\overrightarrow{\rm B}$ uniforme, on a
le couple de Laplace $\overrightarrow{\rm \Gamma_L} = \overrightarrow{\rm \mathcal{M}} \wedge \overrightarrow{\rm B}$
et l'énergie potentielle $E_p = - \overrightarrow{\rm \mathcal{M}} \cdot \overrightarrow{\rm B}$.

## Moteur synchrone
Ces moteurs sont souvent utilisés dans l'industrie, notamment pour les machines
d'arrimage, et dans les véhicules électriques comme les TGV.

### Réalisation d'un champ magnétique
On a un stator composé de deux bobines à 90 degrés qui forment des champs
magnétiques $\overrightarrow{\rm B_1} = B_0 \cos(\omega t) \overrightarrow{\rm e_x}$
et $\overrightarrow{\rm B_1} = B_0 \sin(\omega t) \overrightarrow{\rm e_y}$,
donnant un champ total $\overrightarrow{\rm B} = B_0 [\cos(\omega t) \overrightarrow{\rm e_x} + \sin(\omega t) \overrightarrow{\rm e_y}]$.
Dans la plupart des moteurs synchrones sont des moteurs triphasés décalés
spatialement de $\frac{2 \pi}{3}$.

Le rotor, lui, est un aimant fixe associé à un moment magnétique $\overrightarrow{\rm \mathcal{M}}$,
dans un champ tournant $\overrightarrow{\rm B_0}$ autour de l'axe $(Oz)$.

### Calcul du couple de Laplace
$\overrightarrow{\rm \Gamma_L} = \overrightarrow{\rm \mathcal{M}} \wedge \overrightarrow{\rm B} = \Gamma_L \overrightarrow{\rm e_z}$

Ce couple tend à aligner le moment magnétique avec le champ $\overrightarrow{\rm
B}$. Ainsi, en régime permanent, le moment va suivre le champ magnétique avec la
même vitesse angulaire $\omega$ mais en étant déphasé d'un angle $\varphi$.

> Un moteur synchrone est un moteur pour lequel le rotor tourne à la même fréquence
> que le champ magnétique.

On obtient donc $\overrightarrow{\rm \Gamma_L} = \mathcal{M}_0 B_0 \sin(\varphi) \overrightarrow{\rm e_z}$

### Loi de Faraday
Soit un conducteur placé dans un champ magnétique $\overrightarrow{B}$, on note $\Phi$ le flux de
$\overrightarrow{B}$ à travers une surface $S$.

> La force électromagnétique induite vaut $e = - \frac{d \Phi}{d t}$, avec $\Phi$ le flux.

En pratique, le champ induit sera souvent négligeable dans le champ total dans les calculs,
donnat $\Phi \sim \iint \overrightarrow{B_{\text{ext}}} \cdot d \overrightarrow{S}$.

### Exercices d'application
On prend l'exemple d'un aimant suspendu à un ressort au-dessus d'une spire.
La spire agit comme un aimant en créant un moment magnétique $\overrightarrow{M}$.
Le champ créé par l'aimant est donc de $\overrightarrow{B_\text{ext}} = \frac{\mu_0 M}{2 \pi r^3} (2 \cos(\theta) \overrightarrow{e_r} + \sin(\theta) \overrightarrow{e_\theta})$,
mais puisque le ressort est bien loin de la spire que son rayon ($z \gg R$), et que le ressort
forme donc un très petit angle avec le bord de la spire ($\theta \approx 1 \text{rad}$),
nous donnant $\overrightarrow{B_\text{ext}} \approx \frac{- \mu_0 M}{2 \pi z^3} \overrightarrow{e_z} = - B_\text{ext} \overrightarrow{e_z}$.

On calcule le flux de \overrightarrow{B}$ à travers la surface,
donnant $\Phi = \iint \overrightarrow{B_\text{ext}} \cdot d \overrightarrow{S} = \overrightarrow{B_\text{ext}} \cdot \overrightarrow{S} = \frac{- \mu_0 M R^2}{2 z^3} \overrightarrow{e_z}$.

On obtient ainsi la force électromagnétique $e = - \frac{3 \mu_0 M R^2}{2 z^4} \dot{z}$. On obtient l'intensité par loi d'Ohm,
$i = \frac{e}{r_S} = - \frac{3 \mu_0 M R^2}{2 z^4 r_S} \dot{z}$, avec $r_S$ la résistance de la spire.

On obtient ensuite le champ induit par la spire, qui est
de $\overrightarrow{B_\text{ind}} = \frac{\mu_0 i}{2 \pi R (1 + \frac{z^2}{R^2})^{\frac{3}{2}}} \overrightarrow{e_z}$
$\approx \frac{\mu_0 i R^2}{2 z^3} \overrightarrow{e_z}$, et appliquant l'expression de $i$,
on obtient la valeur finale $- \frac{3 \mu_0^2 M R^4}{4 r_S z^7} \dot{z} \overrightarrow{e_z} = B_\text{ind} \overrightarrow{e_z}.

Le champ magnétique total est ainsi $\overrightarrow{B} = (- B_\text{ext} + B_\text{ind}) \overrightarrow{e_z}$,
et on a l'énergie potentielle $E_p = - \overrightarrow{M} \cdot \overrightarrow{B_\text{ind}} = - \frac{3 \mu_0^2 M^2 R^4}{4 r_S z^7} \dot{z}$.
La force magnétique étant une force conservative, on a
$\overrightarrow{F} = - \overrightarrow{\text{grad}} E_p = - \frac{\part E_p}{\part z} \overrightarrow{e_z}$
$= - \frac{21 \mu_0^2 M^2 R^4}{4 r_S z^8} \dot{z} \overrightarrow{e_z}$. Cette force est ainsi proportionnelle
à $- \overrightarrow{v}$, donnant une force de freinage qui est utilisée dans les freins à induction.
