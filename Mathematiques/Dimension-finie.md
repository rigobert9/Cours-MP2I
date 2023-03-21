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
