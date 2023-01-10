# Filtrage linéaire
## Notion de filtrage linéaire
### Exemple : le filtrage RC
On se place dans un circuit RC. On a ainsi l'entrée en tension qui est un signal
sommé de deux signaux : $e(t) = e_1(t) + e_2(t)$, avec
$e_1(t) = E_1 \cos(\omega_1 t)$ avec $\omega_1 \ll \omega_0 = \frac{1}{RC}$ et
$e_2(t) = E_2 \cos(\omega_2 t)$ avec $\omega_2 \gg \omega_0$.

On applique la formule du pont diviseur de tension : $\underline{u}(t)$
$= \frac{\underline{z}_C}{\underline{z}_R + \underline{z}_C} \underline{e}(t)$
$= \frac{\underline{e}}{1 + j RC \omega} = \frac{\underline{e}}{1 + j \frac{\omega}{\omega_0}}$.

En sortie, on aura donc le signal $s(t) = s_1(t) + s_2(t)$ :
$\underline{s_1}(t) = \frac{\underline{e_1}(t)}{1 + j \frac{\omega}{\omega_0}} \to \underline{e_1}(t)$
et $\underline{s_2}(t) = \frac{\underline{e_2}(t)}{1 + j \frac{\omega}{\omega_0}} \to 0$.

Il s'agit ainsi d'un "filtre passe bas", qui ne laisse passer que les signaux de
basse fréquence.

### Fonction transfert
> En notation complexe, une fonction transfert est une fonction telle qu'avec
> l'entrée $\underline{e}(t) = E_m e^{j \omega t}$ et la sortie
> $\underline{s}(t) = S_m e^{j (\omega t + \Phi)} = \underline{S_m} e^{j \omega t}$,
> on ait la fonction $\underline{H}(\omega) = \frac{\underline{s}(t)}{\underline{e}(t)} = \frac{S_m e^{j \Phi}}{E_m}$.

Si on connaît cette fonction transfert, alors on peut déterminer la sortie pour
tout signal d'entrée sinusoïdal.

Ainsi, on a de même $\underline{s}(t) = \underline{H}(\omega) \underline{e}(t)$,
$S_m(\omega) = |\underline{H}(\omega)| E_m$ et $\Phi(\omega) = \text{arg}(\underline{H}(\omega))$.

> On appelle $G(\omega) = |\underline{H}(\omega)| = \frac{S_m}{E_m}$ le gain de la fonction de transfert,
> une grandeur sans dimension.

> On appelle $\Phi(\omega) = \text{arg}(\underline{H}(\omega))$ la phase de la
> fonction de transfert, une grandeur sans dimension en radians.

> Le gain en décibel est défini comme $G_{\text{dB}}(\omega) = 20 \log_{10} G(\omega)$,
> une grandeur sans dimension en décibel, noté $\text{dB}$.

### Notion de filtre
> Un filtre est un système qui transmet préférentiellement certaines composantes
> d'un signal périodique appliqué en entrée. Un filtre possède donc au moins un
> fréquence ou pulsation ($\omega_0$) caractéristique.

> - Un filtre passe-bas laisse passer les basses fréquences
> - Un filtre passe-haut laisse passer les hautes fréquences
> - Un filtre passe-bande laisse passer une bande de fréquence particulière
> - Un filtre coupe-bande laisse passer tout sauf une bande de fréquence
>   particulière

> Lorsqu'on peut noter la fonction de transfert comme
> $\underline{H}(\omega) = \frac{\underline{N}(\omega)}{\underline{D}(\omega)}$
> avec $\underline{N}(\omega)$ et $\underline{D}(\omega)$ des polynômes,
> l'ordre du filtre est le degré de $\underline{D}(\omega)$.

### Valeur moyenne et valeur efficace d'un signal
#### Définition
On considère des signaux périodiques de période $T$, notés $s(t)$.

> La valeur moyenne de $s(t)$, notées $<s>$, est définie comme la valeur
> $\frac{1}{T} \int\limits_{0}^{T} s(t) dt $
> $= \frac{1}{T} \int\limits_{t_0}^{t_0 + T} s(t) dt$.

Pour un signal constant, de valeur $k$, la valeur moyenne est $k$. Pour un
signal sinusoïdal, la valeur moyenne est nulle (parcourt les mêmes valeurs
positives et négatives).

> - Un signal constant est dit continu
> - Un signal de moyenne nulle est dit alternatif

> La valeur efficace ou valeur quadratique moyenne (en anglais : RMS (root mean
> squared)) est définie comme la valeur $S_\text{eff} = \sqrt{<s^2>}$.

Pour un signal constant, $S_\text{eff} = |k|$ et pour un signal sinusoïdal,
puisque $s^2(t) = A^2 \cos^2(\omega t + \Phi) = \frac{A^2}{2} [1 + \cos(2(\omega t + \Phi))]$,
$<s^2> = \frac{A^2}{2}$ donc $S_\text{eff} = \frac{A}{\sqrt{2}}$.

#### Lien avec la mesure d'un signal électrique
Soit un signal périodique, $s(t) = <s> + s(t) - <s>$.

> Le signal continu $<s>$ est la composante continue de $s(t)$.
> Le signal alternatif $a(t) = s(t) - <s>$ est la composante alternative de
> $s(t)$.

En TP, on retrouve ceci dans de nombreuses mesures :
- Le voltmètre permet de mesurer la tension soit en mode DC (direct current)
  ou CC (courant continu), et affiche ainsi $<u>$; soit en mode AC (alternative
  current) qui donne la valeur efficace.
- L'oscilloscope permet l'utilisation du coupling DC ou CC qui affiche le signal
  $u(t)$, ou le coupling AC ou CA (courant alternatif) qui affichent la
  composante alternative du signal, $u(t) - <u>$.

#### Lien entre RMS et puissance
On prend le cas d'une résistance de tension $u(t)$ traversé par un courant
d'intensité $i(t)$, qui a donc une puissance $P(t) = u(t) i(t) = \frac{u^2(t)}{R}$.
Pour $u(t)$ périodique, on a donc $<P> = \frac{<u^2>}{R} = \frac{u^2_\text{eff}}{R}$.
On mesure cette grandeur avec un Wattmètre.

La valeur efficace $u_\text{eff}$ correspond à la valeur que doit avoir une
tension continue pour dissiper en moyenne la même puissance dans une résistance
$R$ quelconque.

#### Formule de Parseval
Soit un signal $T$-périodique, on peut le décomposer en une série de Fourier
telle que $s(t) = <s> + \sum\limits_{n = 0}^{+\infty} A_n \cos(x \omega t + \Phi)$.

> Pour tout signal $T$-périodique quelconque, on a $s^2_\text{eff} =$
> $<s>^2 + \sum\limits_{n = 0}^{+\infty} <A_n \cos(x \omega t + \Phi_n)>$
> $= <s>^2 + \sum\limits_{n = 1}^{+\infty} \frac{A_n^2}{2}$.

## Filtre passe bas du premier ordre : filtre RC en série
### Présentation
On se place dans un circuit RC en série. En basse fréquence, le condensateur est
équivalent à un interrupteur ouvert (comme $i(t) = 0$, $s(t) = i(t)$). En haute fréquence,
le condensateur est équivalent à un fil, la tension aux bornes d'un fil étant
null on a $s(t) = 0$.

Un filtre passe-bas laisse passer les basses fréquences et coupe les hautes
fréquences.

### Fonction de transfert
On applique la formule du point diviseur de tension :
$\underline{H}(\omega) = \frac{\underline{s}}{\underline{e}}$
$= \frac{\underline{z}_c}{\underline{z}_R + \underline{z}_c}$
$= \frac{\frac{1}{j \omega}}{R + \frac{1}{j c \omega}}$
$= \frac{1}{1 + j RC \omega} = \frac{1}{1 + j \frac{\omega}{\omega_0}}$,
avec $\omega_0 = \frac{1}{RC}$.

Le filtre $RC$ est un filtre du premier ordre.

$\omega_0$ est la pulsation caractéristique, et on définit la pulsation réduite
$x = \frac{\omega}{\omega_0}$, donnant $\underline{H}(x) = \frac{1}{1 + j x}$.

### Gain, pulsation de coupure et bande passante
> Le gain est par définition $G = |\underline{H}(x)| = \frac{1}{\sqrt{1 + x^2}}$.

> On appelle pulsation de coupure les pulsations $\omega_c$ qui vérifient par définition
> $G(\omega_c) = \frac{G_\text{max}}{\sqrt{2}}$.

Ici, la pulsation de coupure d'un filtre RC est $\omega_c = \omega_0 = \frac{1}{RC}$.

La bande passante correspond aux valeur de $\omega$ telles que
$G(\omega) \leq \frac{G_\text{max}}{\sqrt{2}}$.

Le gabarit correspond à un tracé en créneau de hauteur $G_\text{max}$
hors de la band passante.

### Gain en décibel et diagramme de Bode
Le diagramme de Bode est un diagramme du gain en décibel $G_{dB}$ tracé en
fonction de $\log(\omega)$ ou $\log(x)$, et de la phase en fonction de $\log \omega$
ou de $\log x$.

#### Diagramme de Bode en gain
- En basse fréquence, $G(x) \xrightarrow[x \to 0]{} 1$ et donc
  $G_{\text{dB}}(x) = 20 \log(G(x)) \xrightarrow[x \to 0]{} 0$.
- En haute fréquence, $G(x) \underset{x \to +\infty}{\sim} \frac{1}{x}$
  et donc $G_{\text{dB}}(x) = 20 \log(G(x)) \underset{x \to +\infty}{\sim} -20 \log(x)$.
- À la pulsation de coupure, $G_{\text{dB}}(x = 1) = 20 \log(\frac{1}{\sqrt{2}}) = -10 \log(2)$
  $\approx -3 \text{dB}$.

#### Diagramme de Bode en phase
On a $\Phi(x) = \text{arg}(\underline{H}(x)) = -\text{arg}(1 + jx) = - \arctan x$.
- En basse fréquence, $\underline{H}(x) \underset{x \to 0}{\sim} 1$, donc
  $\Phi(x) = \text{arg}(\underline{H}) \xrightarrow[x \to 0]{} 0$.
- En haute fréquence, $\underline{H}(x) \underset{x \to +\infty}{\sim} \frac{1}{jx}$
  $= - \frac{j}{x}$, donc $\Phi(x) = \text{arg}(\underline{H})$
  $\xrightarrow[x \to +\infty]{} \frac{-\pi}{2}$.
- À la pulsation de coupure, pour $x = 1$,
  $\underline{H}(x = 1) = \frac{1}{1 + j} = \frac{1 - j}{2}$
  donc $\Phi(x = 1) = \frac{-\pi}{4}$.
