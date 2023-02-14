# Mécanique du solide
## Description cinétique d'un solide
### Définitions
> Un solide indéformable $\Sigma$ est un ensemble de points $(M_i)_{[\![1,N]\!]}$,
> tel que toute distance $M_i M_j(t)$ est une constante.

> Le centre de gravité ou centre d'inertie (parfois différents) $G$ de $\Sigma$
> est défini par la somme $\sum\limits_{i = 1}^{N} m_i \cdot \overrightarrow{\rm G M_i} = \overrightarrow{\rm 0}$.

D'après la relation de Chasles, $\overrightarrow{\rm 0} = \sum m_i \overrightarrow{\rm G O} + \sum\limits_{i} m_i \overrightarrow{\rm O M_i}$,
donc $(\sum\limits_{i} m_i) \overrightarrow{\rm OG} = \sum\limits_{i} m_i \overrightarrow{\rm O M_i}$. En notant
$m_\text{tot} = \sum\limits_{i} m_i$, pour tout point $O$, $m_\text{tot} \overrightarrow{\rm OG} = \sum\limits_{i} \overrightarrow{\rm O M_i}$.

> En notant $\overrightarrow{\rm v_i}$, la vitesse du point $M_i$ et $\overrightarrow{\rm v_G}$ la vitesse
> du centre d'inertie par rapport à $O$, $\sum\limits_{i} m_i \overrightarrow{\rm v_i} = m_\text{tot} \overrightarrow{\rm v_G}$.

### Solide en mouvement
#### Translation
> Un solide est dit en translation si pour tout $t$, $\overrightarrow{\rm M_i(t) M_j(t)} = \overrightarrow{\rm M_i(0) M_j(0)}$.

On a ainsi de façon équivalente $\overrightarrow{\rm M_i(0) M_j(0)} = \overrightarrow{\rm O M_j}(t) - \overrightarrow{\rm O M_i}(t)$.

> Tous les points d'un solide en translation ont le même vecteur vitesse.

On peut réaliser une translation rectiligne (télésiège) ou circulaire (grande
roue).

#### Rotation autour d'un axe fixe
On pose un axe $\Delta$ orienté selon $\overrightarrow{\rm u_z}$.
On peut ainsi identifier chaque point du solide par des coordonnées cylindriques :
$r_i, \theta_i, z_i$, dans le repère $(\overrightarrow{\rm u_r}, \overrightarrow{\rm u_\theta}, \overrightarrow{\rm u_z})$.

> Tous les points $M_i$ d'un solide ont la même vitesse angulaire $\omega_i$ ($= \dot{\theta}$).
> Ainsi, $\overrightarrow{\rm v_i} = r_i \omega_i \overrightarrow{\rm u_\theta}$.

> Le vecteur rotation instantané du solide $\Sigma$ est $\overrightarrow{\rm \Omega} = \omega \overrightarrow{\rm u}$.

> Pour tout point $O$ quelconque appartenant à l'axe $\Delta$,
> $\overrightarrow{\rm v_i} = \overrightarrow{\rm \Omega} \wedge \overrightarrow{\rm O M_i}$.

### Moment cinétique d'un solide
> Soit un point $O$ quelconque de l'espace, le moment cinétique de $\Sigma$ par
> rapport à $O$ est la somme des moments cinétiques de chacun des points.

On a ainsi $\overrightarrow{\rm \sigma_O} = \sum\limits_{i} \overrightarrow{\rm \sigma_O}(M_i) = \sum\limits_{i} \overrightarrow{\rm OM_i} \wedge m_i \overrightarrow{\rm v_i}$.
On peut à nouveau utiliser la relation de Chasles pour changer de point :
$\overrightarrow{\rm \sigma_O}(\Sigma) = \overrightarrow{\rm OG} \wedge \sum\limits_{i} m_i \overrightarrow{\rm v_i} + \overrightarrow{\rm \sigma_G}(\Sigma)$.

## Dynamique d'un solide
### Forces s'exerçant sur un solide
> Soit un référentiel galiléen, avec $O$ un point fixe, $M_i$ un point
> quelconque de $\Sigma$ subit :
> - la résultante des force extérieures (poids, forces de contact ...) $\overrightarrow{\rm F_{\text{ext}} \to i}$
> - la résultante des forces intérieures notée $\sum\limits_{j \neq i} \overrightarrow{\rm F_{j \to i}}$

> On a toujours les relations dans les forces intérieures, pour tout $i$ et $j$ :
> - $\overrightarrow{\rm F_{i \to j}} = - \overrightarrow{\rm F_{j \to i}}$
> - $\overrightarrow{\rm M_i M_j} \wedge \overrightarrow{\rm F_{i \to j}} = \overrightarrow{\rm 0}$

### Théorème de la résultante dynamique
$m_\text{tot} \overrightarrow{\rm v_G} = \sum\limits_{i} m_i \overrightarrow{\rm v_i}$,
donc $m_\text{tot} \frac{d \overrightarrow{\rm v_G}}{dt} = \sum\limits_{i} m_i \frac{d \overrightarrow{\rm v_i}}{dt}$.
D'après le principe fondamental appliqué au point $M_i$,
$m_i \frac{d \overrightarrow{\rm v_i}}{dt} = \overrightarrow{\rm F_{\text{ext} \to i}} + \sum\limits_{j \neq i} \overrightarrow{\rm F_{j \to i}}$,
donc $m_i \frac{d \overrightarrow{\rm v_i}}{dt} = \sum \overrightarrow{\rm F_{\text{ext} \to i}} + \sum\limits_{i} \sum\limits_{j \neq i} \overrightarrow{\rm F_{j \to i}}$.
Ce second membre est nul, car les forces de point à point s'annulent deux à
deux.

> Théorème de la résultante dynamique : $m_\text{tot} \frac{d \overrightarrow{\rm v_G}}{dt} = \sum \overrightarrow{\rm F_{\text{ext} \to i}}$.

### Théorème du moment cinétique pour un solide
#### Énoncé
> Théorème du moment cinétique pour un solide : $\frac{d \overrightarrow{\rm \sigma_O}(\Sigma)}{dt} = \sum\limits_{i} \mathcal{M}_O (\overrightarrow{\rm F_{\text{ext} \to i}})$.

Dans cette formule, $\overrightarrow{\rm \mathcal{M}_O}(\overrightarrow{\rm F_{\text{ext} \to i}}) = \overrightarrow{\rm OM_i} \wedge \overrightarrow{\rm F_{\text{ext} \to i}}$.

#### Notion d'action mécanique (torseur)
On appelle action mécanique ou torseur exercé sur un solide l'ensemble
$\left\{\begin{matrix} \sum\limits_{i} \overrightarrow{\rm F_{\text{ext} \to i}} \\ \sum\limits_{i} \overrightarrow{\rm \mathcal{M_O}}(\overrightarrow{\rm F_{\text{ext} \to i}}) \end{matrix}\right\}$.

Par exemple, on peut considérer uniquement le poids, et on a alors :
- $\sum\limits_{i} \overrightarrow{\rm F_{\text{ext} \to i}} = \sum\limits_{i} m_i \overrightarrow{\rm g} = m_\text{tot} \overrightarrow{\rm g}$
- $\sum\limits_{i} \overrightarrow{\rm \mathcal{M_O}}(\overrightarrow{\rm F_{\text{ext} \to i}}) = \sum m_i \overrightarrow{\rm OM_i} \wedge \overrightarrow{\rm g} = m_\text{tot} \overrightarrow{\rm OG} \wedge \overrightarrow{\rm g}$

L'action mécanique du poids sur un solide est donc :
$\left\{\begin{matrix} m_\text{tot} \overrightarrow{\rm g} \\ m_\text{tot} \overrightarrow{\rm OG} \wedge \overrightarrow{\rm g} \end{matrix}\right\}$.

### Théorème du moment cinétique scalaire
Soit un axe orienté $\Delta$ selon $\overrightarrow{\rm u}$ et passant par $O$.

> On a le moment cinétique de $\Sigma$ par rapport à l'axe
> $\sigma_\Delta(\Sigma) = \overrightarrow{\rm \sigma_\Delta}(O) \cdot \overrightarrow{\rm }$.

> On a le moment des forces extérieures par rapport à l'axe
> $\mathcal{M}_\Delta(\text{ext}) = \overrightarrow{\rm \mathcal{M}_O}(\text{ext}) \cdot \overrightarrow{\rm u}$.

> Théorème du moment cinétique scalaire :
> $\frac{d \sigma_\Delta}{dt} = \mathcal{M}_\Delta(\text{ext}) = \sum\limits_{i} \mathcal{M}_\Delta(\overrightarrow{\rm F_{\text{ext} \to i}})$.

## Solide en rotation autour d'un axe fixe
Soit un solide en rotation par rapport à $\overrightarrow{\rm u}$ et passant par $O$.

### Notion de couple
On parle de couple lorsqu'on obtient un torseur de la forme
$\left\{\begin{matrix} \overrightarrow{\rm 0} \\ \sum\limits_{i} \overrightarrow{\rm \mathcal{M}_O}(\overrightarrow{\rm F_{\text{ext} \to i}}) \end{matrix}\right\}$.

> Le moment d'un couple ne dépend pas du point de référence : on note alors
> $\overrightarrow{\rm \mathcal{M_O}}(\text{ext}) = \overrightarrow{\rm \mathcal{M}}(\text{ext})$.

> Une liaison pivot parfaite/idéale permet la rotation d'un objet uniquement selon
> un axe $\Delta$, et exerce sur le solide un moment nul.

### Expression du moment cinétique
Pour un objet en mouvement autour d'un axe, on calcule le moment d'inertie :
$\overrightarrow{\rm \sigma_O}(\Sigma) = \sum\limits_{i} \overrightarrow{\rm OM_i} \wedge m_i \overrightarrow{\rm v_i}$\
$= \sum\limits_{i} (\overrightarrow{\rm OH_i} + \overrightarrow{\rm H_i M_i}) \wedge (m_i r_i \omega \overrightarrow{\rm u_{\theta_i}})$\
$= \sum\limits_{i} (z_i \overrightarrow{\rm u_z} + r_i \overrightarrow{\rm u_r}) \wedge (m_i r_i \omega \overrightarrow{\rm u_{\theta_i}})$\
$= \sum\limits_{i} m_i r_i^2 \omega \overrightarrow{\rm u_z} - \sum\limits_{i} m_i r_i z_i \omega \overrightarrow{\rm u_{r_i}}$\
On obtient ainsi le moment d'inertie autour de l'axe $\sigma_\Delta(\Sigma) = \overrightarrow{\rm \sigma_O}(\Sigma) \cdot \overrightarrow{\rm u_z}$
$= \sum\limits_{i} m_i r_i^2 \omega$. On le note parfois $J_{\Delta}$, qui est
une grandeur en $\text{kg} \cdot \text{m}^2$. (Voir l'expérience d'une personne
qui tourne sur une chaise, en éloignant ou rapprochant des haltères de son
corps, le faisant plus ou moins tourner vite dû à la répartition de la masse,
augmentant ou baissant le moment).

En sciences de l'ingénieur ou dans d'autres modèles d'étude, on calculerait
cette grandeur par une triple intégrale (sur l'espace, donnant un volume).

### Expression du théorème du moment cinétique
$\frac{d \sigma_\Delta(\Sigma)}{dt} = \mathcal{M}_\Delta(\text{ext})$, or
$\sigma_\Delta(\Sigma) = J_\Delta \omega$.
Donc $J_\Delta \ddot{\theta} = \mathcal{M}_\Delta(\text{ext})$.

> Théorème du moment cinétique pour un solide en rotation :
> $J_\Delta \ddot{\theta} = \mathcal{M}_\Delta(\text{ext}) = \sum\limits_{i} \mathcal{M}_\Delta(\overrightarrow{\rm F_{\text{ext} \to i}})$.

#### Poulie idéale
On se place dans le cas d'une poulie idéale, d'axe central $\Delta$, soumise à
son poids, à la tension du fil vers l'avant et l'arrière de la poulie, et à la
réaction au contact de la poulie.

Bilan des actions mécaniques (BAM) :
- On obtient la résultante des forces : $\overrightarrow{\rm P} = m_\text{tot} \overrightarrow{\rm g}$
- $\overrightarrow{\rm \mathcal{M}_\Delta}(\overrightarrow{\rm P}) = \overrightarrow{\rm 0}$ (le bras de levier est nul, l'axe est orthogonal au mouvement de la corde)
- La tension $\overrightarrow{\rm T_1}$ sur le fil à droite donne une résultant
  $\overrightarrow{\rm T_1}$, et $\overrightarrow{\rm \mathcal{M}_\Delta}(\overrightarrow{\rm T_1}) = - R \lVert \overrightarrow{\rm T_1} \rVert$.
- La tension $\overrightarrow{\rm T_2}$ sur le fil à droite donne une résultant
  $\overrightarrow{\rm T_2}$, et $\overrightarrow{\rm \mathcal{M}_\Delta}(\overrightarrow{\rm T_2}) = R \lVert \overrightarrow{\rm T_2} \rVert$.
- La réaction du support donne une résultante de $\overrightarrow{\rm R}$ et un
  moment nul.

D'après le théorème de la résultante dynamique, à l'équilibre,
$\overrightarrow{\rm P} + \overrightarrow{\rm T_1} + \overrightarrow{\rm T_2} + \overrightarrow{\rm R} = 0$.
D'après le théorème de la résultante, $J_\Delta \ddot{\theta} = 0 = 0 - R \lVert \overrightarrow{\rm T_1} \rVert + R \lVert \overrightarrow{\rm T_2} \rVert$,
donnant $\lVert \overrightarrow{\rm T_1} \rVert = \lVert \overrightarrow{\rm T_2} \rVert$.

Ainsi, une poulie parfaite transmet parfaitement les efforts.

#### Levier d'Archimède
> Donnez moi un point fixe et un levier, et je soulèverai le monde.
> Archimède, -287 - -212 avant J.C

On cherche à déterminer le levier nécessaire à soulever la tour Eiffel : on
prend un bonhomme de masse $m_1 = 100 \text{kg}$ à une distance $d_1$ du point
d'appui et la tour Eiffel de masse $m_2 = 1 \times 10^{7} \text{kg}$ à
une distance $d_2$ du point d'appui.
- La liaison est parfaite et donc de moment nul
- $\mathcal{M}_\Delta(\text{bonhomme}) = d_1 m_1 g$
- $\mathcal{M}_\Delta(\text{tour}) = d_2 m_2 g$

D'après le théorème du moment cinétique par rapport à $\Delta$ à l'équilibre,
$J_\Delta \ddot{\theta} = 0 = d_1 m_1 g - d_2 m_2 g$
$\Leftrightarrow \frac{d_1}{d_2} = \frac{m_2}{m_1}$.

### Aspect énergétique
$J_\Delta \ddot{\theta} = \mathcal{M}_\Delta(\text{ext})$\
$J_\Delta \ddot{\theta} \dot{\theta} = \sum\limits_{i} \mathcal{M}_\Delta(\overrightarrow{\rm F_{\text{ext} \to i}}) \dot{\theta}$\
$\frac{d}{dt} [\frac{1}{2} J_\Delta \dot{\theta}^2] = \sum\limits_{i} \mathcal{M}_\Delta(\overrightarrow{\rm F_{\text{ext} \to i}}) \dot{\theta}$\

#### Énergie cinétique d'un solide en rotation
> L'énergie cinétique du solide est la somme de l'énergie cinétique de chacun de
> ses points : $E_C(\Sigma) = \sum\limits_{i}  \frac{1}{2} m_i \lVert \overrightarrow{\rm v_i} \rVert^2$.

Pour un mouvement de rotation, $\lVert \overrightarrow{\rm v_i} \rVert = r_i |\omega|$,
donc $E_C(\Sigma) = \sum\limits_{i}  \frac{1}{2} m_i r_i^2 \omega^2$.

> $E_C(\Sigma) = \frac{1}{2} J_\Delta \dot{\theta}^2$

#### Puissance des farces extérieures
$P_i = \overrightarrow{\rm F_{\text{ext} \to i}} \cdot \overrightarrow{\rm v_i}$\
$= r_i \dot{\theta} (\overrightarrow{\rm F_{\text{ext} \to i}} \cdot \overrightarrow{\rm u_{\theta_i}})$\
$\mathcal{M}_\Delta(\overrightarrow{\rm F_{\text{ext} \to i}}) = \overrightarrow{\rm OM} \wedge \overrightarrow{\rm F_{\text{ext} \to i}}$\
$= r_i (\overrightarrow{\rm F_{\text{ext} \to i}} \cdot \overrightarrow{\rm u_{\theta_i}})$\
Ainsi, $P_i = \mathcal{M}_\Delta(\overrightarrow{\rm F_{\text{ext} \to i}}) \dot{\theta}$,
et $P_\text{ext} = \sum\limits_{i} P_i = \sum\limits_{i} \mathcal{M}_\Delta(\overrightarrow{\rm F_{\text{ext} \to i}) \dot{\theta}$
$= \mathcal{M}_\Delta(\text{ext}) \dot{\theta}$.

#### Bilan
> Théorème de l'énergie cinétique pour un solide en rotation :
> $\frac{d}{dt} [E_C(\Sigma)] = \mathcal{M}_\Delta(\text{ext}) \dot{\theta}$
> et $E_C(\Sigma) = \frac{1}{2} J_\Delta \dot{\theta}^2$.

### Exemple : le pendule pesant (à savoir refaire)
BAM :
- liaison pivot parfaite de moment nul
- $\mathcal{M}_\Delta(\overrightarrow{\rm P}) = - m_\text{tot} g \ell \sin \theta$

D'après le théorème du moment cinétique par rapport à l'axe $\Delta$ :
$J_\Delta \ddot{\theta} = - m_\text{tot} g \ell \sin \theta$
$\Leftrightarrow \ddot{\theta} + \omega_0^2 \sin \theta = 0$
où $\omega = \sqrt{\frac{m_\text{tot} g \ell}{J_\Delta}}$.

Dans le cas d'un pendule simple, $J_\Delta = \sum\limits_{i} m_i r_i^2 = m_\text{tot} \ell^2$,
donc $\omega = \sqrt{\frac{g}{\ell}}$.

On finalise avec une étude énergétique, donnant $\frac{d}{dt} [\frac{1}{2} J_\Delta \dot{\theta}^2]$
$= \frac{d E_C}{dt} = \frac{d}{dt} [m_\text{tot} g \ell \cos \theta]$.
Ce second membre est identifié à l'énergie potentielle à une constante près,
car l'énergie mécanique est conservée.

On recherche donc les points d'équilibre et leurs stabilités :
$\frac{d E_p}{d \theta} = m g \ell \sin \theta$ et $\frac{d^2 E_p}{d \theta^2} = m g \ell \cos \theta$.
Ainsi, le système est à l'équilibre pour $\theta_\text{éq} = n \pi$,
avec un équilibre stable pour tout $\theta_\text{éq} \equiv 0 [2\pi]$
et est instable pour tout $\theta_\text{éq} \equiv \pi [2\pi]$.
