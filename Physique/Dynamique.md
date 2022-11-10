# Dynamique du point matériel
## Les lois de Newton
> Isaac Newton : 1642-1727, énonce ces lois dans son traité *Naturalis*
> *philosophae principia mathematica* en 1687.

### Première loi de Newton ou principe de l'inertie
> Un système est dit isolé s'il ne subit aucune force.

> Un système est dit pseudo-isolé si la résultante des forces (la somme
> vectorielle) est nulle.

> Il existe des référentiels, appelés galiléens, dans lesquels un point matériel
> est soit au repos, soit en mouvement rectiligne uniforme.

On peut reformuler ce principe sous la formule $\sum \overrightarrow{\rm F_\text{ext}} = \overrightarrow{\rm 0}$.

On fera l'hypothèse de l'utilisation d'un référentiel terrestre qui est
galiléen lorsque les mouvement observés sont courts devant la période de rotation de
la Terre, de 24 heures.

> Un solide est en translation dans un référentiel s'il garde la même orientation
> au cours de son mouvement.

> Un référentiel en translation rectiligne uniforme par rapport à un référentiel
> galiléen est un référentiel galiléen.

Par hypothèse, les lois de la physique sont les mêmes dans tous les référentiels
galiléens (Einstein, pour poser la relativité universelle).

### Seconde loi de Newton ou principe fondamental de la dynamique (PFD)
> Soit un point matériel $N$ de masse $n$ dans un référentiel galiléen, alors la
> résultante des forces est telle que $\sum \overrightarrow{\rm F_\text{ext}} = \frac{d \overrightarrow{\rm p}}{dt}$,
> où $\overrightarrow{\rm p} = m \overrightarrow{\rm v}$ est la quantité de
> mouvement.

Lorsque $m$ est constante, on a $\sum \overrightarrow{\rm F_\text{ext}} = m \overrightarrow{\rm a}$.

### Troisième loi de Newton ou principe d'action réciproque
> Soient deux points $A$ et $B$ en interaction, de sorte que $A$ exerce sur $B$
> une force $\overrightarrow{\rm F_{A/B}}$ et $B$ exerce sur $A$ une force
> $\overrightarrow{\rm F_{B/A}}$, alors $\overrightarrow{\rm F_{A/B}} = - \overrightarrow{\rm F_{B/A}}$.

### Méthode générale pour résoudre un problème de mécanique
- Définir le système
- Définir le référentiel supposé galiléen (en sup)
- Faire le bilan des forces
- Appliquer le principe fondamental de la dynamique
- Obtenir une équation différentielle, souvent du second ordre
- Résoudre l'équation avec les condition initiales

## Les quatre interactions fondamentales
Ces interactions constituent l'ensemble des interactions présentes en physique,
permettant de modéliser le monde.

On cherche à unifier ces théories sous la forme d'une théorie générale
permettant d'appliquer la relativité générale partout. Deux théories
s'affrontent actuellement, et se recouvrent peut-être :
- Théorie des cordes
- Gravitation quantique à boucles

### Gravitationnelle
L'interaction gravitationnelle est un force attractive entre deux objets qui ont
une masse, de portée infinie.

### Électromagnétisme
Interaction attractive ou répulsive, entre deux champs de portée infinie.

### Interaction faible
Une force qui entre dans le fonctionnement de la désintégration radioactive
(fusion et fission) des éléments, de très courte portée

### Interaction forte
Interaction de très courte portée entre les quarks, responsable de la collision
du noyau.

## Force gravitationnelle
### Définition et propriétés
> Soient $A$ et $B$ deux masses ponctuelles (particules), deux masses $m_A$ et
> $m_B$, $\overrightarrow{\rm F_{A/B}} = - \overrightarrow{\rm F_{B/A}} = -G \frac{m_a m_b}{r^2} \overrightarrow{\rm u}$,
> avec le vecteur unitaire $\overrightarrow{\rm u} = \frac{\overrightarrow{\rm AB}}{\lVert \overrightarrow{\rm AB} \rVert}$
> et $r$ la distance $AB$.

> Le champ gravitationnel créé par un objet $A$ sur un objet $B$, défini par la
> fonction $\overrightarrow{\rm g_A}(B) = -G \frac{m_a}{r} \overrightarrow{\rm u}$.

### Lien avec le poids
La force qu'exerce le centre de la Terre sur un objet, avec $M_T$ la masse de la
Terre, $R_T$ le rayon de la Terre, $h$ l'altitude de l'objet, se résume par la
formule $\overrightarrow{\rm F} = -G \frac{M_T m}{(R_T + h)^2} \overrightarrow{\rm u}$.

Lorsque $h \ll R_T$, on pose $\overrightarrow{\rm F} \approx m (- \frac{G M_T}{R_T^2}) \overrightarrow{\rm u} = m \overrightarrow{\rm g}$.
On a $\overrightarrow{\rm g}$ la force dirigée vers le centre de la Terre et de
valeur d'accélération d'environ $g_T = 9,81 m \cdot s^{-2}$.

On a de plus une approximation de $G = 6.67 \times 10^{-11} m^3 kg^{-1} s^{-2}$.

### Mouvement dans un champ de pesanteur uniforme
> Un point matériel est dit en chute libre si la seule force extérieure qui
> s'exerce sur lui est le poids.

#### Exemple à savoir refaire :
Soit un système {objet M} assimilé à un point
matériel et de masse $m$, dans un référentiel terrestre supposé galiléen, en
mouvement dans le plan $(Oxy)$, avec une vitesse initiale $\overrightarrow{\rm v_0}$
à un angle $\alpha$ formé par rapport à l'axe $x$.\
Concrètement, on lance un ballon de rugby en cloche et on observe sa
trajectoire.\
Le système est soumis uniquement à son poids, on néglige le frottement de l'air
et la poussée d'Archimède.\
D'après le principe fondamental de la dynamique, avec $m$ une constante, on
obtient $\sum \overrightarrow{\rm F_\text{ext}} = m \overrightarrow{\rm a} = m \overrightarrow{\rm g}$
$\Leftrightarrow \overrightarrow{\rm a} = \overrightarrow{\rm g}$. (cette
simplification n'est pas encore prouvé, mais aucune expérience n'a réussi à
montrer l'inverse, et si les deux masses sont différentes, il faut reconstruire
la théorie).\
En projetant sur $(Ox)$ et $(Oy)$, on a $\left\{\begin{matrix} a_x = 0 \\ a_y = -g \end{matrix}\right.$.
Par définition, $\overrightarrow{\rm a} = \frac{d \overrightarrow{\rm v}}{dt}$.
En primitivant par rapport au temps, $\overrightarrow{\rm v} \left|\begin{matrix} v_x(t) = C_1 \\ v_y(t) = -gt + C_2 \end{matrix}\right.$
avec $C_1$ et $C_2$ des constantes. En utilisant les conditions initiales à $t = 0$
$\overrightarrow{\rm v_0} \left|\begin{matrix} v_{0y}(t) = v_0 \cos \alpha \\ v_{0x}(t) = v_0 \sin \alpha \end{matrix}\right.$,
on obtient $\overrightarrow{\rm v} \left|\begin{matrix} v_x(t) = v_0 \cos \alpha \\ v_y(t) = -gt + v_0 \sin \alpha \end{matrix}\right.$.\
Par définition, $\overrightarrow{\rm v} = \frac{d \overrightarrow{\rm OM}}{dt}$.
En primitivant par rapport au temps, avec les conditions initiales $\overrightarrow{\rm OM_0} \left|\begin{matrix} x_0(t) = 0 \\ y_0(t) = 0 \end{matrix}\right.$,
on obtient $\overrightarrow{\rm OM} \left|\begin{matrix} x(t) = v_0 \cos \alpha t \\ y(t) = \frac{-1}{2} gt^2 + v_0 \sin \alpha t \end{matrix}\right.$.\
On en déduit l'équation de la trajectoire, puisque $t = \frac{x}{v_0 \cos \alpha}$, en substituant dans $y(t)$,
$y(x) = \frac{-1}{2} g \frac{x^2}{v_0^2 \cos^2 \alpha} + v_0 \sin \alpha \frac{x}{v_0 \cos \alpha}$
$\Leftrightarrow y(x) = \frac{-1}{2} g \frac{x^2}{v_0^2 \cos^2 \alpha} + x \tan \alpha$, qui est l'équation d'une parabole.

On cherche donc la distance maximale (la portée) du système, c'est à dire le
point $x$ en lequel $y(x_p) = 0$.
$y(x_p) = 0$\
$\Leftrightarrow \frac{-1}{2} g \frac{x_p^2}{v_0^2 \cos^2 \alpha} + x_p \tan \alpha = 0$\
$\Leftrightarrow x_p (\frac{-1}{2} g \frac{x_p}{v_0^2 \cos^2 \alpha} + \tan \alpha) = 0$\
Or, $x_p \neq 0$, donc
$\frac{-1}{2} g \frac{x_p}{v_0^2 \cos^2 \alpha} + \tan \alpha = 0$\
$\Leftrightarrow \frac{2 v_0^2 \cos^2 \alpha \tan \alpha}{g} = x_p$\
$\Leftrightarrow \frac{2 v_0^2 \cos \alpha \sin \alpha}{g} = x_p$\
$\Leftrightarrow \frac{2 v_0^2 \sin 2\alpha}{g} = x_p$\

On cherche de même la flèche du système (sa hauteur maximale), et on cherche
donc la racine de la dérivée de $y(x)$.
$y(x) = \frac{-1}{2} g \frac{x^2}{v_0^2 \cos^2 \alpha} + x \tan \alpha$\
$\Leftrightarrow y'(x) = -g \frac{x}{v_0^2 \cos^2 \alpha} + \tan \alpha$\
Avec lequel on pose :
$y'(x_F) = 0$
$\Leftrightarrow y'(x_F) = -g \frac{x_F}{v_0^2 \cos^2 \alpha} + \tan \alpha = 0$\
$\Leftrightarrow x_F = \frac{v_0^2 \cos^2 \alpha \tan \alpha}{g}$\
$\Leftrightarrow x_F = \frac{v_0^2 \cos \alpha \sin \alpha}{g}$\
$\Leftrightarrow x_F = \frac{v_0^2 \sin 2\alpha}{g} = \frac{x_p}{2}$\
À l'aide de cette valeur, en appliquant la formule de $y(x)$, on obtient
$y(x_F) = \frac{1}{2} \frac{v_0^2}{g} \sin^2 \alpha$.

## Force électromagnétique
### Force électrique
Soient deux charges $q_1$ et $q_2$ ponctuelles et supposées immobiles, on pose
$\overrightarrow{\rm F_{1 \to 2}} = K \frac{q_1 q_2}{r^2} \overrightarrow{\rm u}$
où $r$ est la distance entre la charge $q_1$ et $q_2$ et
$K = \frac{1}{4 \pi \varepsilon_0} \approx 9.0 \times 10^9$ (la constante
électromagnétique, en $m \cdot F^{-1}$, et avec $\varepsilon_0$ la permitivité diélectrique).

C'est une force statique : lorsque les charges bougent, il s'agit d'un champ
magnétique.

### Force magnétique
Pour une charge $q$ en mouvement de vitesse $\overrightarrow{\rm v}$ plongée
dans un champ magnétique dans le vide, on pose
$\overrightarrow{\rm F} = q \overrightarrow{\rm v} \wedge \overrightarrow{\rm B}$.

$\wedge$ dénote un produit vectoriel.

Les forces magnétiques et électriques s'entre-influencent, et se résumeront plus
tard dans l'année à l'aide de la force de Lorentz $\overrightarrow{\rm F} = q\overrightarrow{\rm E} + q\overrightarrow{\rm v} \wedge \overrightarrow{\rm B}$.

#### Exemple
Soit un atome d'hydrogène (un proton et un électron), on obtient
$\left\{\begin{matrix} F_g = G \frac{m_1 m_2}{r^2} \\ F_e = K \frac{q_e q_p}{r^2} = \frac{K e^2}{r^2} \end{matrix}\right.$.\
On calcule $\frac{F_e}{F_g} = \frac{K e^2}{G m_e m_p}$, et on peut appliquer
simplement $\frac{F_e}{F_g} = \frac{9.0 \times 10^9 \times 1.6 \times 10^{-19^2}{6.67 \times 10^{-11} \times 9.1 \times 10^{-31} \times 1.67 \times 10^{-27}} \approx 2.3 \times 10^{39} \gg 1$,
donc $F_g \ll F_e$.

## Force de rappel d'un ressort
On attache une masse assimilée à un point {M} à un ressort, et il est soumis à
une force de rappel du ressort de forme $\overrightarrow{\rm F} = -k (\ell - \ell_0) \overrightarrow{\rm u}$,
avec $\ell$ la longueur maximale du ressort en $m$ et $\ell_0$ la longueur à
vide en $m$ du ressort. $k$ est une constante expérimentale, la raideur du
ressort, en $N \cdot m^{-1}$. $\overrightarrow{\rm u}$ est le vecteur unitaire
orienté du bout du ressort vers la masse.

On note souvent $\Delta\ell = \ell - \ell_0$ l'élongation du ressort.

### Ressort horizontal
On a la masse posée, attachée à un ressort horizontal, qui est soumise au rappel
du ressort, à son poids vers le bas appliquée à son centre de gravitation et à la réaction du sol
appliquée au point de contact au sol.

Le système est un {objet M} assimilé à un point matériel de masse $m$, dans un
référentiel terrestre supposé galiléen. Le système est soumis aux poids
$\overrightarrow{\rm P} = m\overrightarrow{\rm g}$, à la réaction du support
$\overrightarrow{\rm N}$, et à la force élastique $\overrightarrow{\rm F} = -k\Delta\ell$.\
D'après le principe fondamental de la dynamique,
$\sum \overrightarrow{\rm F_\text{ext}} = m \overrightarrow{\rm a}$
$\Leftrightarrow \overrightarrow{\rm P} + \overrightarrow{\rm N} + \overrightarrow{\rm F} = m \overrightarrow{\rm a}$.\
En projetant suivant les axes $(Ox)$ et $(Oy)$, on obtient
$\left\{\begin{matrix} m \ddot{x} = -k(x - \ell_0) \\ m \ddot{g} = N - mg \end{matrix}\right.$.

Le mouvement a lieu suivant $(Ox)$ donc $\ddot{y} = 0$, et on déduit des
équivalences posées précédemment que $N = mg$ et $m \ddot{x} = -k(x - \ell_0)$
$\Leftrightarrow \ddot{x} + \frac{k}{m} x = \frac{k}{m} \ell_0$
$\Leftrightarrow \ddot{x} + \omega_0^2 x = \omega_0^2 x_\text{éq}$
où $\omega_0^2 = \frac{k}{m}$ et $x_\text{éq} = \ell_0$.

### Oscillateur harmonique
Soit une forme $\ddot{x} + \omega_0^2 x = 0$, on a la solution
$x(t) = x_m \cos(\omega_0 t + \varphi)$ (avec $x_m$ l'amplitude, $\omega$ la pulsation, $\varphi$ le déphasage)
ou encore $x(t) = A \cos(\omega_0 t) + B \sin(\omega_0 t)$ (avec $A$ et $B$ des
constantes).

### Resort vertical
C'est le cas qu'on retrouve par exemple lors de l'utilisation du dynamomètre.
La masse est accrochée à plafond par le ressort, subissant son poids par son
centre de gravitation et le rappel par un point de contact (on confond ces deux
points puisqu'on assimile la masse à un point).

Le système est un {objet M} assimilé à un point matériel de masse $m$, dans un
référentiel terrestre supposé galiléen. Il est soumis au poids $\overrightarrow{\rm P}$
et à la force élastique $\overrightarrow{\rm F}$. D'après le principe
fondamental de la dynamique,
$\sum \overrightarrow{\rm F_\text{ext}} = m \overrightarrow{\rm a}$
$\Leftrightarrow \overrightarrow{\rm P} + \overrightarrow{\rm F} = m \overrightarrow{\rm a}$.

En projetant selon $(Oz)$, $mg - k(z - \ell_0) = m \ddot{z}$
$\Leftrightarrow \ddot{z} + \omega_0^2 = \omega_0^2 z_\text{éq}$ où
$\omega_0^2 = \frac{k}{m}$ et $z_\text{éq} = \frac{mg}{k} + \ell_0 > \ell_0$

## Tension d'un fil
