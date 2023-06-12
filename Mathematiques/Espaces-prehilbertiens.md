# Espaces préhilbertiens
Ici, on pourra utiliser des $\mathbb{R}$-espaces vectoriels, mais imagine se
limiter à un corps nul. Il faut néanmoins faire attention à bien rassembler tous
les prérequis, qui ne sont retrouvés souvent qu'avec $\mathbb{R}$.

## Produit scalaire
### Définition
> Un produit scalaire sur un espace vectoriel est une forme bilinéaire symétrique
> positive définie.

Il s'agit donc d'une forme bilinéaire avec $\forall (x,y) \in E^2, \varphi(y,x) = \overline{\varphi(x,y)}$
(symétrie avec conjugaison, symétrie pure pour les espaces réels), $\forall x
\in E, \varphi(x,x) \geq 0$ (positivité de la norme induite), $\forall x \in E,
(\varphi(x,x) = 0 \Rightarrow x = 0_E)$ (positivité définie de la norme
induite).

En commençant par vérifier la symétrie, il suffit de montrer la linéarité selon
l'une des variables pour conclure à la bilinéarité.

On note souvent le produit scalaire comme $\overrightarrow{\rm x} \cdot \overrightarrow{\rm y}$,
$(x | y)$, $<x,y>$ ou encore $<x|y>$.

Le produit scalaire canonique dans $\mathbb{R}^n$ correspond à la somme des
produits un à un des coefficients du tuple. En identifiant les éléments à des
matrices lignes, il s'agit du produit matriciel (let's go théorie de la
représentation) de $X^{\top} Y$.

### Espace préhilbertien / Espace euclidien
Un $\mathbb{R}$-espace vectoriel muni d'un produit scalaire est appelé espace
préhilbertien réel. Si de plus, $E$ est de dimension finie, on l'appelle espace
euclidien (valable seulement sur le corps $\mathbb{R}$).

Par exemple, $\mathbb{C}$ est un espace euclidien de dimension 2, avec pour
produit scalaire $<z,z'> = \Re(z \overline{z'})$. On peut aussi définir un
espace préhilbertien réel (de dimension infinie) par $<f,g> = \int\limits_{a}^{b} f(t) g(t) dt$.
$\mathbb{R}[X]$ est de même un espace préhilbertien réel pour le même produit
scalaire, mais on peut aussi utiliser la série (toujours convergente puisque les
polynômes sont toujours de degré fini) des $\sum\limits_{k = 0}^{+\infty} a_k b_k$.

## Norme associée à un produit scalaire
### Définition
> Soit $E$ un espace préhilbertien réel, la norme euclidienne associée
> est $\begin{aligned} \| . \|: E &\to \mathbb{R}_{+} \\ x &\mapsto \sqrt{<x,x>} .\end{aligned}$.

> On peut ainsi en définir la distance euclidienne
> $\begin{aligned} d: E \times E &\to \mathbb{R}_{+} \\ (x,y) &\mapsto \| x - y \| .\end{aligned}$.
> Celle-ci est bien une mesure sur l'espace vectoriel.

### Inégalité de Cauchy-Schwartz
> $\forall (x,y) \in E^2, |<x,y>| \leq \| x \| \times \| y \|$, et on a égalité si
> et seulement si les vecteurs sont colinéaires.

On obtient ainsi les inégalités classiques sur $\mathbb{R}^n$
et $\mathcal{C}^0([a,b],\mathbb{R})$.

__Preuve :__ Soit $(x,y) \in E^2$, on pose
$\forall \lambda \in \mathbb{R}, P(\lambda) = \| x + \lambda y \|^2$
une fonction de $\mathbb{R}_{+}^{\mathbb{R}}$.
De plus, $P(\lambda) = <x + \lambda y | x + \lambda y>$ (espace de Banach
complet : on utilise cette définition d'une norme définie à partir du produit
scalaire). Par bilinéarité, on développe en
$P(\lambda) = <x | x> + <x | \lambda y> + <\lambda y | x> + <\lambda y | \lambda y>$\
$= \| x \|^2 + 2 \lambda <x | y> + \lambda^2 \| y \|^2$\
Il s'agit d'un polynôme du second degré en $\lambda$.\
Si $<y | y> = 0$, alors $y = 0$ et on obtient immédiatement l'inégalité sur $<x|0>$.\
Si $y \neq 0$, et donc $<y|y> \neq 0$, alors $P$ est un polynôme du second degré
à valeurs positives, et son discriminant est donc inférieur à $0$,
or $\Delta = 4 <x|y>^2 - 4 <x|x> <y|y> \leq 0$, donnant l'inégalité voulue.

### Propriétés de la norme euclidienne
> La norme euclidienne est bien une norme, suivant donc les propriétés suivantes :
> - Séparation : $\| x \| = 0 \Rightarrow x = 0$ (par définition du produit scalaire)
> - Homogénéité : $\| \lambda x \| = \lambda \| x \|$ (par bilinéarité)
> - Positivité : $\| x \| \geq 0$
> - Inégalité triangulaire : $\| x + y \| \leq \| x \| + \| y \|$, avec égalité
>   quand $x$ et $y$ sont colinéaires et de même sens (donc qu'on peut avoir $y$
>   avec $\lambda x$ pour $\lambda \in \mathbb{R}_{+}$).

__Preuve :__ $\| x + y \|^2 = \| x \|^2 + 2 <x | y> + \| y \|^2$ (Bilinéarité),
or $<x|y> \leq |<x|y>| \leq \| x \| \| y \|$ (Cauchy-Schwartz),
donc $\| x + y \| \leq \| x \|^2 + 2 \| x \| \| y \| + \| y \|^2 \leq (\| x \| + \| y \|)^2$,
terminant l'inégalité par croissance de $\sqrt{.}$.\
Pour le cas d'égalité, celui-ci est vrai pour $y = 0$, et sinon, en remplaçant
$x$ par $\lambda y$, on obtient $<x|y> = \lambda \| x \|^2$.

Pour toute norme de façon générale, on peut obtenir comme corollaire de
l'inégalité triangulaire l'inégalité $|N(x) - N(y)| \leq N(x - y) \leq N(x) + N(y)$.
En effet, $N(x - y) \leq N(x) + N(- y) = N(x) + N(y)$,
et $N(x) = N((x - y) + y) \leq N(x - y) + N(y)$,
donc $N(x) - N(y) \leq N(x - y)$, et de même
$N((y - x) + x) - N(x) \leq N(y - x) = N(x - y)$.

### Formule de polarisation
Pour un espace préhilbertien réel (donc il existe un produit scalaire),
on peut obtenir le produit scalaire à partir de la norme induite par le produit
scalaire. En effet, $\forall x,y \in E, \frac{1}{2} (\| x + y \|^2 - \| x \|^2 - \| y \|^2) = <x|y>$
$= \frac{1}{2} (\| x \|^2 + \| y \|^2 - \| x - y \|^2)$
$= \frac{1}{4} (\| x + y \|^2 - \| x - y \|^2)$.

On a de plus l'identité du parallélogramme, $\| x + y \|^2 + \| x - y \|^2 = 2 (\| x \|^2 + \| y \|^2)$.

## Orthogonalité
### Vecteurs orthogonaux
> Deux vecteurs sont orthogonaux si leur produit scalaire est nul. On note $x \bot y$.

Seul le vecteur nul est orthogonal à lui même, et tout vecteur est orthogonal au
vecteur nul.

> Soit $(e_i)_{i \in I}$ une famille de vecteurs de $E$, cette famille est
> orthogonale si les vecteurs sont deux à deux orthogonaux.

> Toute famille orthogonale sans vecteur nul est libre.

__Preuve :__ Le produit scalaire de deux vecteurs liés est non nul si les deux
vecteurs sont non nuls.

> Théorème de Pythagore : Si une famille est orthogonale,
> $\| \sum\limits_{j \in J} e_j \|^2 = \sum\limits_{j \in J} \| e_j \|^2$.

La réciproque est vraie uniquement pour le cas $|I| = 2$ (le théorème classique
de Pythagore).

__Preuve :__ $\| \sum\limits_{j \in J} e_j \|^2 = \sum\limits_{k \in J, \ell \in J} <e_k|e_\ell>$
$= \sum\limits_{k \in J} <e_k|e_k> + 0 = \sum\limits_{k \in J} \| e_k \|^2$.

### Vecteurs orthonormés
> Un vecteur est normé/unitaire si $\| x \| = 1$.

> Une famille orthonormée est une famille orthogonale dont tous les vecteurs sont
> normés.

Ainsi, dans une famille orthonormée, $<e_i | e_j> = \delta_{i,j}$.
Si une famille est orthogonale, on peut la transformer en famille en normalisant
les vecteurs.

### Procédé d'orthonormalisation de Gram-Schmidt
Soit une famille $(e_i)_{i \in I}$, on en tire une famille orthonormée $(f_i)_{i \in I}$
et respectant étape par étape que l'espace généré soit le même pour les deux
familles. Pour construire $f_1$, on normalise le vecteurs, et pour les suivant,
on cherche $f_{k + 1} = e_{k + 1} + \sum\limits_{j = 1}^{n} \lambda_j f_j$ telle
que les vecteurs soient orthonormés. Les coefficients de cette combinaison
linéaire sont $\lambda_j = - <e_{k + 1}|f_j>$. On normalise enfin ce vecteur, et
on peut l'ajouter à la famille.

### Orthogonal d'une partie
> Soit $X \subset E$ une partie quelconque, on définit $X^{\bot} = \{a \in E \mid \forall x \in X, a \bot x\}$.

$\{0_E\}^{\bot} = E$, et $\{u\}^{\bot} = \text{Ker}(x \mapsto <x|u>)$ (c'est
donc un hyperplan car c'est le noyau d'une forme linéaire).

> Soit $X \subset E$ quelconque, $X^{\bot}$ est un SEV de $E$.

__Preuve :__ $X^{\bot}$ est l'intersection de formes linéaires correspondant aux
produits scalaires avec les éléments de $X$ et est donc une intersection
d'hyperplans, et donc un SEV.

> Si $A$ est un SEV de $E$, $A \subset (A^{\bot})^{\bot}$.

> Si $X \subset E$, $X^{\bot} = \text{Vect}(X)^{\bot}$.

__Lemme :__ $A \subset B \Rightarrow B^{\bot} \subset A^{\bot}$.
En effet, soit $A \subset B$, pour $x \in B^{\bot}$,
$\forall b \in B, x \bot b \Rightarrow \forall a \in A \subset B, x \bot a$,
donc $x \in A^{\bot}$.

__Preuve :__ $X \subset \text{Vect}(X)$ donc $\text{Vect}(X)^{\bot} \subset X^{\bot}$,
et $X \subset (X^{\bot})^{\bot}$,
donc $\text{Vect}(X) \subset \text{Vect}((X^{\bot})^\bot)$, et $X^{\bot \bot}$
est un SEV ($X^{\bot \bot} = \text{Vect}(X^{\bot \bot})$)
donc $\text{Vect}(X) \subset (X^{\bot})^{\bot}$,
donc $X^{\bot \bot \bot} \subset \text{Vect}(X)^{\bot}$,
or $X^{\bot} \subset X^{\bot \bot \bot}$, donnant l'inclusion inverse.

### SEV orthogonaux
> Le fait que deux sous-espaces vectoriels $F$ et $G$ soient orthogonaux
> est équivalent à $F \subset G^\bot$ et $G \subset F^{\bot}$.

Ainsi, si $F$ est un SEV de $E$, $F \bot F^{\bot}$, et comme leur intersection
est seulement le vecteur nul, $F \oplus F^{\bot}$.

## Orthogonalité en dimension finie
### Base orthonormée
> Soit $E$ un espace euclidien de dimension $n$, alors il existe une base
> orthonormée de $E$ à $n$ vecteurs.

__Preuve :__ $E$ est de dimension finie, donc admet une base $\mathcal{B}$ à $n$
vecteurs. Par orthonormalisation de Gram-Schmidt, on peut transformer la base,
qui est une famille libre, en famille orthonormée.

> Soit $E$ euclidien et $\mathcal{F}$ une famille orthonormée de vecteurs dans
> $E$, on peut la compléter en base orthonormée.

On peut utiliser ces bases pour obtenir bien plus facilement les coordonnées
d'un vecteur, car $x = \sum\limits_{i = 1}^{n} <x|e_i> e_i$ (projection sur
chacune des composantes de la base, toutes orthogonales). De plus, on peut ainsi
résumer le produit scalaire de deux vecteurs au produit scalaire canonique dans
$\mathbb{R}^n$.

### Supplémentaire orthogonal
> Soit $E$ un espace préhilbertien et $F$ un sous-espace de dimension finie de
> $E$, alors $F$ et $F^{\bot}$ sont supplémentaires dans $E$, et
> $E = F \oplus^{\bot} F^{\bot}$. On appelle $F^{\bot}$ LE supplémentaires
> orthogonal de $F$.

__Preuve :__ L'intersection nulle est toujours le cas. Soit $\mathcal{B}$
une base orthonormée de taille $m$ de $F$. On pose
$x = a + b \in F \times F^{\bot}$. On a alors
$a = \sum\limits_{i = 1}^{m} \lambda_i b_i$, et comme
$<a|e_j> = \lambda_j$, on a $a = \sum\limits_{i = 1}^{m} <a|e_i> e_i$,
et $<x|e_j> = <a + b|e_j> = <a|e_j> + <b|e_j> = \lambda_j + 0$.
On peut ainsi poser $b = x - a$.\
De même, on pose pour tout $x \in E$ $\left\{\begin{matrix} a = \sum\limits_{i = 1}^{m} <x|e_i> e_i \in F \\ b = x - a \end{matrix}\right.$,
et on peut voir que comme $<b|e_j> = <x|e_j> - <a|e_j> = <x|e_j> - <x|e_j> = 0$,
donc que $b \bot e_j$ pour tous les éléments de $\mathcal{B}$, et donc que
$b \in F^{\bot}$.

Ainsi, si $E$ est euclidien (donc de dimension finie) et $F$ un SEV de $E$,
$\text{dim}(F) + \text{dim}(F^{\bot}) = \text{dim}(E)$,
et $F^{\bot \bot} = F$.

__Preuve :__ Comme $F$ est forcément de dimension finie, on obtient la première
assertion directement. De plus, comme on sait que $F \subset F^{\bot \bot}$,
et qu'on peut avec deux itérations du théorème précédent
obtenir $\text{dim}(F) = \text{dim}(F^{\bot \bot})$, donnant l'égalité.

On peut ainsi prouver que toute matrice s'écrit de façon unique comme la somme
d'une matrice symétrique et d'une matrice antisymétrique. En effet, on a
$<A|B> = \text{Tr}(A^{\top} \times B)$ le produit canonique scalaire sur les
matrices. En effet, le produit de deux matrices, l'une symétrique et l'autre
antisymétrique, est à la fois la trace du produit et son inverse et est donc
zéro. Les matrices symétriques faisant ainsi partie de l'espace orthogonal des
matrices antisymétriques, et la dimension de $\mathcal{M}_n - \mathcal{A}_n$
étant celle de $S_n$, il y a égalité, et les deux espaces forment bien $\mathcal{M}_n$
par somme directe.

### Projection orthogonale
> La projection orthogonale sur $F$ est la projection vectorielle sur $F$
> parallèlement à $F^{\bot}$.

Il s'agit bien d'une projection (donc une application linéaire qui respecte les
identités de la projection). On calcule usuellement cette projection à partir du
produit scalaire.

La projection sur une droite $\text{Vect}(a)$ d'un vecteur $x$ est alors
$<x | \frac{a}{\| a \|} \frac{a}{\| a \|} = \frac{<x | a>}{<a | a>} a$.
On caractérise alors de même la projection orthogonale sur un hyperplan de
dimension finie, en la considérant comme l'identité moins la projection sur la
droite orthogonale.

### Distance à un sous-espace vectoriel
> Soit $E$ euclidien et $F$ un SEV de $E$, la distance de $x \in E$
> à $F$ est défini comme la borne inférieure de la distance entre $x$ et un
> vecteur de $F$.

> Soit $F$ un SEV de $E$ et $p_F$ la projection vectorielle dessus, on a
> $d(x,y) \geq d(x,p_F(x))$. On a l'égalité si et seulement si $y = p_F(x)$,
> donnant donc $d(x,F) = \| x - p_F(x) \| = \| p_{F^{\bot}}(x) \|$.

On peut d'ailleurs voir que la borne inférieure est atteinte, et donc qu'il
s'agit d'un minimum. Celui-ci est atteint en l'unique vecteur $p_F(x)$,
car pour $y \in F$, $x - y = (p_F(x) - y) + (x - p_F(x))$, donnant par Pythagore
$\| x - y \|^2 = \| p_F(x) - y \| + \| x - p_F(x) \|$, ce qui prouve que cette
distance est plus minimale en $p_F(x)$.
