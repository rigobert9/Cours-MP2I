# Machines thermiques
## Bilan énergétique
### Cadre de l'étude
Dans un système fermé fonctionnant de manière cyclique, on appelle selon $W$ le
travail associé au système, le système un moteur pour $W < 0$ ou un récepteur
pour $W > 0$.

### Application du premier principe
D'après le premier principe de la thermodynamique,
$\Delta(E_m^{\text{masse}} + U) = W + Q$,
avec $E_m^{\text{masse}}$ la possibilité de mouvement.

On appelle alors un cycle des états tels que $\Delta U = 0$, et donc $W + Q = 0$.
La chaleur étant extensive, s'il y a plusieurs sources de chaleur, on les somme.

### Application du second principe
Dans un cycle, $\Delta S = 0$, donc comme $S_c \geq 0$
on aura toujours $S_e \leq 0$. Si la source de chaleur est un thermostat de
température $T_i$, on a $S_e = \int \sum\limits_{i} \frac{\delta Q_i}{T_i}$.

> Inégalité de Clausius : $S_e = \sum\limits_{i} \frac{Q_i}{T_i} = - S_c \leq 0$.

## Machines thermique monothermes et dithermes
### Machines monothermes
> Dans une machine monotherme, le système échange de l'énergie avec une seule
> source de chaleur. Le système reçoit un travail $W$ et un transfert thermique $Q$ d'une source à la température $T_e$.

Ainsi, dans les cycles, $W + Q = 0$ et $\frac{Q}{T_e} \leq 0$. Comme $W > 0$,
on a nécessairement $Q < 0$, ce qui signifie que le machine ne peut que
chauffer.

### Machines dithermes
> Pour une machine ditherme, le système échange de l'énergie avec deux sources de
> chaleur. Le système reçoit un travail $W$, un transfert thermique $Q_c$ d'une
> source chaude à la température $T_c$ et un transfert thermique $Q_f$ d'une
> source froide à la température $T_f$.

#### Les moteurs
> Un moteur est une machine telle que $W < 0$, $Q_f < 0$ et $Q_c > 0$.

Par convention, on dit que le système reçoit de la chaleur quand $Q > 0$
et fournit de la chaleur quand $Q < 0$.

> Le rendement d'un moteur $\eta = |\frac{\text{grandeur énergétique valorisée}}{\text{coût énergétique}}| = |\frac{\text{énergie utile}}{\text{énergie coûteuse}}|$.

On a donc $\eta = \frac{-W}{Q_c}$. On sait que $-W = Q_c + Q_f$, donc
$\eta = 1 + \frac{Q_f}{Q_c}$. Par l'inégalité de Clausius, $\frac{Q_f}{Q_c} \leq \frac{-T_f}{T_c}$,
donc $\eta \leq \eta_\text{max} = 1 - \frac{T_f}{T_c}$.

> Rendement de Carnot : $\eta_\text{max} = 1 - \frac{T_f}{T_c}$.

#### Les réfrigérateurs
> Les réfrigérateurs sont des machines dithermes telles que $W > 0$, $Q_f > 0$,$Q_c < 0$.

> L'efficacité correspond à $e = |\frac{\text{grandeur énergétique valorisée}}{\text{coût énergétique}}|$.

On peut donc avoir $e \geq 1$

On a donc $e = \frac{Q_f}{W}$, $-W = Q_c + Q_f$. On a donc $e = \frac{-Q_f}{Q_c + Q_f}$
$= \frac{-1}{1 + \frac{Q_c}{Q_f}} \leq \frac{T_f}{T_c - T_f}$. Ainsi, $e \leq e_\text{max} = \frac{T_f}{T_c - T_f}$.

> Efficacité de Carnot : $e_\text{max} = \frac{T_f}{T_c - T_f}$.

#### Les pompes à chaleur
> Les pompes à chaleur sont des machines dithermes telles que $W > 0$, $Q_f > 0$,$Q_c < 0$.

L'efficacité est ici $e = \frac{-Q_c}{W} = \frac{Q_c}{Q_c + Q_f} \leq \frac{T_c}{T_c - T_f}$.

> Efficacité de Carnot pour les pompes à chaleur : $e_\text{max} = \frac{T_c}{T_c - T_f}$.

### Diagramme de Raveau
On représente sur un diagramme $Q_c$ en fonction de $Q_f$. Voir diagramme qui
sépare :
- la zone interdite par le second principe ($\frac{Q_c}{T_c} + \frac{Q_f}{T_f} \leq 0$)
- les moteurs
- les pompes à chaleur et réfrigérateurs
- les machines consommant de
  la chaleur de la source chaude et la délivrant à la source froide (même
  action, en moins efficace, que rien du tout)
- les machines consommant du travail en
  cédant de la chaleur aux deux sources (inutile)

### Cycle de Carnot
Le cycle de Carnot est un cycle idéal permettant d'obtenir le rendement maximal.
Il est composé des transformations :
- AB : Compression isotherme réversible au contact de la source froide ($PV$
  constant)
- BC : Compression adiabatique réversible jusqu'à $T_c$ ($PV^{\gamma}$ constant)
- CD : Détente isotherme au contact de la source chaude
- DA : Détente adiabatique réversible jusqu'à $T_f$

## Exemple de machines ditheremes
### Moteur à explosion
#### Principe
Créé par Eugène Beau de Roches, le moteur à explosion ou à quatre temps suit
un cycle principal et un cycle de renouvellement. Il admet (AB) des gaz et du
carburant, qu'il compresse (BC), avant d'allumer la bougie, créant une rapide
décompression du moteur (CE), puis laisse s'échapper le gaz après réaction (EA)
avant de recommencer.

#### Modélisation
On suit le cycle avec les étapes :
- $AB$ isobare de $V_\text{min}$ à $V_\text{max}$
- $BC$ adiabatique réversible
- $CD$ isochore
- $DE$ adiabatique réversible
- $EB$ isochore
- $BA$ isobare de $V_\text{max}$ à $V_\text{min}$

D'après le premier principe de la thermodynamique, sur un cycle,
$W + Q_f + Q_c = 0$. Le contact avec la source chaude (bougie) se fait au cours
de l'étape $CD$ :  $Q_c = Q_{CD}$. Le contact avec la source froide (atmosphère)
se fait au cours de l'étape $EB$ : $Q_f = Q_{EB}$.

Le rendement du moteur est $\eta = \frac{-W}{Q_c}$,
or $- W = Q_c + Q_f$, donc $\eta = 1 + \frac{Q_{EB}}{Q_{CD}}$.
Puisque les phases $EB$ et $CD$ sont des transformations isochores,
$Q_{EB} = \Delta U_{EB} = C_V (T_B - T_E)$ et $Q_{CD} = C_V (T_D - T_C)$,
donnant $\eta = 1 + \frac{T_B - T_E}{T_D - T_C}$.

Puisque les transformations $BC$ et $DE$ sont adiabatiques réversibles, on
utilise la loi de Laplace $TV^{\gamma - 1} = \text{const}$, donnant
$\left\{\begin{matrix} T_B V_\text{max}^{\gamma - 1} = T_C V_\text{min}^{\gamma - 1} \\ T_D V_\text{min}^{\gamma - 1} = T_E V_\text{max}^{\gamma - 1} \end{matrix}\right.$
$\Leftrightarrow \left\{\begin{matrix} T_B = (\frac{V_\text{min}}{V_\text{max}})^{\gamma - 1} T_D \end{matrix}\right.$.
On remplace dans le rendement, donnant $\eta = \frac{(\frac{V_\text{min}}{V_\text{max}})^{\gamma - 1} (T_C - T_D)}{T_D - T_C} = 1 - (\frac{V_\text{min}}{V_\text{max}})^{\gamma - 1}$.
On pose souvent $a = \frac{V_\text{max}}{V_\text{min}}$, tel que $\eta = 1 - a^{\gamma - 1}$.

### Réfrigérateur
#### Préliminaires : premier principe à un fluide en écoulement
Dans un réfrigérateur, un fluide va d'une source de chaleur à l'autre en
s'écoulant. On va considérer qu'il y a $\Sigma(t)$ fluide dans la machine à un
instant $t$, qu'il y a une masse de fluide $S_1$ à l'entrée du système à
l'instant $t$ et une même masse $S_2$ à la sortie à l'instant $t + \Delta t$.

On a tout le fluide tel que $S(t) = S_1 + \Sigma(t)$ et $S(t + \Delta t) = S_2 + \Sigma(t + \Delta t)$.
On va de plus faire l'hypothèse que $\Sigma$ est en régime stationnaire (ses
propriétés ne dépendent pas du temps).
Ainsi, $V(t) = V_1 + V_\Sigma$ et $V(t + \Delta t) = V_2 + V_\Sigma$,
et les masses totales sont les mêmes aux deux instants.
On calcule la variation d'énergie mécanique de $S$ entre $t$ et $\Delta t$,
$\Delta E_m = E_m(t + \Delta t) - E_m(t) = E_m(S_2) + E_m(\Sigma) - E_m(S_1) - E_m(\Sigma)$
$= E_m(S_2) - E_m(S_1)$. D'après le premier principe de la thermodynamique,
$\Delta E_m = Q + W$.
Comme $W = W_1 \text{ (travail des force en amont) } + W_2 \text{ (Travail des
forces de pression en aval) } + W_u \text{ (Tous les autres travaux : travail
utile)}$.

On a ainsi $W_1 = P_1 x_1 S_1 = P_1 V_1$ et $W_2 = - P_2 V_2$,
donc $P_1 V_1 - P_2 V_2 + W_u = \sum W_{\{1;2;u\}}$.
On a donc $\Delta E_m = P_1 V_1 - P_2 V_2 + W_u + Q$,
or $E_m = E_m^{\text{macro}} + U$,
donc $\Delta E_m^{\text{macro}} + \Delta U = \Delta E_m$
$\Leftrightarrow W_u + Q = [E_m^{\text{macro}} + H](S_2) - [E_m^{\text{macro}} + H](S_1)$.

On pose souvent des grandeurs massiques pour $W_u$ ($w_u$),
$Q$ ($q$), $E_m^{\text{macro}}$ ($e_m^{\text{macro}}$) et
$h = \frac{H}{m}$, nous donnant toujours
$\Delta (e_m^{\text{macro}} + h) = w_u + q$.

On a plusieurs cas particuliers :
- Avec la différence d'altitude, $\Delta z = z_2 - z_1$, $\Delta
  e_m^{\text{macro}} = \Delta_c e^{\text{macro}} \pm g \Delta z$.
- Machine calorifugée : $q = 0$, donnant une détente de Joule-Thompson.
  Pour un fluide en écoulement de $P_1$ à $P_2 < P_1$, si $\Delta e_m^{\text{macro}} = 0$,
  les parois sont calorifugées, et la machine ne fournit pas de travail ($w_u = 0$),
  alors la transformation est isenthalpique, $\Delta h = 0$.

#### Principe
Dans un réfrigérateur, la source chaude est l'atmosphère et la source froide
l'intérieur du réfrigérateur. Le fluide réfrigérant qui circule dans le
réfrigérateur prélève de l'énergie à l'intérieur du réfrigérateur pour maintenir
la température du réfrigérateur à $T_f$

#### Diagramme P-h (Mollier) et calcul de rendement
En appliquant le premier principe, on a donc $\Delta h = w_u + q = w_u + q_c + q_f$.
On peut voir sur le diagramme de Mollier (voir polycopié ou sur internet).

- La transformation de la ligne de droite, de bas en haut, est un compression
  adiabatique, donc $q_{FA} = 0 \Rightarrow \delta h_{FA} = h(A) - h(F)$.
- Le refroidissement $AB$ dans le coin haut-droit, de droite à gauche,
  et la liquéfaction $BB'$ sur la ligne du haut de droite à gauche, ainsi que le refroidissement $B'C$
  qui finit cette ligne, sont adiabatiques, donc $\Delta h_{AC} = h(C) - h(A) = q_{AC} = q_c$.
- La détente $CD$ du coin haut-gauche de haut en bas et la vaporisation
  partielle $DE$ de la ligne de gauche de haut en bas sont telles que
  $w_{u,CE} = 0$ et $q_{CE} = 0$, donnant $\delta h_{CE} = h(E) - h(C) = 0$
- La vaporisation $EE'$ et réchauffement $E'F$ de la ligne du bas de gauche à
  droite est telle que $w_{u,EF} = 0$, et donc $\Delta h_{EF} = h(F) - h(E) = q_{EF} = q_f$
