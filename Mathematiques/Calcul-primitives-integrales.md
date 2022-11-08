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
$\frac{1}{x}$                                            | $\ln(                               | x      | )$ | $\mathbb{R}^{\ast}_{+}$ ou $\mathbb{R}^{\ast}_{-}$
$e^{x}$                                                  | $e^x$                               | $\mathbb{R}$
$e^{\alpha x}, \alpha \in \mathbb{C}^{\ast}$             | $\frac{1}{x} e^{\alpha x}$          | $\mathbb{R}$
$\sin x$                                                 | $-\cos x$                           | $\mathbb{R}$
$\cos x$                                                 | $\sin x$                            | $\mathbb{R}$
$\sinh x$                                                | $\cosh x$                           | $\mathbb{R}$
$\cosh x$                                                | $\sinh x$                           | $\mathbb{R}$
$\ln(x)$                                                 | $x \ln(x) - x$                      | $\mathbb{R}^{\ast}_{+}$
$\frac{1}{1 + x^2}$                                      | $\arctan$                           | $\mathbb{R}$
$\frac{1}{\sqrt{1 - x^2}}$                               | $\arcsin$                           | $]-1;1[$
$\tan x$                                                 | $-\ln(                              | \cos x | )$ | $]\frac{-\pi}{2},\frac{\pi}{2}[ + \pi\mathbb{Z}$
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
même. Ainsi, $\forall x \neq a,b, \frac{1}{(x-a)(x-b)} = \frac{1}{a-b}(\frac{1}{x-a} - \frac{1}{x-b})$,
et cette fonction se primitive donc en $x \mapsto \frac{1}{a-b}(\ln(|x-a|) - \ln(|x-b|))$.
