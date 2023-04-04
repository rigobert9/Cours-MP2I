# Matrices et applications linéaires
## Matrices et dimension finie
### Matrice colonne pour un vecteur
> Soit $E$ un $\mathbb{K}$-EV de dimension finie tel que $n = \text{dim}(E)$
> On prend $\mathcal{B}$ une base de $E$, en laquelle tout vecteur se décompose.
> On appelle coordonnées de $x$ dans $\mathcal{B}$ ou matrice du vecteur dans
> $\mathcal{B}$ la matrice colonne contenant les facteurs de chaque élément de la
> base qui décomposent le vecteur, notée $\text{Mat}_\mathcal{B}(x)$.

> L'application $\begin{aligned} \text{Mat}_{\mathcal{B}}: E &\to \mathbb{K}^n \\ x &\mapsto \text{Mat}_{\mathcal{B}}(x) .\end{aligned}$
> est un isomorphisme.

### Matrice pour une famille de vecteurs
> Soit $\mathcal{F}$ une famille de $p$ vecteurs de $E$, $E$ est un
> $\mathbb{K}$-EV de dimension finie $n$ avec $\mathcal{B}$ une base de
> $E$. Pour tout $j \in [\![1;p]\!]$, le vecteur $v_j \in \mathcal{F}$
> est associé à la matrice colonne de sa décomposition en base $\mathcal{B}$.
> On définit alors la matrice de la famille $\mathcal{F}$ dans
> $\mathcal{B}$ comme la matrice de ces colonnes.

> Ainsi, on a $\text{Mat}_{\mathcal{B}}(\mathcal{F}) \in \mathcal{M}_{n,p}(\mathbb{K})$.

### Matrice d'une application linéaire
> Soient $E$ un $\mathbb{K}$-EV de dimension $p$ et $\mathcal{B}$ une base de $E$,
> et $F$ un $\mathbb{K}$-EV de dimension $n$ et $\mathcal{C}$ une base
> de $\mathcal{F}$, pour $u \in \mathcal{L}(E,F)$,
> $\text{Mat}_{\mathcal{B},\mathcal{C}}(u) = \text{Mat}_{\mathcal{C}}(u(\mathcal{B}))$.

### Matrice d'un endomorphisme
Soit $E$ un $\mathbb{K}$-EV de dimension finie $n$ et $\mathcal{B}$ une base de
$E$, soit $u \in \mathcal{L}(E)$, la matrice dans la base $\mathcal{B}$
de $u$ est la matrice $n \times n$ $\text{Mat}_{\mathcal{B},\mathcal{B}}(u)$.

### Calcul matriciel
Soit $E$ de dimension $p$ et de base $\mathcal{B}$
et $F$ de dimension $n$ et de base $\mathcal{C}$.
Pour $x \in E, X = \text{Mat}_{\mathcal{B}}(x)$.

> Soit $u \in \mathcal{L}(E,F)$, la matrice
> $\text{Mat}_{\mathcal{B},\mathcal{C}}(u) \in \mathcal{M}_{n,p}(\mathbb{K})$
> est l'unique matrice $A \in \mathcal{M}_{n,p}(\mathbb{K})$
> qui vérifie $\forall x \in E,\forall y \in F, y = u(x) \Leftrightarrow Y = AX$.

__Preuve :__
- Unicité : Si $A$ et $A'$ conviennent, alors pour toute colonne $X$, $AX = A'X$, donc $A = A'$.
- Existence : Soit $A = \text{Mat}_{\mathcal{B},\mathcal{C}}(u) = (a_{ij}) \in \mathcal{M}_{n,p}(\mathbb{K})$.
  Ainsi, $A = \text{Mat}_{\mathcal{C}}((u(e_i))_{[\![1;p]\!]})$,
  donc $\forall j \in [\![1;p]\!]$, $u(e_j) = \sum\limits_{i = 1}^{n} a_{ij} f_i$. En appliquant ceci
  à un vecteur $x \in E$, on a $y = u(x) \Leftrightarrow \forall i \in [\![1;n]\!], y_i = \sum\limits_{j = 1}^{p} a_{ij} x_j = L_i$,
  avec $L_i$ la ligne $i$ de la matrice $A$.

### Isomorphisme entre $\mathcal{L}(E,F)$ et $\mathcal{M}_{n,p}(\mathbb{K})$
Les dimensions correspondent bien, car $\text{dim}(\mathcal{L}(E,F)) = \text{dim}(E) \times \text{dim}(F)$.

> Il existe un isomorphisme $\varphi$ de $\mathcal{L}(E,F)$ à $\mathcal{M}_{n,p}(\mathbb{K})$
> (avec $\text{dim}(E) = n$ et $\text{dim}(F) = p$), qui correspond à la matrice
> du morphisme.

On vérifie facilement par les propriétés précédentes qu'il s'agit d'une
bijection linéaire.

> Soit $A \in \mathcal{M}_{n,p}(\mathbb{K})$, on définit $\begin{aligned} u: \mathbb{K}^p &\to \mathbb{K}^n \\ X &\mapsto AX .\end{aligned}$
> en identifiant $\mathbb{K}^p$ avec $\mathcal{M}_{p,1}(\mathbb{K})$ et
> $\mathbb{K}^n$ avec $\mathcal{M}_{n,1}(\mathbb{K})$, qui est l'application
> linéaire canoniquement associée.

### Composition et produit matriciel
> $\text{Mat}_{\mathcal{B}_E,\mathcal{B}_F}(v \circ u) = \text{Mat}_{\mathcal{B}_G,\mathcal{B}_G}(v) \times \text{Mat}_{\mathcal{B}_E,\mathcal{B}_F}(u)$

__Preuve :__ Soit $A = \text{Mat}_{\mathcal{B}_E, \mathcal{B}_F}(u)$ et $B = \text{Mat}_{\mathcal{B}_F,\mathcal{B}_G}(v)$.
Soit $x \in E$ et $y \in G$, $y = v \circ u(x)$
$\Leftrightarrow y = v(u(x))$
$\Leftrightarrow \left\{\begin{matrix} y = v(z) \\ z = u(x) \end{matrix}\right. \Leftrightarrow Y = BZ, Z = AX \Leftrightarrow Y = (BA) X$.

Ainsi, dans les endomorphismes, $\varphi$ est un isomorphisme de
$\mathbb{K}$-algèbre.
De plus, soit $A \in \mathcal{M}_n(\mathbb{K})$ et $u \in \mathcal{L}(\mathbb{K}^n)$ l'endomorphisme canoniquement associé à $A$ :
- $A^2 = A \Leftrightarrow u^2 = u \Leftrightarrow$ $u$ est un projecteur de $\mathbb{K}^n$
- $A^2 = I_n \Leftrightarrow u^2 = \text{id}_{\mathbb{K}^n} \Leftrightarrow$ $u$ est une symétrie de $\mathbb{K}^n$
- Une matrice nilpotente correspond à un endomorphisme nilpotent

### Inversibilité et bijectivité
> Soit $u \in \mathcal{L}(E,F)$ avec $\text{dim}(E) = \text{dim}(F)$. On prend $\mathcal{B}_E$ et
> $\mathcal{B}_F$ des bases de $E$ et $F$, $u$ est isomorphisme si et seulement si
> $\text{Mat}_{\mathcal{B}_E,\mathcal{B}_F}(u)$ est inversible, et dans ce cas,
> l'inverse de la matrice est associé à l'inverse de la fonction.

__Preuve :__ $\Rightarrow$ Si $u$ est isomorphisme, alors $u^{-1} \in \mathcal{L}(F,E)$,
et $u \circ u^{-1}$, donc la matrice associée à $u$ est bien inversible par
celle associée à $u^{-1}$ par conservation des inverses par isomorphisme d'algèbres.\
$\Leftarrow$ Idem.

> __Corollaire :__ Soit $u \in \mathcal{L}(E)$ avec $n = \text{dim}(E)$,
> $u \in \text{GL}(E) \Leftrightarrow \text{Mat}_{\mathcal{B}}(u) \in \text{GL}_n(\mathbb{K})$.

Ainsi, $\varphi$ est bien un morphisme de groupes entre ces deux groupes
linéaires (cela ne nous apporte rien mais nice).

> Soit $A \in \mathcal{M}_n(\mathbb{K})$, $\text{Ker}(A) = \{X \in \mathcal{M}_{n,1} \mid AX = 0\}$
> et $A$ est inversible si et seulement si $\text{Ker}(A) = \{0\}$
> si et seulement si $A$ est intègre.

__Preuve :__ On prend $u$ l'endomorphisme associé canoniquement à $A$,
et son noyau correspond bien à la caractérisation. De plus, si ce noyau est
réduit à la matrice nulle (donc au vecteur nul), $u$ est un endomorphisme
injectif et donc bijectif.
