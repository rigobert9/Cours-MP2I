# Mouvements à force centrale
## Forces centrales
### Définition
> Soit un point matériel $M$ dans un référentiel supposé galiléen, soumis à une
> force $F$, la force est dite centrale si elle peut se mettre sous la forme
> $F = F_r \overrightarrow{\rm u_r}$
> avec $\overrightarrow{\rm u_r} = \frac{\overrightarrow{\rm OM}}{\lVert \overrightarrow{\rm OM} \rVert}$ et
> $r = \lVert \overrightarrow{\rm OM} \rVert$.

C'est le cas par exemple de la force gravitationnelle, de l'intéraction entre un
proton et un électron, de la Terre et d'un satellite...

### Travail et énergie potentielle
Puisque par définition, le travail élémentaire est $\delta W = \overrightarrow{\rm F} \cdot d \overrightarrow{\rm r}$,
en coordonnées sphériques, $d \overrightarrow{\rm r} = d r \overrightarrow{\rm u_r} + r d \theta \overrightarrow{\rm u_\theta} + r \sin \theta \overrightarrow{\rm u_\varphi}$,
et donc $\delta W = F_r \times dr$.

Si on peut trouver une fonction $E_p(r)$ telle que $\delta W = -E_p(r)$,
alors la force est conservative, de forme $F_r(r) = - \frac{d E_p}{dr}$.

> Une force centrale et conservative est portée par le vecteur
> $\overrightarrow{\rm u_r}$, et ne dépend que $r$.

On peut reconnaître cette forme dans la force élastique par exemple :
$F_r(r) = -k (r - \ell_0)$, $E_p(r) = - \int F_r dr = \frac{k}{2} (r - \ell_0)^2 + C$,
avec $C$ une constante.

### Forces centrales newtoniennes
> Une force centrale est dite newtonienne si elle peut se représenter sous la
> forme $F_r = - \frac{K}{r^2}$ avec $K$ une constante.

Si $K < 0$, la force est répulsive, et si $K > 0$, la force est attractive.

C'est le cas de l'interaction gravitationnelle, avec $K = G m_1 m_2$,
et de l'interaction de Coulomb, avec $K = - \frac{q_1 q_2}{4 \pi \varepsilon_0 \varepsilon_1}$.

Dans ces cas, $\frac{d E_p}{dr} = \frac{K}{r^2}$, donc $E_p(r) = - \frac{K}{r} + C$.
À l'infini, $E_p(r = \infty) = 0$, donc $C = 0$, donnant $E_p(r) = - \frac{K}{r}$.

## Conservation du moment cinétique
D'après le théorème du moment cinétique, par rapport à un point $O$ fixe
dans un référentiel supposé galiléen,
$\frac{d \overrightarrow{\rm \sigma_O}(M)}{dt} = \overrightarrow{\rm OM} \wedge \overrightarrow{\rm F}$,
avec $\overrightarrow{\rm \sigma_O}(M) = \overrightarrow{\rm OM} \wedge m \overrightarrow{\rm v}$.
Or $\overrightarrow{\rm F}$ est une force centrale selon $\overrightarrow{\rm u_r}$
donc $\frac{d \overrightarrow{\rm \sigma_O}(M)}{dt} = \overrightarrow{\rm 0}$,
donc $\overrightarrow{\rm \sigma_O}(M)$ est un vecteur constant.

> $\overrightarrow{\rm \sigma_O}(M)$ est un vecteur constant.

### Mouvement plan
Soit un mouvement dans le plan du point $M$, à une position $\overrightarrow{\rm OM}$,
à une vitesse $\overrightarrow{\rm v}$. Le vecteur $\overrightarrow{\rm \sigma_O}(M)$
est orthogonal au plan.

Le mouvement de $M$ est contenu dans le plan perpendiculaire à $\overrightarrow{\rm \sigma_O}$
passant par $O$.

### Constante des aires
Soit une force centrale $\overrightarrow{\rm F} = F(r) \overrightarrow{\rm u_r}$,
on a $\overrightarrow{\rm v} = \frac{d r}{dt} \overrightarrow{\rm u_r} + r \frac{d \theta}{dt} \overrightarrow{\rm u_\theta}$
$= \dot{r} \overrightarrow{\rm u_r} + r \dot{\theta} \overrightarrow{\rm u_\theta}$ et
$\overrightarrow{\rm \sigma_O}(M) = \overrightarrow{\rm OM} \wedge m \overrightarrow{\rm v}$
$= (r \overrightarrow{\rm u_r}) \wedge m (\dot{r} \overrightarrow{\rm u_R} + r \dot{\theta} \overrightarrow{\rm u_\theta})$
$= m r^2 \dot{\theta} \overrightarrow{\rm u_z}$,
donc $m r^2 \dot{\theta} \overrightarrow{\rm u_z}$ est un vecteur constant.

> On note $C$ la constante des aires, de valeur $r^2 \dot{\theta}$.

### Interprétation graphique
On se place de façon à observer $\overrightarrow{\rm OM}$,
et sa valeur un instant plus tard. On a donc
$\overrightarrow{\rm OM}(t) = r \overrightarrow{\rm u_r}$
et $\overrightarrow{\rm OM}(t + dt) = r \overrightarrow{\rm u_r} + dr \overrightarrow{\rm u_r} + r d \theta \overrightarrow{\rm u_\theta}$.

L'aire balayée pendant $dt$ par le vecteur $\overrightarrow{\rm OM}$
est $dA = \frac{(r + dr) r d \theta}{2} - \frac{dr r d \theta}{2}$
$= \frac{r^2 d\theta}{2}$, donnant $\frac{d A}{dt} = \frac{r^2 \dot{\theta}}{2}$,
la moitié de la constante d'aire, qu'on appelle vitesse aérolaire.

> $\frac{d A}{dt} = \frac{r^2 \dot{\theta}}{2} = \frac{C}{2}$ est appelé vitesse aérolaire.

> Loi des aires, ou deuxième loi de Kepler : Pendant des durées égales, le vecteur
> position balaye des aires égales.

## Forces centrales newtoniennes : étude énergétique
### Énergie potentielle effective
On a, pour une force centrale newtonienne, $E_m = \frac{1}{2} m v^2 - \frac{K}{r}$.

En coordonnées polaires, $E_m = \frac{1}{2} m (\dot{r}^2 + r^2 \dot{\theta}^2) - \frac{K}{r}$,
qui est constante puisque la force est conservative.
On introduit $C$ en on réécrit
$E_m = \frac{1}{2} m \dot{r}^2 + \frac{1}{2} m \frac{C^2}{r^2} - \frac{K}{r}$.

> L'étude d'un système à force centrale se rapporte à l'étude d'un système à un
> unique degré de liberté.

> $E_{p,\text{eff}} = \frac{1}{2} m \frac{C^2}{r^2} - \frac{K}{r}$ est l'énergie
> potentielle effective du système à farce centrale newtonienne.

### Trajectoires possibles dans le cas attractif
Dans le cas attractif, $K > 0$, et l'énergie potentielle effective selon $r$
oscille entre ses asymptotes de $\frac{1}{2} m \frac{C^2}{r^2}$ et $- \frac{K}{r}$.

Le minimum de cette valeur est atteint lorsque la dérivée de la valeur selon $r$
est nulle, soit égale à $- \frac{m C^2}{R^3} + \frac{K}{R^2}$,
donc $R = \frac{m C^2}{K}$. La valeur minimale atteinte est donc
$\frac{-K^2}{2 m C^2}$.

#### Trajectoires ouvertes
Lorsque l'énergie mécanique est positive, on parle d'états de diffusion ou
d'états libres. On peut alors faire apparaître la formule d'une hyperbole pour
le mouvement du système. La courbe de l'énergie potentielle ne croise qu'une
seule fois la valeur de l'énergie mécanique.

Si l'énergie mécanique est nulle, la trajectoire forme une parabole.
La courbe de l'énergie potentielle croise une fois la valeur de l'énergie
mécanique, et l'a pour asymptote à l'infini.

#### Trajectoires fermées
Lorsque l'énergie mécanique est négative, on parle d'états liés.
La courbe de l'énergie potentielle effective selon $r$ croise deux fois la
valeur de l'énergie mécanique. La trajectoire de l'objet est alors une ellipse,
avec pour distances à l'origine les valeurs $r_\text{min}$ et $r_\text{max}$ d'intersection
avec l'énergie mécanique.

> Première loi de Kepler : Lorsque la trajectoire est une ellipse, l'axe central
> est l'un de ses deux foyers.

Dans le cas où $r_\text{min} = r_\text{max} = R$, la trajectoire est un cercle.

> Le point de la trajectoire le plus proche du soleil 
> est le périhélie, et le point le plus éloigné est l'aphélie.

> La vitesse est la plus élevée au périhélie, et la plus faible en l'aphélie.

> Au périhélie et à l'aphélie, la vitesse est orthoradiale.

> Le point de la trajectoire le plus proche de la Terre est le périgée,
> et le point le plus éloigné est l'apogée.

Il s'agit de la même chose, autour de la Terre.

#### Trajectoire dans le cas répulsif
Dans ce cas, on a $K < 0$, et les trajectoires sont toujours ouvertes.
La trajectoire forme alors une hyperbole.

## Forces newtoniennes : étude énergétiques des trajectoires formées
### Trajectoire circulaire
#### Force centrale quelconque
Le cercle est de rayon $r = R$ constant. On pose
$\overrightarrow{\rm v} = R \dot{\theta} \overrightarrow{\rm u_\theta} = v \overrightarrow{\rm u_\theta}$,
$\overrightarrow{\rm a} = - R \dot{\theta}^2 \overrightarrow{\rm u_r} + R \ddot{\theta} \overrightarrow{\rm u_\theta}$
$= - \frac{v^2}{R} \overrightarrow{\rm u_r} + \frac{d v}{dt} \overrightarrow{\rm u_\theta}$.
On a $C = R \dot{\theta}^2$ une constante, donc $\dot{\theta}$ est une
constante, et donc la vitesse est constante.

> A mouvement circulaire à force centrale est nécessairement uniforme.

#### Force newtonienne quelconque
$K > 0$, et on pose le $PFD$, donnant
$\overrightarrow{\rm F} = \frac{- K}{r^2} \overrightarrow{\rm u_r} = m \overrightarrow{\rm a }$.
La trajectoire étant circulaire, $r = R$ est une constante.
On a donc $m \frac{v^2}{R} = \frac{K}{R^2}$. Ainsi,
$v = \pm \sqrt{\frac{K}{mR}}$. Si $\dot{\theta} > 0$, $v > 0$.

On peut obtenir le même résultat par une approche énergétique.
On a donc $v^2 = R^2 \dot{\theta}^2 = \frac{(R^2 \dot{\theta})^2}{R^2}$
$= \frac{C^2}{R^2} = \frac{K}{mR}$, donc $v = \pm \sqrt{\frac{K}{mR}}$.

On cherche la période de révolution $T$ telle que $v = \frac{2 \pi R}{T}$.
On a donc $T = \frac{2 \pi R}{|v|} = 2 \pi R \sqrt{\frac{mR}{K}}$
$= 2\pi \sqrt{\frac{mR^3}{K}}$. On $\frac{R^3}{T^2} = \frac{K}{4 \pi^2 m}$
une constante.

On obtient avec l'énergie mécanique $E_m = \frac{1}{2} m v^2 - \frac{K}{R} = - \frac{K}{2R}$.

#### Exemple : attraction gravitationnelle
On se place dans le système d'une object de masse $m$ autour du soleil de masse
$M_0$.

On a donc $K = G M_0 m$, et $v = \pm \sqrt{\frac{G M_0}{R}}$,
et $\frac{R^3}{T^2} = \frac{G M_0}{4 \pi^2}$.

> Troisième loi de Kepler : $\frac{R^3}{T^2} = \frac{G M_0}{4 \pi^2}$.

Ainsi, on a $E_m = - \frac{G M_0 m}{2R}$.

### Trajectoire elliptique
#### Description mathématique d'une ellipse
En coordonnées cartésiennes, une ellipse de centre $(x_0,y_0)$, de "hauteur" $2b$
et de "largeur" $2b$. $a$ est le demi grand axe, et $b$ le demi petit axe, avec
$a > b$. L'équation est alors $\frac{(x - x_0)^2}{a^2} - \frac{(y - y_0)^2}{b^2} = 1$.

En coordonnées polaires, $r(\theta) = \frac{P}{1 - e \cos(\theta)}$,
avec $p$ le paramètre de l'ellipse et $e$ son excentricité, entre $0$ inclus et $1$
exclu.
- Pour $e = 0$, $r(\theta) = p$
- Pour $0 < e < 1$, c'est une ellipse quelconque
- Pour $e > 1$, c'est une hyperbole
- Pour $e = 1$, c'est une parabole

On a $p = \frac{b^2}{a}$, et $e = \sqrt{1 - \frac{b^2}{a^2}}$,
et on a $r_\text{min} = \frac{p}{1 + e}$ et $r_\text{max} = \frac{p}{1 - e}$.

## Applications
### Satellite géostationnaires
Un satellite géostationnaire est un satellite qui reste toujours au dessus de la
surface de la Terre. Il apparaît donc immobile pour un observateur terrestre.

#### Plan de l'orbite
Le plan de l'orbite d'un satellite géostationnaire doit être dans le plan de
l'équateur.

#### Période de rotation
Le mouvement du satellite doit être synchrone avec le mouvement de rotation de
la Terre. On a donc $\omega$ et $T$ des constantes.

> Le jour sidéral correspond à la durée mise par la Terre pour faire un tour sur
> elle-même. Il dure 23 h 56.
