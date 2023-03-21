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
Pour un gaz parfait, $PV = n R Ti# \Leftrightarrow P = \frac{n R T}{V}$,
donnant $W = - \int\limits_{\text{État initial}}^{\text{État final}} n R T \frac{d V}{V}$.
Puisque la température est constante, on a finalement la formule :

> $W = - n R T_0 \ln(\frac{V_2}{V_1}) = n R T_0 \ln(\frac{V_1}{v_2})$

### Le transfert thermique
On ne peut pas intégrer les transferts thermiques, puisqu'ils correspondent à
une agitation, et on ne pourra donc pas déterminer leur travail.

On pose $Q$ la chaleur (la dissipation d'énergie, qu'on ne peut pas vraiment
mesurer).
