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
