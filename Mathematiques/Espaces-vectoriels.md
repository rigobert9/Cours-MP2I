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

Les équations différentielles linéaires homogènes forment un espace vectoriel,
et l'ensemble des solutions d'une équation linéaire forme un sous-espace
vectoriel de $\mathcal{C}^n(I,\mathbb{K})$.

## Combinaison linéaire
> Soit $E$ un $\mathbb{K}$-EV, et $(e_1,e_2,\ldots,e_n)$ une famille de $n$
> vecteurs de $E$, une combinaison linéaire de la famille $(e_1,e_2,\ldots,e_n)$
> est un vecteur $\sum\limits_{i = 1}^{n} \lambda_i \cdot e_i$, avec
> $\lambda_i \in \mathbb{K}^n$.

> Soit $E$ un $\mathbb{K}$-EV et $\mathcal{F} = (e_1,e_2,\ldots,e_n)$ une famille
> de vecteurs de $E$. On note $\text{Vect}_{\mathbb{K}}(\mathcal{F}) = \{\sum\limits_{i = 1}^{n} \lambda_i e_i \mid (\lambda_1,\ldots,\lambda_n) \in \mathbb{K}^n\}$.

$\text{Vect}_\mathbb{K}(\mathcal{F})$ est le plus petit sous-espace vectoriel
qui contient $\mathcal{F}$. On l'appelle l'espace vectoriel engendré par $\mathcal{F}$.

__Preuve :__
- $\text{Vect}(\mathcal{F}) \subset E$
- $0_E = \sum\limits_{i = 1}^{n} 0 \cdot e_i \in \text{Vect}(\mathcal{F})$
- Soient $u,v \in \text{Vect}(\mathcal{F})$ et $\lambda, \mu \in \mathbb{K}$,
  on peut facilement prouver la stabilité par combinaison linéaire.

Il s'agit du plus petit au sens de l'inclusion. Soit $H$ un SEV de $E$ qui
contient $\mathcal{F}$, or $H$ est un SEV donc il est stable par combinaison
linéaire, or $\mathcal{F} \subset H$, donc toute combinaison linéaire de vecteur
de $\mathcal{F}$ est dans $H$, donc $\text{Vect}(\mathcal{F}) \subset H$.

> Soit $F$ un SEV ed $E$ et $\mathcal{F} = (e_i)_{[\![1,n]\!]}$ des vecteurs de $E$,
> on dira que la famille $\mathcal{F}$ est génératrice de $F$ si $F = \text{Vect}(\mathcal{F})$.

On a alors $\mathbb{C} = \text{Vect}_{\mathbb{R}}(1,i)$.

### Intersection de SEV
Puisque les SEV portent la structure d'un sous-groupe, on a les même problèmes
sur l'union, et les mêmes propriétés conservées

> Soit $E$ un $\mathbb{K}$-EV et $(E_i)_{i \in I}$ une famille quelconque de SEV
> de $E$, alors $\bigcap\limits_{i \in  I} E_i$ est encore un SEV de $E$.

__Preuve :__
- $\bigcap\limits_{i \in  I} E_i \subset E$
- $\forall i \in I$, $E_i$ est un SEV donc $0_E \in E_i$, donc $0_e \in \bigcap\limits_{i \in  I} E_i$
- Soient $x,y \in \bigcap\limits_{i \in  I} E_i$ et $\lambda, \mu \in \mathbb{K}$,
  la combinaison linéaire est dans l'intersection.

> Soit $X$ une partie quelconque d'une $\mathbb{K}$-EV E,
> Il existe un plus petit sous-espace vectoriel qui contient $X$,
> qu'on note $\text{Vect}_{\mathbb{K}}(X) = \bigcap\limits_{i \in I} E_i$.

__Preuve :__ $E$ est déjà un SEV qui contient $X$.
On considère $(E_i)_i \in I$ l'ensemble de tous les SEV de E qui contiennent $X$
avec $I \neq \emptyset$ (car $E$ est dedans).
$\bigcap\limits_{i \in  I} E_i$ est alors un SEV de $E$ qui contient $X$ car
$\forall i \in I, X \subset E_i$. C'est le plus petit car c'est l'intersection de
tous (on peut en faire la preuve par l'absurde).

## Applications linéaires
Les applications linéaires correspondent aux homomorphismes d'EV, ou aux
morphismes dans la catégorie des EV.

> Soit $E, F, H$ des $\mathbb{K}$-EV, une application $f: E \to F$ est dite
> $\mathbb{K}$-linéaire si
> $\forall (x,y) \in E^2, \forall (\lambda,\mu) \in \mathbb{K}^2, f(\lambda x + \mu y) = \lambda f(x) + \mu f(y)$.

On note $\mathcal{L}_{\mathbb{K}}(E, F)$ l'ensemble de toutes les applications
linéaires de $E$ dans $F$.

La trace et la transposition sur les matrices sont des applications linéaires.
La conjugaison de complexes est une application $\mathbb{R}$-linéaire.

Puisque les applications linéaires sont des morphismes de groupe, le vecteur
neutre est conservé par l'application ($f(0_E) = 0_F$).

> Toute application linéaire transforme une combinaison linéaire en une
> combinaison linéaire des images.

### Applications linéaires particulières
Comme pour tout morphisme, on peut les caractériser avec des préfixes
supplémentaires :
- un endomorphisme est un morphisme d'un EV sur lui-même (on note alors $\mathcal{L}(E)$)
- un isomorphisme est un morphisme bijectif
- un automorphisme est la fusion des deux d'au-dessus (on note alors $\text{GL}(E)$)
- une forme linéaire est un morphisme vers le corps des scalaires de l'EV, et
  l'ensemble de ces formes linéaires est l'espace dual; l'espace double dual
  d'un EV est naturellement isomorphe à l'EV lui-même, en formant une fonction
  d'application d'un élément à une fonction pour chaque élément de l'EV (parfois
  noté $E^{\ast}$)

### Noyau et image
> Soit $f \in \mathcal{L}(E,F)$ et $E_1$ un SEV de $E$, $F_1$ un SEV de $F$.
> L'image directe $f(E_1)$ est un SEV de $F$ et l'image réciproque
> $f^{-1}(F_1)$ est un SEV de $E$.$$

__Preuve :__ Pour l'image directe, $E_1 \subset E \Rightarrow f(E_1) \subset f(E) \subset F$,
$f(0_E) = 0_F$ et $0_E \in E_1$, et pour tous $x = f(a) \in f(E_1)$
et $y = f(b) \in f(E_1)$, leur combinaison linéaire est bien dans $f(E_1)$.
Pour l'image réciproque, $0_F \in F_1 \Rightarrow 0_E \in f^{-1}(F_1)$,
et pour tous $x,y \in f^{-1}(F_1)$, la combinaison linéaire est dans $f^{-1}(F_1)$.

> Soit $f \in \mathcal{L}(E,F)$, l'image de $f$ est le SEV de $F$ défini par $\text{Im}(f) = f(E)$,
> et le noyau de $f$ est les SEV de $E$ défini par $\text{Ker}(f) = f^{-1}(\{0_E\})$.

> Soit $f \in \mathcal{L}(E,F)$, $f$ est surjective si et seulement si $\text{Im}(f) = F$,
> et $f$ est injective si et seulement si $\text{Ker}(f) = \{0_E\}$.

__Preuve :__ La première assertion correspond à la définition de la
surjectivité.\
Pour la seconde proposition :\
$\Rightarrow$ Si $f$ est injective, on a déjà $f(0_E) = 0_F$ puisque $f$ est
linéaire. Soit $x \in \text{Ker}(f)$, $f(x) = 0_F = f(0_E)$. Par injectivité, on
a $x = 0_E$.\
$\Leftarrow$ Si $\text{Ker}(f) = \{0_E\}$, et $x,y \in E \mid f(x) = f(y)$,
on a $f(x) - f(y) = 0_F \Leftrightarrow f(x - y) = 0_F$,
soit $x - y \in \text{Ker}(f) \Rightarrow x - y = 0_E$, donc
$x = y$.

Calculer le noyau revient à résoudre $f(x) = 0_E$, et calculer l'image
revient à pour tout $y \in F$ chercher à résoudre $f(x) = y$.
Pour calculer l'image, le plus efficace est alors d'utiliser les familles
génératrices.

> Soit $f \in \mathcal{L}(E,F)$ et soit $\mathcal{F} = (e_i)_{[\![0,n]\!]}$
> une famille génératrice de $E$, alors $\text{Im}(f) = \text{Vect}(f(e_i))_{[\![0,n]\!]}$.

__Preuve :__ On prouve que le calcul des images de la famille génératrice permet
par linéarité de reconstituer les images de tout $E$.

### Structure de $\mathcal{L}(E,F)$
> $\mathcal{L}(E,F)$ est un SEV de $\mathcal{F}(E,F)$

__Preuve :__ $\begin{aligned} \tilde{0}: E &\to F \\ x &\mapsto 0_F .\end{aligned}$
est dans $\mathcal{L}(E,F)$, et soient $f,g \in \mathcal{L}(E,F)$
et $\lambda,\mu \in \mathbb{K}$, on veut montrer $\lambda f + \mu g \in \mathcal{L}(E,F)$.
On pose $h = \lambda f + \mu g$, et soit $x,y \in E$, $\alpha, \beta \in \mathbb{K}$,
$h(\alpha x + \beta y) = (\lambda f + \mu g)(\alpha x + \beta y)$\
$= \alpha h(x) + \beta h(y)$, donc $h \in \mathcal{L}(E,F)$.

> Soient $f \in \mathcal{L}(E,F)$ et $g \in \mathcal{L}(F,G)$,
> alors $g \circ f \in \mathcal{L}(E,G)$.

__Preuve :__ Si $x,y \in E$ et $\lambda,\mu \in \mathbb{K}$, $(g \circ f)(\lambda x + \mu y) = \lambda g(f(x)) + \mu g(f(y))$.

Si $f \in \mathcal{L}(E)$, on peut définir le $n$-ième itéré par la composition
de l'endomorphisme $f$.

> Bilinéarité de la composition : Soit $\lambda,\mu \in \mathbb{K}$, en
> $f, g, h$ linéaires :
> - $h \circ (\lambda f + \mu g) = \lambda (h \circ f) + \mu (h \circ g)$ (vrai
>   par linéarité de $h$)
> - $(\lambda f + \mu g) \circ h = \lambda (f \circ h) + \mu (g \circ h)$ (vrai
>   pour toute application)

Soit $h \in \mathcal{L}(F,G)$, $\begin{aligned} G_h: \mathcal{L}(E,F) &\to \mathcal{L}(E,G) \\ f &\mapsto h \circ f .\end{aligned}$
est linéaire, et soit $h \in \mathcal{L}(E,F)$, $\begin{aligned} D_h: \mathcal{L}(F,G) &\to \mathcal{L}(E,G) \\ f &\mapsto f \circ h .\end{aligned}$
est linéaire.

> La réciproque d'un isomorphisme est un isomorphisme, et
> si $f \in \mathcal{L}(E,F)$ est bijective, $f^{-1} \in \mathcal{L}(F,E)$.

__Preuve :__ Si $f$ est bijective de $E$ dans $F$, sa réciproque $f^{-1}$ est
bijective de $F$ dans $E$. Soient $a,b \in F$ et $\lambda,\mu \in \mathbb{K}$,
on pose $x = f^{-1}(a)$ et $y = f^{-1}(b) \in E$. Or, $f(\lambda x + \mu y) = \lambda f(x) + \mu f(y) = \lambda a + \mu b$,
donc en composante par $f^{-1}$, on obtient $\lambda x + \mu y = f^{-1}(\lambda a + \mu b)$,
donc $f^{-1}$ est linéaire.

### Structures
> Les endomorphismes de $E$ forment un anneau $(\mathcal{L}(E),+,\circ)$
> et un $\mathbb{K}$-EV $(\mathcal{L}(E),+,\cdot)$, donc une
> $\mathbb{K}$-algèbre.

$(\mathcal{L}(E),+)$ est un groupe abélien de neutre $\tilde{0}$,
et forme un anneau avec $\circ$ distributive sur $+$,
de neutre $\text{id}_E$.

> Le groupe des inversible pour $\circ$ de l'anneau $(\mathcal{L}(E),+,\circ)$
> est $\text{GL}(E)$, le groupe pour $\circ$ des automorphismes.
