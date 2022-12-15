# Oscillateurs amortis
Les oscillateurs harmoniques sont souvent trop idéalisés, omettant le frottement
ou d'autres forces supplémentaires. En compliquant l'équation différentielle, on
va obtenir des systèmes qui décrivent mieux le problème.

## Position du problème
### Oscillateur amorti en mécanique
#### Expérience verticale
On observe dans une première expérience un objet plongé dans un liquide visqueux
au bout d'un ressort, et on observe son mouvement. Le graphe de sa position
correspond à une sinusoïde qui s'atténue peu à peu. Ce graphe possède une
pseudo-période (période entre chaque ventre et nœud du graphe).

#### Expérience horizontale
Une autre expérience présente un objet au bout d'un ressort horizontal, posé sur
un plan. La force de frottement est toujours dans le sens inverse de l'action du
ressort, atténuant peu à peu le va-et-vient de l'objet. On considèrera
uniquement les frottements fluides (de l'air) et pas les frottements solides.

L'{objet} de masse $m$, assimilé à un point matériel dans un référentiel
terrestre supposé galiléen, est ainsi soumis à son poids $\overrightarrow{\rm P}$,
à la réaction normale du plan sur l'objet qui le compense $\overrightarrow{\rm N}$,
à la force élastique du ressort $\overrightarrow{\rm F} = -k (x - \ell_0) \overrightarrow{\rm e_x}$,
et au frottement de l'air $\overrightarrow{\rm f} = -\lambda \overrightarrow{\rm v}$
(qui est faible donc de forme linéaire).\
On applique donc le principe fondamental de la dynamique, et on obtient une
équation différentielle en $x(t)$ :
$m a(t) = -k (x(t) - \ell_0) - \lambda v(t)$\
$\Leftrightarrow m \ddot{x}(t) = -k (x(t) - \ell_0) - \lambda \dot{x}(t)$\
$\Leftrightarrow \ddot{x}(t) + \frac{\lambda}{m} \dot{x}(t) + \frac{k}{m} x(t)= \frac{k}{m} \ell_0$\

### Oscillateur amorti en électricité
On se place dans un circuit RLC, contenant un condensateur, une bobine et une
résistance en série. On observe aussi une sinusoïde pseudo-périodique, de
décroissance exponentielle.

On cherche à retrouver une équation différentielle en $u_C(t)$, et on obtient
$\frac{E}{CL} = \ddot{u} + \frac{R}{L} \dot{u} + \frac{u}{CL}$.

### Forme canonique et premières propriétés
> Sous forme canonique, un oscillateur harmonique amorti vérifie un équation
> différentielle de la forme : $\ddot{x} + \frac{\omega_0}{Q} \dot{x} + \omega^2 x = \omega_0^2 x_\text{éq}$.

On appelle $\omega_0$ la pulsation propre en $\text{rad} \cdot s^{-1}$, et $Q$
le facteur de qualité, et avec $x_\text{éq}$ un équilibre.

On introduit ces facteurs afin de déterminer des régimes différents.

> Le taux d'amortissement est une grandeur sans dimension, qui est définie par
> $\xi = \frac{1}{2Q}$.

- Pour un système mécanique masse-ressort, les paramètres de l'oscillateur
  harmonique amorti sont $\omega_0 = \sqrt{\frac{k}{m}}$ et $Q = \frac{\sqrt{km}}{\lambda}$.
- Pour un système électrique RLC série, l'oscillateur harmonique amorti a pour
  paramètres $\omega_0 = \frac{1}{\sqrt{LC}}$ et $Q = \frac{1}{R} \sqrt{\frac{L}{C}}$.

## Zoologie des solutions
La forme caractéristique d'une équation sous forme canonique est le polynôme
$r^2 + \frac{\omega_0}{Q} r + \omega_0^2 = 0$. On trouve donc le discriminant
$\Delta = (\frac{\omega_0}{Q})^2 - 4 \omega_0^2 = \omega^2 (\frac{1}{Q^2} - 4)$.
Le signe de $\Delta$ dépend donc de $Q$.

### Cas pseudo-périodique
Dans le cas où $\Delta < 0$ et $Q > \frac{1}{2}$, on a les racines de forme
$r_{\pm} = - \frac{\omega_0}{2Q} \pm j \frac{\sqrt{-\Delta}}{2}$,
donnant la solution $X(t) = [A \cos(\omega_0 t) + B \sin(\omega_0 t)] e^{-\alpha t} + X_\text{éq}$,
avec $A$ et $B$ des constantes.
Les "bornes" de la fonction sont, à tout moment, la fonction
$X_\text{éq} + \sqrt{A^2 + B^2} e^{-\alpha t}$ en haut et
$X_\text{éq} - \sqrt{A^2 + B^2} e^{-\alpha t}$ en bas.

> Le facteur d'amortissement, homogène à $s^{-1}$, est
> $\alpha = \frac{\omega_0}{2Q}$. Il peut aussi correspondre à
> $\frac{1}{\tau}$, lorsqu'on définit un temps caractéristique.

Dans ce cas, le régime est dit pseudo-périodique ou
"sous-amorti". On observe des oscillations dans le régime transitoire.

> Le temps caractéristique de décroissance des oscillations, noté
> $\tau = \frac{1}{\alpha} = \frac{2Q}{\omega_0}$. Pour $t > 5 \tau$, le système a
> atteint $99 %$ de son évolution et on considère que le régime permanent est
> atteint.

Pour $Q \to \infty$, la modélisation tend vers un oscillateur harmonique, et
l'atténuation exponentielle disparaît pour laisser place à une oscillation
régulière. Dans le cas électrique, cela revient à prendre $R = 0$, et pour le
cas mécanique, cela revient à prendre $\lambda = 0$, c'est-à-dire pas de
frottement.

### Cas suramorti ou apériodique
Lorsque $\Delta > 0$ et $Q < \frac{1}{2}$ on a les racines de la forme
$r_{\pm} = - \frac{\omega_0}{2Q} \pm \frac{\sqrt{\Delta}}{2}$
$= - \frac{\omega_0}{2} (\frac{1}{Q} \pm \sqrt{\frac{1}{Q^2} - 4}) < 0$.
On a ainsi une solution de la forme $X(t) = A e^{r + t} + B e^{r - t} + X_\text{éq}$.

Dans ce cas, le régime est dit suramorti ou apériodique.

### Cas critique
Lorsque $\Delta = 0$ et $Q = \frac{1}{2}$, on a $r = \frac{- \omega_0}{2Q} = - \omega_0$,
et on a donc une solution de la forme
$X(t) = (A + B t) e^{- \frac{\omega_0}{2Q} t} = (A + Bt) e^{- \omega_0 t}$.

La courbe croît de façon linéaire au début avant de s'arrondir sous une
asymptote en $X_\text{éq}$.

## Résolution à partir des conditions initiales
### Dans le système mécanique
$\ddot{x} + \frac{\lambda}{m} \dot{x} + \frac{k}{m} x = \frac{k}{m} \ell_0$.

On pose $\omega_0 = \sqrt{\frac{k}{m}}$ et $Q = \frac{\sqrt{m k}}{\lambda}$.

En prenant $x(t = 0) = 0$ et $v(t = 0) = v_0$, on commence par déterminer le
régime en calculant $Q$. On est ensuite en présence d'un problème de Cauchy,
qu'on résout en déterminant à partir des conditions initiales les constantes $A$
et $B$ dans le cas correspondant à la valeur de $Q$.

### Dans le système électrique
$\frac{d^2 u_C(t)}{dt^2} + \frac{R}{L} \frac{d u_C(t)}{dt} + \frac{u_C(t)}{LC} = \frac{E_0}{LC}$

On pose $\omega_0 = \frac{1}{\sqrt{LC}}$ et $Q = \frac{1}{R} \sqrt{\frac{L}{C}}$.
On détermine le régime en calculant $Q$, et on essaie de trouver les constantes
à partir des conditions initiales (lorsque la bobine et le condensateur sont
déchargés, $u_C(t = 0) = 0$ et $\frac{d u_C(t = 0)}{dt} = 0$).

## Étude énergétique
### Cas électrique
$E_0 = R i(t) + L \frac{d i(t)}{dt} + u_C(t) \Leftrightarrow E_0 i(t) = R i^2(t) + \frac{d}{dt} [\frac{1}{2} L i^2(t)] + \frac{d}{dt} [\frac{1}{2} C u_C^2(t)]$

On a la puissance du générateur de la forme
$P = \frac{d}{dt} [E_\text{bobine}] + \frac{d}{dt} [E_\text{condensateur}]$.

$\Delta E_\text{gén} = \Delta E_J + \Delta E_\text{bobine} + \Delta E_\text{condensateur}$

### Cas mécanique
$m \ddot{x} + \lambda \dot{x} + k x = k \ell_0$
$\Leftrightarrow m \dot{x} \ddot{x} + k (x(t) - \ell_0) \dot{x} = - \lambda \dot{x}^2$
$\Leftrightarrow \frac{d}{dt} [\frac{1}{2} m \dot{x}^2] + \frac{d}{dt} [\frac{1}{2} k (x(t) - \ell_0)^2] = - P_\text{dissipative}$
$\Leftrightarrow \frac{d}{dt} [E_C] + \frac{d}{dt} [E_\text{él}] = - P_\text{dissipative}$

La force élastique est non conservative.

### Analogies mécanique/électrique
Mécanique                                                    | Électrique
---                                                          | ---
Position $x(t)$                                              | Charge $q(t)$
Vitesse $\dot{x}(t)$                                         | Intensité $i(t)$
Coefficient $\lambda$ de frottement                          | Résistance $R$
Masse $m$                                                    | Inductance $L$
Raideur $k$                                                  | Inverse de la capacité $\frac{1}{C}$
Énergie cinétique $E_C = \frac{1}{2} v^2$                    | Énergie magnétique $E_L = \frac{1}{2} L i^2(t)$
Énergie potentielle élastique $\frac{1}{2} k (x - \ell_0)^2$ | Énergie électrostatique du condensateur $E_\text{cond} = \frac{1}{2} C u_C^2(t)$
Principe fondamental de la dynamique                         | Loi des mailles
