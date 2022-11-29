# Phénomènes ondulatoires
## Définitions
### Mise en évidence expérimentale
__Vidéo :__ Chercher "Cuve à ondes"

> Lorsqu'une onde incidente rencontre une ouverture dont la taille est de l'ordre
> de sa longueur d'onde, il se produit un étalement de l'onde après l'ouverture.

Selon la taille de l'ouverture, un cône de diffraction d'un angle $\theta$
différent se forme.

### Caractérisations de la diffraction
> Le phénomène de diffraction apparaît pour tout type d'onde (sonore,
> électromagnétique, rayon d'électrons en mécanique quantique).

Le demi-angle $\theta$ est donné par la relation $\sin(\theta) = \frac{\lambda}{a}$,
avec $a$ la taille de l'ouverture.

##### Exemple : diffraction par un LASER rouge
On envoie un faisceau LASER sur un petit trou, et on obtient l'image du LASER
sur un écran en face de ce trou. On obtient en face du trou une grande tache de
largeur $L$, et on a la relation $\tan \theta = \frac{\frac{L}{2}}{D}$. Or,
$\theta \ll 1, \tan \theta \approx \sin \theta \approx \theta$.
Ainsi, $\frac{\lambda}{a} = \frac{L}{2D} \Leftrightarrow a = \frac{2\lambda D}{L}$.

### Théorème de Babinet
> Le phénomène de diffraction est le même pour une fente de largeur $a$ et un
> obstacle de largeur $a$.

## Interférence entre deux sources synchrones
### Mise en évidence expérimentale
Voir la vidéo sur la cuve à ondes.

> Deux sources synchrones sont des sources vibrant à la même fréquence.

Une autre condition pour obtenir l'interférence est celle d'un déphasage
constant (condition de cohérence).

__Exemple :__ Cuve à ondes à plusieurs sources et plusieurs obstacles
- Chaque source produit une onde circulaire à la surface de l'eau
- Les ondes se superposent
- En certains points, les vagues semblent plus faibles ou plus fortes

### Conditions d'interférences constructives et destructives
#### Forme générale d'une onde progressive sinusoïdale
> Une onde monochromatique émise par un point $S$ avec une phase à l'origine
> $\varphi_0$ est de la forme $s(x,t) = A \cos(\omega t -k SM + \varphi_0)$
> (avec $SM$ la distance entre $S$ et un point dans l'espace).

La phase d'une onde sinusoïdale issue du point $S$ au point $M$ est de la forme
$\Phi(M,t) = \frac{2\pi}{T} t - 2\pi \frac{SM}{\lambda} + \varphi_0$.

#### Superposition de deux ondes sinusoïdales de même amplitude
> Soient deux ondes progressives sinusoïdales issues de sources synchrones $S_1$
> et $S_2$, et se rencontrant en un point $M$, on a les formules :\
> $\left\{\begin{matrix} s_1(M,t) = A \cos(\omega t - k S_1 M + \varphi_1) = A \cos(\Phi_1(M,t)) \\ s_2(M,t) = A \cos(\omega t - k S_2 M + \varphi_2) = A \cos(\Phi_2(M,t)) \end{matrix}\right.$\
> On pose donc la formule de l'onde totale :\
> $s_\text{tot}(M,t) = 2A \cos(\omega t, \frac{\Phi_1 + \Phi_2}{2}) \cos(\frac{\Phi_1 - \Phi_2}{2})$\
> $= 2A \cos(\frac{\Delta \varphi}{2}) \cos(\frac{\Phi_1 + \Phi_2}{2})$

L'onde résultante de deux ondes progressives sinusoïdales déphasées de $\Delta \Phi(M)$
est d'amplitude $M = 2A |\cos(\frac{\Delta\varphi(M)}{2})|$.

#### Superposition de deux ondes sinusoïdales d'amplitudes différentes
$s_1(M,t) = A_1 \cos(\omega t - k S_1 M + \varphi_1) = A_1 \cos(\Phi_1(M,t))$\
$s_2(M,t) = A_2 \cos(\omega t - k S_2 M + \varphi_2) = A_2 \cos(\Phi_2(M,t))$\
$s(M,t) = s_1(M,t) + s_2(M,t)$

On utilise la notation complexe, en soulignant les variables complexes.
$\underline{s}(M,t) = A_1 e^{i \Phi_1(M,t)} + A_2 e^{i \Phi_2(M,t)}$\
$= A_\text{tot} e^{i \Phi(M,t)}$\
On pose $\Delta\Phi(M,t) = \Phi_2(M,t) - \Phi_1(M,t)$, et on a
$A_\text{tot}(M,t)^2 = |\underline{s}(M,t)|^2$\
$= |A_1 e^{i \Phi_1(M,t)} + A_2 e^{i \Phi_2(M,t)}|^2$\
$= A_1^2 |1 + \frac{A_2}{A_1} e^{i \Delta\Phi(M,t)}|^2$\
$= A_1^2 (1 + \frac{A_2}{A_1} e^{i \Delta\Phi(M,t)}) (1 + \frac{A_2}{A_1} e^{-i \Delta\Phi(M,t)})$\
$= A_1^2 + A_2^2 + A_2 A_1 (e^{i \Delta\Phi(M,t)} + e^{- i \Delta\Phi(M,t)})$\
$= A_1^2 + A_2^2 + A_2 A_1 2 \cos(\Delta\Phi(M,t))$

#### Bilan (cas d'amplitudes égales)
##### Interférences constructives
Lorsque l'amplitude est maximale, on parle d'interférence constructive :
$\cos(\frac{\Delta \Phi}{2}) = \pm 1$, soit $\Delta\Phi = 2n\pi$ avec $n \in \mathbb{Z}$.
