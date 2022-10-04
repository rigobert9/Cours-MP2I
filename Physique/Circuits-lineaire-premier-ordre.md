# Chapitre 4 : Circuits linéaires du 1er ordre
## Condensateur électrique
### Définition et propriétés
> Dans un condensateur, la charge $q_t$ d'une armature et la tension $u_t$ qui en
> résulte vérifient la relation constitutive $q_t = c u_t$. $c$ est la capacité
> d'un condensateur, mesurée en farad (F).

Condensateurs | Valeurs
---|---
Condensateur de TP | $1 nF$
Condensateur avec isolant en céramique | $1 \mu F$ à $100 \mu F$
Électrochimique | $1 mF$

Un condensateur est déchargé s'il n'y a pas de différence de charge aux armatures.

Représentation schématique : deux barres parallèles et séparées, toutes deux
perpendiculaires au circuit.

> Pour un condensateur en convention récepteur, on a l'égalité $i(t) = c \frac{d u(t)}{dt}$.

La tension aux bornes d'un condensateur est une fonction continue du temps.

On dit qu'un circuit électrique est en régime stationnaire si toutes les
tensions et tous les courants ne dépendent pas du temps (donc sont constants).

En régime stationnaire, $t \to \infty$, $i = c \frac{du}{dt} \to 0$.

> En régime stationnaire, un condensateur est équivalent à un interrupteur ouvert (donc à ouvrir le circuit).

### Aspect énergétique
En convention récepteur, $P_\text{reçue} = u(t) \cdot i(t)$. Or, $i(t) = c \frac{d u(t)}{dt}$, donc
$P_\text{reçue} = u(t) c \frac{d u(t)}{dt}$. Celle ci est ainsi égale à
$P_\text{reçue} = \frac{d}{dt} [\frac{1}{2} c u(t)^2]$ (en reconnaissant
l'identité $(f^2)' = 2 f' f$).

$\frac{1}{2} c u(t)^2$ est l'énergie électrique du condensateur.

### Associations de condensateurs
#### Condensateurs en parallèle
Soient N condensateurs en parallèle, $C_\text{éq} = \sum\limits_{k = 1}^{N} C_k$.

#### Condensateurs en série
Soient N condensateurs en série, $\frac{1}{C_\text{éq}} = \sum\limits_{k = 1}^{N} \frac{1}{C_R}$.

## Bobine d'induction
### Définition et propriétés
> Une bobine est un dipôle constitué d'un fil (souvent en cuivre) enroulé sur
> lui-même ou autour d'un noyau magnétique.

En convention récepteur, la relation constitutive de la bobine est $u(t) = L \frac{d i(t)}{dt}$.
La valeur $L$ correspond à l'inductance, mesurée en henry (H).

Une bobine typique de TP aura une inductance de $10$ à $100 mH$.

L'intensité qui traverse une bobine est une fonction continue du temps.

> Pour une bobine en régime stationnaire, $u = L \frac{Di}{dt} = 0$. La bobine est
> alors équivalente à une fil.

Une bobine réelle est constituée d'une bobine idéale (vérifiant la relation
constitutive), mise en série avec une résistance $r$.

### Associations de bobines
#### Bobines en parallèle
Soit N bobines en parallèle, $\frac{1}{L_\text{éq}} = \sum\limits_{k = 1}^{N} \frac{1}{L_k}$.

#### Bobines en série
Soit N bobines en série, $L_\text{éq} = \sum\limits_{k = 1}^{N} L_k$

## Circuits RC
### Équation différentielle
On pose un circuit à une maille, où sont branchés en série un condensateur
de tension $u_c$, une résistance de résistance $R$ et de tension $u_r$ et un
générateur de tension $E$ et d'intensité $i$.

D'après la loi des mailles, $E = u_r + u_c$. D'après la loi d'Ohm, $u_r = R i$.
Par définition, on a $i = \frac{dq}{dt}$, donc $u_r = R \frac{dq}{dt}$.
De plus, d'après la loi constitutive du condensateur $q = C u_c$, donc
$u_r = R C \frac{d u_c}{dt}$.
Ainsi, $RC \frac{d u_c}{dt} + u_c = E \Leftrightarrow \frac{d u_c}{dt} + \frac{u_c}{R C} = \frac{E}{R C}$.
On pose $\tau = R C$ qui est la constante de temps, soit $\frac{d u_c}{dt} + \frac{u_c}{\tau} = \frac{E}{\tau}$.

### Cas de notre étude
Pour obtenir la solution la plus générale à $u_c$, on additionne :
- Une solution de l'équation différentielle sans second membre (égale à 0),
  $\frac{d u_c}{dt} + \frac{u_c}{\tau} = 0$
- La solution particulière $\frac{d u_c}{dt} = 0$

### Charge des condensateurs
On a l'équation $\frac{d u_c}{dt} - \frac{u_c}{\tau} = \frac{E}{\tau}$

On a la solution globale $u_c(t) = u_{c_h}(t) + u_{c_p}(t)$, la somme des deux
solutions mentionnées plus haut.
- Solution de l'équation sans second membre $\frac{d u_{c_h}(t)}{dt} + \frac{u_{c_h}(t)}{\tau} = 0$.
  Il existe donc une solution de la forme $u_{c_h}(t) = A e^{\alpha t}$ (avec A
  une constante), soit $\alpha A e^{\alpha t} + \frac{1}{\tau} A e^{\alpha t} = 0$
  $\Leftrightarrow \alpha = - \frac{1}{\tau}$, donc $u_{c_h}(t) = A e^{- \frac{t}{2}}$.
- Solution particulière : $\frac{d u_{c_p}(t)}{dt} \Rightarrow u_{c_p}(t) = E$.
- Solution globale : $u_c(t) = E + A e^{- \frac{t}{2}}$ où A est une constante.
- Condition initiale : à $t = 0$, $u_c(t = 0) = E + A \Leftrightarrow A = -E$.

On obtient enfin la relation $u_c(t) = E (1 - e^{- \frac{t}{\tau}})$.

En régime permanent, on a $u_c(t = \tau) \approx 63\% E$ et $u_c(t = 5\tau) \approx 99\% E$.

### Calcul de l'intensité
$i(t) = C \frac{d u_c}{dt}$\
$= C \frac{d}{dt} [E - E e^{- \frac{t}{\tau}}]$\
$= C \frac{d}{dt} [-E e^{- \frac{t}{\tau}}]$\
$= -E C \frac{d}{dt} [e^{- \frac{t}{\tau}}]$\
$= -E C \times (\frac{1}{\tau}) \times e^{- \frac{t}{\tau}}$\
$= -E C \times \frac{1}{RC} e^{- \frac{t}{\tau}} = \frac{E}{R} e^{- \frac{t}{\tau}}$

Soit $i(t) = \frac{E}{R} e^{- \frac{t}{\tau}}$

### Décharge du condensateur
$\frac{d u_c}{dt} + \frac{u_c}{\tau} = 0$

La solution est $u_c(t) = A e^{- \frac{t}{\tau}}$ où A = constante.
On a les conditions initiales à $t = 0$, $u_c(t = 0) = E$, donc on a finalement
$u_c(t) = E e^{- \frac{t}{\tau}}$.

De plus, le courant le traversant (négatif car le condensateur se décharge) est
$i(t) = c \frac{d u_c}{dt} = c \frac{d}{dt} [E e^{- \frac{t}{\tau}}]$\
$= E c \frac{d}{dt} [e^{- \frac{t}{\tau}}]$\
$= E c \times (\frac{-1}{\tau}) \times e^{- \frac{t}{\tau}}$\
$= E c \times (\frac{-1}{RC}) \times e^{- \frac{t}{\tau}}$\
$= \frac{-E}{R} e^{- \frac{t}{\tau}}$

### Aspects énergétiques
#### Cas de la charge
D'après la loi des mailles, $R i + r_c = E$.
Or, par définition, $i = \frac{dq}{dt}$, soit
$R \frac{dq}{dt} + u_c = E$. Or $q = c u_c$ donc $u_c = \frac{q}{c}$,
soit $R \frac{dq}{dt} + \frac{q}{c} = E$.

On obtient donc $R i + \frac{q}{c} = E$, et en multipliant par $i dt$
on obtient $R i^2 dt + \frac{q}{c} i dt = E i dt \Leftrightarrow R i^2 dt + \frac{q}{c} \frac{dq}{dt} dt = E i dt$\
$\Leftrightarrow R i^2 dt + \frac{q}{c} dq = E i dt$\
$\Leftrightarrow R i^2 dt + d[\frac{1}{2} \frac{q^2}{c}] = E i dt$

$\frac{d}{dq} [q^2] = 2q \Leftrightarrow d [q^2] = 2q dq \Leftrightarrow d[\frac{1}{2} \frac{q^2}{c}] = \frac{q}{c} dq$

On calcule ainsi l'énergie fournie par le générateur en intégrant sur tout le
temps de charge :
$E_g = \int\limits_{0}^{5 \tau} E i dt = E \int\limits_{0}^{5 \tau} \frac{dq}{dt} dt$
$= E \int\limits_{0}^{Q} dq = QE$ (avec Q la charge maximale).
Or, $Q = CE$, donc $E_g = CE^2$

Pour calculer l'énergie stockée par le condensateur, on prend $E_c = \int\limits_{0}^{Q} d[\frac{1}{2} \frac{q^2}{c}] = \frac{Q^2}{2C}$.
Or, $Q = CE$, donc $E_c = \frac{1}{2} CE^2$.

Pour calculer l'effet Joule $E_J = E_g - E_c = \frac{1}{2} CE^2$.

#### Cas de la décharge
La même chose, mais à l'envers. À l'issue de la charge, le condensateur qui
avait accumulé l'énergie $\frac{1}{2} c^2$ la restitue intégralement au
conducteur ohmique par effet Joule.

## Le circuit RL
### Équation différentielle
On pose un circuit à une maille contenant en série un générateur de tension $E$
et d'intensité $i$, un résistance de résistance $R$ et de tension $u_r$ et une
bobine de tension $u_l$.

D'après la loi des mailles, $u_r + u_L = E$. D'après la loi d'Ohm, $u_r  = R i$,
donc $R i + u_L = E$. Or, d'après la relation constitutive de la bobine, $u_L = L \frac{di}{dt}$.
On développe donc $R i + L \frac{di}{dt} = E$\
$\Leftrightarrow \frac{di}{dt} + \frac{R}{L} i = \frac{E}{L}$\
$\Leftrightarrow \frac{di}{dt} + \frac{i}{\tau} = \frac{E}{L}$ où $\tau = \frac{L}{R}$.

### Cas de notre étude
$i(t) = i_H(t) + i_p(t)$

### Établissement du courant
$\frac{di}{dt} + \frac{i}{\tau} = \frac{E}{L}$

Solution générale : $d \frac{d i_H}{dt} + \frac{i_H}{\tau} = 0$
soit $i_H(t) = A e^{- \frac{t}{\tau}}$.

Solution particulière : $i_p(t) = ?$ quand $\frac{d i_p}{dt} = 0$.
$\frac{i_p(t)}{\tau} = \frac{E}{L}$ où $\tau = \frac{L}{R}$, donc
$\frac{R}{L} i_p(t) = \frac{E}{L} \Leftrightarrow i_p(t) = \frac{E}{R}$.

Solution globale : $i(t) = \frac{E}{R} + A e^{- \frac{t}{\tau}}$ où $\tau = \frac{L}{R}$

Condition initiale : À $t = 0$, $i(t = 0) = 0 = \frac{E}{R} + A$
$\Leftrightarrow A = - \frac{E}{R}$. Ainsi, $i(t) = \frac{E}{R} (1 - e^{- \frac{t}{\tau}})$

Tension aux bornes de la bobine : $u_L(t) = L \frac{di}{dt}$
$\Leftrightarrow u_L(t) = L \frac{d}{dt} [\frac{E}{R} (1 - e^{- \frac{t}{\tau}})]$,
soit $u_L(t) = L \frac{d}{dt} [\frac{E}{R} - \frac{E}{R} e^{- \frac{t}{\tau}}]$\
$= L \frac{d}{dt} [- \frac{E}{R} e^{- \frac{t}{\tau}}]$\
$= \frac{-E L}{R} \frac{d}{dt} [e^{- \frac{t}{\tau}}]$\
$= \frac{-E L}{R} \times \frac{R}{L} e^{- \frac{t}{\tau}}$\
$= E e^{- \frac{t}{\tau}}$\
On a donc $u_L(t) = E e^{- \frac{t}{\tau}}$.

### Rupture du courant
$\frac{di}{dt} + \frac{i}{\tau} = 0$, soit $i(t) = A e^{- \frac{t}{\tau}}$ où
A est une constante.
À partir de la condition initiale $i(t = 0) = \frac{E}{R}$, on a $i(t) = \frac{E}{R} e^{- \frac{t}{\tau}}$.

Pour les tensions aux bornes de la bobine, on a $u_L(t) = L \frac{di}{dt}$, soit
$u_L(t) = L \frac{d}{dt} [\frac{E}{R} e^{- \frac{t}{\tau}}]$,
soit $L \frac{E}{R} \times (- \frac{1}{\tau}) \times e^{- \frac{t}{\tau}}$\
$= -L \frac{E}{R} \frac{R}{L} e^{- \frac{t}{\tau}}$\
$= -E e^{- \frac{t}{\tau}}$ (négatif, on peut obtenir parfois une étincelle de
rupture).

### Aspects énergétiques
L'énergie que fournit le générateur pendant l'établissement du courant se
partage par moitié dans la bobine où elle est stockée de façon magnétique,
l'autre moitié étant dissipée par effet Joule dans le conducteur Ohmique.

À la rupture du courant, la bobine restitue l'énergie précédemment accumulée au
conducteur ohmique, qui la dissipe une nouvelle fois par effet Joule.
