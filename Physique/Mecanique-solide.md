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
