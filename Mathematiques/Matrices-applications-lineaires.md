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
