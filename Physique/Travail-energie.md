# Travail et énergie
## Puissance et travail d'une force
On considère un points matériel $N$ de masse $m$ dans un référentiel galiléen,
soumis à une force $\overrightarrow{\rm F}$.

> La puissance $P$ exercée par une force $\overrightarrow{\rm F}$ sur $M$, animée
> d'une vitesse $\overrightarrow{\rm v}$, à l'instant $t$, est de la forme
> $P(t) = \overrightarrow{\rm F} \cdot \overrightarrow{\rm v}(t)$.

L'unité d'un puissance est le Watt, en dimension $[ML^2 T^{-3}]$, ce qui est
homogène à une énergie multipliée par une vitesse.

Lorsque $P > 0$, on dit que la force est motrice. Si $P < 0$, la force est
résistante et si $P = 0$, la force ne travaille pas.
Le premier cas correspond à une force "dans le sens" de la vitesse, le second à
une force "contre le sens" de la vitesse, et le dernier cas correspond à une
force perpendiculaire à la vitesse.

> Le travail élémentaire $\delta W$ fourni par une force $\overrightarrow{\rm F}$
> correspond à la valeur $P \cdot dt = \overrightarrow{\rm F} \cdot \overrightarrow{\rm v} dt = \overrightarrow{\rm F} \cdot d \overrightarrow{\rm r}$.

On l'exprime souvent par le produit scalaire de la force .par le déplacement
élémentaire, $\overrightarrow{\rm F} \cdot d \overrightarrow{\rm r}$.

Le travail élémentaire est homogène à une énergie et est exprimé en Joules.

Le système fournit de l'énergie lorsque $\delta W > 0$, et il cède de l'énergie
lorsque $\delta W < 0$.

> Si le déplacement du point $M$ se fait entre les points $M_1$ et $t_1$ et
> $M_2$ en $t_2$ (donc sur le chemin $\mathcal{C}(M_1,M_2)$), le travail
> nécessaire pour effectuer le chemin, si la force est intégrable, est
> $W_{M_1 \to M_2} = \int\limits_{t = t_1}^{t = t_2} P(t) \cdot dt = \int\limits_{\overrightarrow{\rm r} = \overrightarrow{\rm OM_1}}^{\overrightarrow{\rm r} = \overrightarrow{\rm OM_2}} \overrightarrow{\rm F} \cdot d \overrightarrow{\rm r}$.

##### Exemple : Travail du poids
Le système est plongé dans un champ de pesanteur uniforme, et on considère le
poids agissant sur $N$ noté $\overrightarrow{\rm P}= m \overrightarrow{\rm g}$.
On se place en coordonnées cartésiennes avec $(Oz)$ dirigé vers le haut.

On a le chemin effectué $\overrightarrow{\rm OM}(t) = x(t) \overrightarrow{\rm u_x} + y(t) \overrightarrow{\rm u_y} + z(t) \overrightarrow{\rm u_z}$,
qu'on dérive (pour obtenir $d \overrightarrow{\rm r}$). On a donc $\delta W = \overrightarrow{\rm F} \cdot d \overrightarrow{\rm r} = -mg(z_2 - z_1)$.

Ainsi, pour un trajet quelconque entre 2 points d'altitude $z_1$ et $z_2$,
$W_{M_1 \to M_2}(\overrightarrow{\rm P}) = -mg(z_2 - z_1)$.
