# Mouvements de particules chargées
Les particules chargées correspondent aux particules élémentaires de charge
électrique ($+$ : proton, $-$ : électron) et aux particules qui présentent des
différences de charge, comme les ions ($+$ : cations, $-$ : anions).

## Forcé électromagnétique
### Interaction entre deux charges
On prend deux charges $q_1$ et $q_2$.

> $\overrightarrow{\rm F_{1 \to 2}} = - \overrightarrow{\rm F_{2 \to 1}}$

> $\overrightarrow{\rm F_{1 \to 2}} = \frac{1}{4 \pi \varepsilon_0 \varepsilon_r} \cdot \frac{q_1 q_2}{r^2} \overrightarrow{\rm u_{1 \to 2}}$

$\varepsilon_0$ est la permitivité diélectrique dans le vide, de valeur
$8,85 \times 10^{-12} F \cdot m^{-1}$, de dimension
$M^{-1} L^{-2} T^4 I^2 \cdot M^{-1} = M^{-2} L^{-2} T^4 I^2$.

$\varepsilon_r$ est la permitivité diélectrique relative, un coefficient sans
dimension expérimental selon le milieu.

Deux charges de même signe de valeur se repoussent; deux charges de signe
différent s'attirent.

> On peut créer une nouvelle grandeur, le champ électrique, noté
> $\overrightarrow{\rm E_1}(M_2) = \frac{q_1}{4\pi \varepsilon_0 \varepsilon_r} \frac{1}{r^2} \overrightarrow{\rm u_{1 \to 2}}$
> $= \frac{q_1}{4\pi \varepsilon_0 \varepsilon_r} \frac{\overrightarrow{\rm M_1 M_2}}{\lVert \overrightarrow{\rm M_1 M_2} \rVert^3}$

Ce champ ne dépend pas de la charge $q_2$.

> La force exercée par la charge $q_1$ sur la charge $q_2$ placée en
> $M_2$ est $\overrightarrow{\rm F_{1 \to 2}} = q_2 \overrightarrow{\rm E_1}(M_2)$.

> Par définition, $\delta W = \overrightarrow{\rm F_{1 \to 2}} \cdot d \overrightarrow{\rm OM}$
> $= \frac{q_1 q_2}{4\pi \varepsilon_0 \varepsilon_r} \frac{d r}{r^2}$.

Ainsi, $\delta W = - E_p$, et $E_p(r) = \frac{q_1 q_2}{4 \pi \varepsilon_0 \varepsilon_r} \frac{1}{r} + C$,
avec $C$ une constante.

> Le potentiel créé par la charge $q_1$ au point $M_2$ est noté
> $V_1(M_2) = \frac{q_1}{4 \pi \varepsilon_0 \varepsilon_r} \frac{1}{r} + C$,
> avec $C$ une constante.

$V$ est une tension, en volt (différence de potentiel).

> Une charge $q_2$ plongée dans le potentiel $V_1$ a pour énergie potentielle
> $E_p(M_2) = q_2 V_1(M_2)$.

Les charges positives ont tendance à se diriger vers les zones de plus faible
potentiel. Les charges électriques négatives ont tendance à se diriger vers des
zones de potentiel plus fort.

Un champ électrique est dirigé des zones de fort potentiel vers les zones de
faible potentiel.

> Le différentiel total $df$ est la somme des différentielles partielles des
> variables $df = \nabla = \frac{\partial f}{\partial x} dx + \frac{\partial f}{\partial y} dy + \frac{\partial f}{\partial z} dz$.

Ainsi, on a $df = \left(\begin{matrix} \frac{\partial f}{\partial x} \\ \frac{\partial f}{\partial y} \\ \frac{\partial f}{\partial z} \end{matrix}\right)$
$\cdot \left(\begin{matrix} dx \\ dy \\ dz \end{matrix}\right)$.

> On note le gradian de $f$ $\overrightarrow{\rm \text{grad}} f = \left(\begin{matrix} \frac{\partial f}{\partial x} \\ \frac{\partial f}{\partial y} \\ \frac{\partial f}{\partial z} \end{matrix}\right)$,
> donnant $df = \overrightarrow{\rm \text{grad}} f \cdot d \overrightarrow{\rm OM}$.

On a $d V = - \overrightarrow{\rm E} \cdot d \overrightarrow{\rm OM}$, et $\overrightarrow{\rm E} = - \overrightarrow{\rm \text{grad}} V$.

### Charge dans un champ extérieur uniforme
Un champ $\overrightarrow{\rm E}(M,t)$ est une application de l'espace et du
temps vers l'espace : $\begin{aligned} \overrightarrow{\rm E}(M,t): \mathbb{R}^3 \times \mathbb{R} &\to \mathbb{R}^3 \\ M,t &\mapsto \overrightarrow{\rm E}(M,t) .\end{aligned}$.

> Un champ $\overrightarrow{\rm E}$ est dit :
> - uniforme si $\overrightarrow{\rm E}(M_1,t) = \overrightarrow{\rm E}(M_2,t)$
>   pour tous points $E_1$ et $E_2$.
> - statique si $\overrightarrow{\rm E}(M,t_1) = \overrightarrow{\rm E}(M, t_2)$
>   pour toutes dates $t_1$ et $t_2$.

Pour créer un champ électrostatique uniforme, on place face à face des plaques
de potentiel négatif et positif. La différence de potentiel de ces deux plaques
est la tension. Le champ va dans le sens des potentiel décroissants.

On note la tension dans le champ $U = V_1 - V_2$, et la densité surfacique de
charge $\sigma = \frac{q}{S} = \frac{CU}{S}$. On a ainsi $\overrightarrow{\rm E} = \frac{\sigma}{\varepsilon_0} \overrightarrow{\rm u_z}$.
$= \frac{CU}{S \varepsilon_0} \overrightarrow{\rm u_z}$.

### Propriétés et ordres de grandeur
Il existe une fonction de la position pour la tension $V(M)$,
telle que $dV = - \overrightarrow{\rm E} \cdot d \overrightarrow{\rm OM}$
$\Leftrightarrow \overrightarrow{\rm E} = - \overrightarrow{\rm \text{grad}} V$.

À la surface de la Terre, le champ est de $\lVert \overrightarrow{\rm E} \rVert \approx 10^2 V \cdot m^{-1}$.
Pour une charge de $1$ coulomb à un mètre de distance, le champ est de
$\lVert \overrightarrow{\rm E} \rVert \approx 10^{-9} V \cdot m^{-1}$.
Avant l'orage, le champ est environ de
$\lVert \overrightarrow{\rm E} \rVert \approx 10^4 V \cdot m^{-1}$.

### Force électrique
> Soit une charge $q$ dans champ électrique $\overrightarrow{\rm E}$,
> $\overrightarrow{\rm F_\text{électrique}} = q \overrightarrow{\rm E}(M)$.

#### Lien entre le potentiel $V$ et l'énergie potentielle $E_p$
$d E_p = - \overrightarrow{\rm F} \cdot d \overrightarrow{\rm OM}$,
or $\overrightarrow{\rm F} = q \overrightarrow{\rm E}$,
donc $d E_p  = -q \overrightarrow{\rm E} \cdot d \overrightarrow{\rm OM}$.

> $E_p(M) = q V(M)$, avec $V(M)$ le potentiel électrique

On rappelle que la tension correspond à la différence de ces potentiels.

$V(M) = -\overrightarrow{\rm E} \overrightarrow{\rm OM} + C$, avec $C$ une
constante.

> Pour un champ uniforme, $E_p(M) = q V(M) = -q \overrightarrow{\rm E} \overrightarrow{\rm OM} + C$

### Charge dans un champ magnétique extérieur
#### Dispositif permettant de créer un champ magnétostatique uniforme
> Le champ magnétique est mesuré en Tesla, des $kg \cdot A^{-1} \cdot s^{-2}$.

On cherche à prouver que le champ magnétique dans une bobine est de formule
$\overrightarrow{\rm B} \approx u_0 \frac{N}{\ell} i \overrightarrow{\rm u_z}$,
avec $N$ le nombre de spires de la bobine, $i$ l'intensité qui la traverse, et
$\ell$ la longueur de la bobine.

> La perméabilité magnétique du vide est $\mu_0 \approx 4\pi \times 10^{-7} H \cdot m^{-1}$.

#### Propriétés et ordres de grandeur
Des champs magnétiques peuvent être engendrés par des fils traversés par un
courant électrique, ou par les aimants.

À la surface de la Terre, $\lVert \overrightarrow{\rm B} \rVert \approx 10^{-4} T$,
et un aimant classique génère un champ $\lVert \overrightarrow{\rm B} \rVert \approx 0,1$ jusqu'à
$1 T$, un aimant supraconducteur génère $\lVert \overrightarrow{\rm B} \rVert \approx 20 T$.

#### Force magnétique
Soit une charge $q$, animée d'une vitesse $\overrightarrow{\rm v}$, placée dans
un champ magnétique extérieur $\overrightarrow{\rm B}$.

> $\overrightarrow{\rm F_\text{magnétique}} = q \overrightarrow{\rm v} \wedge \overrightarrow{\rm B}$

### Synthèse : force de Lorentz
#### Expressions
Soit une charge $q$, animée d'une vitesse $\overrightarrow{\rm v}$,
plongée dans un champ électromagnétique $(\overrightarrow{\rm E}, \overrightarrow{\rm B})$ :
$\overrightarrow{\rm F_\text{Lorentz}} = \overrightarrow{\rm F_\text{électrique}} + \overrightarrow{\rm F_\text{magnétique}}$
$= q(\overrightarrow{\rm E}(M) + \overrightarrow{\rm v} \wedge \overrightarrow{\rm B})$.

#### Comparaison avec le poids
Pour un électron, on a une masse $m_e \approx 9,1 \times 10^{-31} kg$ et une
charge $q_e = -e = - 1,6 \times 10^{-19} C$.
Dans le champ magnétique terrestre, on a
$\lVert \overrightarrow{\rm F_\text{électrique}} \rVert = e \lVert \overrightarrow{\rm E} \rVert$,
et on a $\lVert \overrightarrow{\rm P_e} \rVert \ll \lVert \overrightarrow{\rm F_\text{électrique}} \rVert$
si $\lVert \overrightarrow{\rm E} \rVert \gg \frac{\lVert \overrightarrow{\rm P_e} \rVert}{e} \approx 10^{-10 V \cdot m^{-1}}$.
De plus, $\lVert \overrightarrow{\rm F_\text{magnétique}} \rVert = e \lVert \overrightarrow{\rm v} \rVert \lVert \overrightarrow{\rm B} \rVert$,
donc $\lVert \overrightarrow{\rm P} \rVert \ll \lVert \overrightarrow{\rm F_\text{magnétique}} \rVert$ si
$\lVert \overrightarrow{\rm v} \rVert \gg \frac{\lVert \overrightarrow{\rm P_e} \rVert}{e \lVert \overrightarrow{\rm B} \rVert} \approx 10^{-10} m \cdot s^{-1}$

Dans l'immense majorité des cas, le poids est négligeable devant la force de
Lorentz.

#### Puissance de la force de Lorentz
$P(t) = \overrightarrow{\rm F} \overrightarrow{\rm v} = q \overrightarrow{\rm E} \cdot \overrightarrow{\rm v} + q (\overrightarrow{\rm v} \wedge \overrightarrow{\rm B} \overrightarrow{\rm v})$,
et ce dernier terme est toujours nul.

> $P(t) = \overrightarrow{\rm F} \overrightarrow{\rm v} = q \overrightarrow{\rm E} \cdot \overrightarrow{\rm v}$

La force exercée par le champ magnétique ne travaille pas.

## Mouvement dans un champ électrique uniforme et constant
### Mise en équation
On se place dans le système d'une particule de charge $q$ et de masse $m$,
associée à un point matériel, dans un référentiel terrestre supposé galiléen.

On fait le bilan des forces, comprenant le poids qui est négligeable, la force
magnétique qui est nulle car $\overrightarrow{\rm B} = \overrightarrow{\rm 0}$,
et la force électrique $\overrightarrow{\rm F_\text{électrique}} = q \overrightarrow{\rm E}$.

D'après le principe fondamental de la dynamique, on a $\overrightarrow{\rm a} = \frac{q}{m} \overrightarrow{\rm E}$

### Trajectoire
$\overrightarrow{\rm E} = E_0 \overrightarrow{\rm u_y}$, et on les conditions
initiales $M(t = 0) = 0$ et $\overrightarrow{\rm v}(t = 0) = \overrightarrow{\rm v_0}$.

En primitivant, on obtient ainsi
$\left\{\begin{matrix} x(t) = v_0 t \cos \alpha \\ y(t) = \frac{1}{2} \frac{q E_0}{m} t^2 + v_0 t \sin \alpha \\ z(t) = 0 \end{matrix}\right.$.
La trajectoire est donc
$y = \frac{q e_0}{2 m v_0^2 \cos^2 \alpha} x^2 + \tan \alpha x$

### Applications
#### Freinage
Soit une particule $q$ avec une vitesse $\overrightarrow{\rm v}(t = 0) = v_0 \overrightarrow{\rm u_x}$,
se déplaçant entre deux grilles de potentiel $V_1$ et $V_2$, $\overrightarrow{\rm E} = - E_0 \overrightarrow{\rm u_x}$.

D'après le théorème de l'énergie mécanique, $E_C(0) + E_p(0) = E_C(t_1) + E_p(t_1)$,
donc $\frac{1}{2} m v_0^2 + q E_0 x(0) = 0 + q e_0 x(t_1)$
$\Leftrightarrow \frac{1}{2} m v_0^2 = q E_0 a$
$\Leftrightarrow E_0 = \frac{m v_0^2}{2 q a}$

#### Principe de l'oscilloscope
On se place dans un oscilloscope, où une particule chargée
est envoyée à une vitesse $v_0$ entre les deux plaques sur une longueur $L$, et entre en collision
avec l'écran après une distance supplémentaire $D$ à l'horizontale.

Dans la première zone, $0 \leq x \leq L$,
$\overrightarrow{\rm E} = -E_0 \overrightarrow{\rm u_z}$ uniforme,
donc $d V = - \overrightarrow{\rm E} d \overrightarrow{\rm OM} = E_0 dz$.
Ainsi, $V(z) = E_0 z + C$, avec $C$ une constante,
or $V(\frac{h}{2}) = V_2$ et $V(\frac{h}{2}) = V_1$,
donc $E_0 = \frac{V_1 - V_2}{h} = \frac{v}{h}$, et
$C = \frac{v_1 + v_2}{2}$.

Dans la zone $2$, $L \leq x \leq L + D$, $\overrightarrow{\rm E} = \overrightarrow{\rm 0}$.
La trajectoire est donc $z(x) = \frac{-e v}{2 m  h v_0^2} x^2$.

D'après le principe de l'inertie, $z = ax + b$ (une droite). Par continuité de
la position la vitesse en $x = L$, on obtient
$\frac{- e U}{2 m h v_0^2} L^2 = a L + b$ et $\frac{-e U}{m h v_0^2} = a$,
donnant $\left\{\begin{matrix} a = - \frac{e U}{m h v_0^2} L \\ b = \frac{eU}{2 m h v_0^2} L^2 \end{matrix}\right.$,
donc $z = \frac{e U L}{m h v_0^2} (\frac{L}{2} - x)$.

Ainsi, on a le point d'impact $z_\text{impact} = z(x = D + L) = \frac{e U L}{m h v_0^2 (-D - \frac{L}{2})}$.

## Mouvement dans un champ magnétique uniforme et constant
### Mise en équation
On se place dans le système d'une particule de charge $q$ et de masse $m$, dans
un référentiel terrestre supposé galiléen.
Le bilan des forces comprend un poids négligeable, une force électrique nulle
car $\overrightarrow{\rm E} = \overrightarrow{\rm 0}$, et une force magnétique
$\overrightarrow{\rm F_\text{magnétique}} = q \overrightarrow{\rm v} \wedge \overrightarrow{\rm B}$ avec
$\overrightarrow{\rm B}$ un vecteur constant.

D'après le principe fondamental de la dynamique, on a $q \overrightarrow{\rm v} \wedge \overrightarrow{\rm B} = m \overrightarrow{\rm a}$.
La force magnétique ne travaille pas. D'après le théorème de l'énergie
cinétique, la vitesse est uniforme.

> Une particule soumise uniquement à un champ magnétique est en mouvement
> uniforme.

### Trajectoire dans le cas général
Puisque $\overrightarrow{\rm OM}(t = 0) = \overrightarrow{\rm 0}$,
$\overrightarrow{\rm B = B_0 \overrightarrow{\rm u_z}}$ avec $B_0 > 0$
et $\overrightarrow{\rm v} = v_x \overrightarrow{\rm u_x} + v_y \overrightarrow{\rm u_y} + v_z \overrightarrow{\rm u_z}$,
d'après le principe fondamental de la dynamique selon $\overrightarrow{\rm u_z}$,
$m \frac{d v_z}{dt} = q (\overrightarrow{\rm v} \wedge \overrightarrow{\rm B}) \cdot \overrightarrow{\rm u_z} = 0$.

#### Vitesse initiale colinéaire au champ
$\overrightarrow{\rm v_0} = v_0 \overrightarrow{\rm u_z}$.
Or, $\lVert \overrightarrow{\rm v} \rVert^2$ est une constante, de valeur
$v_x^2 + v_y^2 + v_z^2$ et $v_z$ est une constante.
Ainsi, $v_z(t) = v 0$ et $v_x(t) = v_y(t) = 0$.

#### Vitesse initiale orthogonale au champ
$\overrightarrow{\rm v_0} = v_0 \overrightarrow{\rm u_x}$ avec $v_0 > 0$.
$v_z(t) = v_z(t = 0) = 0$; le mouvement est dans le plan $(Oxy)$.
D'après le principe fondamental de la dynamique,
$\frac{d \overrightarrow{\rm v}}{dt} = \frac{q B_0}{m} (v_x \overrightarrow{\rm u_x} + v_y \overrightarrow{\rm u_y}) \wedge \overrightarrow{\rm u_z}$
$= \frac{q B_0}{m} (- v_x \overrightarrow{\rm u_y} + v_y \overrightarrow{\rm u_x})$
$\Leftrightarrow \left\{\begin{matrix} \dot{v_x} = \omega_c v_y \\ \dot{v_y} = - \omega_c v_x \end{matrix}\right.$,
avec $\omega_c = \frac{|q| B_0}{m} > 0$.

En dérivant, on peut obtenir
$\left\{\begin{matrix} \ddot{v_x} + \omega_c^2 v_x = 0 \\ \ddot{v_y} + \omega_c^2 v_y = 0 \end{matrix}\right.$.
On obtient la condition aux limites $v_x(t = 0) = v_0$ et $v_y(t = 0) = 0$,
donnant le résultat final
$\left\{\begin{matrix} v_x(t) = v_0 \cos(\omega_c t) \\ v_y(t) = - v_0 \sin(\omega_c t) \end{matrix}\right.$.
On remarque aussi l'identité $v_x^2 + v_y^2 = v_0^2$.

En posant plutôt sous forme complexe, avec $\underline{u}(t) = v_x(t) + j v_y(t)$,
alors on a $\dot{\underline{u}} = \dot{v_x} + j \dot{v_y} = \omega_c v_y - j \omega_c v_x$
$= - j \omega_c$
....

En prenant la partie réelle et imaginaire de $\underline{u}(t)$, on trouve
$\left\{\begin{matrix} v_x(t) = v_c \cos(\omega_c t) \\ v_y(t) = - v_0 \sin(\omega_c t) \end{matrix}\right.$.
Puisqu'à $t = 0$, $x(0) = 0$ et $y(0) = 0$, on pose finalement
$x(t) = \frac{v_0}{\omega_c}$
....

> Dans le cadre d'une vitesse initiale orthogonale au champ magnétique, le
> mouvement est circulaire uniforme de rayon $R = \frac{v_0}{\omega_c} = \frac{m v_0}{|q| B}$.

> Le temps de parcours du cercle pour la particule est de
> $T = \frac{2 \pi}{\omega_c} = \frac{2 \pi m}{|q| B_0}$.

Pour retrouver l'expression de $R$, on pose
$|q| \cdot \lVert \overrightarrow{\rm v} \rVert \cdot \lVert \overrightarrow{\rm B} \rVert = m \lVert \overrightarrow{\rm a} \rVert$.
Pour un mouvement circulaire et uniforme,
$\lVert \overrightarrow{\rm a} \rVert = \frac{v_0^2}{R}$,
donc $R = \frac{m v_0}{|q| B} = \frac{v_0}{\omega_c}$.

#### Cos quelconque
$\overrightarrow{\rm v_0} = v_0 \cos \alpha \overrightarrow{\rm u_x} + v_0 \sin \alpha \overrightarrow{\rm u_z}$,
et on peut décomposer le mouvement en mouvement uniforme selon
$\overrightarrow{\rm u_z}$ à la vitesse $v_0 \sin \alpha \overrightarrow{\rm u_z}$
et en mouvement circulaire dans un plan perpendiculaire à $\overrightarrow{\rm u_z}$
de rayon $R = \frac{v_0 \cos \alpha}{\omega_c}$.

## Cas d'applications complexes
### Le spectromètre de masse
Le spectromètre de masse est un dispositif permettant de mesurer la masse d'une
particule. Il est composé d'une chambre d'ionisation chargée de produire des
particules chargées de faible vitesse initiale, d'un accélérateur à particules,
d'un déflecteur qui dévie les particules, et enfin d'un écran permettant de
détecter les impacts des particules.

On se place dans le cas d'une première particule de masse $m_1$ et
de charge $-z_1 e$, et d'une seconde particule de masse $m_2$
et de charge $- z_2 e$. Les $z$ correspondent à la charge.

#### Étude de l'accélérateur
L'accélérateur présente un champ électrique
$\overrightarrow{\rm E} = - E_0 \overrightarrow{\rm u_x}$,
avec une différence de potentiel entre l'entrée de potentiel $v_1$
et la sortie de plus grand potentiel $v_2$, $u = v_2 - v_1$.
À l'entrée de l'accélérateur, $v = 0$. D'après le théorème de l'énergie
mécanique, $0 - z_i e v_1 = \frac{1}{2} m_i v_i^2 - z_i e v_2$
$\Leftrightarrow v_i = \sqrt{\frac{2 z_i e u}{m_i}}$.

#### Étude du déflecteur
$\overrightarrow{\rm B} = - B_0 \overrightarrow{\rm u_z}$, avec $B_0 > 0$.
$R_i = \frac{m_i v_i}{z_i e B_0}$. Or, $v_i = \sqrt{\frac{2 z_i e u}{m_i}}$,
donc $R_i = \sqrt{\frac{m_i}{z_i}} \sqrt{\frac{2 u}{e B_0^2}}$.

L'appareil permet donc de discriminer entre les particules selon le rapport
entre leur masse et leur charge.

### Cyclotron
Un cyclotron est formé de deux demi-capsules munis d'un champ électrique,
menant la particule à tourner et à de plus en plus accélérer.
