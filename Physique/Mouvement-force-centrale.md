# Mouvements à force centrale
## Forces centrales
### Définition
> Soit un point matériel $M$ dans un référentiel supposé galiléen, soumis à une
> force $F$, la force est dite centrale si elle peut se mettre sous la forme
> $F = F_r \overrightarrow{\rm u_r}$
> avec $\overrightarrow{\rm u_r} = \frac{\overrightarrow{\rm OM}}{\lVert \overrightarrow{\rm OM} \rVert}$ et
> $r = \lVert \overrightarrow{\rm OM} \rVert$.

C'est le cas par exemple de la force gravitationnelle, de l'intéraction entre un
proton et un électron, de la Terre et d'un satellite...

### Travail et énergie potentielle
Puisque par définition, le travail élémentaire est $\delta W = \overrightarrow{\rm F} \cdot d \overrightarrow{\rm r}$,
en coordonnées sphériques, $d \overrightarrow{\rm r} = d r \overrightarrow{\rm u_r} + r d \theta \overrightarrow{\rm u_\theta} + r \sin \theta \overrightarrow{\rm u_\varphi}$,
et donc $\delta W = F_r \times dr$.

Si on peut trouver une fonction $E_p(r)$ telle que $\delta W = -E_p(r)$,
alors la force est conservative, de forme $F_r(r) = - \frac{d E_p}{dr}$.

> Une force centrale et conservative est portée par le vecteur
> $\overrightarrow{\rm u_r}$, et ne dépend que $r$.

On peut reconnaître cette forme dans la force élastique par exemple :
$F_r(r) = -k (r - \ell_0)$, $E_p(r) = - \int F_r dr = \frac{k}{2} (r - \ell_0)^2 + C$,
avec $C$ une constante.

### Forces centrales newtoniennes
> Une force centrale est dite newtonienne si elle peut se représenter sous la
> forme $F_r = - \frac{K}{r^2}$ avec $K$ une constante.

Si $K < 0$, la force est répulsive, et si $K > 0$, la force est attractive.

C'est le cas de l'interaction gravitationnelle, avec $K = G m_1 m_2$,
et de l'interaction de Coulomb, avec $K = - \frac{q_1 q_2}{4 \pi \varepsilon_0 \varepsilon_1}$.

Dans ces cas, $\frac{d E_p}{dr} = \frac{K}{r^2}$, donc $E_p(r) = - \frac{K}{r} + C$.
À l'infini, $E_p(r = \infty) = 0$, donc $C = 0$, donnant $E_p(r) = - \frac{K}{r}$.

## Conservation du moment cinétique
D'après le théorème du moment cinétique, par rapport à un point $O$ fixe
dans un référentiel supposé galiléen,
$\frac{d \overrightarrow{\rm \sigma_O}(M)}{dt} = \overrightarrow{\rm OM} \wedge \overrightarrow{\rm F}$,
avec $\overrightarrow{\rm \sigma_O}(M) = \overrightarrow{\rm OM} \wedge m \overrightarrow{\rm v}$.
Or $\overrightarrow{\rm F}$ est une force centrale selon $\overrightarrow{\rm u_r}$
donc $\frac{d \overrightarrow{\rm \sigma_O}(M)}{dt} = \overrightarrow{\rm 0}$,
donc $\overrightarrow{\rm \sigma_O}(M)$ est un vecteur constant.

> $\overrightarrow{\rm \sigma_O}(M)$ est un vecteur constant.

### Mouvement plan
Soit un mouvement dans le plan du point $M$, à une position $\overrightarrow{\rm OM}$,
à une vitesse $\overrightarrow{\rm v}$. Le vecteur $\overrightarrow{\rm \sigma_O}(M)$
est orthogonal au plan.

Le mouvement de $M$ est contenu dans le plan perpendiculaire à $\overrightarrow{\rm \sigma_O}$
passant par $O$.
