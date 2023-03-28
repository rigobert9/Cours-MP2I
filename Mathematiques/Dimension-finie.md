# Algèbre linéaire en dimension finie
## Familles génératrices, libres et bases
### Famille génératrice
> Soit $E$ un $\mathbb{K}$-EV et $\mathcal{F} = (e_i)_{i \in I}$
> une famille quelconque de vecteurs de $E$,
> $\mathcal{F}$ est une famille génératrice de $E$
> si $E = \text{Vect}(\mathcal{F})$, c'est-à-dire que
> $\forall x \in E, \exists (\lambda_i)_{i \in I}$
> une famille presque nulle de scalaire telle que $x = \sum\limits_{i \in I} \lambda_i e_i$.

Ainsi, tout vecteur de $E$ peut s'écrire comme une combinaison linéaire finie de
vecteurs de $\mathcal{F}$.

> Si $E = \text{Vect}(e_i)_{[\![1;n+1]\!]}$ et si $e_{n + 1} \in \text{Vect}(e_i)_{[\![1;n]\!]}$,
> alors $E = \text{Vect}(e_i)_{[\![1;n]\!]}$.

__Preuve :__
- $\text{Vect}(e_i)_{[\![1;n]\!]} \subset \text{Vect}(e_i)_{[\![1;n+1]\!]}$
- Soit $x = \sum\limits_{i = 1}^{n + 1} \lambda_i e_i \in \text{Vect}(e_i)_{[\![1;n+1]\!]}$,
  or $e_{n + 1} = \sum\limits_{i = 1}^{n} \mu_i e_i \in \text{Vect}(e_i)_{[\![1;n]\!]}$,
  donc $x = \sum\limits_{i = 1}^{n} (\lambda_i + \mu_i \lambda_{n+1}) e_i \in \text{Vect}(e_i)_{[\![1;n]\!]}$.

### Famille libre, famille liée
> Soit $(u,v) \in E^2$, $u$ et $v$ sont colinéaires si $\exists \lambda \in \mathbb{K}, u = \lambda v \lor v = \lambda u$.

$0_E$ est alors colinéaire à tout vecteur de l'espace vectoriel.

> Soit $\mathcal{F} = (e_i)_{[\![1;n]\!]}$ une famille de vecteurs de $E$,
> on dira que $\mathcal{F}$ est libre (ou linéairement indépendante) si
> l'unique décomposition du vecteur nul selon cette famille $\mathcal{F}$
> est la décomposition triviale.

Cette propriété correspond à $\forall (\lambda_i)_{[\![1;n]\!]} \in \mathbb{K}^n,$
$(\sum\limits_{i = 1}^{n} \lambda_i e_i = 0_E \Rightarrow \forall i \in I, \lambda_i = 0)$.

> Si $\mathcal{F}$ n'est pas libre, on dit qu'elle est liée, donc
> $\exists (\lambda_i)_{[\![1;n]\!]} \in \mathbb{K}^n$
> non tous nuls tel que $\sum\limits_{i = 1}^{n} \lambda_i e_i = 0_E$.

Si $\mathcal{F} = (e_i)_{[\![1;n]\!]}$ est libre, alors tout vecteur engendré
par $\mathcal{F}$ s'écrit de manière unique comme combinaison linéaire de $\mathcal{F}$.

> Si $(e_i)_{[\![1;n]\!]}$ est libre, et si $e_{n+1} \not\in \text{Vect}(e_i)_{[\![1;n]\!]}$
> Alors $(e_i)_{[\![1;n+1]\!]}$ est libre.

__Preuve :__ Soit $(\lambda_i)_{[\![1;n+1]\!]} \in \mathbb{K}^{n+1}$ tel que
$0_E = \sum\limits_{i = 1}^{n + 1} \lambda_i e_i$.
Ainsi, $0_E = \sum\limits_{i = 1}^{n} \lambda_i e_i + \lambda_{n+1} e_{n+1}$.
Si $\lambda_{n+1} \neq 0$, $e_{n+1} = \sum\limits_{i = 1}^{n} \frac{- \lambda_i}{\lambda_{n+1}} e_i \in \text{Vect}(e_i)_{[\![1;n]\!]}$,
donc $\lambda_{n+1} = 0$ donc $0_E = \sum\limits_{i = 1}^{n} \lambda_i e_i$. Par
liberté de $(e_i)_{[\![1;n]\!]}$, $\forall i \in [\![1;n]\!], \lambda_i = 0$,
donc $(e_i)_{[\![1;n+1]\!]}$ est libre.

> Extension aux familles libres infinies :
> une famille $\mathcal{F}$ est libre si toutes ses sous-familles finies sont
> libres. Une famille $\mathcal{F}$ est donc liée s'il existe une sous-famille
> liée.

Par exemple, dans $\mathbb{K}[X]$, la famille $(X^k)_{k \in \mathbb{N}}$ est une
famille libre infinie.

### Bases
> Une base d'un $\mathbb{K}$-EV $E$ est une famille libre et génératrice de $E$.

Ainsi, si $\mathcal{B} = (e_i)_{i \in I}$ est une base de $E$, elle est
génératrice de $E = \text{Vect}(\mathcal{B})$, et elle est libre donc l'écriture
selon cette base est unique.

Si on prend chacun des éléments de la base, on peut aussi l'interpréter comme
$\forall x \in E,\exists! (\lambda_i)_{i \in I} \in \mathbb{K}^{\mathbb{N}}$
presque nulle telle que $x = \sum\limits_{i \in I} \lambda_i e_i$,
ou encore $\bigoplus\limits_{i \in I} \text{Vect}(e_i) = E$.

### Liens avec les sommes d'espaces vectoriels
> Soit $F,G$ des SEV de $E$, si $\mathcal{F}$ est génératrice de
> $F$ et $\mathcal{G}$ est génératrice de $G$,
> alors $\mathcal{F} \cup \mathcal{G}$ est génératrice de $F + G$.

> Si $F$ et $G$ sont en somme directe, et si $\mathcal{F}$ est une famille libre
> de $F$ et $\mathcal{G}$ est une famille libre de $G$, est $\mathcal{F} \cup \mathcal{G}$
> est une famille libre de $F \oplus G$.

> Si $E = F \oplus G$, et $\mathcal{B}_F$ est une base de $F$ et
> $\mathcal{B}_G$ est une base de $G$, alors
> $\mathcal{B}_E \cup \mathcal{B}_F$
> Forme une base de $E$.

### Lien avec les applications linéaires
> Soit $f \in \mathcal{L}(E,F)$ si $E = \text{Vect}(\mathcal{F})$
> alors $\text{Im}(f) = \text{Vect}(f(\mathcal{F}))$.

> L'image d'une famille libre de $E$ par une application linéaire injective est
> une famille libre de $F$.

__Preuve :__ Soit $f \in \mathcal{L}(E,F)$ injective et $(e_i)_{i \in I}$ une famille libre
de $E$, on cherche à montrer que $(f(e_i))_{i \in I}$ est libre.
Soit $(\lambda_i)_{i \in I}$ tel que $\sum\limits_{i \in I} \lambda_i f(e_i) = 0_F$.
Par linéarité de $f$, $f(\sum\limits_{i \in I} \lambda_i e_i) = 0_F$.
Puisque $\text{Ker}(f) = \{0_F\}$ car $f$ est injective,
on obtient nécessairement $\sum\limits_{i \in I} \lambda_i e_i = 0_E$,
donnant par liberté de $(e_i)_{i \in I}$, $\forall i, \lambda_i = 0$.

> Soit $f \in \mathcal{L}(E,F)$, et $\mathcal{B}$ une base de $E$,
> $f$ est un isomorphisme si et seulement si
> $f(\mathcal{B})$ est une base de $F$.

__Preuve :__ Si $f$ est bijective, $f$ est injective et surjective,
or $\mathcal{B}$ est libre et génératrice de $E$. Ainsi,
$f(\mathcal{B})$ est libre et génératrice de $E$, donc $f(\mathcal{B})$
est une base de $E$.\
Si $f(\mathcal{B})$ est une base de $F$, $f(\mathcal{B})$ est génératrice
de $F$, donnant $F = \text{Vect}(f(\mathcal{B})) = f(\text{Vect}(\mathcal{B}))$
$= f(E) = \text{Im}(f)$, donc $f$ est surjective.
De plus, soit $x \in \text{Ker}(f)$, $f(x) = 0_F$,
$x \in E$ donc $x$ se décompose dans la base $\mathcal{B}$.
En notant $\mathcal{B} = (e_i)_{i \in I}$,
$\exists (\lambda_i)_{i \in I}, x = \sum \lambda_i e_i$.

> Toute application linéaire est entièrement caractérisée par les images des
> vecteurs de la base du domaine.

## Théorie de la dimension
> $E$ est un $\mathbb{K}$-EV de dimension finie si $E$ possède au moins une
> famille génératrice finie.

### Existence de bases
> Soit $\mathcal{G}$ une famille génératrice finie de $E$, toute sous-famille
> $\mathcal{L}$ libre peut être complétée en une base de $E$ uniquement à l'aide
> de vecteurs de $\mathcal{G}$.

__Preuve :__ Soit $\mathcal{L} = (e_j)_{j \in J}$ une sous-famille libre
de $\mathcal{G}$, avec $J \subset [\![1;n]\!]$. On note
$A = \{|I \mid \left\{\begin{matrix} J \subset I \subset [\![1;n]\!] \\ (e_i)_{i \in I} \text{ est libre} \end{matrix}\right.\}$.
$A$ est une partie non vide ($|J| \in A$), est majorée (par $n$) de $\mathbb{N}$.
Elle possède donc un maximum qu'on note $r = \text{max}(A)$.
Ainsi, il existe une partie $I_0$ telle que
$J \subset I_0 \subset [\![1;n]\!]$ avec
$|I_0| = r$ et $\mathcal{L}' = (e_i)_{i \in I_0}$ est libre.
On cherche à montrer que $\mathcal{L}'$ est génératrice de $E$,
or si $i \in [\![1;n]\!]$, pour $i \in I_0$, $e_i \in \mathcal{L}'$,
et pour $i \not\in I_0$, il est absurde que $e_i \not\in \text{Vect}(\mathcal{L}')$,
car sinon $\mathcal{L}' \cup e_i$ serait une famille libre, contredisant la
maximalité de $\mathcal{L}'$.\
Ainsi, $\mathcal{L}'$ est une famille génératrice de $E$, et est une base de
$E$.

> Base extraite : De tout famille génératrice de $E$, on peut extraire une base de $E$.

__Preuve :__ Soit $E$ de dimension finie engendrée par $\mathcal{G}$,
si $E = \{0_E\} = \text{Vect}(\emptyset)$, la base a 0 vecteurs, et si
$\exists! =\{0_E\}$, il existe $u \in \mathcal{G}$ avec $u \neq 0_E$,
et $u$ est une sous-famille libre de $E$. Par la propriété précédente,
on peut compléter $u$ avec des vecteurs de $\mathcal{G}$ pour former une base de
$E$.

> Tout $EV$ de dimension finie possède une base.

Et il peut y en avoir une infinité dans la plupart des cas.

> Base incomplète : Toute famille libre d'un EV de dimension finie peut être
> complétée en une base.

On prend $\mathcal{L}$ une famille libre de $E$. On a $\mathcal{G}$
une famille génératrice de $E$. On pose $\mathcal{G'} = \mathcal{G} \cup \mathcal{L}$.
D'après la proposition précédente, $\mathcal{L}$ est bien une sous-famille libre
de $\mathcal{G'}$, donc peut être complétée en base uniquement avec des vecteurs
de $\mathcal{G'}$.

### Cardinal d'une base
> Si $E$ possède une famille génératrice à $n$ vecteurs, alors toute famille
> à $(n+1)$ vecteurs est liée.

__Preuve :__ On procède par récurrence sur $n$.
Pour $n = 0$, $E = \text{Vect}(\emptyset) = \{0_E\}$,
et $(0_E)$ est une famille liée (car $\exists \lambda \neq 0 \mid \lambda 0_E = 0_E$).
Soit $n \geq 1$ tel que le rang $n - 1$ est vérifié, on suppose que $E$ est
engendré par $(e_i)_{[\![1;n]\!]}$. Soit $(u_i)_{[\![1;n+1]\!]}$ une famille
quelconque de $E$, on pose $F = \text{Vect}(e_i)_{[\![1;n-1]\!]}$,
et on a $E = F + \text{Vect}(e_n)$. Pour tout $i \in [\![1;n+1]\!]$,
$u_i \in E$, donc $u_i = f_i + \lambda_i e_n$ avec $f_i \in F$
et $\lambda_i \in \mathbb{K}$.\
Si $\forall i, \lambda_i = 0$, les $u_i$ sont tous dans $F$, donc par hypothèse
de récurrence, ils sont liés.
Sinon, on prend $i_0 \mid \lambda_{i_0} \neq 0$, et on pose alors
$\forall i \in [\![1;n+1]\!] \setminus \{i_0\}$,
$x_i = u_i - \frac{\lambda_i}{\lambda_{i_0}} u_{i_0}$,
donnant une famille de $n$ vecteurs et ils sont tous dans $F$ :
$x_i = (f_i + \lambda_i e_n) - \frac{\lambda_i}{\lambda_{i_0}} (f_{i_0} + \lambda_{i_0} e_n)$
est dans $F$, donc par hypothèse de récurrence, la famille
$(x_i)_{i \in [\![1;n+1]\!] \setminus \{i_0\}}$ est liée,
donc la famille des $(u_i)$ aussi.

> Toute famille libre contient un nombre de vecteurs inférieur ou égal à toute
> famille génératrice de $E$.

> Toutes les bases d'une EV $E$ de dimension finie est de même cardinal
> $n$, qu'on appelle la dimension de $E$, notée $\text{dim}_{\mathbb{K}}(E) = n = \text{dim}(E)$.

__Preuve :__ Soit deux bases de $E$ ayant pour cardinaux $n$ et $p$,
la première est libre et la seconde est génératrice donc $n \leq p$;
et la première est génératrice et la seconde est libre, donc $n \geq p$.

Toute famille libre de $E$ est au plus aussi grande que $\text{dim}(E)$
et toute famille génératrice de $E$ est au moins aussi grande que
$\text{dim}(E)$.

### Caractérisation des bases en dimension finie
> Soit $E$ un EV de dimension finie, $n = \text{dim}(E)$.
> Soit $\mathcal{F}$ une famille de $E$ de taille $n$,
> $\mathcal{F}$ est une base de $E$ si et seulement si
> $\mathcal{F}$ est libre si et seulement si
> $\mathcal{F}$ est génératrice.

__Preuve :__ Lorsque $\mathcal{F}$ est libre, par théorème de la base
incomplète, on peut en faire une base de taille $n$, qui est elle-même.
Si $\mathcal{F}$ est génératrice, par théorème de la base extraite, on en
extrait une base, qui est de taille $n$ et qui est donc $\mathcal{F}$.

### Sous-espaces vectoriels et dimension
#### Produit d'espaces vectoriels
> Soient $E,F$ deux $\mathbb{K}$-EV de dimension finie, alors
> $E \times F$ est un $\mathbb{K}$-EV ed dimension finie et
> $\text{dim}(E \times F) = \text{dim}(E) + \text{dim}(F)$.

__Preuve :__ Soient $\left\{\begin{matrix} n = \text{dim}(E) \\ p = \text{dim}(F) \end{matrix}\right.$,
on prend $(e_i)_{[\![1;n]\!]}$ une base de $e$ et $(f_i)_{[\![1;p]\!]}$ une base
de $F$. On pose $B = \{(e_i,0_F)_{1 \leq i \leq n}\}$
$\cup \{(0_E,f_j)_{1 \leq j \leq p}\}$.
$B$ contient $n + p$ vecteurs de $E \times F$. On prouve ensuite que $B$ est
génératrice de $E \times F$ et est libre, donc est une base de $E \times F$.

On peut généraliser ce produit au produit de nombreux espaces vectoriels, et la
dimension du produit sera alors la somme des dimensions des espaces vectoriels
donnés. De même, les $n$-uplets d'un espace vectoriel $E$ sont de dimension
$p \times \text{dim}(E)$.

#### Sous-espace vectoriel de dimension finie
> Soit $E$ de dimension finie, tout SEV $F$ de $E$ est un SEV de dimension finie
> et $\text{dim}(F) \leq \text{dim}(E)$.

__Preuve :__ Si $F = \{0_E\}$, alors $F$ est de dimension finie et $\text{dim}(F) = 0$,
sinon $\exists e_1 \in F \mid e_1 \neq 0_E$, et donc $\text{Vect}(e_1) \subset F$
et $(e_1)$ est une famille libre. Si $(e_1)$ est génératrice de $F$, alors c'est
un base de $F$ et $\text{dim}(F) = 1$, sinon, on ajoute des vecteurs jusqu'à
avoir une base de $F$, or toute famille libre de $E$ (donc de $F$) est plus
petite que la base, donc $\text{dim}(F) \leq \text{dim}(E)$.

> Soient $F,G$ deux SEV de $E$ avec $p = \text{dim}(F)$ et $q = \text{dim}(G)$
> de dimension finie, si $F \subset G$ et $p = q$, alors $F = G$.

__Preuve :__ On prend $(e_i)_{[\![1;p]\!]}$ une base de $F$,
or $F \subset G$, donc $\text{Vect}(e_i) \subset G$, et $(e_i)$
y est libre, donc y est une base, donc y est génératrice dans $F$
comme dans $G$.

#### Somme d'espaces vectoriels
> Formule de Grassman : Soient $F$ et $G$ deux SEV de dimension finie d'un
> $\mathbb{K}$-EV $E$, alors $\text{dim}(F + G) = \text{dim}(F) + \text{dim}(G) - \text{dim}(F \cap G)$.

__Preuve :__ $F \cap G$ est un SEV de $F$ et de $G$. Soit $r = \text{dim}(F \cap G)$,
$p = \text{dim}(F)$ et $q = \text{dim}(G)$. Par inclusion, $r \leq p$ et
$r \leq q$. On prend $(e_i)_{[\![1;r]\!]}$ une base de $F \cap G$, par base
incomplète, on construit une base de $F$ complétée par $(u_i)_{[\![r+1;p]\!]}$
et une base de $G$ complétée par $(v_i)_{[\![r+1;q]\!]}$.
On pose la base de l'union de ces deux bases, qui est une famille génératrice de
$F + G$. On montre que cette famille est libre. Si tel est le cas, on aura bien
$\text{dim}(F + G) = r + (p - r) + (q - r) = p + q - r$.

Ainsi, $\text{dim}(F + G) \leq \text{dim}(F) + \text{dim}(G)$,
avec le cas d'égalité quand $F \oplus G$ ou $F \cap G = \{0_E\}$.

#### Caractérisation des supplémentaires
> Soit $E$ un $\mathbb{K}$-EV de dimension finie et $F,G$ deux SEV de $E$,
> $E = F \oplus G$ si et seulement si $E = F + G$ et $\text{dim}(E) = \text{dim}(F) + \text{dim}(G)$
> si et seulement si $F \cap G = \{0_E\}$ et $\text{dim}(E) = \text{dim}(F) + \text{dim}(G)$.

On peut souvent utiliser cette troisième proposition pour prouver la
supplémentarité de $F$ et $G$.

__Preuve :__ Directe du premier cas au deux autres.
On peut prouver à partir de la seconde proposition la première avec la formule
de Grassman.

> Existence de supplémentaire : Soit $E$ un $\mathbb{K}$-EV de dimension finie et $F$ un
> SEV de $E$, alors $F$ possède au moins un supplémentaire dans $E$.

__Preuve :__ On prend une base de $F$, qui est une famille libre dans $E$. Par
théorème de la base incomplète, on peut le compléter par la plus petite famille qui en fait
une base de $E$. La famille qui complète, qui est libre, est génératrice
d'un espace $G$, dans lequel elle est une base (car elle y est libre aussi).
Ainsi, la somme des deux espaces est bien $E$, et $F \cap G = \{0_E\}$.

Ainsi, on a toujours un espace supplémentaire de dimension $\text{dim}(E) - \text{dim}(F)$.

> Caractérisation d'un hyperplan en dimension finie : Soit $E$ un $\mathbb{K}$-EV
> de dimension finie $n = \text{dim}(E) \in \mathbb{N}^{\ast}$ et $H$ un SEV
> de $E$, $H$ est un hyperplan de $E$ si et seulement si
> $\text{dim}(H) = n - 1$.

__Preuve :__ $\Rightarrow$ Si $H$ est un hyperplan de $E$, il existe une droite
$D$ supplémentaire, nous donnant la bonne dimension par la formule de Grassman
pour une somme directe.\
$\Leftarrow$ On utilise le théorème précédent pour obtenir un espace
supplémentaire à $H$, puis on obtient par Grassman que ce supplémentaire est de
dimension $1$.

### Notion de rang
> Soit $\mathcal{F} = (e_i)_{[\![1;p]\!]}$ une famille de vecteurs de $E$,
> le rang de la famille $\mathcal{F}$ est défini par
> $\text{rg} = \text{dim}(\text{Vect}(\mathcal{F}))$.

> Le rang d'une famille de $p$ vecteurs est majoré par $p$, et il y a égalité si
> la famille est libre.

> Soit une famille de vecteurs de $E$ un EV de dimension finie, le rang de cette
> famille est majoré par la dimension de $E$, et il y a égalité si la famille
> génère $E$.

Ainsi, une famille de $p$ vecteurs est une base de $E$ si le rang de la famille
est égal à $p$ et à la dimension de $E$.

Le rang d'une famille est invariant par :
- Le retrait ou l'ajout du vecteur nul dans la famille
- L'échange de place de deux vecteurs dans la famille
- La multiplication par un scalaire non nul
- Ajout d'une combinaison linéaire de vecteurs de la famille à un autre

## Application linéaire en dimension finie
### Rang d'une application linéaire
> Soit $f \in \mathcal{L}(E,F)$, on dit que $f$ est de rang fini si $\text{Im}(f)$
> est de dimension finie. Le rang de $f$ est alors défini comme la dimension de
> $\text{Im}(f)$.

> Si $E$ est de dimension finie avec $(e_i)_{[\![1;p]\!]}$ une base de $E$,
> alors $\text{Im}(f) = \text{Vect}(f(e_i)_i)$, donc le rang de $f$ est le rang
> de $(f(e_i))_i$.

###  Isomorphismes d'EV
> Soit $E$ un $\mathbb{K}$-EV de dimension finie et $F$ un $\mathbb{K}$-EV,
> $F$ est isomorphe à $E$ si et seulement si $\left\{\begin{matrix} F \text{ est de dimension finie} \\ \text{dim}(E) = \text{dim}(F) \end{matrix}\right.$.

__Preuve :__ $\Rightarrow$ Si il existe $f \in \mathcal{L}(E,F)$ un isomorphisme entre $E$ et $F$.
On prend $n = \text{dim}(E)$ et $(e_i)_{[\![1;n]\!]}$ une base de $E$.
Comme $f$ est un isomorphisme, $(f(e_i))_i$ est une base de $F$,
donc $F$ est de dimension finie et $\text{dim}(F) = n$.\
$\Leftarrow$ Si $\text{dim}(E) = \text{dim}(F) = n$, en fixant une base pour
chaque EV, il ne peut exister qu'une unique application linéaire de $E$ vers vers
$F$ déterminée comme $f(e_i) = f_i$. Elle est bien définie et est bien un isomorphisme.
