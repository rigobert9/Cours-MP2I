# Circuit mobile dans un champ magnétique fixe
## Conversion d'énergie électrique en énergie mécanique
### Principe
On prend des rails de Laplace alimentés par un générateur de tension,
plongé dans un champ magnétique $\overrightarrow{\rm B}$ stationnaire et
uniforme.\
On représente le tout par un circuit avec un générateur de tension $E$,
parcouru par un courant $i$, avec $\overrightarrow{\rm B}$ dirigé dans la
direction $\overrightarrow{\rm e_z}$ vers au-dessus du circuit, avec une
distance de circuit $x$ entre le générateur et le rail de longueur $L$
et de centre $G$.\
On allume le générateur.

### Équation mécanique et électrique
#### Équation mécanique
On prend le système {tige} dans le référentiel terrestre supposé galiléen,
soumis aux forces se compensant du poids $\overrightarrow{\rm P}$ et de la
réaction du support $\overrightarrow{\rm R}$, sans frottement et déplacé par la
force de Laplace $\overrightarrow{\rm F_L}$.

On a alors pour le PFD la seule force $d \overrightarrow{\rm F_L} = i d \overrightarrow{\rm l} \wedge \overrightarrow{\rm B}$,
donnant $\overrightarrow{\rm F_L} = i B \int\limits_{0}^{L} (- \overrightarrow{\rm e_y}) \wedge (e\overrightarrow{\rm e_z})$
$= - i B L \overrightarrow{\rm e_x}$, donnant finalement
$m \frac{d v_x}{dt} = - i B L$.

#### Équation électrique
On représente le circuit comme un générateur de tension $E$ avec une résistance
du circuit $r$, et un nouveau générateur $e$ correspondant à la force
électromotrice du rail, donnant $E$.

On a le flux $\Phi = - B L x$, donnant par la loi de Faraday $e = - \frac{d \Phi}{dt}$,
donnant $e = B L v_x$, ce qui permet d'obtenir $E = ri - B L v_x$.

#### Découplage et résolution
$\left\{\begin{matrix} m \frac{d v_x}{dt} = - i L B \\ E = ri - B L v_x \end{matrix}\right.$\
Comme on prend $E$ constant, avec les conditions initiales de $v_x(t = 0) = 0$,
on a $v_x = \frac{ri - E}{BL}$ et $\frac{d v_x}{dt} = \frac{i L B}{m}$.
En dérivant la première équation, on a $\frac{d v_x}{dt} = \frac{r}{BL} \frac{d i(t)}{dt}$,
donnant $r \frac{d i(t)}{dt} + \frac{B^2 L^2}{m} i = 0$, donnant
$\frac{d i}{dt} + \frac{i}{\tau} = 0$ avec $\tau = \frac{m r}{B^2 L^2}$, et on
a donc $i(t) = \frac{E}{r} e^{\frac{-t}{\tau}}$ (puisque $i(0) = \frac{E}{r}$).

On obtient finalement en rassemblant que $v_x(t) = - \frac{E}{LB} (1 - e^{\frac{-t}{\tau}}) \leq 0$.

### Bilan de puissance
En prenant la puissance mécanique comme $\overrightarrow{\rm F_L} \cdot \overrightarrow{\rm v} = m \frac{d \overrightarrow{\rm v}}{dt} \cdot \overrightarrow{\rm v}$,
et la puissance électrique comme $Ei = r i^2 - ei = P_J - e i$.
On a par la première égalité $\frac{d E_c}{dt} = P_L$,
et $P_g = P_J - P_{\text{force électromotrice}} = P_J - P_L$,
donnant $e i = B L v_x i$, et comme $\overrightarrow{\rm F_L} = - i L B \overrightarrow{\rm e_x}$,
et donc $P_{\text{fem}} = - P_L$, donnant $P_g = P_J + P_L$.

### Rendement
On compare $E_g$ l'énergie totale fournie par le générateur,
et $E_L$ l'énergie totale reçue par la tige par force de Laplace,
pour le coefficient $\nu = \frac{E_L}{E_g}$.

On prend la tige en mouvement entre $t = 0$ et $t_f \gg \tau$,
donnant $E_g = \int\limits_{0}^{t_f} E_i dt = \int\limits_{0}^{t_f} \frac{E^2}{r} e^{\frac{-t}{\tau}} dt$
$= \frac{E^2}{r} [- \tau e^{\frac{-t}{\tau}}]_0^{t_f} \approx \frac{E^2 \tau}{r}$
(on considère que $t_F \approx +\infty$).

L'énergie totale reçue de la force de Laplace est de
$E_L = \int\limits_{0}^{t_f} P_L dt = \int\limits_{0}^{t_f} d E_c = \Delta E_c = E_c(t_f)$.
Comme $i(t_f) \approx 0$ et que $e = B L v_x  = r i - E$, on a $v_x(t_f) \approx \frac{-E}{BL}$,,
donnant finalement $E_L = \frac{1}{2} m v_x(t_f)^2 = \frac{\tau E^2}{2 r} = \frac{E_g}{2}$,
donc $\nu = \frac{1}{2}$. La moitié de l'énergie fournie par le générateur est
donc perdue par effet Joule.

## Conversion d'énergie mécanique en énergie électrique
### Principe
On reprend la même circuit, mais cette fois-ci, on tire le rail par une force
$\overrightarrow{\rm F}$ qui éloigne le rail du générateur.

Ce mouvement donne naissance à un courant induit. La tige constitue donc un conducteur
parcouru par un courant $i$ et placé dans un champ magnétique extérieur.
Pour s'opposer à la variation du flux, le courant doit être positif; ce courant
génère une force de Laplace qui s'oppose à la force $\overrightarrow{\rm F}$.

La force de Laplace est une force constante $\overrightarrow{\rm F_L} = -i L B \overrightarrow{\rm e_x}$.

### Équations mécanique, électrique et résolution
Comme précédemment, on obtient $m \frac{d v_x}{dt} = -i L B + F$,
et on a $\Phi = \iint \overrightarrow{\rm B} \cdot d \overrightarrow{\rm S} = - BS = - B L x$,
donc $e = - \frac{d \varphi}{dt} = BL v_x$, et on a $i = \frac{e}{r} = \frac{BL}{r} v_x$.

À nouveau, on forme une équation différentielle sur $v_x$.
