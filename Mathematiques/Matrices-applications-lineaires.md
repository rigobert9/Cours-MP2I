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

### Rang d'une matrice
> Le rang d'une matrice $A \in \mathcal{M}_{n,p}$ est le rang de la famille de ses
> colonnes.

Ce rang correspond bien au rang de l'application représentée par la matrice, car
il s'agit du rang de la famille obtenue par la base du domaine.

On peut facilement réappliquer les propriétés trouvées sur le rang d'une application linéaire sur
les matrices les représentant : on a ainsi pour $A \in \mathcal{M}_{n,p}, \text{rg}(A) \leq \text{min}(n,p)$,
les propriétés sur le rang de la multiplication de matrices (sur la composition de fonctions).
Les matrices inversibles sont le neutre dans le rang (si $A$ est inversible, $\text{rg}(AB) = \text{rg}(BA) = \text{rg}(B)$).

On obtient aussi la conservation du rang de la matrice par les opération
élémentaires autorisées par le pivot de Gauss, mais celles-ci marchent aussi
sur ses lignes.

Pour trouver le rang d'une matrice, on prend ainsi chaque coefficient diagonal,
puis on annule tout les coefficients en-dessous sur la colonne, puis les
coefficients à sa droite sur la ligne. Ainsi, le nombre de coefficients non
nuls obtenus par cette procédure correspond au rang de la matrice.

À la façon du pivot de Gauss (mais en ayant agi sur les lignes comme les colonnes),
il existe alors des matrices inversibles $P \in \text{GL}_n(\mathbb{K})$ et
$Q \in \text{GL}_p(\mathbb{K})$ pour tout matrice $A \in \mathcal{M}_{n,p}$ telles que
$PAQ = \begin{pmatrix} I_r & 0 \\ 0 & 0 \end{pmatrix}$, avec $r$ le rang de $A$.

> $\text{rg}(A) = \text{rg}(A^{T})$

__Preuve :__ Il existe pour $A$ de rang $r$ des matrices inversibles $P$ et $Q$
telles que $PAQ = \begin{pmatrix} I_r & 0 \\ 0 & 0 \end{pmatrix} = J_r^{(n,p)}$.
En transposant, on obtient $(J_r^{(n,p)})^{T} = (PAQ)^{T}$
$\Leftrightarrow J_r^{(p,n)} = Q^{T} A^{T} P^{T}$, donc le rang de $A^{T}$
qui est égal à celui de cette multiplication puisque $Q^{T}$ et  $P^{T}$ sont inversibles,
est celui de $J_r^{(p,n)} = r$.

> On appelle $\lambda \in \mathbb{R}$ une valeur propre d'une application
> linéaire $f$ s'il existe un vecteur $u$ non nul dans le domaine tel que $f(u) =
> \lambda u$.

$\lambda$ est valeur propre de $f$ si et seulement si $\text{Ker}(f - \lambda \text{id}) \neq \{0\}$
si et seulement si $f - \lambda \text{id}$ n'est pas bijective si et seulement si
$f - \lambda \text{id}$ est de rang différent de la dimension du domaine.

## Changement de base
### Matrice de passage
> Soit $E$ un EV de dimension $n$, et $\mathcal{B}$ et $\mathcal{B'}$ des bases de $E$,
> on appelle matrice de passage de $\mathcal{B}$ à $\mathcal{B'}$ la matrice
> $P_\mathcal{B}^{\mathcal{B'}} = \text{Mat}_{\mathcal{B}}(\mathcal{B'})$.

> Si $P$ est la matrice de passage de $\mathcal{B}$ à $\mathcal{B'}$,
> $P \in \text{GL}_n(\mathbb{K})$ et $P^{-1} = P_{\mathcal{B'}}^{\mathcal{B}}$.

__Preuve :__ Il s'agit respectivement des matrices
$\text{Mat}_{\mathcal{B'},\mathcal{B}}(\text{id})$ et $\text{Mat}_{\mathcal{B},\mathcal{B'}}(\text{id})$,
donc leur multiplication est l'identité.

> Soit $x \in E$, $\text{Mat}_{\mathcal{B}}(x) = P_{\mathcal{B}}^{\mathcal{B'}} \text{Mat}_{\mathcal{B'}}(x)$.

__Preuve :__ Par la même caractérisation que dans la preuve précédente, en écrivant
$P_{\mathcal{B}}^{\mathcal{B'}} = \text{Mat}_{\mathcal{B},\mathcal{B'}}(\text{id})$
et les matrices d'un vecteur correspondant aux matrices de la fonction constante dans une base de ce vecteur.

> Soit $u \in \mathcal{L}(E,F)$ avec $\mathcal{B},\mathcal{B'}$ deux bases de $E$ et
> $\mathcal{C},\mathcal{C'}$ deux bases de $F$,
> on a $\text{Mat}_{\mathcal{B'},\mathcal{C'}}(u) = (P_{\mathcal{C}^{\mathcal{C'}}})^{-1} \text{Mat}_{\mathcal{B},\mathcal{C}}(u) P_{\mathcal{B}}^{\mathcal{B'}}$.

__Preuves :__ On obtient la matrice en traduisant sous deux bases différentes $y = u(x)$,
puis en les reliant.
Autrement, on peut utiliser les fonctions identité dans une base ou dans l'autre pour représenter les matrices.

> Soit $u \in \mathcal{L}(E)$ avec $\mathcal{B},\mathcal{B'}$ deux bases de $E$,
> on a $\text{Mat}_{\mathcal{B'},\mathcal{B'}}(u) = (P_{\mathcal{B}^{\mathcal{B'}}})^{-1} \text{Mat}_{\mathcal{B},\mathcal{B}}(u) P_{\mathcal{B}}^{\mathcal{B'}}$.

### Matrices équivalentes
> Soit $A,B \in \mathcal{M}_{n,p}$, $A$ est équivalente à $B$ si
> $\exists Q \in \text{GL}_n(\mathbb{K}), \exists P \in \text{GL}_p(\mathbb{K}), A = Q B P$.
> On note $A \approx B$.

Il s'agit d'une relation d'équivalence (réflexivité par la matrice identité, symétrie par
inversibilité des matrices inversibles, et transitivité par stabilité des matrices inversibles).

Pour montrer que $A$ et $B$ sont équivalentes, on montre que $A$ et $B$ représentent la même application linéaire
$u \in \mathcal{L}(\mathbb{K}^p,\mathbb{K}^n)$ dans des bases différentes.

> $A \in \mathcal{M}_{n,p}(\mathbb{K})$ est de rang $r$ si et seulement si
> $A \approx J_r$, avec $J_r = \begin{pmatrix} I_r & 0 \\ 0 & 0 \end{pmatrix}$.

Il y a $\text{min}(m,p) + 1$ classes d'équivalences pour $\approx$ sur $\mathcal{M}_{n,p}(\mathbb{K})$.

> Soient $(A,B) \in \mathcal{M}_{n,p}(\mathbb{K})^2$, $A \approx B$
> si et seulement si $\text{rg}(A) = \text{rg}(B)$

__Preuve :__ $\Rightarrow$ Si $A \approx J_r$, alors on a $\text{rg}(A) = \text{rg}(Q J_r P) = \text{rg}(J_r) = r$.\
$\Leftarrow$ On pose $u \in \mathcal{L}(\mathbb{K}^p,\mathbb{K}^n)$ canoniquement associé à
$A$ de rang $r$. Par théorème du range, $\text{dim}(\text{Ker}(u)) = p - r$.
Ainsi, il existe $G$ tel que $\mathbb{K}^p = G \oplus \text{Ker}(u)$,
et $\text{dim}(G) = r$. En rassemblant une base de $G$ et de $\text{Ker}(u)$,
on obtient une base de $\mathbb{K}^p$.\
Par le théorème du rang, $u$ est un isomorphisme, donc on peut construire l'image d'une base de $G$
par un isomorphisme, qui est une base de $\text{Im}(u)$. On construit donc une base de $F$
avec la base de $\text{Im}(u)$ qu'on complète, et ainsi on obtient bien une matrice pour cette base de $u$
qui est $J_r$.

### Matrices semblables
> Deux matrices (carrées) $A$ et $B$ sont semblables s'il existe
> $P \in \text{GL}_n(\mathbb{K})$ telle que $B = P^{-1} A P$.

Les puissances successives sont ainsi faciles à appliquer.

> La ressemblance de matrice est une relation d'équivalence de $\mathcal{M}_n(\mathbb{K})$.

Si $A$ et $B$ sont semblables, alors leur rang et leur trace sont égales entre
elles (car le rang n'est pas modifié par la multiplication par une application
bijective/matrice inversible, et la trace est commutative donc $P$ et $P^{-1}$
s'annulent lors du calcul).

> $A$ et $B$ sont semblables si et seulement si elles représentent le même
> endomorphisme dans des bases différentes.

En pratique, pour montrer que $A$ et $B$ sont semblables, on montre qu'il s'agit
toutes deux de matrices associées à une même application $f$ dans une base
différente. On va donc en général poser $f$ l'application canoniquement associée
à $A$, puis on applique la formule de changement de base.

> Soit $f \in \mathcal{L}(E)$, avec $E$ de dimension finie,
> la trace de $f$ est la trace des matrices associée à $f$ dans une base de $E$.

Comme la trace est la même pour toutes ces matrices, elle est bien définie.
On a aussi les mêmes résultats sur la trace par la bijection entre les matrices
et les applications linéaires : $\text{tr}(u \circ v) = \text{tr}(v \circ u)$.

Les projecteurs de rang $p$ sont semblable aux matrices diagonales de $1$ de $1$ à $p$
et sont ainsi de trace $p$.
