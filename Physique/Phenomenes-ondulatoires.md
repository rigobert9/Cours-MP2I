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

##### Interférence destructives
Dans le cas des interférences destructives, on a des signaux en opposition de
phase : $\cos(\frac{\Delta \Phi}{2}) = 0 \Leftrightarrow \Delta \Phi = \pi + 2n \pi, n \in \mathbb{Z}$.

Ainsi, l'"addition" des deux signaux est un signal nul.

### Différence de marche $\delta$
> On appelle différence de marche $\delta$ la différence des distances parcourues
> par les deux ondes depuis un ou des endroits où elles sont en phase.
> On a donc la relation $\Delta \Phi = k \delta = \frac{2 Gp}{\lambda}\delta$.

- Si $\delta = 0 + n \lambda = n\lambda$, alors les interférences sont constructives et les
  ondes sont en phase.
- Si $\delta = \frac{\lambda}{2} + n \lambda = (n + \frac{1}{2}) \lambda$, alors les interférences sont
  destructives et les ondes sont en opposition de phase.

## Cas des ondes lumineuses
### Que voit-on quand on regarde la lumière ?
Nos yeux ne réagissent qu'à la charge énergétique de la lumière (son intensité
lumineuse, correspondant à l'énergie portée par un photon). La majorité de nos
détecteurs sont quadratiques, c'est-à-dire qu'ils mesurent la moyenne du carré
du signal. Physiquement, cela revient à dire que les détecteurs sont sensibles à
une grandeur énergétique.

La grandeur énergétique pour notre perception de la lumière, l'intensité
lumineuse, correspond à $I(M,t) = \alpha <\Delta(M,t)^2>$
$= \alpha A^2 <\cos^2(\omega t - k SM + \varphi)> = \alpha \frac{A^2}{2}$, avec
$\alpha$ un coefficient expérimental qui dépend de l'onde et du capteur.

On définit la moyenne d'une fonction du temps $s(t)$ comme la valeur
$<s(t)> = \frac{1}{T} \int\limits_{t_0}^{t_0 + T} s^2(t) dt$.

### Interférences et intensité lumineuse
Soit $s_1(M,t) = A_1 \cos(\Phi_1(M,t)) \to I_1 = \frac{\alpha A_1^2}{2}$
et $s_2(M,t) = A_2 \cos(\Phi_2(M,t)) \to I_2 = \frac{\alpha A_2^2}{2}$.
On a ainsi $\cos^2(\omega t + \varphi) = \frac{1}{2} (1 + \cos(2 \omega t + 2 \varphi))$,
et enfin $<\cos^2(\omega t + \varphi)> = \frac{1}{2} + <\frac{\cos(2 \omega t + 2 \varphi)}{2}>$,
avec $<\frac{\cos(2 \omega t + 2 \varphi)}{2}> = 0$.

D'après la formule de Fresnel, $I(M) = I_1(M) + I_2(M) + 2 \sqrt{I_1(M) I_2(M)} \cos(\Delta\Phi(M))$.
Si $I_1 = I_2 = I_0$, alors $I(M)=  2 I_0 [1 + \cos(\Delta\Phi(M))]$.

### Chemin optique
Dans un milieu homogène d'indice optique $n$, le chemin optique $L_{AB}$, aussi
noté $(AB)$ entre deux points $A$ et $B$ est de valeur $n \cdot AB$.

$\Delta \Phi(M) = \frac{2 \pi}{\lambda} (S_2 M - S_1 M)$ pour deux sources $S_1$
et $S_2$ éclairante un point $M$. Or, $\lambda = \frac{\Lambda_0}{n}$, donc
$\Delta \Phi(M) = 2\pi \frac{n (S_2 M - S_1 M)}{\lambda_0} = \frac{2\pi}{\lambda_0} [(S_2 M) - (S_1 M)]$.

> En optique ondulatoire, la différence de marche correspond à la différence de
> chemin optique, soit $\Delta \Phi = 2\pi \frac{\delta}{\lambda_0}$.

### Expérience des trous de Young
On a dans ce schéma les points $S(0,0,-d)$, $S_1(0,\frac{a}{2},0)$, $S_2(0, \frac{-a}{2})$, $M(x,y,D)$.
On fait aussi les hypothèses que $a \approx 1 \text{mm}$, $|x| \approx |y| \approx 1 \text{cm}$,
$d \approx D \approx 1 \text{m}$. Ainsi, $a, |x|, |y| \ll d, D$.

> Le champ d'interférence correspond à la zone où les ondes issues de $S_1$ et de
> $S_2$ se recouvrent.

La différence de marche $\delta$ se calcule à partir de $S = (S_2 M) - (S_1 M)$,
qu'on obtient avec les relations $S_1 M = \sqrt{(y - \frac{a}{2})^2 + x^2 + D^2}$
et $S_2 M = \sqrt{(y - \frac{a}{2})^2 + x^2 + D^2}$. Pour un $\varepsilon \ll 1$,
$(1 + \varepsilon)^n \approx 1 + n \varepsilon$ (développement limité).
Ainsi, on a $S_1 M = D \sqrt{1 + (\frac{x}{D})^2 + (\frac{y}{D} - \frac{a}{2D})^2}$
$\approx D [1 + \frac{1}{2} (\frac{x}{D})^2 + \frac{1}{2} (\frac{y}{D} - \frac{a}{2D})^2]$
$= D [1 + \frac{1}{2} (\frac{x}{D})^2 + \frac{1}{2} (\frac{y}{D})^2  + \frac{1}{2} (\frac{a}{2D})^2 - \frac{ay}{D^2}]$
$= D + \frac{D}{2} [(\frac{x}{D})^2 + (\frac{y}{D})^2  + (\frac{a}{2D})^2] - \frac{ay}{2D}$.
De même,
$S_2 M \approx D + \frac{D}{2} [(\frac{x}{D})^2 + (\frac{y}{D})^2  + (\frac{a}{2D})^2] + \frac{ay}{2D}$.

On en déduit enfin la différence de marche $\delta = (S_2 M) - (S_1 M) = \frac{ay}{D}$,
puis le déphasage $\Delta \Phi(M) = \frac{2\pi}{\lambda_0} \frac{ay}{D}$,
en l'intensité lumineuse $I(y) = 2 I_0 [1 + \cos(\frac{2\pi}{\lambda_0} \frac{ay}{D})]$.

> Une frange d'interférence correspond à l'ensemble des points de même déphasage :
> - Si $\Delta\Phi = 0$, alors on a une frange brillante
> - Si $\Delta\Phi = \pi$, alors on a une frange sombre

> L'interfrange est la distance entre deux franges brillantes ou deux franges sombres.

Puisque l'interfrange correspond à $i = y_{n + 1} - y_n$, et qu'on a
$\frac{a y_n}{\lambda_0 D} = n$ et $\frac{a y_{n+1}}{\lambda_0 D} = n + 1$
$\Rightarrow y_n = n \frac{\lambda_0 D}{a}$ et $y_{n + 1} = (n + 1) \frac{\lambda_0 D}{a}$.
L'interfrange a donc une valeur de $i = \frac{\lambda_0 D}{a}$.
