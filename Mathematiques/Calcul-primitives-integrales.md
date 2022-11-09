# Calcul de primitives et intégrales
Soit $I$ un intervalle de $\mathbb{R}$ d'intérieur non vide, les fonctions
$f$ et $g$ seront définies sur $I$, à valeurs dans $\mathbb{R}$ ou
dans $\mathbb{C}$ (dans $\mathbb{K}$ en général).

## Primitives
### Définition
> Soit $f: I \to \mathbb{K}$ une fonction continue sur $I$,
> on dit que $F: I \to \mathbb{K}$ est une fonction primitive de $f$
> sur $I$ si $F$ est dérivable sur I et $F' = f$

Soit $f \in \mathfrak{C}(I,\mathbb{K})$ et $F: I \to \mathbb{K}$ une primitive
de $f$, alors l'ensemble des primitives de $f$ sur $I$ est
$\{F + \lambda, \lambda \in \mathbb{K}\}$.

En cherchant une primitive à une fonction, on ajoutera toujours une constante
d'intégration.

#### Preuve
Soit $G$ une primitive de $f$ sur $I$, alors $G' = f = F'$,
donc $G' - F' = 0$ sur l'intervalle $I$ donc $G - F$ est constante
sur $I$, donc $G \in \{F + \lambda, \lambda \in \mathbb{K}\}$.
Réciproquement, $(F + \lambda)' = F' = f$ donc $F + \lambda$ est une primitive
de $f$ sur $I$.

Remarque : Dire que $f: I \to \mathbb{C}$ est continue signifie que $\Re(f)$
et $\Im(f)$ sont continues sur $I$.

### Primitives usuelles

$f(x)$                                                   | $F(x)$                              | Intervalle
---                                                      | ---                                 | ---
$\lambda \in \mathbb{C}$                                 | $\lambda x$                         | $\mathbb{R}$
$x^n, n \in \mathbb{N}$                                  | $\frac{x^{n + 1}}{n + 1}$           | $\mathbb{R}$
$x^n, n \leq -2 \in \mathbb{Z}$                          | $\frac{x^{n + 1}}{n + 1}$           | $\mathbb{R}^{\ast}_{+}$ ou $\mathbb{R}^{\ast}_{-}$
$x^{\alpha}, \alpha \in \mathbb{R} \setminus \mathbb{Z}$ | $\frac{x^{\alpha + 1}}{\alpha + 1}$ | $\mathbb{R}^{\ast}_{+}$
$\frac{1}{x}$                                            | $\ln(\text{abs}(x))$                | $\mathbb{R}^{\ast}_{+}$ ou $\mathbb{R}^{\ast}_{-}$
$e^{x}$                                                  | $e^x$                               | $\mathbb{R}$
$e^{\alpha x}, \alpha \in \mathbb{C}^{\ast}$             | $\frac{1}{x} e^{\alpha x}$          | $\mathbb{R}$
$\sin x$                                                 | $-\cos x$                           | $\mathbb{R}$
$\cos x$                                                 | $\sin x$                            | $\mathbb{R}$
$\sinh x$                                                | $\cosh x$                           | $\mathbb{R}$
$\cosh x$                                                | $\sinh x$                           | $\mathbb{R}$
$\ln(x)$                                                 | $x \ln(x) - x$                      | $\mathbb{R}^{\ast}_{+}$
$\frac{1}{1 + x^2}$                                      | $\arctan$                           | $\mathbb{R}$
$\frac{1}{\sqrt{1 - x^2}}$                               | $\arcsin$                           | $]-1;1[$
$\tan x$                                                 | $-\ln(\text{abs}(\cos x))$          | $]\frac{-\pi}{2},\frac{\pi}{2}[ + \pi\mathbb{Z}$
$\tanh x$                                                | $\ln(\cosh x)$                      | $\mathbb{R}$
$\tan^2 x$                                               | $\tan x - x$                        | $]-\frac{\pi}{2},\frac{\pi}{2}[ + \pi\mathbb{Z}$
$\tanh^2 x$                                              | $x - \tanh x$                       | $\mathbb{R}$
$f(ax + b), a,b \in \mathbb{R}$                          | $\frac{1}{a} F(ax + b)$             | Selon $f$ et les constantes

##### Méthode : primitive de  $x \mapsto \frac{1}{(x-a)(x-b)}$ avec $a \neq b$ deux réels
On applique alors la décomposition en éléments simples, c'est à dire la
recherche de deux constantes $\alpha$ et $\beta$ (on verra qu'elles existent et
sont uniques) telles que
$\frac{1}{(x-a)(x-b)} = \frac{\alpha}{x-a} + \frac{\beta}{x-b} = \frac{\alpha (x - b) + \beta (x - a)}{(x-a)(x-b)} = \frac{(\alpha + \beta)x - (\alpha b + \beta a)}{(x-a)(x-b)}$.

On veut alors $\left\{\begin{matrix} \alpha + \beta = 0 \\ -(\alpha b + \beta a) = 1 \end{matrix}\right.$
(identification des coefficients des polynômes au numérateur), ce qui donne
$\left\{\begin{matrix} \beta = -\alpha \\ -(-\beta b + \beta a) = 1 \end{matrix}\right.$
$\Leftrightarrow \left\{\begin{matrix} \alpha = \frac{1}{a - b} \\ \beta = \frac{1}{b - a} \end{matrix}\right.$.

Ainsi, $\forall x \neq a,b, \frac{1}{(x-a)(x-b)} = \frac{1}{a-b} [\frac{1}{x-a} - \frac{1}{x - b}]$.

Une autre stratégie est de poser $A(x) = \frac{1}{(x-a)(x-b)} = \frac{\alpha}{x-a} + \frac{\beta}{x-b}$.
On a donc $(x-a)A(x) = \frac{1}{x-b} = \alpha + (x-a) \frac{\beta}{x-b}$.
On évalue en $a$ ($x \to a$), $\frac{1}{a-b} = \alpha$, et on obtient $\beta$ de
et cette fonction se primitive donc en $x \mapsto \frac{1}{a-b}(\ln(|x-a|) - \ln(|x-b|))$.

##### Méthode : détecter les composées
Puisque $(f \circ u)' = u' \times f' \circ u$, on a la primitive de
toute fonction $u' \times (f \circ u)$ qui est $F \circ u$.

##### Méthode : Primitive de $x \mapsto \frac{1}{x^2 + px + q}$
Avec $(p,q) \in \mathbb{R}^2$, on pose $\Delta = p^2 - 4q$.
- Si $\Delta > 0$, on a deux racines réelles distinctes $a < b$, et on décompose en éléments simples :
  $\frac{1}{x^2 + px + q = \frac{1}{(x-a)(x-b)} = \frac{1}{a-b} (\frac{1}{x-a} - \frac{1}{x-b})$.
  Alors, sur les intervalles $]-\infty,a[$ ou $]a,b[$ ou $]b,+\infty[$, une
  primitive sera $x \mapsto \frac{1}{a-b} (\ln(|x-a|) - \ln(|x-b|)) = \frac{1}{a-b} \ln(\frac{|x-a|}{|x-b|})$
- Si $\Delta = 0$, on note $r$ l'unique racine double, $r = \frac{-p}{2}$. On a
  alors $\frac{1}{x^2 + px + q} = \frac{1}{(x - r)^2}$, dont une primitive est
  $x \mapsto \frac{-1}{x-r}$ sur l'intervalle $]-\infty,r[$ ou $]r,+\infty[$.
- Si $\Delta < 0$, il n'y a pas de racine réelles, et le trinôme ne l'annule
  pas. On se place sur $I = \mathbb{R}$, or on obtient la forme canonique
  $x^2 + px + q = (x + \frac{p}{2})^2 + q - \frac{p^2}{4} = (x + \frac{p}{2})^2 - \frac{\Delta}{4}$
  $= (x + \alpha)^2 + \beta^2$ (avec $\left\{\begin{matrix} \alpha = \frac{p}{2} \\ \beta^2 = \frac{-\Delta}{4} \end{matrix}\right.$).\
  Ainsi, $\frac{1}{(x+\alpha)^2 + \beta^2} = \frac{1}{\beta^2 [(\frac{x + \alpha}{p})^2 + 1]}$
  $= \frac{1}{\beta} \times \frac{\frac{1}{\beta}}{1 + (\frac{x + \alpha}{\beta})^2}$.
  On obtient ainsi une primitive sur $\mathbb{R}$ qui est
  $x \mapsto \frac{1}{\beta} \arctan(\frac{x + \alpha}{\beta})$.

##### Méthode : Primitive de $x \mapsto \frac{1}{x - \alpha}$ avec $\alpha \in \mathbb{C} \setminus \mathbb{R}$
$\forall x \in \mathbb{R}, f(x) = \frac{1}{x - \alpha}$ (on ne peut pas avoir $x = \alpha$, donc la fonction est bien définie pour tout $x \in \mathbb{R}$),
on se ramène aux parties et imaginaires à l'aide de la multiplication par le
conjugué : $\forall x \in \mathbb{R}, \frac{1}{x - \alpha} \times \frac{\overline{x - \alpha}}{\overline{x - \alpha}}$
$= \frac{x - \overline{\alpha}}{|x - \alpha|^2}$.\
On note $\alpha = a + ib$ avec $a \in \mathbb{R}$ et $b \in \mathbb{R}^{\ast}$.
$f(x) = \frac{x-\alpha}{|x-\alpha|^2} + i \frac{b}{|x - \alpha|^2}$
$= \frac{x-a}{(x-a)^2 + b^2} + i \frac{b}{(x-a)^2 + b^2}$.

La partie réelle de $f$ se primitive donc en $x \mapsto \frac{1}{2} \ln(|(x-a)^2 + b^2|)$
$= \frac{1}{2} \ln((x-a)^2 + b^2) = \ln(|x-\alpha|)$.
De plus la partie imaginaire de $f$ se primitive en
$x \mapsto \arctan(\frac{x-a}{b})$.
On a donc la primitive de $f$ telle que
$x \mapsto \ln(|x-\alpha|) + i \arctan(\frac{x-a}{b})$.

## Intégrale
On étend l'intégrale à $f \in \mathfrak{C}([a,b], \mathbb{C})$, et on appelle
intégrale de $f$ sur $[a,b]$ le complexe tel que
$\int\limits_{a}^{b} f(t) dt = \int\limits_{a}^{b} \Re(f(t)) dt + i \int\limits_{a}^{b} \Im(f(t))$

> Soit $f \in \mathfrak{C}(I, \mathbb{K})$ où $I$ est une intervalle de $\mathbb{R}$.
> Soient $a,b \in I$ :
> - La fonction $x \mapsto \int\limits_{a}^{x} f(t) dt$ est l'unique primitive de
>   $f$ sur I qui s'annule en $a$.
> - Pour toute primitive $F$ de $f$, $\int\limits_{a}^{b} f(t) dt = F(b) - F(a) = [F(t)]_a^b$.

- Toute fonction continue sur $I$ admet des primitives sur $I$
- Si $F: x \mapsto \int\limits_{a}^{x} f(t) dt$, il s'agit de la primitive de $f$ sur
  $I$ telle que $F(a) = 0$, et $F$ est dérivable et $F' = f$ (pour tout $x \in I$)

Si $G$ est une autre primitive de la fonction $f$ comme $F' = G' = f$,
alors $\exists C \in \mathbb{K}, G = F + C$.
Donc $G(b) - G(a) = F(b) + C - (F(a) + C) = F(b) - F(a)$, soit
$[G(t)]_a^b = [F(t)]_a^b$.

Puisque $f$ est continue sur $I$, et $F$ sa primitive est continue sur $I$,
la fonction $F$ est au moins de classe $\mathcal{C}^1$ sur $I$.

### Propriétés de l'intégrale
- Si $f \in \mathfrak{C}(I, \mathbb{K})$ et $a,b \in I$, $\int\limits_{a}^{b} f = \int\limits_{b}^{a} -f$
- On peut noter, avec $a < b \in I$, $\int\limits_{[a,b]} f = \int\limits_{a}^{b} f$
- Linéarité : si $f,g \in \mathcal{C}(I,\mathbb{K})$ et $\lambda, \mu \in \mathbb{K}$,
  $\int\limits_{a}^{b} (\lambda f + \mu g) = \lambda \int\limits_{a}^{b} f + \mu \int\limits_{a}^{b} g$
- Relation de Chasles : si $a,b,c \in I$ et $f \in \mathcal{C}(I,\mathbb{K})$,
  on a $\int\limits_{a}^{b} f + \int\limits_{b}^{c} f = \int\limits_{a}^{c} f$.
- Positivité : Soit $f \in \mathcal{C}(I, \mathbb{R})$ (uniquement les fonction
  à valeurs réelles), et $a \leq b \in I$, si $f$ est positive sur $[a,b]$
  alors $\int\limits_{a}^{b} f \geq 0$.
- Croissance de l'intégrale : soient $f,g \in \mathcal{C}(I,\mathbb{R})$,
  $a \leq b \in I$, si $f \leq g$ sur $[a,b]$ alors $\int\limits_{a}^{b} f \leq \int\limits_{a}^{b} g$.
- Propriétés de la symétrie : si $f$ est continue sur $[-a,a]$ :
  - et paire : alors $\int\limits_{-a}^{a} f = 2 \int\limits_{0}^{a} f$
  - et impaire : alors $\int\limits_{-a}^{a} f = 0$

### Intégration par parties
Puisque $(uv)' = u'v + uv'$, on a
$\int\limits_{a}^{b} (uv)'(t) dt = \int\limits_{a}^{b} u'(t)v(t) dt + \int\limits_{a}^{b} u(t)v(t)' dt$,
donc $[u(t)v(t)]_a^b = \int\limits_{a}^{b} u'(t)v(t) dt + \int\limits_{a}^{b} u(t)v(t)' dt$.

> Soit $u,v \in \mathcal{C}^1([a,b],\mathbb{K})$,
> $\int\limits_{a}^{b} u'(t)v(t) dt = [u(t)v(t)]_a^b - \int\limits_{a}^{b} u(t)v'(t) dt$

On peut utiliser aussi l'IPP pour établir des récurrences de suites
d'intégrales, ou pour trouver des primitives à certaines fonctions
(la primitive qui s'annule en 0 de $\arctan$ est $\int\limits_{0}^{x} 1 \times \arctan$).

### Changement de variable
> Soit $f \in \mathcal{C}(I,\mathbb{K})$ et $\varphi \in \mathcal^1(J,I)$,
> soient $a,b \in J$, on a $\int\limits_{a}^{b} f(\varphi(t)) \varphi'(t) dt = \int\limits_{\varphi(a)}^{\varphi(b)} f(u) du$.

##### Preuve
On note $F$ une primitive de $f$, et on a $\int\limits_{\varphi(a)}^{\varphi(b)} f(u) du = F(\varphi(b)) - F(\varphi(a))$,
or $(F \circ \varphi)' = \varphi' \times (F' \circ \varphi) = \varphi' \times (f \circ \varphi)$.
Ainsi $\int\limits_{a}^{b} (F \circ \varphi)' = (F \circ \varphi)(b) - (F \circ \varphi)(a)$

__Rédaction autorisée__ : On pose le changement de variable $u = \varphi(t)$,
donc $\frac{d u}{dt} = \varphi'(t)$. On écrit $du$ comme $\varphi'(t) dt$,
enfin on calcule.

__En pratique__, pour calculer $\int\limits_{a}^{b} f(t) dt$, on
posera le changement $u = \varphi(t)$. Pour cela, il faut que $\varphi$ soit
bijective, et de classe $\mathcal{C}^1$.
