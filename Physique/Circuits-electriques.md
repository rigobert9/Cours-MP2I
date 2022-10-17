# Chapitre 3 : Circuits électriques dans l'ARQS
> ARQS : Approximation des régimes quasi-stationnaires

## Approximation des régimes quasi-stationnaires
> En régime variable (au cours du temps), les fluctuations de courant se
> propagent à une vitesse proche de la vitesse de la lumière. Pour des circuits
> de taille raisonnable, la durée de propagation $\tau$ est très petite devant
> le temps caractéristique T des fluctuations (période du signal s'il est
> périodique).
> Il est alors légitime de négliger $\tau$ devant T. C'est ce qu'on appelle
> l'approximation des régimes quasi-stationnaires.
> Autrement dit, l'ARQS est applicable pour l'étude d'un courant électrique si
> la longueur des fils électriques et des temps caractéristiques de variation T
> sont tels que $L \ll C T$ ou $T \gg \frac{L}{C}$.

##### Exemples
1. Fréquence du secteur en Europe : $50 Hz$ (différent dans d'autres pays, la
   fréquence est plus grande au Japon et Street Fighter était donc plus rapide
   sur la PS1). On a alors $C T = \frac{C}{f} = \frac{3 \times 10^{8}}{50} = 6 \times 10^6$.
   Il faut donc que la taille du circuit soit très petite devant $6000 km$ (la
   PlayStation passe) pour appliquer l'ARQS.
2. En TP, la taille des circuits est de $L \approx 1m$, $f \ll \frac{C}{L} = 300 MHz$.
    Or, on ne dépasse pas $300 MHz$. On peut donc appliquer l'ARQS.

## Intensité du courant électrique
### Charges et postures de charge
> La charge est notée Q ou q, d'unité coulomb (C)

La charge électrique nette Q ou q est une grandeur algébrique qui caractérise la
sensibilité d'un porteur de charge à l'intersection électromagnétique.

La charge Q d'un porteur de charge est un multiple de la charge élémentaire $e$,
correspondant à la charge d'un proton (dont on connaît jusqu'à au moins la 11ème
décimale), d'approximation $e \approx 1.6 \times 10^{-19}$. On a donc
$\forall Q, \exists z \in \mathbb{Z}, Q = z \cdot e$.

Il y a différents types de porteurs de charge :
- Les électrons $e^{-}$ dans un métal conducteur
- Les ions dans les solutions ioniques (comme dans les piles)
- des électrons $e^{+}$ des lacunes dans le semi-conducteurs

> La charge électrique se conserve; il n'y a donc pas de création ni de
> disparition de charge.

> Le courant électrique dans les métaux conducteurs correspond au déplacement
> ordonné des porteurs de charge.

##### Exemple de porteur de charge
$Q(Cu^{2+}) \approx +2 e$

### L'intensité du courant électrique
> L'intensité du courant électrique est le débit de charge à travers une section
> du conducteur. Il s'agit donc de $i(t) = \frac{dq(t)}{dt}$, avec $i$ en
> Ampères, $q$ en Coulombs et t en secondes.

Dans l'ARQS, l'intensité reste la même le long d'une branche (donc à travers des
dipôles en série).

> Le sens conventionnel du courant est celui pour lequel $i(t) > 0$. Cela
> correspond au sens de déplacement des charges positives (bien que ce soit en
> fait les électrons qui se déplacent).

##### Exemples de valeurs :
Composant ou appareils       | Courant
---                          | ---
Circuits électriques         | $10 mA$ à $100 mA$
Ampoule à incandescence 230V | $1 A$
Feu ou chauffage électrique  | $10 A$
Démarreur automobile         | $100 A$
Moteur de TGV                | $1 kA$
Foudre                       | $10^5 A$
Seuil létal                  | $40 mA$ pendant 3 s ou $300 mA$ pendant 0,1 s

### Loi des nœuds
> La loi des nœuds traduit la conservation de la charge en régime stationnaire
> et exprime le fait que la charge ne peut pas s'accumuler au niveau d'un nœud

En chaque nœud d'un circuit, $\sum\limits_{k} \varepsilon_k i_k = 0$, où $\varepsilon_k = +1$
quand le courant est entrant et $\varepsilon_k = -1$ quand le courant est sortant.

##### Exemple
Soit un nœud N à quatre chemins $i_{1 \ldots 4}$, avec $i_{1 \ldots 3}$ entrants
et $i_4$ sortant, on a $i_1 + i_2 + i_3 - i_4 = 0 \Leftrightarrow i_1 + i_2 + i_3 = i_4$.

## Tension électrique
### Le potentiel électrique
#### Expérience de Wimshurst
(voir vidéo, expérience avec deux boules qui accumulent de l'électricité
statique, mais avec une différence de potentiel, et produisent une étincelle en
étant rapprochées l'une de l'autre)

#### Le potentiel électrique
> Toute distribution de charge induit un champ scalaire, c'est à dire une
> fonction définie en tout point de l'espace qu'on appelle potentiel électrique

On note cette fonction $\begin{aligned} V: \mathbb{R}^3 &\to \mathbb{R} \\ (x, y, z) &\mapsto V((x, y, z)) .\end{aligned}$.
Le potentiel s'exprime en Volts.

### La tension électrique
> La tension correspond à une différence en potentiel : $U_{AB} = V_A - V_B$.

La tension $U_{AB}$, représentée par une flèche allant de B vers A est la
différence de potentiel entre les points A et B. On la mesure ainsi souvent aux
bornes des dipôles.

##### Exemples de valeurs
Composants ou appareils | Tension
---                     | ---
Secteur                 | $230 V$
Pile                    | Quelques Volts
Circuits électroniques  | Quelque mV
Signaux nerveux         | $75 mV$
Alimentation TGV        | $25 kV$
Éclair                  | $10^8 V$
Ligne à haute tension   | $150~1000 kV$

> Un dipôle électrocinétique (à faible puissance) est une partie d'un circuit qui
> peut être reliée au reste du circuit par deux fils (cela peut donc être un
> ensemble de dipôles). On définit son comportement par sa caractéristique
> $i = f(u)$ (une fonction souvent bijective), dans une convention donnée.

Deux conventions existent, la convention récepteur et la convention générateur.
La convention récepteur est la plus utilisée.
- En convention récepteur, si le courant algébrique est orienté dans le sens AB, alors $u = V_A - V_B$
- En convention générateur, si le courant algébrique est orienté dans le sens AB, alors $u = V_B - V_A$

### Loi des mailles
> Une maille est un parcours fermé, sur un circuit électrique partant d'un nœud
> partant d'un nœud pour revenir à ce même nœud. On associe à cette maille un sens
> de parcours arbitraire.

En prenant une maille et en choisissant arbitrairement un sens de parcours, on
visite toutes les branches de la maille et on associe un coefficient $\varepsilon_k = +1$
lorsqu'elle est dans le sens de parcours et un $\varepsilon_k = -1$ lorsque la
tension rencontrée est orientée dans l'autre sens. La loi des mailles donne
alors la relation suivante : $\sum\limits_{k} \varepsilon_k u_k = 0$.

> On note les valeur u, i et q en minuscule lorsqu'elles sont variables avec le
> temps, et U, I et Q en majuscule lorsqu'elles sont constantes.

## Puissance électrique
> La puissance électrique reçue (l'énergie reçue par unité de temps) par un dipôle
> à l'instant $t$, soumis à une tension $u_t$ et traversé par un courant
> d'intensité $i_t$, vaut, en convention récepteur, $P(t) = u(t) i(t)$, avec $P(t)$
> en Watt, $u(t)$ en Volt et $i(t)$ en Ampère.

- Si $P(t) > 0$, le dipôle absorbe de l'énergie électrique. On dit que le dipôle
  a un caractère récepteur.
- Si $P(t) < 0$, le dipôle fournit de l'énergie électrique. On dit que le
  dipôle a un caractère générateur.

## Dipôle ohmique
### Loi d'Ohm et effet Joule
> Soit un dipôle ohmique traversé par un courant $i(t)$, et aux bornes duquel on
> mesure une tension $u(t)$, on a la relation avec la résistance $R$ en Ohm ($\Omega$) :
> $u(t) = R i(t)$.

La courbe représentative caractéristique de la tension selon l'intensité (ou
l'inverse) est une droite (une fonction affine).

> On a $P(t) = u(t) i(t) = R i(t)^2$.

Effet Joule : $E = P \cdot \Delta t = R i^2 \Delta t$

### Association de résistances
#### Résistances en série
Pour deux résistances en série qui ont à leur bornes des tensions $R_1$ et
$R_2$, et qui sont traversés par un courant d'intensité $i$, on a, d'après la
loi d'Ohm, $u_1 = R_1 i$ et $u_2 = R_2 i$. Par additivité des tensions, on a la
tension des deux dipôles ensemble $U = u_1 + u_2$, et donc la résistance de
cette série $R_\text{eq} = \frac{u}{i} = (R_1 + R_2)$.

> Pour $n$ dipôles en série de résistance $R_k$, on a la résistance de la série
> $R_\text{éq} = \sum\limits_{k = 1}^{n} R_k$.

#### Résistances en parallèle
Pour deux dipôles en dérivation qui ont à leur bornes des tensions $u_1$ et
$u_2$, qui ont une résistance $R_1$ et $R_2$ et qui sont traversés par un
courant d'intensité $i$, on a, d'après la loi d'Ohm, $u_1 = R_1 i_1$, $u_2 = R_2i_2$ et $u = R_\text{éq} i$.
D'après la loi des nœuds, $i = i_1 + i_2$, or $i_1 = \frac{u_1}{R_1}$ et
$i_2 = \frac{U_2}{R_2}$, donc $i = \frac{u_1}{R_1} + \frac{u_2}{R_2}$.
D'après la loi des mailles, $u = u_1 = u_2$, donc $i = (\frac{1}{R_1} + \frac{1}{R_2}) u$,
or $u = R_\text{éq} i$, donc $i = \frac{u}{R_\text{éq}}$, donc $\frac{1}{R_\text{éq}} = \frac{1}{R_1} + \frac{1}{R_2}$.

> Pour n résistances en parallèle, $\frac{1}{R_\text{éq}} = \sum\limits_{k = 1}^{n} \frac{1}{R_k}$.

## Pont diviseur de tension et de courant
### Pont diviseur de tension
Voir schéma.
D'après la loi d'Ohm, on a $\left\{\begin{matrix} u_1 = R_1 i \\ u_2 = R_2 i \\ u = (R_1 + R_2) i \end{matrix}\right.$,
donc $i = \frac{u_1}{R_1} = \frac{u_2}{R_2} = \frac{u}{R_1 + R_2}$,
donc $u_1 = \frac{R_1}{R_1 + R_2} u$ et $u_2 = \frac{R_2}{R_1 + R_2} u$.


### Pont diviseur de courant
Voir schéma.
D'après la loi d'Ohm, on a $\left\{\begin{matrix} u_1 = R_1 i \\ u_2 = R_2 i \\ u = \frac{R_1 R_2}{R_1 + R_2} i \end{matrix}\right.$,
d'après la loi des nœuds et des mailles, $\left\{\begin{matrix} i = i_1 + i_2 \\ u = u_1 = u_2 \end{matrix}\right.$,
soit $\frac{R_1 R_2}{R_1 + R_2} i = R_1 i_1 = R_2 i_2$,
donc $i_1 = \frac{R_2}{R_1 + R_2} i$ et $i_2 = \frac{R_1}{R_1 + R_2} i$.

### Conductance
Pour donner une autre forme aux relations utilisées, on utilise la conductance
$G = \frac{1}{R}$, l'inverse de la résistance. On a ainsi
$i_1 = \frac{G_1}{G_1 + G_2} i$ et $i_2 = \frac{G_2}{G_1 + G_2}$.

En chimie, son unité est le Siemens.

## Modélisation d'un générateur
### Source de tension
#### Source idéale de tension
> Une source idéale de tension de tension $u$, avec un $e$ sa force électromotrice
> respecte pour toute intensité du courant qui le traverse $i$, $u = e$.

#### Source réelle de tension
> Pour tenir compte des pertes par effet Joule d'une source de tension, on
> modélise la source par une source idéale en série avec une résistance $r$
> appelée résistance interne. On a donc $u = e - ri$

### Source de courant
#### Source idéale de courant
> Une source idéale de courant d'intensité $i$, avec un $i_0$ une intensité,
> respecte pour toute tension qui le traverse $u$, $i = i_0$.

#### Source réelle de courant
> Pour tenir compte des pertes par effet Joule d'une source de courant, on
> modélise la source par une source idéale en série avec une résistance $r$
> appelée résistance interne. On a donc $i = i_0 - \frac{u}{r} = i_0 - gu$.

## Appareils de mesure
### Voltmètre
> Un Voltmètre est un appareil mesurant la tension qui se branche en dérivation
> autour d'un dipôle ou du segment mesuré.

Le voltmètre est représenté par un cercle avec un V, et a sa borne "COM" vers le - et A vers le +.

> Un voltmètre idéal est un dipôle de résistance infinie. 

La résistance d'entrée d'un voltmètre doit être grande devant les résistance du
circuit sur lequel il est branché, par un ordre de grandeur d'environ $10 M\Omega$.

### Ampèremètre
> Un ampèremètre est un appareil mesurant l'intensité, branché en série.

Le voltmètre est représenté par un cercle avec un A, et a sa borne "COM" vers le - et A vers le +.

> Un ampèremètre idéal est un dipôle de résistance nulle.

La résistance interne d'un ampèremètre doit être petite devant les résistances
du circuit sur lequel il est branché, de l'ordre de grandeur du Ohm.
