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
ou encore $\bigoplus_\limits_{i \in I} \text{Vect}(e_i) = E$.

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
or si $i \in [\![1;n]\!]$, pour $ \in I_0$, $e_i \in \mathcal{L}'$,
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

