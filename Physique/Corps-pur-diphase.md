# Corps pur diphasé
## Corps pur sous différentes phases
### Rappel : définition d'une phase
> Une phase est une zone de l'espace dans laquelle les variables
> d'état intensives (pression, température, masse volumique) varient
> continument.

> Une frontière entre deux phases correspond donc à une discontinuité de ces variables d'état.

### Diagramme de phase d'un corps pur
> On appelle diagramme de phase ou diagramme d'état une représentation graphique
> qui cartographie la ou les phases stables d'un échantillon de corps pur en
> fonction de deux variables d'état.

Il s'agit donc de représentations en trois dimensions.

### Diagramme $(P,T)$
Voir les images dans le cours ou sur internet.

#### Lecture du diagramme
En général, la frontière séparant l'état solide à droite et liquide en haut à
gauche est parallèle à l'axe $P$, sauf par exemple pour le diagramme de l'eau où cette
frontière penche vers la gauche.

Au point triple, la rencontre des frontières entre les trois états, avec les
variables $(P_T,T_T)$, on retrouve sans distinction l'élément sous les trois
états.

Le point critique est le point au-delà duquel les phases liquides et gazeuses ne
peuvent plus être discernées et ne forment plus qu'une unique phase appelée
fluide supercritique.

Pour l'eau, $T_T = 273,16 K$ et $P_T = 6,11 \times 10^{-3} \text{bar}$,
et le point critique est à $T_C = 647 K$ et $P_C = 221 \text{bar}$.

#### Condition nécessaire de coexistence
> Lorsqu'un corps pur est en équilibre stable sous deux phases $A$ et $B$,
> alors la pression et la température de coexistence ne sont pas indépendantes
> l'une de l'autre : il existe une relation $P = P_{AB}(T)$.

Ainsi, à une température donnée, il ne peut y avoir qu'une seule valeur de
pression possible pour la coexistence, et inversement.

> Dans le cas de la transition entre liquide et gaz, la pression $P_{LG}(T)$
> est appelée pression de vapeur saturante, notée $P_\text{sat}(T)$.

## Étude de l'équilibre liquide-gaz
> Un diagramme de Clapeyron est une autre vue de la surface de phase complète,
> cette fois projetée le long de l'axe des températures, avec la pression en
> ordonnée et le volume ou molaire en abscisse.

### Diagramme de Clapeyron (P,v)
#### Lecture du diagramme
Voir le diagramme sur internet ou dans le cours.

Le diagramme de $P$ en fonction de $v$ montre la phase liquide à gauche, gazeuse
à droite, et la cohabitation sous une courbe en cloche au sommet de laquelle
culmine le point critique. Le solide se trouve assez bas sous la courbe.
La montée de la courbe est appelée courbe d'ébullition et la descente,
courbe de rosée.

> Les courbes séparant les domaines monophasés des domaines diphasés sont
> appelées courbes de saturation. Celle entre liquide + gaz et liquide est la
> courbe d'ébullition et celle entre liquide + gaz et gaz est la courbe de rosée.

#### Isothermes d'Andrews
Le diagramme de Clapeyron peut être augmenté de tracés représentant des points
Isothermes entre eux. Ces tracés forment souvent des paliers et des changements
de course en croisant les courbes de saturation.

> On appelle isotherme d'Andrews une courbe dans le digramme de Clapeyron représentant
> l'état du système pour une température fixée.

> Dans un domaine diphasé, une isotherme est nécessairement horizontale car la
> pression est égale à la pression de vapeur saturante.

#### Composition d'un mélange diphasé
On s'intéresse aux points $v_L$ et $v_G$, les points d'intersection de
l'isotherme d'Andrews avec les courbes de saturation à gauche et à droite
respectivement.

Pour un gaz parfait, on aura $v_G = \frac{V}{m} = \frac{nRT}{P m} = \frac{RT}{M P_\text{sat}}$.
$v_L$ est est en général donné ou laissé en lecture graphique. 

> À tout moment, on aura $m_\text{tot} = m_L + m_G$. On peut donc donner le titre
> en vapeur $x_G = \frac{m_G}{m_\text{tot}}$ et le titre en liquide et $x_L = \frac{m_L}{m_\text{tot}}$.

On peut donc procéder et obtenir $V = m_\text{tot} v = m_L v_L + m_G v_G = x_L m_\text{tot} v_L + x_G m_\text{tot} v_G$,
donnant $v = x_L v_{L} + x_G v_G$, or $x_L + x_G = 1$, donc $v = (1 - x_G) v_L + x_G v_G$.
On en tire enfin que $x_G = \frac{v - v_L}{v_G - v_L}$ et $x_L = \frac{v_G - v}{v_G - v_L}$.

Ces deux dernière valeurs constituent le théorème des moments, à connaître.

#### Exercice d'application
Soit un volume de $1 L$ d'eau de masse $m_\text{eau} = 0.1 kg$, à $T = 423 K$,
sous $P_\text{sat} = 4.8 \text{bar}$. On donne $M_\text{eau} = 18 g \cdot \text{mol}^{-1}$.

On a $v_L = 1.09 \times 10^{-3} m^{3} \times kg^{-1}$, et on cherche donc à
obtenir $v$, $v_G$, et $x_G$. On a $v = \frac{V}{m} = 1.0 \times 10^{-7} m^{3} kg^{-1}$,
et $v_G = \frac{RT}{M P_\text{sat}} = 0.41 m^{3} \cdot kg^{-1}$, donnant donc
$x_G = \frac{v - v_L}{v_G - v_L} = 0.022$.
