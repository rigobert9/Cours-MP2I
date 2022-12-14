# Structures algébriques
## Loi de composition interne
### Loi de composition interne
> Soit $E$ un ensemble, une loi de composition interne sur $E$ est une application
> de $E \times E$ dans $E$.

Bien qu'on note ces opérations généralement avec une notation infixe, il s'agit
bien d'une application classique. On notera dans la suite du cours ces opérations
par des symboles $+, *, \times, \oplus, \otimes, \top$.

On utilise en général $*$ pour une loi indéfinie.

##### Exemple
Soit $E$ un ensemble muni d'une loi de composition interne $*$, on a donc
l'application $\begin{aligned} *: E \times E &\to E \\ (x,y) &\mapsto  x * y .\end{aligned}$.

En prenant 4 éléments de $E$ $a,b,c,d$, on ne peut pas donner de sens à
l'expression $a * b * c * d$ (car on ne connaît pas les propriétés de
l'opération : cette notation est valable uniquement pour une opération
associative). En ajoutant des parenthèses, on peut décider d'un sens
d'évaluation.

En notant $C_n$ le nombre de parenthésages possibles pour $a_1 * a_2 * \ldots * a_n$,
on a $C_2 = 1$, $C_3 = 2$, $C_4 = 5$, $C_5 = 14$ ...
On a une formule par récurrence, telle que $C_{n+1} = \sum\limits_{k = 1}^{n} C_k \times C_{n+1-k}$.
Il s'agit des nombres de Catalan.

### Propriétés des loi de composition interne

> Soit $E$ un ensemble muni d'une loi de composition interne $*$, on dit que la
> loi $*$ est associative si : $\forall (x,y,z) \in E^3, (x * y) * z = x * (y * z)$.

Dans ce cas, l'écriture sans parenthèses $x * y *z$ n'est pas ambigüe.

> On dit que deux éléments commutent pour la loi $*$ lorsque $x * y = y * x$.
> Si cette propriété est valide pour tous les éléments, alors la loi $*$ est
> commutative : $\forall (x,y) \in E^2, x * y = y * x$.

##### Exemples usuels
__Sommes et produits :__  Dans $\mathbb{N}, \mathbb{Z}, \mathbb{Q}, \mathbb{R}, \mathbb{C}$,
$+$ et $\times$ sont des loi de composition interne associatives et
commutatives.

La soustraction n'est en revanche pas commutative, pas associative, et n'est
même pas une loi de composition interne dans $\mathbb{N}$. La division n'est pas
non plus associative ou commutative.

__Composition d'applications :__ Soit $E$ un ensemble et $\mathcal{F}(E)$
l'ensemble des applications de $E$ dans $E$, la loi de composition $\circ$
est associative mais pas commutative en général. En revanche, l'identité est
toujours commutative avec les autres éléments. De même, $f$ commute avec
soi-même.

__Opérations ensemblistes :__ Soit $E$ un ensemble et $\mathcal{P}(E)$
l'ensemble de ses parties. Dans $\mathcal{P}(E)$, $\cup$ et $\cap$
sont des loi de composition interne associatives et commutatives.
La différence $A \setminus B$ n'est ni commutative ni associative,
et la différence symétrique est commutative et associative.

__Minimum et maximum :__ Soit $(E,  \preceq)$ un ensemble totalement ordonné,
alors les opérateurs $\begin{aligned} \text{min}: E \times E &\to E \\ (x,y) &\mapsto \left\{\begin{matrix} x \text{ x si } x \preceq y \\ y \text{ sinon} \end{matrix}\right. .\end{aligned}$
et $\text{max}$ sont des loi de composition interne associative et commutatives
dans $E$.

__PGCD et PPCM :__ Soit $\begin{aligned} \wedge: \mathbb{Z} \times \mathbb{Z} &\to \mathbb{Z} \\ (a,b) &\mapsto a \wedge b = \text{pgcd}(a,b) .\end{aligned}$
et $\text{ppcm} = \vee$ sont des loi de composition interne associatives et
commutatives.

__Extension aux applications :__ Soit $(E, \ast)$ un ensemble muni d'une loi de composition interne
$\ast$, et $X$ un ensemble quelconque. Dans l'ensemble $\mathcal{F}(X,E)$ des
applications de $X$ dans $E$, on peut définir une opération $\tilde{\ast}$ induite :
$\begin{aligned} \tilde{\ast}: \mathcal{F}(X,E) \times \mathcal{F}(X,E) &\to \mathcal{F}(X,E) \\ (f,g) &\mapsto f \tilde{\ast} g .\end{aligned}$,
où $\forall x \in X, (f \tilde{\ast} g)(x) = f(x) \ast g(x)$,
$\tilde{\ast}$ est une loi de composition interne de $\mathcal{F}(X,E)$.
De plus, si $\ast$ est associatives et commutative, alors $\tilde{\ast}$ l'est aussi.
On retrouve ce type d'opérations dans la somme et le produit de suites, et dans
l'addition de fonctions.

__Ensembles finis :__ On prend la relation de congruences dans $\mathbb{Z}$
modulo $n$ avec $n \in \mathbb{N}^{\ast}$ fixé, et la congruence est donc une
relation d'équivalence sur $\mathbb{Z}$. Il y donc $n$ classes d'équivalence
distinctes. On note $\mathbb{Z} / n \mathbb{Z}$ l'ensemble des classes
d'équivalence, qui est un ensemble fini à $n$ éléments.
On peut définir une addition $\tilde{+}$ et une multiplication
$\tilde{\times}$ telles que
$\begin{aligned} \tilde{+}: \mathbb{Z} / n\mathbb{Z} \times \mathbb{Z} / n\mathbb{Z} &\to \mathbb{Z} / n\mathbb{Z} \\ \dot{a}, \dot{b} &\mapsto \dot{a + b} .\end{aligned}$
et $\begin{aligned} \tilde{\times}: \mathbb{Z} / n\mathbb{Z} \times \mathbb{Z} / n\mathbb{Z} &\to \mathbb{Z} / n\mathbb{Z} \\ \dot{a}, \dot{b} &\mapsto \dot{a \times b} .\end{aligned}$.

### Éléments neutre et inversibilité
> Soit $\ast$ une loi de composition interne sur $E$, on dit que $e \in E$ est neutre
> par $\ast$ si $\forall x \in E, x \ast e = e \ast x = x$.

Si $\ast$ est commutative, il suffit de vérifier l'un des deux cas de figure. Bien
qu'ils puissent exister dans les $\ast$ non commutatives des éléments neutres à
droite et à gauche, on n'en traitera pas ici.

> S'il existe, l'élément neutre est unique.

En effet, on prouve simplement par l'absurde que si deux éléments $e_1$ et $e_2$
sont neutres, alors $e_1 \ast e_2 = e_1$ et $e_2 \ast e_1 = e_2$, donnant $e_1 = e_2$.

> Soit $\ast$ une loi de composition interne sur $E$, avec $\ast$ associative possédant
> un élément neutre $e$, on dira qu'un élément $x \in E$ est inversible pour $\ast$
> si $\exists y \in E, x \ast y = y \ast x = e$. Dans ce cas, $y$ est unique et on
> l'appelle inverse de $x$ pour $\ast$, et on note $y = x^{-1}$.

Si il existe $y_1, y_2 \in E$ tels que $x \ast y_1 = y_1 \ast x = e$
et $x \ast y_2 = y_2 \ast x = e$, alors $(y_1 \ast x) \ast y_2 = e \ast y_2 = y_2$
et $(y_2 \ast x) \ast y_1 = e \ast y_1 = y_1$. Par associativité du
$\ast$, ces deux opérations sont identiques, et donc $y_1 = y_2$.

##### Exemples
__Addition :__ L'élément neutre est toujours $0$. Les inversibles de l'addition
dans $\mathbb{N}$ sont $\{0\}$ et les inversibles dans $\mathbb{Z}$ sont $\mathbb{Z}$.

__Multiplication :__ L'élément neutre est $1$. Dans $\mathbb{N}$, les
inversibles sont $\{1\}$, dans $\mathbb{Z}$ ils sont
$\{-1, 1\}$, dans $\mathbb{Q}$ ils sont $\mathbb{Q}^{\ast} \setminus \{0\}$,
dans $\mathbb{R}$ ils sont $\mathbb{R} \setminus \{0\}$
et dans $\mathbb{C}$ ils sont $\mathbb{C} \setminus \{0\}$.

__Composition :__ Dans $(\mathcal{F}(E), 0)$, le neutre est $\text{id}_E$,
$f$ est inversible si $\exists g \in \mathcal{F}(E), f \circ g = g \circ f = \text{id}_E$,
auquel cas $f$ est bijective et admet une réciproque $g$.

__Opérations fonctionnelles :__ Dans $\mathcal{F}(\mathbb{R},\mathbb{R})$,
on peut définir la somme de fonctions (d'élément neutre $\tilde{0}$),
la multiplication de fonctions (d'élément neutre $\tilde{1}$),
et la composition (d'élément neutre $\text{id}_\mathbb{R}$).
Toute fonction $f: \mathbb{R} \to \mathbb{R}$ admet ainsi
un inverse par la somme $-f$, un inverse par la multiplication $\frac{1}{f}$
si $f$ ne s'annule pas, et un inverse $f^{-1}$ si $f$ est bijective.

### Opérations sur l'inversibilité
> Soit $\ast$ une loi de composition interne sur $E$, associative et de neutre
> $e$. Soient $x,y \in E$ deux éléments invisibles, alors $x \ast y$ est
> inversible et $(x \ast y)^{-1} = y^{-1} \ast x^{-1}$.

En effet, soient $x$ et $y$ inversibles, on a $x^{-1}, y^{-1} \in E$.
$(x \ast y) \ast (y^{-1} \ast x^{-1})$\
$= (x \ast (y \ast y^{-1}) \ast x^{-1})$\
$= (x \ast e \ast x^{-1})$\
$= (x \ast x^{-1})$\
$= e$\
et de même :
$(y^{-1} \ast x^{-1}) \ast (x \ast y)$\
$= (y^{-1} \ast (x^{-1} \ast x) \ast y)$\
$= (y^{-1} \ast e \ast y)$\
$= (y^{-1} \ast y)$\
$= e$

### Conventions d'écriture
Si la loi est notée $+$, le neutre sera noté $0$ (ou $0_E$)
et si $x$ est inversible par $+$, on notera son opposé $-x$.
En pratique, on prend toujours $+$ commutative.

Si la loi est notée $\times$, on notera son neutre $1$ (ou $1_E$)
et si $x$ est inversible, on notera $x^{-1}$ son inverse.

### Distributivité
> Soit $E$ muni de deux loi de composition interne $\oplus$ et
> $\otimes$, on dira que $\otimes$ est distributive sur $\oplus$
> si :
> $\forall (x,y,z) \in E^3, (x \oplus y) \otimes z = (x \otimes z) \oplus (y \otimes z)$
> $\land x \otimes (y \oplus z) = (x \otimes y) \oplus (x \otimes z)$.

On observe cette distributivité pour la multiplication sur l'addition dans $\mathbb{N}$,
mais aussi des opérations l'une sur l'autre dans le cas de $\cap$ et $\cup$ dans
les ensembles, $\lor$ et $\land$ dans les booléens ...

La composition de fonctions est distributive à droite mais pas à gauche sur la
somme de fonctions.

### Stabilité d'une loi
> Soit $\ast$ une loi de composition interne sur $E$, et $F \subset E$ une partie
> de $E$. $F$ est une partie stable par $\ast$ si
> $\forall (x,y) \in F^2, x \ast y \in F$.

Dans ce cas, on peut définir une loi $*$ induite qui est une loi de composition interne de $F$.

##### Exemples
$\mathbb{R}_{+}$ est stable par $+$ et $\times$, $\mathbb{R}_{-}$ est stable
pour $-$. $[-1;1]$ est stable par $\times$,
et $\mathbb{U}$ est stable par $\times$.

## Groupes
> Soit $G$ muni d'une loi de composition interne $\ast$,
> $(G,\ast)$ est une groupe si $\ast$ est associative, possède un neutre et tout
> élément de $G$ est inversible dans $G$.

Si $\ast$ est aussi commutative, alors $(G,\ast)$ est un groupe commutatif,
aussi appelé groupe Abélien.

$G$ n'est jamais vide, car il contient toujours un élément neutre. Le cas
dégénéré du plus petit groupe qu'on puisse construire est $(\{e\}, \ast)$.

##### Exemples
$\mathbb{N}$ ne peut pas former un groupe avec $+$ ou $\times$, car $1$ n'a pas
d'inverse dans le premier cas et $0$ n'a pas d'inverse dans le second.
De même, $\mathbb{R}$ ne peut pas former de groupes avec $\times$ car $0$ ne
possède pas d'inverse.

On a pour exemples de groupes :
- $(\mathbb{Z}, +), (\mathbb{Q}, +), (\mathbb{R}, +), \ldots$ (groupes abéliens)
- $(2\mathbb{Z}, +)$ (abélien)
- $(\mathbb{R}_{+}^{\ast}, \times), (\mathbb{R}^{\ast}, \times), (\mathbb{C}^{\ast}, \times)$ (abéliens)
- $(\mathbb{U}, \times)$ (abélien)
- $(\mathbb{U}_n, \times)$ (abéliens)

#### Groupe des permutations
> Soit $E$ un ensemble $(\mathcal{F}{E}, \circ)$ est l'ensemble des bijections de $E$
> dans $E$ et forme le groupe qu'on appelle groupe des permutations de $E$,
> noté $\mathfrak{S}(E)$

Le groupe des permutations d'un ensemble de cardinal $n$ contient
$n!$ éléments.

##### Exemple
En prenant le groupe des permutations d'un ensemble à 3 éléments $\{1, 2, 3\}$ contient 3
opérations "échangeant" $\tau_{12}, \tau_{23}, \tau{31}$
(comme $\tau_{12} \left|\begin{matrix} 1 \to 2 \\ 2 \to 1 \\ 3 \to 3 \end{matrix}\right.$),
l'identité $\text{id}$ et deux "rotations" $\sigma^1, \sigma^{-1}$.

$\text{id}$ est l'élément nombre, et les échanges sont leur propre inverse et
les rotations sont l'inverse l'une de l'autre, donc tous les éléments possèdent
un inverse.

En dressant un tableau des compositions possibles pour les éléments, on peut
voir que chaque élément apparaît une fois par ligne.

> Dans un groupe, il y a bijectivité de la loi de composition interne avec
> l'élément sur le groupe (à droite ou à gauche).

#### Itérés
> Soit $x \in G$, où $(G,\ast)$ est un groupe, on définit le $k$-ième itéré de $x$
> comme $x^k \left\{\begin{matrix} x^0 = e_G \\ x^{k+1} = x^{k} \ast x  \in G \end{matrix}\right.$.

> Puisque $x^{-1} \in G$, les itérés de $x^{-1}$ sont les itérés d'indice
> négatifs.

> $\forall (n,m) \in \mathbb{Z}^2$ :
> - $x^n \ast x^m = x^{n + m}$
> - $(x^n)^m = x^{n \ast m}$

Dans le cas où $(G,+)$, on note l'itéré $n$-ième de $x$
$nx$, avec $n \in \mathbb{Z}$. On réécrit la propriété précédente comme :
- $nx + mx = (n+m)x$
- $m(nx) = (n \times m)x$

> Si $x$ et $y$ commutent et $n \in \mathbb{Z}$, $(x \ast y)^n = x^n \ast y^n$.

### Sous-groupes
> Soit $(G, \ast)$ un groupe, $H \subset G$ une partie de $G$, $H$ est un
> sous-groupe de $G$ si
> - $H$ est non vide
> - $H$ est stable par $\ast$ : $\forall (x,y) \in H, x \ast y  \in H$
> - $H$ est stable pour passage à l'inverse : $\forall x \in H, x^{-1} \in H$

> Un sous-groupe de $(G,\ast)$ est un groupe

__Preuve :__ Soit $H$ un sous-groupe de $(G,\ast)$ :
- Comme $H$ est stable par $\ast$, alors $\ast$ est une loi de composition interne
  de $H$.
- $\ast$ est associative car $(G,\ast)$ est un groupe
- Tout élément de $H$ possède un inverse dans $H$, et comme $H$ est non vide et
  stable par $\ast$, alors $e_G$ est dans $H$.

> Soit $(G,\ast)$ un groupe et $H$ une partie non vide de $G$, $H$ est un
> sous-groupe si et seulement si $\forall (x,y) \in H^2, x \ast y^{-1}  \in H$.

__Preuve :__ $\Rightarrow$ Trivial\
$\Leftarrow$ Puisque $H$ est non vide, alors $\exists x \in H$, et donc
$x \ast x^{-1} \in H$, donc $e_G \in H$. Ainsi, pour $y \in H$,
$e \ast y^{-1} \in H$ donc $y^{-1} \in H$ (donnant la stabilité par l'inverse).
Pour $x \in H$ et $y^{-1} \in H$, $(y^{-1})^{-1} = y$, et donc
$x \ast (y^{-1})^{-1} \in H$ (stabilité par $\ast$).

Pour tout groupe $(G, \ast)$ on a toujours deux sous-groupes :
$G$ et $\{e_G\}$.

On a par exemple $(\mathbb{U}_n, \times)$ un sous-groupe de $(\mathbb{U}, \times)$,
qui est lui-même un sous-groupe de $(\mathbb{C}, \times)$.

#### Sous-groupes par opérations
Soit $(G, \ast)$ un groupe, et $H, K$ des sous-groupes de $G$. On cherche à
montrer que $H \cup K$ est nu sous-groupe si et seulement si $H \subset K \lor K \subset H$.\
$\Leftarrow$ Si $H \subset K$, alors $H \cup K = K$, et si $K \subset H$,
alors $H \cup K = H$, qui sont bien des sous-groupes de $G$.\
$\Rightarrow$ On suppose que $H \cup K$ est un groupe. Si $H \subset K$,
$H \cup K$ est bien un sous-groupe, et si $H \not\subset K$, alors
$\exists x \in H$ et $x \not\in K$. On veut montrer que $K \subset H$. Soit
$y \in K$, comme $x \in K \cup H$, $y \in K \cup H$, donc $x \ast y \in K \cup H$.
On suppose que $x \ast y \in K$, or $y \in K$,donc $y^{-1} \in K$, donc
$(x \ast y) \ast y^{-1}  \in K$, donc $x \in K$, ce qui est absurde.
$x \ast y  \in H$, et comme $x \in H$, $x^{-1} \in H$, et donc
$x^{-1} \ast (x \ast y) \in H$, donc $y \in H$, donc $K \subset H$.

> Une intersection quelconque entre deux sous-groupes est un sous-groupe.

__Preuve :__ Soit $(G,\ast)$ un groupe et $(H_i)_{i \in I}$ un famille de
sous-groupes de $G$. On pose $H = \bigcap\limits_{i \in I} H_i$. On cherche à
montrer que $H$ est un sous-groupe de $G$.\
Le neutre $e_G \in H_i$ pour tout i car $H_i$ est un sous-groupe de $G$,
donc $e_G \in \bigcap\limits_{i \in I} H_i$, donc $H$ n'est pas vide et contient
$e_G$.\
Pour $x,y \in H$, $\forall i \in I, x \in H_i \land y \in H_i$, or comme $H_i$
est un groupe, $x \ast y^{-1} \in H$, et donc $x \ast y^{-1} \in H$.
Par caractérisation des sous-groupes, $H$ est un sous-groupe de $H$.
