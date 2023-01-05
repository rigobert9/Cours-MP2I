# Régime sinusoïdal forcé
## Exemples illustratifs
### Système du premier ordre : circuit RC
Dans un circuit RC, avec un GBF délivrant une tension sinusoïdale de pulsation
$\omega$, représentée par la fonction $e(t) = E_m \cos(\omega t)$.

> La pulsation $\omega$ est appelée pulsation de forçage

Ici, cette pulsation est imposée par le GBF. D'après la loi des mailles,
$RC \frac{d u(t)}{dt} + u(t) = E_m \cos(\omega t)$
$\Leftrightarrow \frac{d u(t)}{dt} + \frac{u(t)}{\tau} = \frac{E_m}{\tau}$
avec $\tau = RC$.
La solution de l'équation homogène est $u_{SH}(t) = A e^{\frac{-t}{\tau}}$,
la solution particulière est $u_{SP}(t) = U_m \cos(\omega t + \Phi)$,
donnant la solution globale $u(t) = A e^{\frac{-t}{\tau}} + U_m \cos(\omega t + \Phi)$.

### Système du deuxième ordre : exemple mécanique
On prend l'exemple d'un ressort horizontal sur un object associé à un point
matériel, soumis à la réaction du support sur lequel il est posé, la pesanteur,
la force élastique du ressort et le frottement du support.

En utilisant le PFD, on obtient $m \ddot{x}(t) = -k [x(t) - x_A(t) - \ell_0] - \lambda \dot{x}(t)$.
On pose $y(t) = x(t) - \ell_0$, et on a $m \ddot{y} + \lambda \dot{y} + kg = k x_A(t)$.
Sous forme canonique, on pose $\ddot{y} + \frac{\omega_0}{Q} \dot{y} + \omega_0^2 y = \omega_0^2 A_m \cos(\omega t)$,
avec $\omega_0 = \sqrt{\frac{k}{m}}$ et $Q = \frac{\sqrt{km}}{\lambda}$.

La solution homogène est, selon $Q$ :
- si $Q < \frac{1}{2}$, régime apériodique, $y_{SH}(t) = A e^{r_1 t} + B e^{r_2 t}$
- si $Q = \frac{1}{2}$, $y_{SH}(t) = (A + Bt) e^{\frac{-\omega_0}{2Q} t}$
- si $Q > \frac{1}{2}$, $y_{SH} = [A \cos(\Omega t) + B \sin(\Omega t)] e^{\frac{-\omega_0}{2Q} t}$,
  avec $\Omega = \omega_0 \sqrt{1 - \frac{1}{4Q^2}}$.

La solution particulière est $y_{SP} = y_m \cos(\omega t + \varphi)$, et la
solution finale est la somme de ces deux solutions.

### Le régime sinusoïdal forcé
> Le régime sinusoïdal forcé correspond au régime atteint après le régime
> transitoire d'un système physique soumis à une excitation sinusoïdale. On parle
> de régime établi.

On modélise ce modèle sous la forme d'une entrée $e(t)$, une excitation en
entrée, passant dans le système $\Sigma$, qui donne $s(t)$, un signal d'intérêt
en sortie.

> Un système physique qui lie une entrée $e(t)$ à une sortie $s(t)$ est dit
> linéaire et invariant temporel si les deux grandeur sont liées par une équation
> différentielle linéaire à coefficients constants. Ce sera le cas qu'on
> observera.

#### Propriétés
- Si $e(t) \xrightarrow{\Sigma} s(t)$ alors pour tout réel ou complexe k,
  $k e(t) \xrightarrow{\Sigma} k s(t)$.
- Si $e_1(t)  \xrightarrow{\Sigma} s_1(t)$ et $e_2(t)  \xrightarrow{\Sigma} s_2(t)$,
  alors $e_1(t) + e_2(t)  \xrightarrow{\Sigma} s_1(t) + s_2(t)$.
- Si $e(t)  \xrightarrow{\Sigma} s(t)$, alors pour tout $T$ réel,
  $e(t + T)  \xrightarrow{\Sigma} s(t + T)$.
- Si l'entrée $e(t)$ est de la forme $e(t) = E_m \cos(\omega t)$,
  alors en régime établi la sortie est de la forme
  $s(t) = S_m \Phi(\omega)$, avec $\Phi(\omega)$
  dépendant de la pulsation de forçage.

## La rotation complexe pour l'étude du régime sinusoïdal forcé
### Brefs rappels sur les nombres complexes
$z = a + jb$, avec $j^2 = -1$, et on note $a = \Re(z)$ et $b = \Im(z)$.
On peut noter $z = |z| e^{j \Phi}$, avec $\Phi = \text{arg}(z)$.
On note le conjugué $\overline{z} = a - jb$.

### Représentation complexe d'un signal sinusoïdal
À tout signal sinusoïdal $s(t) = S_m \cos(\omega t + \Phi)$,
on associe le signal complexe $\underline{s}(t) = S_m e^{j(\omega t + \Phi)}$

Si $e(t)  \xrightarrow{\Sigma} s(t)$, alors $\overline{e(t)}$
et $\overline{s(t)}$ sont liés par la même équation différentielle.

> Pour tout signal complexe $\underline{s}(t)$ de la forme
> $\underline{s}(t) = S_m e^{j(\omega t + \Phi)}$ avec $S_m > 0$,
> on note $\underline{S_m} = S_m e^{j \Phi}$.

### Dérivation et intégration en notation complexe
$\underline{u}(t) = U_m e^{j(\omega t + \Phi)} = \underline{U_m} e^{j \omega t}$

Voir cours de mathématiques.

### Circuit électrique du 1er ordre
Dans un circuit RC, $\tau \frac{d u(t)}{dt} + u(t) = e(t)$
où $e(t) = E_m \cos(\omega t)$ et $\tau = RC$. On cherche $s(t) = S_m \cos(\omega t + \Phi)$.
En notation complexe $\underline{e}(t) = E_m e^{j \omega t}$ et
$\underline{s}(t) = S_m e^{j \Phi} e^{j \omega t}$. Ainsi,
$\tau \frac{d \underline{u}(t)}{dt} + \underline{u}(t) = \underline{e}(t)$, soit
$j \omega \tau \underline{u}(t) + \underline{u}(t) = \underline{e}(t)$\
$\Leftrightarrow (1 + j \omega \tau) \underline{u}(t) = \underline{e}(t)$\
$\Leftrightarrow (1 + j \omega \tau) U_m e^{j \Phi} = E_m$\
On a donc $\underline{U_m} = \frac{E_m}{1 + j \omega \tau}$, donc
$U_m = |U_m| = \frac{E_m}{\sqrt{1 + (\omega \tau)^2}}$,
et $\Phi = \text{arg}(\underline{U_m})$.

## Impédence complexe
### Définition
> En physique, deux grandeurs variables sont dites conjuguées si leur produit est
> homogène à une énergie ou à une puissance.

Par exemple, la tension et l'intensité ou la pression et le volume sont des
grandeur conjuguées.

> Une impédence est le rapport entre deux grandeurs conjuguées.

> En électricité, en régime sinusoïdal forcé, l'impédence d'un dipôle linéaire
> est, en convention récepteur, $\underline{z}_D = \frac{\underline{u}}{\underline{i}}$
> $\Leftrightarrow \underline{u} = \underline{z}_D \underline{i}$.

### Impédence de dipôles usuels
#### Résistance
D'après la loi d'Ohm, $u(t) = R i(t)$, donc
$\underline{u}(t) = R \underline{i}(t)$, soit $\underline{z}_R = R$.

#### Condensateur
D'après la relation constituante du condensateur $i(t) = C \frac{d u(t)}{dt}$,
soit $\underline{i} = j C \omega \underline{u} \Leftrightarrow \underline{u} = \frac{1}{j C \omega} \underline{i}$.
Ainsi, $\underline{z}_C = \frac{1}{j C \omega}$.
- En régime de très basse fréquence, lorsque $\omega = 2 \pi f \to 0$, $\underline{z}_C \to +\infty$
  (condensateur équivalent à un interrupteur ouvert).
- En régime de très haute fréquence, $\omega \to +\infty$, $\underline{z}_C \to 0$
  (condensateur équivalent à un fil)

#### Bobine
En convention récepteur, $\underline{z}_L = j L \omega$.
- En régime de très basse fréquence, lorsque $\omega = 2 \pi f \to 0$, $\underline{z}_L \to 0$
  (bobine équivalente à un fil).
- En régime de très haute fréquence, $\omega \to +\infty$, $\underline{z}_L \to +\infty$
  (bobine équivalente à un interrupteur ouvert)

#### Admitance
> L'admitance d'un dipôle linéaire est définie comme $\underline{y}_D = \frac{1}{\underline{z}_D}$

#### Bilan
> En régime sinusoïdal forcé, $\underline{u} = \underline{z}_D \underline{i}$.

Dipôle linéaire | Impédence
---             | ---
Résistance      | $\underline{z}_R = R$
Condensateur    | $\underline{z}_C = \frac{1}{j C \omega}$
Bobine          | $\underline{z}_L = j L \omega$

### En mécanique
Équivalence                     | Système    | Impédence
---                             | ---        | ---
$\frac{1}{C} \Leftrightarrow k$ | Ressort    | $\underline{z}_\text{ressort} = \frac{k}{j \omega}$
$L \Leftrightarrow m$           | Masse      | $\underline{z}_\text{masse} = j m \omega$
$R \Leftrightarrow \lambda$     | Frottement | $\underline{z}_\text{frottement} = \lambda$

### Association d'impédence en régime sinusoïdal forcé
#### Loi de Kirchhoff
ARQS : $f = \frac{\omega}{2 \pi} \ll \frac{C}{L_\text{circuit}}$

Dans le cadre de l'ARQS, les lois de Kirchhoff restent valables en régime
sinusoïdal forcé, à savoir la loi des nœuds et la loi des mailles.

#### Association en série
> En série, les impédences de dipôles s'ajoutent.

En effet, $\underline{u} = \underline{u}_1 + \underline{u}_2$,
$\underline{u}_1 = \underline{z}_1 \underline{i}$ et
$\underline{u}_2 = \underline{z}_2 \underline{i}$, soit
$\underline{u} = (\underline{z}_1 + \underline{z}_2) \underline{i} = \underline{z}_\text{éq} \underline{i}$.

#### Association en dérivation
D'après la loi des nœuds, dans un circuit en dérivation, $\underline{i} = \underline{i}_1 + \underline{i}_2$.
$\underline{i}_1 = \underline{y}_1 \underline{u}$ et
$\underline{i}_2 = \underline{y}_2 \underline{u}$, soit
$\underline{i} = (\underline{y}_1 + \underline{y}_2) \underline{u}$.

> En dérivation, les admitances des dipôles s'ajoutent.

#### Pont diviseur de tension
Dans un pont diviseur de tension, les impédences des dipôles donnent les
formules $\underline{u}_1 = \frac{\underline{z}_1}{\underline{z}_1 + \underline{z}_2}$
et $\underline{u}_2 = \frac{\underline{z}_2}{\underline{z}_1 + \underline{z}_2}$

#### Pont diviseur de courant
Dans un pont diviseur de courant, les admitances des dipôles donnent les
formules $\underline{i}_1 = \frac{\underline{y}_1}{\underline{y}_1 + \underline{y}_2} \underline{i}$
et $\underline{i}_2 = \frac{\underline{y}_2}{\underline{y}_1 + \underline{y}_2} \underline{i}$.

## Phénomène de résonance
> La résonance d'un système en régime sinusoïdal forcé correspond à une excitation
> menant un maximum d'amplitude du signal considéré.
> La pulsation $\omega_r$ à laquelle ce maximum a lieu est la pulsation de
> résonance.

### Résonance en intensité/vitesse : exemple du circuit RLC
#### Étude à basse et haute fréquence
À basse comme à haute fréquence, la bobine ou le condensateur se comporte comme
un interrupteur, donnant un circuit à intensité nulle.

#### Mise en équation
On obtient l'équation différentielle
$\frac{d^2 u_c(t)}{dt^2} + \frac{\omega_0}{Q} \frac{\frac{d u_c(t)}{dt} + \omega_0^2 u_c(t)}{\omega_0^2 e(t)}$.
En notation complexe, $\underline{a} = E_m e^{j\omega t}$, $\underline{u_c} = \underline{U}_m e^{j \omega t}$
et $\underline{i} = \underline{I}_m e^{j \omega t}$.
L'équation se réécrit donc $[(j \omega)^2 + j \omega \frac{\omega_0}{Q} + \omega_0^2] \underline{U}_m e^{j \omega t}$
$= \omega_0^2 E_m e^{j \omega t}$.
$\underline{U}_m = \frac{E_m}{1 - (\frac{\omega}{\omega_0})^2 + j \frac{\omega}{Q \omega_0}}$,
et $i(t) = C \frac{d u_c}{dt}$ soit $\underline{i} = j C \omega \underline{u}$,
donc $\underline{I}_m = j C \omega \underline{U}_m$ soit
$\underline{I}_m = \frac{j C \omega E_m}{1 - (\frac{\omega}{\omega_0})^2 + j \frac{\omega}{Q \omega_0}}$.

> La pulsation réduite est définie par $x = \frac{\omega}{\omega_0}$.
On réécrit ainsi $\underline{I}_m = \frac{Q C \omega_0 E_m}{1 + jQ (x - \frac{1}{x})}$.
Or, $Q = \frac{1}{r} \sqrt{\frac{L}{C}}$ et $\omega_0 = \frac{1}{\sqrt{LC}}$,
donnant $\underline{I}_m = \frac{E_m}{R} \frac{1}{1 + jQ(x - \frac{1}{x})}$.

#### Evolution du module
On pose $I_0 = \frac{E_m}{R} > 0$. $I_m(x) = |\underline{I}_m|$
$= \frac{I_0}{\sqrt{1 + Q^2 (x - \frac{1}{x})^2}}$. On a
$\lim\limits_{x \to 0} I_m(x) = 0$ et $\lim\limits_{x \to + \infty} I_m(x) = 0$.
Pour $x = 1$, $\omega = \omega_0$, il y a un maximum.

> Pour une résonance en intensité, la résonance a lieu pour $\omega_r = \omega_0$.

> Pour $C$ et $L$ fixés, la résonance est d'autant plus marquée que $Q$ est grand.

#### Notion d'acuité
Voir schémas

> La largeur de la résonance d'une bande de résonance de la taille $\Delta \omega$
> contient par définition l'ensemble des pulsations pour lesquelles $I_m(\omega) \geq \frac{I_{m,\text{max}}}{\sqrt{2}}$.

> L'acuité est, par définition, $a = \frac{\omega_r}{\Delta \omega}$.

> $a = \frac{\omega_0}{\omega_2 - \omega_1} = Q$

Ainsi, plus $Q$ est grand, plus le pic sera fin et grand.

#### Évolution de la phase
$\Phi = \text{arg}(\underline{I}_m) = \text{arg}(\frac{E_m}{R} \frac{1}{1 + jQ(x - \frac{1}{x})})$
$= - \text{arg}(1 + j Q(x - \frac{1}{x}))$
$\Leftrightarrow \Phi = \arctan(Q(x - \frac{1}{x}))$

La phase évolue ainsi selon la fréquence de $\frac{\pi}{2}$ à $\frac{-\pi}{2}$,
avec un tracé d'autant plus droit que $Q$ est petit.
- En basse fréquence, $x \ll 1$, $\lim\limits_{x \to 0} \Phi(x) = \frac{\pi}{2}$
- En haute fréquence, $x \gg 1$, $\lim\limits_{x \to + \infty} \Phi(x) = \frac{-\pi}{2}$
- À la résonance, $x = 1$, $\Phi(x = 1) = 0$

> Pour la résonance en intensité et en vitesse, les deux signaux sont en phase.

### Résonance en tension/élongation : exemple du circuit RLC
#### Mise en équation
$\underline{U}_m = \frac{E_m}{1 - x^2 + j \frac{x}{Q}}$,

#### Système mécanique équivalent
En notation complexe, $\underline{x}_a = A_m e^{j \omega t}$
et $\underline{y}(t) = \underline{V}_m e^{j \omega t}$,
donnant $(- \omega^2 + j \frac{\omega \omega_0}{Q} + \omega^2) \underline{V}_m = \omega_0^2 A_m$
$\Leftrightarrow$

#### Evolution du module
$Y_m(t) = \frac{A_m}{\sqrt{(1 - x^2)^2 + (\frac{x}{Q})^2}}$. On a ainsi
$\lim\limits_{x \to 0} Y_m(x) = A_m$ et $\lim\limits_{x \to + \infty} Y_m(x) = 0$.
Pour $Q > \frac{1}{\sqrt{2}}$, il y a un maximum $\omega_r = \omega_0 \sqrt{1 - \frac{1}{2Q^2}}$

> Si $Q > \frac{1}{\sqrt{2}}$, la pulsation de résonance est $\omega_r = \omega_0 \sqrt{1 - \frac{1}{2Q^2}}$

#### Notion d'acuité
Voir schémas

> La largeur de la résonance d'une bande de résonance de la taille $\Delta \omega$
> contient par définition l'ensemble des pulsations pour lesquelles $I_m(\omega) \geq \frac{I_{m,\text{max}}}{\sqrt{2}}$.

> L'acuité est, par définition, $a = \frac{\omega_r}{\Delta \omega}$.

> $a = \frac{\omega_0}{\omega_2 - \omega_1} = Q$

Ainsi, plus $Q$ est grand, plus le pic sera fin et grand.

#### Évolution de la phase
$\Phi = \text{arg}(\underline{I}_m) = \text{arg}(\frac{E_m}{R} \frac{1}{1 + jQ(x - \frac{1}{x})})$
$= - \text{arg}(1 + j Q(x - \frac{1}{x}))$
$\Leftrightarrow \Phi = \arctan(Q(x - \frac{1}{x}))$

La phase évolue ainsi selon la fréquence de $\frac{\pi}{2}$ à $\frac{-\pi}{2}$,
avec un tracé d'autant plus droit que $Q$ est petit.
- En basse fréquence, $x \ll 1$, $\lim\limits_{x \to 0} \Phi(x) = \frac{\pi}{2}$
- En haute fréquence, $x \gg 1$, $\lim\limits_{x \to + \infty} \Phi(x) = \frac{-\pi}{2}$
- À la résonance, $x = 1$, $\Phi(x = 1) = 0$

> Pour la résonance en intensité et en vitesse, les deux signaux sont en phase.

$\Phi_\text{tenison} = \text{arg}(\frac{A_m}{1 - x^2 + j \frac{x}{Q}})$\
$= - \text{arg}(1 - x^2 + j \frac{x}{Q})$\
$= - \text{arg}([\frac{Q}{x} - jQx - 1] \frac{x}{jQ})$\
$= - \text{arg}(j[1 + j Q (x - \frac{1}{x})])$\
$= - \frac{\pi}{2} - \text{arg}(1 + jQ (x - \frac{1}{x}))$\
$= -\frac{\pi}{2} + Q_\text{intensité}$

La phase évolue selon la fréquence de $0$ à $-\pi$, de façon d'autant plus
droite que $Q$ est petit.

### Bilan sur les deux types de résonance
Intensité/Vitesse                                  | Tension/Élongation
---                                                | ---
$i(t) / \dot{x}(t)$                                | $u_c(t) / x(t)$
Résonance toujours présente, $\omega_r = \omega_0$ | Résonance uniquement si $Q > \frac{1}{\sqrt{2}}$, $\omega_r = \omega_0 \sqrt{1 - \frac{1}{2Q^2}}$
Proportionnelle à $Q$                              | Proportionnelle à $Q$ si $Q$ est grand
$a = Q$ : pic d'autant plus fin que $Q$ est grand  | Proportionnelle à $Q$ si $Q$ est grand
