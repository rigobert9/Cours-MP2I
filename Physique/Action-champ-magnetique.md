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
### Réalisation d'un champ magnétique
