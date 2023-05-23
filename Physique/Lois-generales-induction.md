# Lois générales de l'induction
## Flux d'un vecteur à travers une surface
### Vecteur surface
Le vecteur surface élémentaire $\overrightarrow{\rm n}(M,t)$ au point
$d S(M,t)$ d'une surface $S(t)$ donne, pour le vecteur $d \overrightarrow{\rm S}(M,t) = d S(M,t) \overrightarrow{\rm n}(M,t)$,
le vecteur surface $\overrightarrow{\rm S}(t) = \iint d \overrightarrow{\rm S}(M,t)$.
Si $\overrightarrow{\rm n}$ ne dépend pas du point $M$, $\overrightarrow{\rm S}(t) = S(t) \overrightarrow{\rm n}(t)$.

### Surface orientée par un contour
Pour une surface orientée, le vecteur normal est orthogonal à la surface vers le
haut en prenant la surface orientée dans le sens trigonométrique.

### Flux à travers une surface
Soit $S$ une surface orientée, le flux de $\overrightarrow{\rm B}$ à travers $S$
vaut $\Phi(t) = \iint \overrightarrow{\rm B}(M,t) \cdot d \overrightarrow{\rm S}(M,t)$.

On exprime le flux en weber, avec $1 Wb = 1 T \cdot m^2$. Si le champ
magnétique est uniforme, $\Phi = \overrightarrow{\rm B} \iint d \overrightarrow{\rm S} = \overrightarrow{\rm B} \cdot \overrightarrow{\rm S}$.

#### Exemple : Solénoïde
On a $\overrightarrow{\rm B} = \mu_0 n i \overrightarrow{\rm e_z} = B \overrightarrow{\rm e_z}$.
Le flux à travers une spire est de $\varphi = \overrightarrow{\rm B} \cdot \overrightarrow{\rm S} = \overrightarrow{\rm B} \cdot (\pi R^2 \overrightarrow{\rm e_z})$
$= \pi R^2 B$.
Ainsi, le flux du champ à travers l'ensemble de solénoïde est $N \varphi = N \varphi R^2 B$.

## Lois de Lenz et de Faraday
### Constatations expérimentales
On bouge un aimant par rapport à une spire en circuit fermé.
- Si l'aimant et le circuit sont immobiles, $i = 0$
- Si le circuit est immobile et si on éloigne l'aimant, $i > 0$
- Si l'aimant est immobile et si on approche le circuit, $i < 0$
- Si on éloigne le circuit, $i > 0$

On modélise la spire par un générateur de Thévenin, avec un générateur parfait
de tension et une résistance.

### Loi de Lenz
Le champ magnétique de l'aimant entraine un courant dans le circuit que l’on
nomme courant induit. Ce courant crée lui même un champ magnétique que l’on
nomme champ induit. Le champ magnétique induit s'oppose à celui de l'aimant.

### Loi de Faraday
