# Théorème du moment cinétique
Il s'agit d'un outil géométrique adapté aux systèmes en rotation.

## Produit vectoriel
### Définition géométrique
> Pour deux vecteurs $\overrightarrow{\rm A}$ et $\overrightarrow{\rm B}$ est
> défini comme
> $\overrightarrow{\rm A} \wedge \overrightarrow{\rm B} = \|\overrightarrow{\rm A}\| \cdot \lVert \overrightarrow{\rm B} \rVert \cdot \sin \theta \cdot \overrightarrow{\rm u}$.

### Définition algébrique
> Dans une base orthonormée directe, pour les 3 bases normées $\overrightarrow{\rm u_1}, \overrightarrow{\rm u_2}, \overrightarrow{\rm u_3}$,
> on a :
> - $\overrightarrow{\rm u_1} \wedge \overrightarrow{\rm u_2} = \overrightarrow{\rm u_3}$
> - $\overrightarrow{\rm u_2} \wedge \overrightarrow{\rm u_3} = \overrightarrow{\rm u_1}$
> - $\overrightarrow{\rm u_3} \wedge \overrightarrow{\rm u_1} = \overrightarrow{\rm u_2}$

Soient deux vecteurs $\overrightarrow{\rm A}$ et $\overrightarrow{\rm B}$
quelconques, exprimés dans la base orthonormée directe $\overrightarrow{\rm u_1}, \overrightarrow{\rm u_2}, \overrightarrow{\rm u_3}$,
on a $\overrightarrow{\rm A} \wedge \overrightarrow{\rm B}$
$\left\(\begin{matrix} a_1 \\ a_2 \\ a_3 \end{matrix}\right) \wedge \left\(\begin{matrix} b_1 \\ b_2 \\ b_3 \end{matrix}\right)$
$= \left\(\begin{matrix} a_2 b_3 - a_3 b_2 \\ a_3 b_1 - a_1 b_3 \\ a_1 b_2 - a_2 b_1 \end{matrix}\right)$

On a de plus $\frac{d}{dt} [\overrightarrow{\rm A}(t) \wedge \overrightarrow{\rm B}(t)] = \frac{d \overrightarrow{\rm A}}{dt} \wedge \overrightarrow{\rm B} + \overrightarrow{\rm A} \wedge \frac{d \overrightarrow{\rm B}}{dt}$.

### Propriétés
- Anticommutativité : $\overrightarrow{\rm A} \wedge \overrightarrow{\rm B} = - \overrightarrow{\rm B} \wedge A$
- Distributivité : $\overrightarrow{\rm A} \wedge (\overrightarrow{\rm B} + \overrightarrow{\rm C}) = \overrightarrow{\rm A} \wedge \overrightarrow{\rm B} + \overrightarrow{\rm A} \wedge \overrightarrow{\rm C}$
- Condition de colinéarité : $\overrightarrow{\rm A} \wedge \overrightarrow{\rm B} = \overrightarrow{\rm 0}$ si et seulement si les vecteurs sont colinéaires
- Double produit vectoriel : $\overrightarrow{\rm A} \wedge (\overrightarrow{\rm B} \wedge \overrightarrow{\rm C}) = (\overrightarrow{\rm A} \cdot \overrightarrow{\rm C}) \overrightarrow{\rm B} = (\overrightarrow{\rm A} \cdot \overrightarrow{\rm B}) \overrightarrow{\rm C}$

Le produit vectoriel n'est pas associatif.

## Moment cinétique d'un point matériel
### Définition
#### Moment cinétique
> On a la quantité de mouvement $\overrightarrow{\rm \sigma_0}(M) = \overrightarrow{\rm L_0}(M) = \overrightarrow{\rm OM} \wedge \overrightarrow{\rm P}$,
> où $\overrightarrow{\rm P} = m \overrightarrow{\rm v}$ la quantité de
> mouvement.

Ce moment cinétique correspond à des Joules par secondes, de dimension
$[L M L T^{-1}] = [M L^2 T^{-1}]$.

Pour un point $O'$ quelconque,
$\overrightarrow{\rm \sigma_{O'}}(M) = \overrightarrow{\rm O'M} \wedge m \overrightarrow{\rm v} = (\overrightarrow{\rm O'O} + \overrightarrow{\rm OM}) \wedge m \overrightarrow{\rm v}
= \overrightarrow{\rm O'O} \wedge m \overrightarrow{\rm v} + \overrightarrow{\rm \sigma_O}(M)$.

Le moment cinétique par rapport à l'axe $\Delta$ est
$\sigma_{\Delta}(M) = \overrightarrow{\rm \sigma_O}(M) \cdot \overrightarrow{\rm u}$

La valuer de $\sigma_\Delta$ est indépendante du choix du point $O$ sur l'axe.

__Preuve :__ $\overrightarrow{\rm \sigma_O} = \overrightarrow{\rm O'O} \wedge m \overrightarrow{\rm v} + \overrightarrow{\rm \sigma_O}$.
Or $O' \in \Delta$ et $\overrightarrow{\rm O'O}$ est colinéaire à $\overrightarrow{\rm u}$.
$\overrightarrow{\rm \sigma_{O'}} \cdot \overrightarrow{\rm u}$
$= (\overrightarrow{\rm O'O} \wedge m\overrightarrow{\rm v}) \cdot \overrightarrow{\rm u} + \overrightarrow{\rm \sigma_O} \cdot \overrightarrow{\rm u}$
$= \overrightarrow{\rm \sigma_O} \cdot \overrightarrow{\rm u}$

Comme $\sigma_\Delta$ est un scalaire, on peut étudier le signe :
- Si $\sigma_\Delta > 0$, $M$ tourne autour de $\Delta$ dans le sens de la règle
  de tire-bouchon
- Sinon, $M$ tourne autour de $\Delta$ dans l'autre sens

### Théorème du moment critique
#### Énoncé et démonstration
> Soit un point matériel $M$ de masse $m$ dans un référentiel supposé galiléen,
> le moment cinétique par rapport au point $O$ fixe est
> $\overrightarrow{\rm \sigma_O}(M) = \overrightarrow{\rm OM} \wedge \overrightarrow{\rm P}$.

En dérivant par rapport au temps :
$\frac{d}{dt} \overrightarrow{\rm \sigma_O}(M)$
$= \frac{d \overrightarrow{\rm OM}}{dt} \wedge \overrightarrow{\rm P} + \overrightarrow{\rm OM} \wedge \frac{d \overrightarrow{\rm P}}{dt}$
$= \overrightarrow{\rm v} \wedge (m \overrightarrow{\rm v}) + \overrightarrow{\rm OM} \wedge (\sum \overrightarrow{\rm F_\text{ext}})$
$= \sum\limits_{i = 1}^{n} \overrightarrow{\rm OM} \wedge \overrightarrow{\rm F_\text{ext}}$

> Le moment d'une force $\overrightarrow{\rm F}$ appliqué au point $M$ par rapport
> au point $O$ fixe, $\mathcal{M_O}(\overrightarrow{\rm F}) = \overrightarrow{\rm OM} \wedge \overrightarrow{\rm F}$.
