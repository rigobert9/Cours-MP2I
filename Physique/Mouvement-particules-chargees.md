# Mouvements de particules chargées
Les particules chargées correspondent aux particules élémentaires de charge
électrique ($+$ : proton, $-$ : électron) et aux particules qui présentent des
différences de charge, comme les ions ($+$ : cations, $-$ : anions).

## Forcé électromagnétique
### Interaction entre deux charges
On prend deux charges $q_1$ et $q_2$.

> $\overrightarrow{\rm F_{1 \to 2}} = - \overrightarrow{\rm F_{2 \to 1}}$

> $\overrightarrow{\rm F_{1 \to 2}} = \frac{1}{4 \pi \varepsilon_0 \varepsilon_r} \cdot \frac{q_1 q_2}{r^2} \overrightarrow{\rm u_{1 \to 2}}$

$\varepsilon_0$ est la permitivité diélectrique dans le vide, de valeur
$8,85 \times 10^{-12} F \cdot m^{-1}$, de dimension
$M^{-1} L^{-2} T^4 I^2 \cdot M^{-1} = M^{-2} L^{-2} T^4 I^2$.

$\varepsilon_r$ est la permitivité diélectrique relative, un coefficient sans
dimension expérimental selon le milieu.

Deux charges de même signe de valeur se repoussent; deux charges de signe
différent s'attirent.

> On peut créer une nouvelle grandeur, le champ électrique, noté
> $\overrightarrow{\rm E_1}(M_2) = \frac{q_1}{4\pi \varepsilon_0 \varepsilon_r} \frac{1}{r^2} \overrightarrow{\rm u_{1 \to 2}}$
> $= \frac{q_1}{4\pi \varepsilon_0 \varepsilon_r} \frac{\overrightarrow{\rm M_1 M_2}}{\lVert \overrightarrow{\rm M_1 M_2} \rVert^3}$

Ce champ ne dépend pas de la charge $q_2$.

> La force exercée par la charge $q_1$ sur la charge $q_2$ placée en
> $M_2$ est $\overrightarrow{\rm F_{1 \to 2}} = q_2 \overrightarrow{\rm E_1}(M_2)$.

> Par définition, $\delta W = \overrightarrow{\rm F_{1 \to 2}} \cdot d \overrightarrow{\rm OM}$
> $= \frac{q_1 q_2}{4\pi \varepsilon_0 \varepsilon_r} \frac{d r}{r^2}$.

Ainsi, $\delta W = - E_p$, et $E_p(r) = \frac{q_1 q_2}{4 \pi \varepsilon_0 \varepsilon_r} \frac{1}{r} + C$,
avec $C$ une constante.

> Le potentiel créé par la charge $q_1$ au point $M_2$ est noté
> $V_1(M_2) = \frac{q_1}{4 \pi \varepsilon_0 \varepsilon_r} \frac{1}{r} + C$,
> avec $C$ une constante.

$V$ est une tension, en volt (différence de potentiel).

> Une charge $q_2$ plongée dans le potentiel $V_1$ a pour énergie potentielle
> $E_p(M_2) = q_2 V_1(M_2)$.

Les charges positives ont tendance à se diriger vers les zones de plus faible
potentiel. Les charges électriques négatives ont tendance à se diriger vers des
zones de potentiel plus fort.

Un champ électrique est dirigé des zones de fort potentiel vers les zones de
faible potentiel.

> Le différentiel total $df$ est la somme des différentielles partielles des
> variables $df = \nabla = \frac{\partial f}{\partial x} dx + \frac{\partial f}{\partial y} dy + \frac{\partial f}{\partial z} dz$.

Ainsi, on a $df = \left(\begin{matrix} \frac{\partial f}{\partial x} \\ \frac{\partial f}{\partial y} \\ \frac{\partial f}{\partial z} \end{matrix}\right)$
$\cdot \left(\begin{matrix} dx \\ dy \\ dz \end{matrix}\right)$.

> On note le gradian de $f$ $\overrightarrow{\rm \text{grad}} f = \left(\begin{matrix} \frac{\partial f}{\partial x} \\ \frac{\partial f}{\partial y} \\ \frac{\partial f}{\partial z} \end{matrix}\)$,
> donnant $df = \overrightarrow{\rm \text{grad}} f \cdot d \overrightarrow{\rm OM}$.

On a $d V = - \overrightarrow{\rm E} \cdot d \overrightarrow{\rm OM}$, et $\overrightarrow{\rm E} = - \overrightarrow{\rm \text{grad}} V$.

### Charge dans un champ extérieur uniforme
Un champ $\overrightarrow{\rm E}(M,t)$ est une application de l'espace et du
temps vers l'espace : $\begin{aligned} \overrightarrow{\rm E}(M,t): \mathbb{R}^3 \times \mathbb{R} &\to \mathbb{R}^3 \\ M,t &\mapsto \overrightarrow{\rm E}(M,t) .\end{aligned}$.

> Un champ $\overrightarrow{\rm E}$ est dit :
> - uniforme si $\overrightarrow{\rm E}(M_1,t) = \overrightarrow{\rm E}(M_2,t)$
>   pour tous points $E_1$ et $E_2$.
> - statique si $\overrightarrow{\rm E}(M,t_1) = \overrightarrow{\rm E}(M, t_2)$
>   pour toutes dates $t_1$ et $t_2$.

Pour créer un champ électrostatique uniforme, on place face à face des plaques
de potentiel négatif et positif. La différence de potentiel de ces deux plaques
est la tension. Le champ va dans le sens des potentiel décroissants.

On note la tension dans le champ $U = V_1 - V_2$, et la densité surfacique de
charge $\sigma = \frac{q}{S} = \frac{CU}{S}$. On a ainsi $\overrightarrow{\rm E} = \frac{\sigma}{\varepsilon_0} \overrightarrow{\rm u_z}$.
$= \frac{CU}{S \varepsilon_0} \overrightarrow{\rm u_z}$.

### Propriétés et ordres de grandeur
Il existe une fonction de la position pour la tension $V(M)$,
telle que $dV = - \overrightarrow{\rm E} \cdot d \overrightarrow{\rm OM}$
$\Leftrightarrow \overrightarrow{\rm E} = - \overrightarrow{\rm \text{grad}} V$.
