# Dénombrement
## Ensembles finis
### Cardinal
> Soit $E$ un ensemble, $E$ est dit fini s'il existe $n \in \mathbb{N}$
> et $\varphi$ une bijection entre $E$ et $[\![1;n]\!]$,
> alors le cardinal de $E$ sera $n$, noté $\text{Card}(E)$,
> $|E|$ ou $# E$.

$\varphi$ correspond alors à une numérotation des éléments de $E$. Si $E$ est
fini de cardinal $n \in \mathbb{N}^{\ast}$, on pourra écrire $E = \{x_1, \ldots, x_n\}$
où les $x_i$ sont distincts.

> Soient $E,F$ deux ensemble finis et non vides, on a $|E| = |F|$ si et seulement si
> il existe une bijection entre $E$ et $F$.

__Preuve :__ $\Rightarrow$ $\exists n \in \mathbb{N}^{\ast}, |E| = |F| = n$,
donc il existe des bijections de chacun dans $[\![1;n]\!]$, et la composition de
celles-ci avec l'inverse de l'autre forment des bijections.\
$\Leftarrow$ On forme les bijections de chacun dans $[\![1;n_E]\!]$
et $[\![1;n_F]\!]$, puis on compose avec la bijection disponible.

Pour travailler sur l'ensemble $F$, on cherche un ensemble $E$ fini
et une bijection $\varphi: E \to F$, alors $F$ sera fini et $|F| = |E|$.

### Sous-ensemble fini
> Si $E$ est fini sur $F \subset E$, alors $F$ est fini et $|F| \leq |E|$.
> Il y a cas d'égalité si et seulement si $F = E$.

### Applications entre ensemble finis
> Soit $f: E \to F$ et $E,F$ de cardinaux finis,
> $f(E) \subset F$ donc $|f(E)| \leq |F|$ et il y a égalité si et seulement si
> $F$ est surjective.

> $|f(E)| \leq |E|$ et il y a égalité si et seulement si $f$ est injective.

On peut ainsi comparer les cardinaux d'ensemble par l'existence de surjections
et injection. On peut aussi constater le lemme des tiroirs par exemple (si
l'ensemble de départ est plus grand que celui d'arrivée, la fonction n'est pas
injective).

> Soit $f: E \to F$ avec $E$ et $F$ finis de même cardinal, on a $f$ injective
> si et seulement si $f$ est surjective si et seulement si $f$ est bijective.

__Preuve :__ $f$ injective si et seulement si $|E| = |f(E)|$
si et seulement si $|F| = |f(E)|$ si et seulement si $f$ surjective.

## Principes de dénombrement
### Principe additif
> Soit $A$ et $B$ des ensemble finis,
> $|A \cup B| = |A| + |B| - |A \cap B|$.

On peut le justifier comme $A \cup B = A \sqcup (B \setminus A)$.

La somme set simple pour les ensembles disjoints (sans soustraction).
On peut donc généraliser facilement cette somme de cardinaux aux familles
d'ensemble disjoints.

### Complémentaire
> Soit $A \subset E$ avec $E$ fini, $\overline{A} = E \setminus A$
> est tel que $|\overline{A}| = |E| - |A|$.

### Principe multiplicatif
> Si $A$ et $B$ sont finis, $|A \times B| = |A| \times |B|$.

> Si $A$ est fini et $p \in \mathbb{N}^{\ast}$, alors $|A^p| = |A|^p$.

### Applications entre ensemble finis
> Soit $E,F$ finis de cardinaux $p$ et $n$, les applications de $E$ dans $F$
> sont notées $F^E$ et $|F^E| = |F|^{|E|} = n^p$.

__Preuve :__ Pour tout fonction entre les deux ensembles, on a $n$ choix
possibles pour chacun des $p$ éléments.

### Ensemble des parties d'un ensemble
> Si $E$ est fini, $\mathcal{P}(E)$ est l'ensemble des parties de $E$ et
> $|\mathcal{P}(E)| = 2^{|E|}$.

__Preuve :__ Si $A \subset E$, $A$ est caractérisée par son indicatrice, et on a
donc la bijection des parties de $E$ dans $\{0;1\}^{E}$, donnant bien
un cardinal de $|\{0;1\}|^{|E|}$.

## Les classiques du dénombrement
### $p$-uplets
Voir plus haut.

Ils correspondent ainsi aux nombres de séquences possibles de lancers successifs
d'un dé, les possibilités de suites de lancers de pièces, les tirages de balles
dans des urnes avec remise ...

### Arrangements sans répétition
> Soit $E$ un ensemble de cardinal fini $p$, un $p$-arrangement est un $p$-uplet
> de $E$ où il n'y a pas répétition du même élément.

Pour $E$ de cardinal $n$, il y a $0$ $p$-arrangements de $E$ si $p > n$
et $\frac{n!}{(n-p)!}$ $p$-arrangements si $p \leq n$. On peut constater ceci
facilement en construisant les arrangements (on a $n$ choix puis $n-1$ choix
...).

> Un $p$-arrangement de $E$ à $n$ éléments correspond à une injection de $[\![1;p]\!]$
> dans $E$.

> Une permutation de $E$ est un $n$-arrangement de $E$.

Il s'agit donc de compter les bijections de $E$ sur lui-même, ou encore les
ordres totaux sur $E$. Il y en a donc $n!$.

### Combinaisons (pas d'ordre)
> Soit $E$ à $n$ éléments, une $p$-combinaison est ensemble à $p$ éléments de $E$.

On compte donc les sous-ensembles d'une certaine cardinalité possibles.
Il y a $\binom{n}{p}$ $p$-combinaisons de $E$, avec $\binom{n}{p} = \left\{\begin{matrix} \frac{n!}{p! (n-p)!} \text{ si } p \in [\![0;n]\!] \\ 0 \text{ si } p > n \end{matrix}\right.$.
En effet, il existe $p!$ $p$-arrangements d'une combinaison, donc on a $\frac{n!}{(n-p)!} = \binom{n}{p} \times p!$.

## Preuves combinatoires
### Symétrie des coefficients binomiaux
On montre que pour tout ensemble $A \in \mathcal{P}(E)$,
on a une bijection vers son complémentaire dans $\mathcal{P}(E)$,
et comme si $A \in \mathcal{P}_k(E)$, $\overline{A} \in \mathcal{P}_{n-k}(E)$,
donc on a une bijection entre ces deux ensembles de parties, permettant de
conclure.

### Formule du chef
Pour $k \geq 1$, $k \binom{n}{k} = n \binom{n-1}{k-1}$. Voir le cours du début
d'année sur les calculs algébriques.

### Binôme de Newton sans récurrence
Comme $(x + y)^n = (x+y) \times (x+y) \times \ldots \times (x+y)$ $n$ fois,
en développant tout, on obtient $2^n$ termes de la forme
$xyyx \ldots x$, ce qui revient à construire un mot de longueur $n$ sur un
alphabet à $2$ lettres $\{x;y\}$. On compte le nombre de mots de longueur $n$
comportant $k$ lettres $"x"$ et donc $n-k$ lettres $"y"$.

On choisit simultanément les emplacements des $k$ $"x"$, avec $\binom{n}{k}$ choix possibles (qui sont tous par $x^k y^{n-k}$ par commutativité),
et donc il reste à choisir les emplacements des $"y"$, avec $\binom{n-k}{n-k} = 1$ choix possibles.
