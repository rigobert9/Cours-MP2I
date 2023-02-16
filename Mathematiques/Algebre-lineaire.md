# Algèbre linéaire
## Espaces vectoriels
### Définitions
Soit $E$ un ensemble muni d'une loi de composition interne $+$ et et d'une
loi de composition externe $\cdot : \mathbb{K} \times E \to E$.

> On dit que $(E,+,\cdot)$ est un $\mathbb{K}$-espace vectoriel si
> $(E,+)$ est un groupe abélien de neutre $0_E$, et si les quatre propriétés
> suivantes sont vérifiées, $\forall \lambda, \mu \in \mathbb{K}^2, \forall u,v \in E^2$ :
> - $(\lambda + \mu) \cdot u = \lambda \cdot u + \mu \cdot u$
> - $\lambda \cdot (u + v) = \lambda \cdot u + \mu \cdot u$
> - $\lambda \cdot (\mu \cdot u) = (\lambda \times \mu) \cdot u$
> - $1 \cdot u = u$

Ces propriétés caractérisent aussi les modules sur un anneau, une généralisation
des espaces vectoriels aux anneaux. Les éléments de $E$ sont appelés vecteurs,
et les éléments de $\mathbb{K}$ sont appelées scalaires.

Il est important de remarquer que l'on a pas défini de produit dans ces espaces
vectoriels. Le produit vectoriel ou d'autres produits particuliers qui vérifient
la propriété de bilinéarité permettent de former une algèbre sur l'espace
vectoriel (distributivité et compatibilité comme on s'y attendrait).

### Exemples
$(\mathbb{K},+,\times)$ est un $\mathbb{K}$-espace vectoriel.

$(\mathbb{C},+,\cdot)$ est un $\mathbb{R}$-espace vectoriel, en prenant
$\lambda \cdot z = \lambda \times z$.

$(\mathbb{K}^n, +,\cdot)$ est un $\mathbb{K}$-espace vectoriel, $n \in \mathbb{N}^{\ast}$,
$\mathbb{K}$ est l'ensemble des $n$-uplets d'éléments de $\mathbb{K}$ (on peut
l'identifier avec les matrices colonnes $\mathcal{M}_{n,1}(\mathbb{K})$).
On peut choisir pour cette addition l'addition indice à indice des $n$-uplets,
et $(\mathbb{K}^n,+)$ est ainsi bien un groupe abélien ayant pour neutre le
$n$-uplet avec tous les indices à $0$. L'opposé est toujours le $n$-uplet
contenant, indice par indice, l'inverse de l'original.
Pour la loi externe, on multiplie un par un tous les éléments par le scalaire.
On vérifie pour ces cas les 4 propriétés à la main.

$(\mathbb{K}[X],+,\cdot)$ est un $\mathbb{K}$-espace vectoriel avec les mêmes
opérations que pour les $n$-uplets.

Soit $(E,+,\cdot)$ un $\mathbb{K}$-espace vectoriel, et $X$ un ensemble
quelconque, $(\mathcal{F}(X,F),+,\cdot)$ est un $\mathbb{K}$-espace
vectoriel, muni de l'addition et de la multiplication point à point.

$(\mathcal{M}_{n,p}(\mathbb{K}),+,\cdot)$ est un $\mathbb{K}$-espace vectoriel.

De plus, les fonctions d'un espace vectoriel vers ses scalaires
(espace dual) est un espace vectoriel, et les suites sont des
espaces vectoriels. L'espace dual d'un espace dual est isomorphe à l'espace
vectoriel d'origine, donc on ne peut pas vraiment créer des nouveaux espaces
vectoriels supplémentaires dans le sens où il seront équivalent au précédent.

Pour deux $\mathbb{K}$-espaces vectoriels $(E,+,\cdot)$ et $(F,+,\cdot)$,
on peut construire le $\mathbb{K}$-espace vectoriel produit,
tel que $(u,v) + (u',v') = (u + u', v + v')$,
avec le neutre $(0_E, 0_F)$, l'opposé de chaque objet l'objet indice par indice,
et la multiplication par un scalaire la multiplication indice par indice.
On peut généraliser cette construction pour $n$ $\mathbb{K}$-espaces vectoriels.

### Calculs dans un EV
> Soit $E$ un $\mathbb{K}$-EV, et $\lambda,\lambda_1,\ldots,\lambda_n \in \mathbb{K}$
> et $u,u_1,\ldots,u_n \in E$ :
> - $\sum\limits_{k = 1}^{n} (\lambda_k \cdot u) = (\sum\limits_{k = 1}^{n} \lambda_k) \cdot u$
> - $\sum\limits_{k = 1}^{n} (\lambda \cdot u_k) = \lambda \cdot (\sum\limits_{k = 1}^{n} u_k)$
> - $0_\mathbb{K} \cdot u = 0_E$ et $\lambda \cdot 0_E = 0_E$
> - $(-1_{\mathbb{K}}) \cdot u = -u$
> - $\lambda \cdot u = 0_E \Leftrightarrow (\lambda = 0_\mathbb{K}) \lor u = 0_E$

__Preuve :__ On prouve les deux premiers résultats par récurrence sur $n \geq 1$.
On prouve la troisième propriété comme pour les anneaux, en décomposant
$0_{\mathbb{K}}$ en $0_\mathbb{K} + 0_\mathbb{K}$. De même, on prouve que
$(-1) \cdot u$ est l'inverse de $u$ en additionnant les deux et en factorisant.
Enfin, la dernière propriété se vérifie facilement pour le cas $\lambda = 0$,
et sinon on utilise l'inversibilité de $\lambda$ pour montrer que
$1 \cdot u = 0_E$.

### Sous-espace vectoriel
> Si $u,v \in E$ et $\lambda,\mu \in \mathbb{K}$, le vecteur $\lambda u + \mu v \in E$
> est appelé une combinaison linéaire de $u$ et $v$.

> Soit $E$ un $\mathbb{K}$-EV te $F \subset E$, on dira que $F$ est un sous-EV de
> $E$ si $F$ est non vide, et si $F$ est stable par combinaison linéaire.

On a les SEV triviaux de $E$, $\{0_E, E\}$.

> $F$ est un SEV de $E$ si et seulement si le vecteur nul est dans $F$ et si
> $F$ est stable par combinaison linéaire.

__Preuve :__ Si $F \neq \emptyset$, alors $\exists u \in F$, donc $0 \cdot u \in F$.

On peut donc invalider la structure de sous-espace vectoriel de certain exemples
en testant le présence du vecteur nul, par exemple pour $F = \{(x,y) \in \mathbb{R}^2 \mid 2x + y = 1\}$.
On peut voir ici que $F$ est contraint par une contrainte affine qui contredit
la structure d'espace vectoriel, contrairement à la contrainte linéaire pour
$G = \{(x,y) \in \mathbb{R}^2 \mid 2x + y = 0\}$

> Si $F$ est un SEV de $E$, alors $F$ est un $\mathbb{K}$-EV.

__Preuve :__ $F \subset E$ et $E$ est un EV, donc les axiomes de calcul dans
$E$ sont vrais dans $F$ et $+$ et $\cdot$ sont stables dans $F$.

### Exemples variés
$\mathbb{R}$ et $i\mathbb{R}$ sont des SEV supplémentaires dans $\mathbb{C}$.

$\mathbb{K}_n[X]$ (les polynômes en dessous d'un certain degré), sont un SEV de
$\mathbb{K}[X]$.

Les suites bornées sont un SEV de $\mathbb{K}^{\mathbb{N}}$.

Les suites convergentes sont un SEV de $\mathbb{K}^{\mathbb{N}}$.

Les classes de continuité et de dérivation de fonctions sont des SEV de $\mathcal{F}(I,\mathbb{K})$.

Les matrices triangulaires, diagonales, symétrique et antisymétriques sont des
SEV de $\mathcal{M}_n(\mathbb{K})$, mais $GL_n(\mathbb{K})$ n'en est pas un car
il ne contient pas le $0$.
