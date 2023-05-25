# Circuit fixe dans un champ magnétique variable
## Induction et force électromotrice
### Flux propre
> Soit $\overrightarrow{B_p}$ créé par le courant $i$, le flux propre correspond à
> $\Phi_p = \iint \overrightarrow{B_p} \cdot d \overrightarrow{S}$.

> On définit l'induction $L$ comme $L = \frac{\Phi_p(t)}{i(t)}$, qu'on mesure en Henry.

##### Solénoïde infini
À l'intérieur d'une spire de solénoïde, on a le champ propre
$\overrightarrow{B_p}(t) = \mu_0 n i(t) \overrightarrow{e_z}$,
donnant le flux propre $\phi_p = \iint \overrightarrow{B_p} \cdot d \overrightarrow{S} = \overrightarrow{B_p} \cdot \overrightarrow{S}$
$= \mu_0 n i \times \pi R^2 = \mu_0 \pi R^2 \frac{N}{l} i$.

Le flux propre total à travers tout le solénoïde est alors
$\Phi_p = N \phi_p$, et on obtient en divisant par l'intensité l'inductance
$L = \mu_0 \pi R^2 \frac{N^2}{l}$. D'après la loi de Faraday,
$e = - \frac{d \Phi}{d t} = - L \frac{d i}{dt}$.

Cette tension, comme beaucoup dans ce chapitre, est exprimée en convention générateur.

### Détermination de la force électromagnétique
On plonge le circuit dans un champ magnétique extérieur, donnant un flux
$\Phi = \iint \overrightarrow{\rm B} \cdot d \overrightarrow{\rm S} = \iint (\overrightarrow{\rm B_\text{ext}} + \overrightarrow{\rm B_p}) \cdot d \overrightarrow{\rm S}$.
La force électromagnétique induite est alors $e = - \frac{d \Phi_\text{ext}}{dt} - \frac{d \Phi_p}{dt}$,
qu'on réécrit $e = - \frac{d \Phi_\text{ext}}{dt} - L \frac{d i}{dt}$.

Le flux propre ne sera pas négligé si :
- le flux extérieur est nul
- le circuit possède une bobine
- l'énoncé mentionne une inductance propre

### Interprétation énergétique
Ce calcul fait les hypothèses suivantes :
- Pour un conducteur en absence de champ extérieur, $\overrightarrow{\rm B_\text{ext}} = \overrightarrow{\rm 0}$
- Un conducteur alimenté par un générateur $E$
- On a une induction totale $L$
- On a la résistance interne $r$

D'après la loi des mailles, $E = r i - e = r i + L \frac{d i}{dt}$,
donnant l'expression de la puissance
$P_g = E i = r i^2 + \frac{d}{dt} [\frac{1}{2} L i^2] = P_J + P_\text{mag}$
(somme de la puissance dissipée par effet Joule et de la puissance magnétique).

Comme $P_\text{mag} = \frac{d E_\text{mag}}{dt}$, on a $E_\text{mag} = \frac{1}{2} L i^2$.

## Inductance mutuelle
### Couplage entre deux circuits
On se met dans le cas de deux circuits qui créent chacun un champ magnétique $\overrightarrow{\rm B_1}$
et $\overrightarrow{\rm B_2}$.

On obtient pour le premier circuit le flux $\Phi_1 = \Phi_{p_1} + \Phi_{\text{ext}_1}$.
On a $\Phi_{p_1} = \iint \overrightarrow{\rm B_1} \cdot d \overrightarrow{\rm S_1} = L_1 i_1$,
et $\Phi_{\text{ext}_1} = \Phi_{2 \to 1} = \iint \overrightarrow{\rm B_2} \cdot d \overrightarrow{\rm S_1}$.
Pour le second circuit, on obtient de même
$\Phi_2 = L_2 i_2$ et $\Phi_{\text{ext}_2} = \Phi_{1 \to 2} = \iint \overrightarrow{\rm B_1} \cdot d \overrightarrow{\rm S_2}$.

On note alors $M$ l'inductance mutuelle en henry des deux circuits, telle que
$\Phi_{1 \to 2} = M i_1$ et $\Phi_{2 \to 1} = M i_2$.
Par exemple, pour deux solénoïdes imbriqués, avec le solénoïde 2 enveloppant le
1, on a $\Phi_{2 \to 1} = \iint \overrightarrow{\rm B_2} \cdot d \overrightarrow{\rm S_1}$
$= (\mu_0 n_2 i_2 \overrightarrow{\rm e_z}) \cdot (N_1 \pi R_1^2 \overrightarrow{\rm e_z})$
$= (\mu_0 n_2 N_1 \pi R_1^2) i_2$, ce qui nous donne la valeur de $M$.

### Détermination de la force électromagnétique
$e_1 = - \frac{d \Phi_1}{dt} = - L_1 \frac{d i_1}{dt} - M \frac{d i_2}{dt}$
et $e_2 = - L_2 \frac{d i_2}{dt} - M \frac{d i_1}{dt}$.

### Interprétation énergétique
On fait l'hypothèse que le circuit $1$ est alimenté par
un générateur $E$ parcouru par une intensité $i_1$,
et que le circuit $2$ est parcouru par une intensité $i_2$ mais pas de tension
générée par un générateur (pas de résistance).

Ainsi, on a avec les forces électromotrices le système
$\left\{\begin{matrix} e_1 = - L_1 \frac{d i_1}{dt} - M \frac{d i_2}{dt} \\ 0 = - L_2 \frac{d i_2}{dt} - M \frac{d i_1}{dt} \end{matrix}\right.$.
D'après la loi des mailles, $E = r_1 i_1 - e_1$ et $0 = r_2 i_2 - e_2$, donnant
l'extension
$\left\{\begin{matrix} E = r_1 i_1 + L_1 \frac{d i_1}{dt} + M \frac{d i_2}{dt} \\ 0 = r_2 i_2 + L_2 \frac{d i_2}{dt} + M \frac{d i_1}{dt} \end{matrix}\right.$.
En ajoutant les deux équations multipliées respectivement par $i_1$ et $i_2$,
on obtient $E i_1 = r_1 i_1^2 + r_2 i_2^2 + \frac{d}{dt} [\frac{1}{2} L_1 i_1^2 + \frac{1}{2} L_2 i_2^2 + M i_1 i_2] = P_J + P_\text{mag}$.
Comme $P_\text{mag} = \frac{d E_\text{mag}}{dt}$, on obtient finalement
l'énergie magnétique $E_\text{mag} = \frac{1}{2} L_1 i_1^2 + \frac{1}{2} L_2 i_2^2 + M i_1 i_2$,
qui correspond à l'énergie magnétique stockée dans les circuits.

## Applications
### Le transformateur
#### Principe
Un transformateur correspond à un cadre ferromagnétique (qui conduit bien le
champ magnétique sans en avoir un lui-même, le flux est alors le même partout)
auquel on attache le fil primaire et le fil secondaire en bobines, traversés
respectivement par les tensions $u_1$ et $u_2$. La bobine primaire présente un
nombre $n_1$ de spires plus grand que le nombre $n_2$ de spires de la bobine
secondaire.

On a pour les forces électromotrices $\left\{\begin{matrix} e_1 = - u_1 = - N_1 \frac{d \varphi}{dt} \\ e_2 = - u_2 = - N_2 \frac{d \varphi}{dt} \end{matrix}\right.$,
donnant la relation $\frac{u_2}{u_1} = \frac{N_2}{N_1}$.
En négligeant les pertes par la résistance des bobines ou par les courants de
Foucault, la puissance fournie par la bobine primaire est égale à celle reçue
par la bobine secondaire, donnant $u_1 i_1 = - u_2 i_2$, nous donnant enfin
$\frac{i_2}{i_1} = \frac{-N_1}{N_2}$.

#### Usages
Un transformateur permet de diminuer ou d'augmenter la tension du courant,
ce qui permet de transporter par lignes à haute tension de jusqu'à $800 kV$ le courant afin
d'éviter les pertes par effet Joule.

### Courants de Foucault
Les courants de Foucault (les courants induits par le champ magnétique) sont
utilisés dans les chauffages par induction, dans le contrôle de matériaux ou
dans le freinage par induction.
