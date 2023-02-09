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
