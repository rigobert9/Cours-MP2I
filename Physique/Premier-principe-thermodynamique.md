# Premier principe de la thermodynamique
## Transformation d'un système thermodynamique
### Définition
> Une transformation d'un système thermodynamique est une évolution de ce système
> entre deux états d'équilibre, l'un dit initial et l'autre dit final.

> On dit qu'un système thermodynamique est en équilibre interne à tout instant $t$
> si l'on peut définir ses variables d'état intensives, donc si elles sont homogènes
> dans le système.

Ainsi, l'équilibre thermodynamique implique l'équilibre interne.

### Vocabulaire
> Une transformation est dite fermée si à tout instant, $n$ est une constante : il
> n'y a donc pas de perte de matière ni de transformation chimique.

> Une transformation est dite isochore si à tout instant, le volume $V$ est
> constant.

> Une transformation est dite isotherme si à tout instant, la température $T$ est
> constante.

> Une transformation est dite isobare si à tout instant, la pression $P$ est
> constante.

Ces deux transformations précédentes impliquent l'équilibre interne du système.

> Une transformation est dite monotherme si le système est à tout instant en
> contact avec un système de température constante au niveau d'une paroi
> diathermane.

Ainsi, des échanges thermiques sont possibles entre les deux systèmes.

> Une transformation est dite monobare si le système est à tout instant en
> contact avec un système de pression constante au niveau d'une paroi
> libre de se déplacer.

C'est par exemple le cas d'un système avec un piston.

> Une transformation est dite adiabatique si le système ne réalise pas d'échange
> thermique avec l'extérieur durant la transformation.

Ces transformations sont différentes des transformations isothermes, puisque la
température n'est pas nécessairement constante.

> Une transformation est dite cyclique si l'état final est le même que l'état
> initial.

> Une transformation est dite quasistatique si elle est suffisamment lente pour
> que le système soit à tout instant en état d'équilibre interne.

Ce sera le cas d'une transformation qui est assez continue, comme l'ajout de
masse grain par grain sur un piston.

> Au cours d'une transformation quasistatique, le système est en équilibre
> mécanique avec l'extérieur à tout instant.

Il n'y a en revanche pas nécessairement équilibre thermique.

> Une transformation quasistatique est monobare et isobare.

> Une transformation est dite réversible si elle est quasistatique et renversable.

## Bilan d'énergie : premier principe
### Le travail
#### Travail des forces de pression pour un piston sans masse
On prend un gaz dans une enceinte scellée par un piston sans masse de surface
$S$ libre de se déplacer sans frottement. L'expérimentateur tire sur le piston.

On prend pour système {gaz et piston}, qui sont soumis à la pression du gaz et à
la pression de l'atmosphère qu'on considère constante, exerçant une force $\overrightarrow{\rm F_\text{atm}} = - P_\text{atm} S \overrightarrow{\rm u_x}$.
La force exercée par l'opérateur, elle, est une force $\overrightarrow{\rm F_\text{op}} = F_\text{op} \overrightarrow{\rm u_x}$.
On a $\delta W = - P_\text{atm} S dx + F_\text{op} dx$, or $dV = S dx$, et $\delta W = - (P_\text{atm} - \frac{F_\text{op}}{S}) dV = -P_\text{ext} dV$.

#### Travail des forces de pression pour un piston avec masse
On refait la même expérience, en donnant une masse au piston et en le plaçant
verticalement afin de prendre en compte le travail de son poids.

D'après le théorème de l'énergie cinétique, $d E_c = \sum \delta W$.
On a $\delta W_\text{op} = F_\text{op} dz$, $\delta W_\text{atm} = - P_\text{atm} S dz$
et $\delta W_\text{poids} = -m g dz$.
Ainsi, $\delta W_{\text{gaz} \to \text{piston}} = d E_c - F_\text{op} dz + P_\text{atm} S dz + m g dz$,
et d'après la troisième loi de Newton, $d V = S dz$, donnant
$\delta W = \delta W_{\text{piston} \to \text{gaz}} = - (- \frac{F_\text{op}}{S} + P_\text{atm} + \frac{mg}{S}) dV - d E_c$.
Entre deux états d'équilibre (ici, l'initial et le final), $d E_c = 0$.\
$W = \int\limits_{\text{État initial}}^{\text{État final}} \delta W = - \int\limits_{\text{État initial}}^{\text{État final}} P_\text{ext} dV$

## Généralisation
> Le travail élémentaire des forces de pression extérieures sur un système
> est $\delta W = - P_\text{ext} d V$.

Si la transformation est entre un état final et initial, on a donc
$W = - \int\limits_{\text{État inital}}^{\text{État final}} P_\text{ext dV}$.

Si $W$ est positif, on dit que le système reçoit de l'énergie de la part de
l'extérieur (on appuie sur le piston). Si $W$ est négatif, le système fournit de
l'énergie à l'extérieur (le système se détend).

> Pour une transformation isochore, le travail des forces de pression est nul.

#### Cas d'une transformation monobare
$W = - \int\limits_{\text{État initial}}^{\text{État final}} P_\text{ext} dV$
$= - P_\text{ext} \int\limits_{\text{État initial}}^{\text{État final}} dV$
$= - P_\text{ext} (V_2 - V_1)$.

> Pour une transformation monobare entre deux états d'équilibre interne, $W = -P_\text{ext} \Delta V$.

#### Transformation quasistatique et diagramme de Watt
> Le diagramme de Watt représente la pression en ordonnée pour le volume en
> abscisse.

En représentant cette courbe, l'intégrale pour calculer le travail correspond à
l'opposé de l'aire sous la courbe du diagramme.

Lorsque ce diagramme est une ellipse (transformation cyclique),
si le cycle est parcouru dans le sens horaire le cycle est moteur ($W < 0$),
sinon le cycle est récepteur ($W > 0$).

#### Transformation isotherme d'un gaz
Pour un gaz parfait, $PV = n R T \Leftrightarrow P = \frac{n R T}{V}$,
donnant $W = - \int\limits_{\text{État initial}}^{\text{État final}} n R T \frac{d V}{V}$.
Puisque la température est constante, on a finalement la formule :

> $W = - n R T_0 \ln(\frac{V_2}{V_1}) = n R T_0 \ln(\frac{V_1}{v_2})$

### Le transfert thermique
On ne peut pas intégrer les transferts thermiques, puisqu'ils correspondent à
une agitation, et on ne pourra donc pas déterminer leur travail.

On pose $Q$ la chaleur (la dissipation d'énergie, qu'on ne peut pas vraiment
mesurer).

- La conduction est un transfert thermique de proche en proche dans un milieu matériel.
- La convexion est un transfert thermique de proche en proche avec un déplacement
  de matière au sein d'un fluide (par exemple l'air ou l'eau chaud qui remonte
  vers le haut).
- Le rayonnement est un transfert thermique à distance qui se fait à l'aide de
  la propagation d'un rayonnement électromagnétique (peut se produire dans le
  vide).

### Premier principe de la thermodynamique
Cet énoncé est important et doit être connu par cœur.

> Dans un système fermé, il existe une fonction d'état extensive appelée énergie
> interne $\Phi$ telle que sa variation au cours d'une transformation est égale à
> la somme du travail et de la chaleur échangée avec le milieu extérieur.

On pose ainsi $\Delta U = W + Q$, ou sous forme différentielle $d U = \delta W + \delta Q$.

## Exemples et applications
### Transformation isochore
$\delta W = - P_\text{ext} dt$ et $V$ est constant, donc
$W = 0$. D'après le premier principe de la thermodynamique,
$d U = \delta W  + \delta Q \Rightarrow d U = 0 + \delta Q$,
soit $d U = (\frac{\partial U}{\partial T})_V d T + (\frac{\partial U}{\partial V})_T d V$
$\Leftrightarrow d U = (\frac{\partial U}{\partial T})_V d T + 0$,
donc $d U = C_V dT$.

> Pour une transformation isochore, $\delta Q = C_V dT$,
> et si $C_V$ est constant comme c'est souvent le cas,
> $Q = C_V \Delta T$.

### Détente de Joule-Gay-Lussac
Soit deux fioles de même volume, l'une avec un
gaz à la pression $P_1$ et température $T_1$, l'autre vide,
reliées par un robinet, qui commence fermé. Après avoir ouvert le robinet,
l'état final correspond à des températures et pressions égales entre les deux fioles.
On considère que l'exemple est calorifugé et n'échange donc pas de température
avec l'extérieur.

On prend pour système le {gaz à l'intérieur des 2 réservoirs}. Ce système est
isolé et n'échange donc pas de chaleur ou de matière. Les parois sont aussi
indéformables, rendant le système isobare, donc $\Delta U = 0$, c'est à dire
qu'elle est identique entre l'état initial et l'état final.

> La détente de Joule-Gay-Lussac est une détente qui concerne l'énergie interne.

> Un gaz dont la température ne varie pas au cours d'une détente de Joule-Gay-Lussac
> vérifie la première loi de Joule.

### Transformation adiabatique quasistatique et loi de Laplace
Soit un système {n moles de gaz parfait}. On a $\gamma$ le coefficient adiabatique
(aussi appelé coefficient de Laplace). D'après le premier principe de la
thermodynamique, $d U = \delta W + \delta Q$. Puisque la transformation est
adiabatique, $\delta Q = 0$. La transformation étant quasistatique, on est
toujours à l'équilibre mécanique, nous permettant de calculer le travail
$\delta W = - P_\text{ext} d V$. Puisque c'est un gaz parfait, $PV = n RT$,
donc $\delta W = - P d V = - \frac{nRT}{V} dV$. D'après la loi de Joule,
$d U = C_V dT = \frac{n R}{\gamma - 1} d T$, donc
$\frac{n R}{\gamma - 1} dT = - n RT \frac{d V}{V}$
$\Leftrightarrow \frac{d T}{T} + (\gamma - 1) \frac{d V}{V} = 0$,
donc $\ln(T) + \ln(V^{\gamma - 1})$ est une constante,
donc $\ln(T V ^{\gamma - 1})$ est constant,
et on $T V^{\gamma - 1} = C_1$ est une constante.

En utilisant $PV = n R T$, on a $T^{\gamma} P^{1 - \gamma} = C_2$
et $P V^{\gamma} = C_3$ des constantes.

> Pour un gaz parfait qui subit une transformation quasistatique et adiabatique,
> les trois produits $PV^{\gamma}$, $TV^{\gamma - 1}$ et $T^{\gamma} P^{1 - \gamma}$
> sont des constantes.

### Thermostat
#### Définition
> Un thermostat est un système dont la température reste constante quelque soit
> les échanges thermiques qu'il réalise.

Soit un $\Sigma_1$ le système d'une masse d'eau liquide, de capacité thermique $C_1$, et de température $T_1$.
$\Sigma_2$ est un solide PCII, de capacité thermique $C_2$ et de température $T_2$.

À l'équilibre thermique, on a une température finale $T_F$. On considère que le
système {$\Sigma_1$ et $\Sigma_2$} est isolé. D'après le premier principe de la
thermodynamique, $\Delta U = 0$. Par extensivité, $\Delta U_1 + \Delta U_2 = 0$,
et comme $\Delta U_1 = C_1 (T_F - T_1)$ et $\Delta U_2 = C_2 (T_F - T_2)$,
on a $C_1 (T_F - T_1) + C_2 (T_F - T_2) = 0$
$\Leftrightarrow T_F - T_1 = \frac{C_2}{C_1} (T_2 - T_F)$.
Ainsi, on a $T_F \approx T_1$ si $C_2 \ll C_1$.

> Un système agit comme un thermostat si sa capacité thermique est grande devant
> le système avec lequel il est en contact thermique.

#### Loi de Newton
> Loi de Newton (expérimentale) : $P = - h S (T - T_\text{ext})$
> avec $P$ la puissance thermique en $W$, $h$ le coefficient de transfert
> thermique déterminé expérimentalement en $W \cdot m^{-2} \cdot K^{-1}$, $S$ la surface d'échange, et $T$ la
> température du système.

On se place dans le système d'une tasse de café.
D'après le premier principe de la thermodynamique, $d U = \delta W + \delta Q$.
Puisque le volume est constant, $\delta W = 0$, donc $dU = \delta Q$,
or $d U  = C dT$ et $\delta Q = P dt$,
donc $C dT = - hS (T - T_\text{atm}) dt$,
donc $\frac{d T(t)}{dt} + \frac{h S}{C} T(t) = \frac{h S}{C} T_\text{atm}$.
On pose $\tau = \frac{C}{h S}$. Pour $t$ qui tend vers $+\infty$, $T(t) = T_\text{atm}$,
et $T(t = 0) = T_0$ (la température de départ).
Ainsi, $T(t) = A e^{\frac{-t}{\tau}} + T_\text{atm}$,
donnant finalement par application des conditions initiales
$T(t) = (T_0 - T_\text{atm}) e^{\frac{-t}{\tau}} + T_\text{atm}$.

## Bilans d'enthalpie
### Transformation monobare
Puisque l'enthalpie est $H = U + PV$,
$\Delta H = \Delta U + \Delta (PV)$. Si la transformation est monobare,
$W = -P_\text{ext} \Delta V$. Dans un système à l'équilibre mécanique
à l'état initial et final, $P_\text{État initial} = P_\text{État final} = P_\text{ext}$,
donc $\Delta H = Q - P_\text{ext} \Delta V + P_\text{ext} \Delta V = Q$.

Pour une transformation monobare avec équilibre mécanique aux états initiaux et
finaux, $\Delta H = Q$.

### Application aux transitions de phase
Les transitions de phase correspondent aux changements d'état entre les états
liquides, solides, et gazeux.

> Soient deux phases $\alpha$ et $\beta$ d'un même corps pur, l'enthalpie massique
> de la transformation $\alpha \to \beta$ à la température $T$,
> $L_{\alpha \to \beta}(T) = h_\beta(T) - h_\alpha(T)$,
> ou $h_i$ est l'enthalpie massique du corps pur dans la phase $i$.

On a toujours $L_{\alpha \to \beta} = - L_{\beta \to \alpha}$.

Par exemple, on a pour l'eau à $0°C$, $L_{\text{solide} \to \text{liquide}} = 3,3 \times 10^2 kJ \cdot kg^{-1}$.

> Les transitions de phase sont très énergétiques (au moins de l'ordre du $kJ$).

### Calorimétrie
#### Principe
> La calorimétrie est l'art de mesurer les transferts thermiques entre deux
> systèmes.

> Une enceinte calorifugée est une enceinte isolée de manière à limiter les
> échanges thermiques avec l'extérieur.

On étudie un agitateur et un thermomètre dans le vide, à l'intérieur d'un
revêtement métallique.

> La transformation subie par un système placé dans un calorimètre est monobare,
> en équilibre mécanique aux états initiaux et finaux, et
> adiabatique.

Ainsi, on a $\Delta H = 0$.

#### Premier exemple
On prend pour système $500 g$ d'aluminium à $T_\text{al} = 5°C$, dans
$m_\text{eau} = 200 g$ d'eau à $T_\text{eau} = 20°C$. À l'équilibre,
$T_F = 15°C$. On a $c_\text{eau} = 4,2 kJ \cdot K^{-1} \cdot kg^{-1}$.
On a $\Delta H = 0$, et par extensivité,
$\Delta H_\text{eau} + \Delta H_\text{al} = 0$.
Ainsi, comme on a $\left\{\begin{matrix} \Delta H_\text{eau} = m_\text{eau} C_\text{eau} (T_F - T_\text{eau}) \\ \Delta H_\text{al} = m_\text{al} C_\text{al} (T_F - T_\text{al}) \end{matrix}\right.$,
on obtient $m_\text{eau} C_\text{eau} (T_F - T_\text{eau}) + m_\text{Al} C_\text{Al} (T_F - T_\text{Al}) = 0$
$\Leftrightarrow C_\text{al} = C_\text{eau} \frac{m_\text{eau}}{m_\text{Al}} \frac{T_\text{eau} - T_\ell}{T_F - T_\text{al}}$.

Ainsi, $C_\text{al} \approx 840 J \cdot K^{-1} \cdot kg^{-1}$, ce qui est une
valeur inférieure à celle attendue de $900 J \cdot K^{-1} \cdot kg^{-1}$. Il
faut prendre en compte la capacité thermique du calorimètre.

$m_\text{eau} C_\text{eau} (T_F - T_\text{eau}) + m_\text{Al} C_\text{Al} (T_F - T_\text{Al})$
$+ C_\text{calo} (T_F - T_\text{eau}) = 0$

La masse en eau de calorimètre est définie $\mu = \frac{C_\text{calo}}{C_\text{eau}}$.

$C_\text{Al} = C_\text{eau} \frac{m_\text{eau} + \mu}{m_\text{Al}} \frac{T_\text{eau} - T_F}{T_F - T_\text{Al}}$.

#### Second exemple : fonte d'un glaçon
On suppose qu'à l'état final tout est liquide, et donc
$\Delta H = m_1 C_\text{eau} (T_F - T_1) + m_2 C_g (T_0 - T_2) + m_2 L_\text{fusion} + m_2 C_\text{eau} (T_F - T_0)$,
ce qui nous permet de calculer $T_F$.
