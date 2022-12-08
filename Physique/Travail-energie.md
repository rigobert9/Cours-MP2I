# Travail et énergie
## Puissance et travail d'une force
On considère un points matériel $N$ de masse $m$ dans un référentiel galiléen,
soumis à une force $\overrightarrow{\rm F}$.

> La puissance $P$ exercée par une force $\overrightarrow{\rm F}$ sur $M$, animée
> d'une vitesse $\overrightarrow{\rm v}$, à l'instant $t$, est de la forme
> $P(t) = \overrightarrow{\rm F} \cdot \overrightarrow{\rm v}(t)$.

L'unité d'un puissance est le Watt, en dimension $[ML^2 T^{-3}]$, ce qui est
homogène à une énergie multipliée par une vitesse.

Lorsque $P > 0$, on dit que la force est motrice. Si $P < 0$, la force est
résistante et si $P = 0$, la force ne travaille pas.
Le premier cas correspond à une force "dans le sens" de la vitesse, le second à
une force "contre le sens" de la vitesse, et le dernier cas correspond à une
force perpendiculaire à la vitesse.

> Le travail élémentaire $\delta W$ fourni par une force $\overrightarrow{\rm F}$
> correspond à la valeur $P \cdot dt = \overrightarrow{\rm F} \cdot \overrightarrow{\rm v} dt = \overrightarrow{\rm F} \cdot d \overrightarrow{\rm r}$.

On l'exprime souvent par le produit scalaire de la force .par le déplacement
élémentaire, $\overrightarrow{\rm F} \cdot d \overrightarrow{\rm r}$.

Le travail élémentaire est homogène à une énergie et est exprimé en Joules.

Le système fournit de l'énergie lorsque $\delta W > 0$, et il cède de l'énergie
lorsque $\delta W < 0$.

> Si le déplacement du point $M$ se fait entre les points $M_1$ et $t_1$ et
> $M_2$ en $t_2$ (donc sur le chemin $\mathcal{C}(M_1,M_2)$), le travail
> nécessaire pour effectuer le chemin, si la force est intégrable, est
> $W_{M_1 \to M_2} = \int\limits_{t = t_1}^{t = t_2} P(t) \cdot dt = \int\limits_{\overrightarrow{\rm r} = \overrightarrow{\rm OM_1}}^{\overrightarrow{\rm r} = \overrightarrow{\rm OM_2}} \overrightarrow{\rm F} \cdot d \overrightarrow{\rm r}$.

### Travail du poids
Le système est plongé dans un champ de pesanteur uniforme, et on considère le
poids agissant sur $N$ noté $\overrightarrow{\rm P}= m \overrightarrow{\rm g}$.
On se place en coordonnées cartésiennes avec $(Oz)$ dirigé vers le haut.

On a le chemin effectué $\overrightarrow{\rm OM}(t) = x(t) \overrightarrow{\rm u_x} + y(t) \overrightarrow{\rm u_y} + z(t) \overrightarrow{\rm u_z}$,
qu'on dérive (pour obtenir $d \overrightarrow{\rm r}$). On a donc $\delta W = \overrightarrow{\rm F} \cdot d \overrightarrow{\rm r} = -mg(z_2 - z_1)$.

Ainsi, pour un trajet quelconque entre 2 points d'altitude $z_1$ et $z_2$,
$W_{M_1 \to M_2}(\overrightarrow{\rm P}) = -mg(z_2 - z_1)$.

Le travail du poids ne dépend que des points de départ et d'arrivée, pas du
chemin suivi. Ainsi, de façon générale pour une force constante, $W_{M_1 \to M_2}(\overrightarrow{\rm P}) = \overrightarrow{\rm P} \cdot \overrightarrow{\rm M_1 M_2}$.

Pour une force constante $\overrightarrow{\rm F}$ agissant sur un point $M$
allant de $M_1$ à $M_2$, le travail fourni s'écrit
$W_{M_1 \to M_2}(\overrightarrow{\rm F}) = \overrightarrow{\rm F} \cdot \overrightarrow{\rm M_1 M_2}$.

### Travail d'une force de frottements solides
Pour un objet soumis à son poids, à la réaction du support (opposée au poids),
à une force d'un opérateur qui tire sur l'objet $\overrightarrow{\rm F}$ et
$\overrightarrow{\rm T}$ le frottement de l'objet sur le support, on a les
relations : $\overrightarrow{\rm P} = m \overrightarrow{\rm g}$,
$\overrightarrow{\rm N} = - \overrightarrow{\rm P}$ et
$\lVert \overrightarrow{\rm T} \rVert = \mu_d \lVert \overrightarrow{\rm N} \rVert$.

De plus, on a $P(\overrightarrow{\rm T}) = \overrightarrow{\rm T} \cdot \overrightarrow{\rm v} < 0$
et donc $\delta W = P(t) dt < 0$.

## Théorème de l'énergie cinétique
### Théorème de la puissance cinétique
On observe un système {point matériel M}, dans un référentiel terrestre supposé
galiléen. On a d'après le principe fondamental de la dynamique :
$\sum\limits_{i = 1}^{n} \overrightarrow{\rm F_i} = m \frac{d \overrightarrow{\rm v}}{dt}$.
Le produit scalaire avec $\overrightarrow{\rm v}$ est donc
$m \frac{d \overrightarrow{\rm v}}{dt} \cdot \overrightarrow{\rm v} = \sum\limits_{i = 1}^{n} \overrightarrow{\rm F_i} \cdot \overrightarrow{\rm v}$
$\Leftrightarrow \frac{d}{dt} [\frac{1}{2} m \lVert \overrightarrow{\rm v} \rVert^2] = \sum\limits_{i = 1}^{n} P_i(t)$

> L'énergie cinétique est une énergie en un point $M$ exprimée en Joules, et de la forme
> $E_c = \frac{1}{2} m v^2$.

L'énergie cinétique est modifiée par l'action des forces extérieures tel que
$\frac{d E_c}{dt} = \sum\limits_{i} P_i(t)$

### Théorème de l'énergie cinétique
#### Énoncé
> $\int\limits_{t_1}^{t_2} \frac{d E_c}{dt} dt = \sum\limits_{i} \int\limits_{t_1}^{t_2} \overrightarrow{\rm F_i} \cdot \overrightarrow{\rm v} dt = \sum\limits_{i} \int\limits_{t_1}^{t_2} \overrightarrow{\rm F_i} \cdot \frac{d \overrightarrow{\rm OM}}{dt} dt$

> La variation de l'énergie cinétique est égale à la somme des travaux des forces
> extérieures.
> $E_c(t_2) - E_c(t_1) = \sum\limits_{i = 1}^{n} W_{M_1 \to M_2}(\overrightarrow{\rm F_i})$

#### Application
On considère la chute d'une bille lâchée d'une hauteur $h$ sans vitesse
initiale en $t = t_1 = 0$. Elle atteint le sol en $t = t_2$ avec une vitesse $v_0$.
On recherche sa vitesse à l'impact à l'aide du théorème de l'énergie cinétique.

$\Delta E_c = E_c(z_2) - E_c(z_1) = m g (z_1 - z_2) = mgh$. Or, $E_c(z_2) = \frac{1}{2} m v_0^2$
et $E_c(z_1) = 0$, donc $\frac{1}{2} m v_0^2 = mgh \Leftrightarrow v_0 = \sqrt{2 g h}$.

## Énergie mécanique
### Forces conservatives
> Une force est dite conservative si son travail entre deux points quelconques ne
> dépend pas du chemin suivi.

Le poids est une force conservative, alors que les forces de frottement ne le
sont pas.

> Si la force $\overrightarrow{\rm F_c}$ est conservative, alors il existe une
> fonction appelée énergie potentielle $E_p$ telle que $\delta W = - d E_p$.

> L'énergie potentielle associée au poids est appelée énergie potentielle de pesanteur,
> parfois notée $E_{pp}(M)$.

Pour un axe orienté vers le haut, $E_{pp} = + mgz + C$, et pour un axe orienté
vers le bas, $E_{pp} = - mgz + C$, avec $C$ une constante.

### Théorème de l'énergie mécanique
#### Énoncé
$\sum\limits_{i = 1}^{n} \overrightarrow{\rm F_i} = \sum\limits_{i = 1}^{n} \overrightarrow{\rm F_{i,C}} + \sum\limits_{i = 1}^{n} \overrightarrow{\rm F_{i,nC}}$,
avec $\overrightarrow{\rm F_{i,C}}$ une force conservative et $\overrightarrow{\rm F_{i,nC}}$ des forces non conservatives.

D'après le théorème de la puissance cinétique, $\frac{d E_c}{dt} = - \sum\limits_{i = 1}^{n}  \frac{d E_{p,i}}{dt} + \sum\limits_{i = 1}^{n} P_{i,nC}$
$\Leftrightarrow \frac{d}{dt} [E_c + \sum\limits_{i = 1}^{n} E_{p,i}] = \sum\limits_{i = 1}^{n} P_{i,nC}$.
On note le terme dérivé comme étant l'énergie mécanique.

> L'énergie mécanique du point $M$ est définie comme
> $E_m = E_c + \sum\limits_{i = 1}^{n} E_{p,i}$.

> L'énergie mécanique ne varie que par l'action des forces non conservatives.
> Ainsi, $\frac{d E_m}{dt} = \sum\limits_{i = 1}^{n} P_{i,nC}$.

> La variation de l'énergie mécanique est égale à la somme des travaux des forces
> non conservatives : $\Delta E_m = \sum\limits_{i = 1}^{n} W(\overrightarrow{\rm F_{i,nC}})$.

> Un système conservatif conserve son énergie mécanique, car il n'y a aucune force
> non conservative en jeu, soit $\frac{d E_m}{dt} = \sum\limits_{i = 1}^{n} P_{i,nC} = 0$
> $\Leftrightarrow E_m = C$, avec $C$ une constante.

> L'équation $E_m = C$ est appelée intégrale première du mouvement.

#### Exemple du pendule simple
On étudie un pendule assimilé à un point matériel {M} de masse $m$, accroché à
un fil indéformable de longueur $\ell$ et de masse nulle formant un angle $\theta$ avec la normale au
sol.

L'énergie cinétique est de valeur $E_c = \frac{1}{2} m v^2$. En coordonnées
polaires, on a $\overrightarrow{\rm OM} = \ell \overrightarrow{\rm ur}$ et $\overrightarrow{\rm v} = \frac{d \overrightarrow{\rm OM}}{dt}$
$= \ell \dot{\theta} \overrightarrow{\rm u_\theta}$, donnant $E_c = \frac{1}{2} m l^2 \dot{\theta}^2$.

L'énergie potentielle est de valeur $E_{pp} = -mgz + C = -mg \ell \cos(\theta) + C$.
En $\theta = 0$, $E_{pp} = 0$, donc $C = mg\ell$, donnant
$E_{pp} = mg\ell (1 - \cos \theta)$.

Ici, $W(\overrightarrow{\rm T}) = 0$, et on a l'énergie mécanique qui est donc
constante et égale à $\frac{1}{2} m l^2 \dot{\theta}^2 + mg\ell (1 - \cos \theta)$.
En dérivant par rapport au temps, $0 = m \ell^2 \ddot{\theta} \dot{\theta} + mg\ell \dot{\theta} \sin \theta$.
Puisque que $\dot{\theta}$ est non nul, on a $\ddot{\theta} + \frac{g}{\ell} \sin \theta = 0$

### Exemples de forces
#### Forces de frottement
Le travail d'une force de frottement dépend du chemin suivi. Une force de
frottement n'est donc pas conservative.

#### Champ de pesanteur uniforme
Formules précédemment données.

#### Champ gravitationnel général
Les forces exercées par un champ gravitationnel sont telles que
$\overrightarrow{\rm F} = -G \frac{m_0 m}{r^2} \overrightarrow{\rm u_r}$,
où $\overrightarrow{\rm r} = \overrightarrow{\rm OM}$.

On a $d E_p = - \overrightarrow{\rm F} \cdot d\overrightarrow{\rm r}$.
En coordonnées sphériques,
$d \overrightarrow{\rm OM} = d \overrightarrow{\rm r} \overrightarrow{\rm u_r} + r d\theta \overrightarrow{\rm u_\theta} + r \sin \theta d \varphi \overrightarrow{\rm u_\varphi}$,
donc $d E_p = - \overrightarrow{\rm F} d \overrightarrow{\rm OM} = G \frac{m_0 m}{r^2} dr$.

En intégrant par rapport à $r$, $E_p(r) = - G \frac{m_0 m}{r} + C$ (l'énergie
potentielle d'interaction gravitationnelle). De plus, on a
$E_p(r \to +\infty) = 0$.

#### Force de rappel d'un ressort
Dans le cas de la force de rappel d'un ressort,
on a la force $\overrightarrow{\rm F} = -k (x - \ell_0) \overrightarrow{\rm u_x}$,
$d \overrightarrow{\rm r} = d x \overrightarrow{\rm u_x}$
et donc $d E_p = - \overrightarrow{\rm F} \cdot d\overrightarrow{\rm r} = k (x - \ell_0) dx$.
En intégrant par rapport à $x$, on obtient
$E_{p\ell} = \frac{1}{2} k (x - \ell_0)^2 + C$ l'énergie potentielle élastique.

Souvent $E_{p\ell}(x = \ell_0) = 0$ (constante nulle).

## Mouvements unidimensionnels
### Définition et exemples
> Un système ou un mouvement est dit unidimensionnel ou à 1 degré de liberté si la
> position du point $M$ est entièrement définie par la donnée d'une seule variable
> d'espace.

Dans le cas d'un ressort vertical, l'énergie mécanique du système est
$E_m = \frac{1}{2} m \dot{z}^2 + \frac{1}{2} k (z - \ell_0)^2 - mgz + C$.
Dans le cas du pendule simple, l'énergie mécanique du système est
$E_m = \frac{1}{2} m \ell^2 \dot{\theta}^2 + mg\ell (r - \cos \theta) + C$.

> On admet que l'énergie mécanique d'un système unidimensionnel peut toujours se
> présenter sous la forme $E_m(x, \dot{x}) = \frac{1}{2} m \dot{x}^2 + E_{p, \text{effective}}$.

$x$ sera généralement une variable spatiale, homogène à une longueur. $\dot{x}$
est une vitesse généralisée, $m$ correspond à la masse inertielle.
$E_{p,\text{effective}}$ est une fonction uniquement de $x$.

Lorsque le système est conservatif, $E_m$ est une constante.

### Équilibre d'un système conservatif unidimensionnel
Pour un système unidimensionnel tel que $\frac{1}{2} m \dot{x}^2 + E_p = C$.
En dérivant par rapport au temps,
$m \dot{x} \ddot{x} + \dot{x} \frac{d E_p}{dt} = 0$.
Puisque $\dot{x} \neq 0$, on a donc
$m \ddot{x} = -\frac{d E_p}{dt}$.

> Le terme $F(x) = -\frac{d E_p}{dt}$ est analogue à une force s'exerçant sur le système.

Une position d'équilibre ou point d'équilibre, qu'on note $x_\text{eq}$ est un
état du système tel que $\frac{d x_\text{eq}}{dt}$.

> Ce point d'équilibre est dit stable si, lorsqu'on écarte légèrement le système
> de ce point, il tend à s'en rapprocher. Dans le cas où il tend à s'en éloigner,
> il est dit instable.

On regarde l'évolution du système en fonction de $x_\text{eq}$, et on pose
$\varepsilon(t) = x(t) - x_\text{éq}$. On a $m\ddot{x} = - \frac{d E_p}{dx}$,
et donc $m \ddot{\varepsilon} = - \frac{d E_p}{dx}(x_\text{éq} + \varepsilon)$.
On pose un développement limité
$m\ddot{\varepsilon} \approx - \frac{d E_p}{dx}(x_\text{éq}) - \varepsilon \frac{d^2 E_p}{dx^2}(x_\text{éq}) + O(\varepsilon^2)$,
donnant en un point d'équilibre
$\ddot{\varepsilon} + \frac{1}{m} \frac{d^2 E_p}{dx^2}(x_\text{éq}) \varepsilon = 0$.

Dans le cas où $\frac{d^2 E_p}{dx^2} > 0$, le système est un oscillateur
harmonique, et dans le cas où $\frac{d^2 E_p}{dx^2} < 0$, le système est en
équilibre instable.

Un point d'équilibre $x_\text{éq}$ est stable si c'est un minimum local
de $E_p(x_\text{éq})$, donnant $\frac{d E_p}{dx} = 0$ et $\frac{d^2 E_p}{dx^2} > 0$.

Un point d'équilibre $x_\text{éq}$ est instable si c'est un maximum local de
$E_p(x_\text{éq})$, donnant $\frac{d E_p}{dx} = 0$ et $\frac{d^2 E_p}{dx^2} < 0$.

### Paysage énergétique
$E_p(x) \approx E_p(x_\text{éq}) + \frac{d E_p}{dx}(x_\text{éq}) (x - x_\text{éq}) + \frac{1}{2} \frac{d^2 E_p}{dx^2}(x_\text{éq}) (x - x_\text{éq})^2 \ldots$\
$\Leftrightarrow \frac{d}{dt} [\frac{1}{2} \dot{x}^2 + \frac{1}{2} \omega_0^2 (x - x_\text{éq})^2] = 0$\
$\Leftrightarrow \frac{d}{dt} [\frac{1}{2} m \dot{x}^2 + \frac{1}{2} m \omega_0^2 (x - x_\text{éq})^2] = 0$\
$\Leftrightarrow \frac{d}{dt} [E_m] = 0$, soit une énergie mécanique constante.

On a le potentiel harmonique $\ddot{x} + \omega_0^2 x = \omega_0^2 x_\text{éq}$,
qu'on multiplie par $\dot{x}$, donnant
$\dot{x}\ddot{x} + \omega_0^2 \dot{x} (x - x_\text{éq}) = 0$.

> Au voisinage d'une position d'équilibre stable, la position du système est un
> oscillateur harmonique de la forme $\ddot{x} + \omega_0^2 x = \omega_0^2 x_\text{éq}$,
> avec $\omega = \sqrt{\frac{1}{m} \frac{d^2 E_p}{dx^2}(x_\text{éq})}$.
