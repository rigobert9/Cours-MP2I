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

Dans $\mathbb{Z}$, les sous-groupes $A$ sont tels que $0 \in A$
et $\forall x,y \in A, x - y \in A$. Ainsi, $\forall n \in \mathbb{N}$,
$n\mathbb{Z}$ est un groupes, mais les impairs ne sont pas stables par
l'addition. $\{0\}$ et $\mathbb{Z}$ sont des sous-groupes triviaux.

> Les sous-groupes de $(\mathbb{Z}, +)$ sont exactement les $n\mathbb{Z}$, avec $n \in \mathbb{N}$

__Preuve :__ Les propositions sont bien des sous-groupes de $\mathbb{Z}$, et il
reste à prouver qu'ils sont les seuls. Soit $H$ un sous-groupe de $\mathbb{Z}$,
qui contient $0$ (l'élément neutre). Si $H = \{0\}$, alors on a $n = 0$,
et sinon, alors il existe $a \neq 0 \in \mathbb{Z}$ tel que $a \in H$.
Puisque $a \in H$, $-a  \in H$. L'ensemble $H \cap \mathbb{N}^{\ast}$ est non
vide (il contient $|a|$), donc il possède $n = \text{min}(H \cap \mathbb{N}^{\ast})$.\
On montre donc que si $n \in H$, alors tous les itérés de $n$ appartiennent à H,
donc $\forall k \in \mathbb{Z}, nk \in H$, soit $n\mathbb{Z} \subset H$.\
Pour l'inclusion inverse, soit $h \in H$, la division euclidienne de $h$ par $n$
donne $\exists qins\mathbb{Z}, r \in \mathbb{Z} \mid h = nq + r$ avec
$0 \leq r < n$, or $r = h - nq$. Puisque $H$ est stable, $h \in H$ et
$nq \in n\mathbb{Z} \subset H$, alors $r \in H$, donc $r \in H \cap \mathbb{N}$.
Or, $n = \text{min}(H \cap \mathbb{N}^{\ast})$ et $r < n$, donc $r = 0$,
donc $h = nq \in n\mathbb{Z}$, en donc $H \subset n\mathbb{Z}$.

### Morphismes de groupes
> Soit deux groupes $(G,\ast)$ et $(H,\otimes)$, on dit que $f: G \to H$ est un
> morphisme de groupes si $\forall (x,y) \in G^2, f(x \ast y) = f(x) \otimes f(y)$.

> Si $f: G \to H$ est un morphisme de groupes, alors
> - $f(e_G) = e_H$
> - $\forall x \in G, f(x^{-1}) = f(x)^{-1}$

__Preuve :__
- $f(e_G) = f(e_G \ast e_G) = f(e_G) \otimes f(e_G)$, or $f(e_G) \in H$, donc
  admet un inverse $f(e_G)^{-1} \in H$, soit
  $f(e_G)^{-1} \otimes f(e_G) = f(e_G)^{-1} \otimes f(e_G) \otimes f(e_G)$
  $\Leftrightarrow e_H = e_H \otimes f(e_G) \Leftrightarrow e_H = f(e_G)$
- Pour $x \in G, x^{-1} \in G, x \ast x^{-1} = e_G$. Ainsi, $f(x \ast x^{-1})$
  $= f(e_G)$. On a donc $f(x) \otimes f(x^{-1}) = e_H$, or $f(x) \in H$,
  donc $f(x)^{-1} \in H$, $f(x)^{-1} \otimes f(x) \otimes f(x^{-1}) = f(x)^{-1} \otimes e_H$,
  donc $f(x)^{-1} = f(x^{-1})$

L'exponentielle est un morphisme de $(\mathbb{R},+)$ (de neutre 0)
dans $(\mathbb{R}_{+}^{\ast}, \times)$ (de neutre 1).

> - Un isomorphisme est un morphisme bijectif
> - Un endomorphisme est un morphisme de $G$ dans $G$
> - Un automorphisme est un endomorphisme bijectif (endo- et isomorphisme)

> La composée de deux morphismes de groupes est un morphisme de groupes

__Preuve :__ Soit $f : (G, \ast) \to (H, \otimes)$ et $g : (H, \otimes) \to (K, \top)$
des morphismes de groupes, alors $g \circ f : (G, \ast) \to (K, \top)$.
Soient $x,y \in G, (g \circ f)(x \ast y) = g(f(x \ast y)) = g(f(x) \otimes f(y))$
$= g(f(x)) \top g(f(y)) = g \circ f(x) \top g \circ f(y)$

> La réciproque d'un isomorphisme est un isomorphisme

__Preuve :__ Soit $f : (G,x) \to (H, \otimes)$ un morphisme bijectif,
la réciproque $f^{-1} : H \to G$, on cherche à évaluer $f^{-1}(h_1 \otimes h_2)$.
Soient $h_1, h_2 \in H$, $f^{-1}(h_1), f^{-1}(h_2) \in G$.
On note $x = f^{-1}(h_1)$ et $y = f^{-1}(h_2)$, et on a donc
$f(x \ast y) = f(x) \otimes f(y) = h_1 \otimes h_2$. $f$ est bijective,
donc $x \ast y = f^{-1}(h_1 \otimes h_2)$.

> L'image directe d'un sous-groupe par un morphisme est un sous-groupe

> L'image réciproque d'un sous-groupe par un morphisme est un sous-groupe

L'image d'un sous-groupe $G_1$ de $G$ par $f: (G, \ast) \to (H, \otimes)$, son
image est $f(G_1) = \{f(x) \mid x \in G_1\}$.

__Preuve :__ On montre que $f(G_1)$ est un sous-groupe de $H$ :
- $e_g \in G_1$ car $G_1$ est un groupe, et donc $f(e_G) = e_H$,
  donc $e_H \in f(G_1)$
- Soient $a,b \in f(G_1)$, il existe $x,y \in G_1$ tels que
  $\left\{\begin{matrix} a = f(x) \\ b = f(y) \end{matrix}\right.$,
  alors $a \otimes b^{-1} = f(x) \otimes f(y)^{-1} = f(x) \otimes f(y^{-1})$
  $= f(x \ast y^{-1})$. Or, $x,y \in G_1$ donc $x \ast y^{-1} \in G_1$,
  donc $a \otimes b^{-1} = f(x \ast y^{-1}) \in f(G_1)$.
  Donc $f(G_1)$ est un sous-groupe de H

__Preuve :__ On cherche à montrer que $f^{-1}(H_1)$ est un sous-groupe de $G$.
Comme dans la preuve précédente, $e_G \in f^{-1}(H_1)$. On prouve la stabilité
des opérations.\
Soient $x,y \in f^{-1}(H_1)$, on a $f(x \ast y^{-1}) = f(x) \otimes f(y)^{-1}$,
ce qui par stabilité du sous-groupe est dans $H_1$, donc $x \ast y^{-1} \in f^{-1}(H_1)$.

> L'image d'un groupe par un morphisme est un sous-groupe du groupe d'arrivée.

L'image du groupe sera le groupe d'arrivée si et seulement si le morphisme est surjectif.

> Soit $f:G \to H$ un morphisme, le noyau de $f$ est l'ensemble des éléments $x$ de $G$
> tels que $f(x) = e_H$. C'est donc l'ensemble $\{x \in G \mid f(x) = e_H\} = \{x \in G \mid f(x) \in \{e_H\}\}$,
> soit $x \in f^{-1}(\{e_H\})$.

On note le noyau d'un morphisme $\text{Ker}(f)$. Puisque $\{e_H\}$ est un
sous-groupe de $H$, $\text{Ker}(f)$ est un sous-groupe de $G$.

> Le morphisme de groupe $f$ est injectif si et seulement si $\text{Ker}(f) = \{e_G\}$.

__Preuve :__ $\Rightarrow$ Trivial\
$\Leftarrow$ On suppose que $\text{Ker}(f) = \{e_G\}$, et on cherche à montrer
l'injectivité de $f$. Soient $a,b \in G$, tels que $f(a) = f(b)$. Ainsi,
$f(a) \otimes (f(b))^{-1} = e_H \Leftrightarrow f(a \ast b^{-1}) = e_H$,
donc $a \ast b^{-1} \in \text{Ker}(f) = \{x \in G \mid g(x) = e_H\}$.
Or, $\text{Ker}(f) = \{e_G\}$, donc $a \ast b^{-1} = e_G$, donc $a = b$.

## Structure d'anneau
### Définition
> Soit $A$ un ensemble muni de deux lois de composition interne $+, \times$. On
> dit que $(A,+,\times)$ est un anneau si :
> - $(A,+)$ est un groupe abélien de neutre $0_A$
> - $\times$ est associative, de neutre $1_A$
> - $\times$ est distributive sur $+$

> Si de plus $\times$ est commutative, on parle d'anneau commutatif.

Dans un anneau, un élément $a \in A$ n'a pas forcément d'inverse pour $\times$,
donc $a^{-1}$ n'a pas toujours de sens.

Par exemple, les matrices carrées sont un anneau non commutatif aux élément
parfois sans inverse par $\times$.

### Calculs dans un anneau
> $\forall (a,b,c) \in A^3$ :
> - $a \times 0_A = 0_A \times a = 0_A$
> - $(-a) \times b = a \times (-b) = -(a \times b)$
> - $(-a) \times (-b) = a \times b$
> - $a \times (b - c) = a \times b - a \times c$
> - $(a - b) \times c = a \times c - b \times c$

__Preuves :__
- $(a \times 0_A) = a \times (0_A + 0_A) = (a \times 0_A) + (a \times 0_A)$. On
  soustrait $(a \times 0_A)$, donnant $0_A = a \times 0_A$.
- $(-a) \times b + (a \times b) = (-a + a) \times b = 0_A \times b = 0_A$

Puisque $+$ et $\times$ sont associatives, on peut généraliser les notations
$\sum$ et $\prod$ dans les anneaux.
Soient $a_1, a_2,\ldots, a_n \in A$, où $(A,+,\times)$ est un anneau, on note
$a_1 + a_2 + \ldots + a_n = \sum\limits_{i = 1}^{n} a_i$ et
$a_1 \times a_2 \times \ldots \times a_n = \prod\limits_{i = 1}^{n} a_i$.

On considère, par convention, que si la somme est vide, elle est égale à $0_A$,
et que si un produit est vide, il est égal à $1_A$.

Par la distributivité de $\times$ sur $+$, on a
$b \times (\sum\limits_{i \in I} a_i) = \sum\limits_{i \in I} (b \times a_i)$
et $(\sum\limits_{i \in I} a_i) \times b = \sum\limits_{i \in I} (a_i \times b)$.
De même, $(\sum\limits_{i = 1}^{n} a_i) \times (\sum\limits_{i = 1}^{n} b_i)$
$= \sum\limits_{i = 1}^{n} (a_i \times \sum\limits_{j = 1}^{m} b_j)$
$= \sum\limits_{i = 1}^{n} \sum\limits_{j = 1}^{m} a_i \times b_j$
$= \sum\limits_{\begin{matrix} 1 \leq i \leq n \\ 1 \leq j \leq m \end{matrix}} a_i \times b_j$.
Des simplifications sont possible lorsqu'on a commutativité.

> Soient $a,b \in A$ qui commutent, soit $ab = ba$, où $(A,+,\times)$ est un
> anneau. Soit $n \in \mathbb{N}$ (sur les itérés par $\times$) :
> - $(a \times b)^n = a^n \times b^n$
> - $(a + b)^n = \sum\limits_{k = 0}^{n} \binom{n}{k} a^k b^{n - k}$
> - $a^{n+1} - b^{n+1} = (a - b) \times \sum\limits_{k = 0}^{n} a^k b^{n - k}$

En particulier, $a$ en $1_A$ commutent toujours, nous permettant d'appliquer ces
formules avec cet élément neutre.

On ne peut rien conclure en général de $a \times b = 0_A$ (par exemple, dans
l'anneau $\mathbb{Z}/6\mathbb{Z},+,\times$ ou les matrices de dimension $2 \times 2$).

> Un anneau $A$ est dit intègre si
> $\forall (a,b) \in A^2, ab = 0_A \Rightarrow (a = 0_A \lor b = 0_A)$.

Par exemple, $(\mathbb{R}[x],+,\times)$ (les polynômes à coefficients réels), $(\mathbb{Z},+,\times)$
sont des anneaux commutatifs intègres, $(\mathbb{Z}/6\mathbb{Z},+,\times)$ est
un anneau commutatif non intègre et $(\mathcal{M}_2(\mathbb{R}),+,\times)$
(les matrices réelles $2 \times 2$) est un anneau non commutatif et non intègre.

Ainsi, dans un anneau intègre, $ab = ac$\
$\Leftrightarrow ab - ac = 0_A$\
$\Leftrightarrow a \times (b - c) = 0_A$\
Par intégrité, soit $a = 0_A$, soit $b - c = 0_A \Leftrightarrow b = c$.

### Inversibles dans un anneau
> Soit $(A,+,\times)$ un anneau, l'ensemble des éléments inversibles de l'anneau
> $A$ forme un groupe multiplicatif (pour la loi $\times$), qu'on note $U(A)$
> ou $A^{\ast}$, le groupe des inversibles de l'anneau.

On peut le récapituler par $U(A) = \{a \in A \mid \exists b \in A, ab = ba = 1_A\}$.

__Preuves :__ Puisque $1_A$ est inversible par lui-même, $1_A \in U(A)$,
donc $U(A)$ contient le neutre pour $\times$. La loi $\times$ est associative,
et est bien une loi loi de composition interne. En effet, si $a,b \in U(A)$,
$a$ et $b$ sont inversibles, donc $ab$ est inversible et $(a \times b)^{-1}$
$= b^{-1} \times a^{-1} \in A$, donc $ab \in U(A)$. $\times$ est donc une loi de composition interne
dans $U(A)$. Le groupe est stable par passage à l'inverse car si $a \in U(A)$,
$a$ est inversible et $(a^{-1})^{-1} = a$, donc $a^{-1}$ est inversible, donc
$a^{-1} \in U(A)$.

Dans l'anneau $(\mathbb{Z},+,\times)$, on a $U(\mathbb{Z}) = \{-1,1\}$,
pour $(\mathbb{R},+,\times)$, $U(\mathbb{R}) = \mathbb{R}^{\ast}$.

### Sous-anneau
> Soit $(A,+,\times)$ un anneau, $B$ est un sous-anneau de $A$ si :
> - $(B,+)$ est un sous-groupe de $A$
> - $1_A \in B$
> - $\forall (a,b) \in B^2, a \times b \in B$

> Si $B$ est un sous-anneau, alors $B$ est un anneau.

__Preuve :__ $(B,+)$ est un sous-groupe, et donc est un groupe,
$1_A$ est le neutre pour $\times$, $\times$ est une loi de composition interne
dans $B$, et $\times$ est associative et distributive sur $+$.

On prend par exemple l'anneau $\mathbb{Z}[\sqrt{2}] = \{a + b\sqrt{2}, (a,b) \in \mathbb{Z}^2\}$,
on on cherche à montrer que $\mathbb{Z}[\sqrt{2}]$ est un anneau pour
$+,\times$.
- $\mathbb{Z}[\sqrt{2}] \subset \mathbb{R}$ et $(\mathbb{R},+,\times)$ est un
  anneau
- $1 = 1 + 0 \sqrt{2} \in \mathbb{Z}[\sqrt{2}]$ (neutre pour $\times$)
- Pour $x = a + b\sqrt{2}$ et $y = c + d\sqrt{2} \in \mathbb{Z}[\sqrt{2}]$
  $x + y \in \mathbb{Z}[\sqrt{2}]$ et $x \times y \in \mathbb{Z}[\sqrt{2}]$
- $x - y \in \mathbb{Z}[\sqrt{2}]$ (permet de prouver l'inversibilité)
- $\mathbb{Z}[\sqrt{2}]$ est donc un sous-anneau de $\mathbb{R}$, et est donc un
  anneau

### Morphismes d'anneau
> Soient $(A,+,\times)$ et $(B,\oplus,\otimes)$ deux anneaux, l'application
> $f:A \to B$ est un morphisme d'anneaux si $\forall (x,y) \in A^2$,
> $\left\{\begin{matrix} f(x+y) = f(x) \oplus f(y) \\ f(1_A) = 1_B \\ f(x \times y) = f(x) \otimes f(y) \end{matrix}\right.$

## Structure de corps
> Soit $K$ muni de deux loi de composition interne $+$ et $\times$,
> $(K,+,\times)$ est un corps si :
> - $(K,+,\times)$ est un anneau commutatif (donc $\times$ est aussi commutative)
> - Tout élément non nul est inverse par $\times$

Si $K$ est un corps, le groupe des inversibles de l'anneau $K$ est
$K \setminus \{0\}$.

Des exemples de corps sont $(\mathbb{R},+,\times)$, $(\mathbb{C},+,\times)$
et $(\mathbb{Q},+,\times)$.

> L'ensemble $L$ est un sous-corps du corps $(K,+,\times)$ si
> - $L$ est un sous-anneau de $K$
> - $\forall x \in L \setminus \{0\}, x^{-1} \in L$
