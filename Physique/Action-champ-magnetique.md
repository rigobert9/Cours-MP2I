# Action d'un champ magnétique
## Force de Laplace
### Expression
On représente un conducteur par une courbe $\mathcal{C}$ de $D$ à $F$,
parcourue par le courant $i$, et qui en chaque point $M$ possède ainsi un
déplacement infinitésimal $d \overrightarrow{\rm l}$.

On définit la force de Laplace par sa différentielle.

> $d \overrightarrow{\rm F_L} = i d \overrightarrow{\rm l} \wedge \overrightarrow{\rm B}$

On a donc $\overrightarrow{\rm F_L} = \int\limits_\mathcal{C} i d \overrightarrow{\rm l} \wedge \overrightarrow{\rm B}$,
ou encore $\overrightarrow{\rm F_L}(t) = i(t) \int\limits_\mathcal{C} d \overrightarrow{\rm l}(M,t) \wedge \overrightarrow{\rm B}(M,t)$.
Si $\overrightarrow{\rm B}$ est uniforme on peut simplifier en
$\overrightarrow{\rm F_L}(t) = i(t) \overrightarrow{\rm B} \wedge \int\limits_{D}^{F} d \overrightarrow{\rm OM} = i \overrightarrow{\rm DF} \wedge \overrightarrow{\rm B}$.

##### Exemple : Pendule pesant
Soit un pendule pesant de longueur $L$, tournant autour d'une liaison pivot
parfaite, tenant à une ligne conductrice parcourue par $i$, nous donnant $d \overrightarrow{\rm F_L} = i d \overrightarrow{\rm l} \wedge \overrightarrow{\rm B}$
$= - i d r B \overrightarrow{\rm e_\theta}$,
donc $\overrightarrow{\rm F_L} = - i B \int\limits_{0}^{L} d \overrightarrow{\rm r} \overrightarrow{\rm e_\theta}$
$= - i B L \overrightarrow{\rm e_\theta}$.
