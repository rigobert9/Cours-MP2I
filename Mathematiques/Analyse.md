# Compléments d'analyse réelle
## Partie A : Bases de l'analyse réelle
Voir polycopié.

## Partie B : Fonctions usuelles
### Logarithme, exponentielle en base quelconque
$\forall x \in \mathbb{R}^{\ast}_{+}, \ln(x) = \int\limits_{1}^{x} \frac{d}{dt}$,
et $\ln'(x) = \frac{1}{x}$.
La fonction $\ln$ est croissante sur $\mathbb{R}^{\ast}_{+}$, et croît depuis
sa limite inférieure en 0 de $-\infty$ jusqu'à sa limite supérieure en $+\infty$
de $+\infty$.
La fonction $\ln : \mathbb{R}^{\ast}_{+} \to \mathbb{R}$ est bijective, et sa
réciproque est $\exp : \mathbb{R} \to \mathbb{R}^{\ast}_{+}$.

La fonction exponentielle est caractérisée par sa dérivée
$\exp' = \exp$ et par $\exp(0) = 1$.

> En base $a \mid \left\{\begin{matrix} a \in \mathbb{R}^{\ast}_{+} \\ a \neq 1 \end{matrix}\right.$,
> on appelle logarithme de base a la fonction
> $\begin{aligned} \log_a: \mathbb{R}^{\ast}_{+} &\to \mathbb{R} \\ x &\mapsto \log_a(x) = \frac{\ln(x)}{\ln(a)} .\end{aligned}$.

On obtient ainsi $\log_a(a) = 1$.

En pratique, on utilise le logarithme décimal en physique et en chimie, le
logarithme binaire en informatique, et le logarithme népérien (logarithme de
base $e$) en mathématiques.

On a les relations :
- $\ln(e^x) = x$
- $\log_2(2^K) = k$
- $\log(10^k) = k$
- etc...

Si $a \in ]0,1[$, la fonction $\log_a$ est décroissante de sa limite en 0 de
$+\infty$ à sa limite en $+\infty$ de $-\infty$, et a pour valeur en $a$ 1 et
pour valeur en $1$ 0.

Si $a \in ]1, +\infty[$, la fonction $\log_a$ est croissante de sa limite en 0 de
$-\infty$ à sa limite en $+\infty$ de $+\infty$, et a pour valeur en $a$ 1 et
pour valeur en $1$ 0.

$\forall (x,y) \in \mathbb{R}^{\ast}_{+}, \log_a(xy) = \log_a(x) + \log_a(y)$,
et $\log_a(1) = 0$.
De plus, $\log_a$ est une bijection de $\mathbb{R}^{\ast}_{+}$ dans
$\mathbb{R}$,
dérivable et qui admet donc une réciproque.

Sa réciproque est donc, soit $y \in \mathbb{R}$ et $x \in \mathbb{R}^{\ast}_{+}$,
la solution de $y = \frac{\ln(x)}{\ln(a)}$
$\Leftrightarrow \ln(a) y = \ln(x) \Leftrightarrow \exp(y \ln(a)) = a$.

> On a la réciproque du logarithme de base $a$ la fonction
> $(\log_a)^{-1}(y) = \exp(y \ln(a))$.

> On définit pour $a \in \mathbb{R}^{\ast}_{+}$ et $x \in \mathbb{R}$,
> $a^x = \exp(x \ln(a))$.

On a ainsi $\begin{aligned} \mathbb{R} &\to \mathbb{R}^{\ast}_{+} \\ x &\mapsto a^x .\end{aligned}$ la réciproque
de $\begin{aligned} \log_a: \mathbb{R}^{\ast}_{+} &\to \mathbb{R} \\ x &\mapsto \log_a(x) = \frac{\ln(x)}{\ln(a)} .\end{aligned}$
pour $\left\{\begin{matrix} a \in \mathbb{R}^{\ast}_{+} \\ a \neq 1 \end{matrix}\right.$.

Pour $(x,y) \in \mathbb{R}^2$ et pour tout $(a,b) \in (\mathbb{R}^{\ast}_{+})^2$,
on a les propriétés :
- $a^0 = 1$
- $1^\alpha = 1$
- $a^x \times a^y = a^{x + y}$
- $\frac{1}{a^x} = a^{-x}$
- $(a^x)^y = a^{xy}$
- $a^x \times b^x = (ab)^x$

##### Preuves
- $a^0 = \exp(0 \ln(a)) = \exp(0) = 1$
- $1^{\alpha} = \exp(x \ln(1)) = \exp(0) = 1$.
- $a^x \times a^y = e^{x \ln(a)} \times e^{y \ln(a)} = e^{x \ln(a) + y \ln(a)} = e^{(x + y)\ln(a)} = a^{x + y}$
- $(a^x)^y = e^{y \ln(a^x)} = e^{y \ln(\exp(x \ln(a)))} = e^{yx \ln(a)} = e^{xy}$
- $a^x \times a^y = e^{x \ln(a)} \times e^{x \ln(b)} = e^{x (\ln(a) + \ln(b))} = e^{x \ln(ab)} = (ab)^x$

#### Puissance réelle
> $x^y$ signifie :
> - si $y \in \mathbb{N}$, on peut prendre $x \in \mathbb{R}$ (y fois la
>   multiplication de x)
> - si $y \in \mathbb{Z}$, $y < 0$, on peut prendre $x \in \mathbb{R}^{\ast}$ (-y
>   fois la multiplication de $\frac{1}{x}$)
> - si $y \not\in \mathbb{Z}, y \in \mathbb{R}$ quelconque, il faut prendre
>   $x \not\in \mathbb{R}^{\ast}_{+}$ ($e^{y \ln(x)}$)

### Fonctions puissances
> $\begin{aligned} f_\alpha: \mathbb{R}^{\ast}_{+} &\to \mathbb{R} \\ x &\mapsto x^\alpha = e^{\alpha \ln(x)} .\end{aligned}$,
> avec $\alpha \in \mathbb{R}$.

On remarque les cas suivants :
- Pour $\alpha = 0$, $f_\alpha : x \mapsto 1$
- Pour $\alpha = 1$, $f_\alpha : x \mapsto x$
- Pour $\alpha = 2\mathbb{N}$, $f_\alpha : x \mapsto x^{2p}$
- Pour $\alpha = 2\mathbb{N} + 1$, $f_\alpha : x \mapsto x^{2p + 1}$
- Pour $\alpha = \frac{1}{2}$, $f_\alpha : x \mapsto \sqrt{2}$
- Pour $\alpha = -1$, $f_\alpha : x \mapsto \frac{1}{x}$

Pour $\alpha < 0$ fixé, $f_\alpha$ est un bijection strictement décroissante de
$\mathbb{R}^{\ast}_{+}$ dans $\mathbb{R}^{\ast}_{+}$.
Pour $\alpha > 0$ fixé, $f_\alpha$ est un bijection strictement croissante de
$\mathbb{R}^{\ast}_{+}$ dans $\mathbb{R}^{\ast}_{+}$.
En effet, $f_\alpha$ est dérivable sur $\mathbb{R}^{\ast}_{+}$, et on a
$\forall x \in \mathbb{R}^{\ast}_{+}, f_\alpha'(x) = \frac{\alpha}{x} \times e^{\alpha \ln(x)}$
$= \frac{\alpha}{x} \times x^\alpha = \alpha x^{\alpha - 1}$.

La limite en 0 de la fonction $f_\alpha$ est, si $\alpha > 0$,
$\alpha \ln(x)  \to_{0} -\infty$, donc $e^{\alpha ln(x)} \to _{0} 0$;
Si $\alpha < 0$, $\alpha \ln(x) \to_{0} +\infty$, donc
$e^{\alpha ln(x)} \to_{0} +\infty$.

Dans le cas où $\alpha > 0$, $f_\alpha$ se prolonge continument en 0 en ajoutant
la valeur $f_\alpha(0) = 0$. On obtient ainsi
$\begin{aligned} x^\alpha: \mathbb{R}_{+} &\to \mathbb{R}_{+} \\ x &\mapsto \left\{\begin{matrix} e^{x \ln(x)} \,\text{ si }\, x > 0 \\ 0 \,\text{ si }\, x = 0 \end{matrix}\right. .\end{aligned}$,
puisque $e^{\alpha \ln(x)} \to_{x \to 0} 0$. Ce prolongement n'est pas possible
pour $\alpha < 0$.

On peut dériver en 0 $f_\alpha$, avec $\forall x > 0, \frac{f_\alpha(x) - f_\alpha(0)}{x} = \frac{f_\alpha(x)}{x}$
$= \frac{x^\alpha}{x} = x^{\alpha - 1}$.
On obtient ainsi les limites :
- Si $\alpha > 1$, $\lim\limits_{x \to 0} x^{\alpha - 1} = 0$, et donc $f_\alpha$ est dérivable en 0,
  et $f_\alpha'(0) = 0$ (tangente horizontale).
- Si $\alpha = 1$, $\lim\limits_{x \to 0} x^{\alpha - 1} = 1$, car $f_1 = id$.
- Si $\alpha \in ]0,1[$, et donc $f_\alpha$ n'est pas dérivable en 0,
  et on a une tangente verticale en 0, soit $\lim\limits_{x \to 0} x^{\alpha - 1} = +\infty$.

## Fonctions trigonométriques réciproques
### Arcsinus
> $\sin : [\frac{-\pi}{2}, \frac{\pi}{2}] \to [-1, 1]$ est bijective, continue,
> dérivable, et strictement croissante.

> La fonction $\arcsin$ est définie comme la réciproque de $\sin$, telle que
> $\arcsin : [-1, 1] \to [\frac{-\pi}{2}, \frac{\pi}{2}]$, une fonction bijective
> continue et strictement croissante.

De plus, $\arcsin$ est dérivable, puisque $\sin' = \cos$, qui s'annule en
$\pm \frac{\pi}{2}$. Ainsi, $\sin'$ ne s'annule pas sur $]\frac{-\pi}{2}, \frac{\pi}{2}[$
donc (par théorème de la dérivée de la réciproque), $\arcsin$ est dérivable sur
$\sin(]\frac{-\pi}{2}, \frac{\pi}{2}[) = ]-1, 1[$.
Ainsi, $\forall x \in ]-1, 1[, \arcsin'(x) = \frac{1}{\cos(\arcsin x)}$.
Or, $\sin(\arcsin(x)) = x$ pour tout $x \in [-1, 1]$ car $\sin \circ \arcsin = id_{[-1, 1]}$,
et comme $\cos^2 + \sin^2 = 1$, on a $\forall x \in [-1, 1], \cos^2(\arcsin x) + \sin^2(\arcsin)$
$= \cos^2(\arcsin x) + x^2 = 1$, donc $\cos^2(\arcsin x) = 1 - x^2$, donc
$|\cos(\arcsin x)| = \sqrt{1 - x^2}$.
Or, $\arcsin(x) \in [-\frac{\pi}{2}, \frac{\pi}{2}]$, donc $\cos(\arcsin) \geq 0$,
donc $\forall x \in [-1,1], \cos(\arcsin(x)) = \sqrt{1 - x^2}$.

> La dérivée de $\arcsin$ est $\forall x \in ]-1,1[, \arcsin' = \frac{1}{\sqrt{1 - x^2}}$.

> $\arcsin$ est impaire

##### Preuve
$x \in [-1, 1], y \in [-\frac{\pi}{2}, \frac{\pi}{2}]$\
$y = \arcsin(-x)$\
$\Leftrightarrow \sin(y) = -x$\
$\Leftrightarrow -\sin(y) = x$\
$\Leftrightarrow \sin(-y) = x$\
$\Leftrightarrow -y = \arcsin(x)$\
$\Leftrightarrow y = -\arcsin(x)$

Ainsi, $\forall x \in [-1, 1], \arcsin(-x) = -\arcsin(x)$

#### Composées et identités
> On a $\sin \circ \arcsin = id_{[-1, 1]}$ et $\arcsin \circ \sin_{[-\frac{\pi}{2}, \frac{\pi}{2}]}$.

De plus, on a seulement pour les $x \in [\frac{-\pi}{2}, \frac{\pi}{2}]$,
$\arcsin(\sin x) = x$.
Ainsi, si $\sin \theta = x$, on a $\arcsin(\sin \theta)  = \arcsin(x)$

##### Preuve
- Si $\theta \in [-\frac{\pi}{2}, \frac{\pi}{2}]$, alors $\theta = \arcsin(x)$
- Si $\theta \not\in [-\frac{\pi}{2}, \frac{\pi}{2}]$, alors il existe un $k \in \mathbb{Z} \mid \theta + k\pi \in [-\frac{\pi}{2}, \frac{\pi}{2}]$ :
  - Si k est pair, alors $\sin \theta = \sin(\theta + k\pi)$, donc $\arcsin(\sin \theta) = \arcsin(\sin(\theta + k\pi))$
    $= \theta + k\pi$ et $\theta = \arcsin(x) - k\pi$.
  - Si k est impair, $\sin(\theta) = - \sin(\theta + k\pi)$ donc
    $\arcsin(\sin \theta) = \arcsin(-\sin(\theta + k\pi))$
    $= -\arcsin(\sin(\theta + k\pi)) = -(\theta + k\pi)$,
    donc $\theta = -\arcsin(x) + k\pi$.

Ainsi, si $\sin \theta = x$, alors $\theta \equiv \pm \arcsin(x [\pi])$.

Par exemple, on a donc $\arcsin(\sin(\frac{21 \pi}{4}))$, puisque $\frac{21 \pi}{4} = 5 \pi + \frac{\pi}{4}$,
$\arcsin(-\sin(\frac{\pi}{4})) = -\arcsin(\sin(\frac{\pi}{4})) = \frac{-\pi}{4}$.

### Arccosinus
> $\cos : [0, \pi] \to [-1, 1]$ est bijective, continue,
> dérivable, et strictement décroissante.

> La fonction $\arccos$ est définie comme la réciproque de $\cos$, telle que
> $\arccos : [-1, 1] \to [0, \pi]$, une fonction bijective
> continue et strictement décroissante.

De plus, $\arccos$ est dérivable, puisque $\cos' = -\sin$, qui s'annule en
$0$ et $\pi$. Ainsi, $\cos'$ ne s'annule pas sur $]0, \pi[$
donc (par théorème de la dérivée de la réciproque), $\arccos$ est dérivable sur
$\cos(]0, \pi[) = ]-1, 1[$.
Ainsi, $\forall x \in ]-1, 1[, \arccos'(x) = \frac{-1}{\sin(\arccos x)}$.
Or, $\cos(\arccos(x)) = x$ pour tout $x \in [-1, 1]$ car $\cos \circ \arccos = id_{[-1, 1]}$,
et comme $\sin^2 + \cos^2 = 1$, on a $\forall x \in [-1, 1], \cos^2(\arccos x) + \sin^2(\arccos x)$
$= \sin^2(\arccos x) + x^2 = 1$, donc $\sin^2(\arccos x) = 1 - x^2$, donc
$|\sin(\arccos x)| = \sqrt{1 - x^2}$.
Or, $\arccos(x) \in [0, \pi]$, donc $\sin(\arccos) \geq 0$,
donc $\forall x \in [-1,1], \sin(\arccos(x)) = \sqrt{1 - x^2}$.

> La dérivée de $\arccos$ est $\forall x \in ]-1,1[, \arccos' = \frac{-1}{\sqrt{1 - x^2}}$.

> $\forall x \in [-1, 1], \arccos(x) + \arcsin(x) = \frac{\pi}{2}$

##### Preuve
Soit $f = \arcsin + \arccos$, $f$ est continue sur $[-1, 1]$, dérivable sur
$]-1, 1[$ et $f' = \arcsin' + \arccos' = 0$.
On en déduit que $f$ est constante sur $]-1, 1[$, et comme $f$ est continue en 1
et en -1, on a $f$ constante sur $[-1,1]$. Or $f(0) = \arccos(0) + \arcsin(0) = 0 + \frac{\pi}{2}$
donc $f = \frac{\pi}{2}$ constante.

Autre preuve : On cherche à montrer que $\arccos(x) = \frac{\pi}{2} - \arccos(x)$, et on calcule séparément
leur sinus. On a $\sin(\arcsin(x)) = x$ et $\sin(\frac{\pi}{2} - \arccos(x)) = \cos(\arccos(x)) = x$. On vient de montrer que
$\sin \alpha = \sin \beta$, or $\alpha = \arcsin(x) \in [\frac{-\pi}{2}, \frac{\pi}{2}]$,
$\arccos(x) \in [0,\pi]$, donc $\beta = \frac{\pi}{2} - \arccos \in [\frac{-\pi}{2}, \frac{\pi}{2}]$.

#### Parité de Arccosinus
> $\arccos$ est paire

##### Preuve
À effectuer à la façon de celle de $\sin$.

#### Composées et identités
> On a $\cos \circ \arccos = id_{[-1, 1]}$ et $\arccos \circ \cos_{[0, \pi]}$.

De plus, on a seulement pour les $x \in [0, \pi]$,
$\arccos(\cos x) = x$.
Ainsi, si $\cos \theta = x$, on a $\arccos(\cos \theta)  = \arccos(x)$

### Arctangente
> $\tan : ]\frac{-\pi}{2}, \frac{\pi}{2}[ \to \mathbb{R}$ est bijective, continue,
> dérivable, et strictement croissante.

> La fonction $\arctan$ est définie comme la réciproque de $\tan$, telle que
> $\arctan : \mathbb{R} \to ]\frac{-\pi}{2}, \frac{\pi}{2}[$, une fonction bijective
> continue et strictement croissante.

$\tan' = 1 + \tan^2$ ne s'annule pas sur $]\frac{-\pi}{2}, \frac{\pi}{2}[$. Par
théorème de la dérivée de la réciproque, $\arctan$ est dérivable sur $\tan(]\frac{-\pi}{2}, \frac{\pi}{2}[) = \mathbb{R}$.
$\forall x \in \mathbb{R}, \arctan'(x) = \frac{1}{\tan'(\arctan(x))}$
$= \frac{1}{1 + \tan^2(\arctan)} = \frac{1}{1 + x^2}$.

> La dérivée de $\arctan$ est $\forall x \in ]-1,1[, \arctan' = \frac{1}{\sqrt{1 - x^2}}$.

> $\arctan$ est impaire

##### Preuve
$x \in \mathbb{R}, y \in [-\frac{\pi}{2}, \frac{\pi}{2}]$\
$y = \arctan(-x)$\
$\Leftrightarrow \tan(y) = -x$\
$\Leftrightarrow -\tan(y) = x$\
$\Leftrightarrow \tan(-y) = x$\
$\Leftrightarrow -y = \arctan(x)$\
$\Leftrightarrow y = -\arctan(x)$

Ainsi, $\forall x \in \mathbb{R}, \arctan(-x) = -\arctan(x)$

#### Composées et identités
> On a $\tan \circ \arctan = id_{\mathbb{R}}$ et $\arctan \circ \tan_{]-\frac{\pi}{2}, \frac{\pi}{2}[}$.

De plus, on a seulement pour les $x \in ]\frac{-\pi}{2}, \frac{\pi}{2}[$,
$\arctan(\tan x) = x$.
Ainsi, si $\tan \theta = x$, on a $\arctan(\tan \theta)  = \arctan(x)$

##### Preuve
Si $\theta \in \mathbb{R} \setminus \{\frac{\pi}{2} + k\pi, k \in \mathbb{Z}\}$,
il existe $k \in \mathbb{Z}$, $\theta + k\pi \in ]\frac{-\pi}{2}, \frac{\pi}{2}[$.
Par $\pi$ -périodicité, $\arctan(\tan \theta) = \arctan(\tan(\theta + k\pi))$
$\theta + k\pi \equiv \theta[\pi]$.

### Taux d'accroissement
$\lim\limits_{x \to 0} \frac{\arcsin(x)}{x} = \arcsin'(0) = \frac{1}{\sqrt{1 - 0^2}} = 1$

$\lim\limits_{x \to 0} \frac{\arctan(x)}{x} = \arctan'(0) = \frac{1}{1 - 0^2} = 1$

$\lim\limits_{x \to 0} \frac{\arccos(x)}{x} = \arccos'(0) = \frac{1}{\sqrt{1 - 0^2}} = 1$

## Fonctions hyperboliques
### Sinus et cosinus hyperboliques
> On pose pour tout $x \in \mathbb{R}$, $\cosh(x) = \frac{e^{x} + e^{-x}}{2}$
> et $\sinh(x) = \frac{e^{x} - e^{-x}}{2}$.

> $\cosh$ et $\sinh$ sont dérivables sur $\mathbb{R}$, et $\cosh' = \sinh$
> $\sinh' = \cosh$.

$\cosh$ est paire et $\sinh$ est impaire, $\cosh$ est toujours positif.
Ainsi, par tableau de variations, on a :

x                | $-\infty$ | -          | 0   | -          | $+\infty$
---              | ---       | ---        | --- | ---        | ---
$\sinh' = \cosh$ | +         | +          | +   | +          | +
$\sinh$          | $-\infty$ | croissante | 0   | croissante | $+\infty$

x                | $-\infty$ | -            | 0   | -          | $+\infty$
---              | ---       | ---          | --- | ---        | ---
$\cosh' = \sinh$ | $-\infty$ | -            | 0   | +          | $+\infty$
$\cosh$          | $+\infty$ | décroissante | 1   | croissante | $+\infty$

Les courbes représentatives des deux fonctions ont toutes deux une asymptote en
$+\infty$ de $x \mapsto \frac{1}{2}e^{x}$.

De même, on a $\cosh: \mathbb{R}_{+} \to [1; +\infty[$ bijective, $\cosh: \mathbb{R}_{-} \to [1; +\infty[$
bijective, et $\sinh: \mathbb{R} \to \mathbb{R}$ bijective.

> $\lim\limits_{x \to 0} \frac{\sinh x}{x} = \sinh' 0 = \cosh 0 = 1$

On a les relations de trigonométrie hyperbolique suivantes :
- $\forall  \in \mathbb{R}, \cosh(x) + \sinh(x) = e^{x}$
- $\forall  \in \mathbb{R}, \cosh(x) - \sinh(x) = e^{-x}$
- $\forall  \in \mathbb{R}, \cosh^2(x) - \sinh^2(x) = 1$
- $\forall  \in \mathbb{R}, (\cosh(x) - \sinh(x)) \times (\cosh(x) + \sinh(x)) = 1$

Ces fonction sont accompagnées de nombreuses relations trigonométriques
supplémentaires.
- $\cosh(a + b) = \cosh(a)\cosh(b) + \sinh(a)\sinh(b)$
- $\cos(x) = \cosh(ix)$
- $\sin(x) = \frac{1}{i} \sinh(ix)$

> La tangente hyperbolique est définie comme
> $\tanh(x) = \frac{\sinh(x)}{\cosh(x)}$.

Puisque $\forall x \in \mathbb{R}, \cosh(x) \geq 1$, $\tanh$ est définie sur $\mathbb{R}$.
On a donc $\forall x \in \mathbb{R}, \tanh(x) = \frac{e^{x} - e^{-x}}{e^x - e^{-x}} = \frac{e^{2x} - 1}{e^{2x} + 1}$.
$\tanh$ est impaire sur $\mathbb{R}$ par imparité de $\sinh$ et parité de $\cosh$.

La fonction $\tanh$ peut être dérivée sur $\mathbb{R}$, telle que
$\tanh' = (\frac{\sinh}{\cosh})' = \frac{\sinh'\cosh - \cosh'\sinh}{\cosh^2}$,
soit $\tanh' = \frac{\cosh^2 - \sinh^2}{\cosh^2} = \frac{1}{\cosh^2} = 1 - \tanh^2$.

Cette dérivée étant strictement positive, $\tanh$ est strictement croissante sur
$\mathbb{R}$, en on obtient le tableau de variations suivant :

x       | $-\infty$ | -          | 0   | -          | $+\infty$
---     | ---       | ---        | --- | ---        | ---
$\tanh$ | -1        | croissante | 0   | croissante | 1

Enfin, on a $\lim\limits_{x \to -\infty} \tanh(x) = \lim\limits_{x \to -\infty} \frac{e^{2x} - 1}{e^{2x} + 1} = \frac{0-1}{0 + 1} = 1$
et $\lim\limits_{x \to 0} \frac{\tanh x}{x} = \tanh'(0) = \frac{1}{\cosh'(0)} = 1$.

La réciproque de $\tanh$ est notée $\text{argth}: ]-1;1[ \to \mathbb{R}$.
Pour calculer cette réciproque, on résout $y = \tanh(x)$ avec $\left\{\begin{matrix} x \in \mathbb{R} \\ y \in ]-1;1[ \end{matrix}\right.$ :
$y = \tanh(x)$\
$\Leftrightarrow y = \frac{e^{2x} - 1}{e^{2x} + 1}$\
$\Leftrightarrow (e^{2x} + 1)y = e^{2x} - 1$\
$\Leftrightarrow e^{2x} (y-1) = -1 - y$\
$\Leftrightarrow e^{2x} = \frac{1 + y}{1 - y}$\
$\Leftrightarrow 2x = \ln(\frac{1 + y}{1 - y})$\
$\Leftrightarrow x = \frac{1}{2} \ln(\frac{1 + y}{1 - y})$\
$\Leftrightarrow x = \ln(\sqrt{\frac{1 + y}{1 - y}})$\

De même, cette réciproque a pour dérivée sur $\tanh(\mathbb{R}) = ]-1;1[$,
$\text{argth}'(x) = \frac{1}{\tanh'(\text{argth}(x))} = \frac{1}{1 - \tanh^2(\text{argth} x)} = \frac{1}{1 - x^2}$.
On peut obtenir ce même résultat par l'expression montrée ci-dessus.

## Fonctions de la variable réelle à valeurs complexes
> Soit $I$ un intervalle de $\mathbb{R}$,
> et $\begin{aligned} f: I &\to \mathbb{C} \\ x &\mapsto f(x) .\end{aligned}$,
> on introduit :
> - $\begin{aligned} \Re(f): I &\to \mathbb{R} \\ x &\mapsto \Re(f)(x) .\end{aligned}$
> - $\begin{aligned} \Im(f): I &\to \mathbb{R} \\ x &\mapsto \Im(f)(x) .\end{aligned}$
> - $\begin{aligned} \overline{f}: I &\to \mathbb{C} \\ x &\mapsto \overline{f(x)} .\end{aligned}$
> - $\begin{aligned} |f|: \mathbb{R} &\to \mathbb{R}_{+} \\ x &\mapsto |f(x)| .\end{aligned}$

Ainsi, $f = \Re(f) + i\Im(f)$, $f \times \overline{f} = |f|^2$,
$\Re(f) = \frac{1}{2} (f + \overline{f})$ et
$\Im(f) = \frac{1}{2} (f - \overline{f})$.

> Soit $f: I \to \mathbb{C}$, on dira que $f$ est dérivable sur $I$ si
> $\Re(f)$ et $\Im(f)$ sont dérivables sur $I$. Dans ce cas, on pose
> $f' = (\Re(f))' + i(\Im(f))'$.

Les propriétés graphiques et utilisant des inégalités n'ont plus de sens dans $\mathbb{C}$,
mais les calculs (égalités) sont toujours valables.

Soient $f$,$g$ des fonction $I \to \mathbb{C}$ dérivables, on a les propriétés :
- de linéarité
- de produit : $(fg)' = f'g + fg'$
- d'inverse : $\frac{1}{g}'$, si $g$ ne s'annule pas sur $I$, est $\frac{-g'}{g^2}$
- de quotient : si $g$ ne s'annule pas sur $I$, $(\frac{f}{g})' = \frac{f'g - fg'}{g^2}$

On aura des difficultés à composer ces fonctions, puisqu'on ne s'intéresse
qu'aux fonction de la variable réelle.

> Soir $\varphi: I \to \mathbb{C}$ dérivable en $I$, $\exp \circ \varphi: I \to \mathbb{C}$
> est dérivable sur $I$ et $(\exp \circ \varphi)' = \varphi' \times (\exp \circ \varphi)$.

Pour tout complexe $\alpha \in \mathbb{C}$, on a ainsi
$\begin{aligned} f_\alpha: \mathbb{C} &\to \mathbb{C} \\ t &\mapsto f_\alpha(t) = e^{\alpha t} .\end{aligned}$
qui est dérivable sur $\mathbb{R}$ et $f_\alpha'(t) = \alpha e^{\alpha t}$,
et $\forall n \in \mathbb{N}$, $f_\alpha$ est $n$ fois dérivable et
$\forall t \in \mathbb{R}, f_\alpha^{n}(t) = \alpha^t e^{\alpha t}$.

##### Retour sur l'exemple
Dériver $n$ fois $\begin{aligned} f: \mathbb{R} &\to \mathbb{R} \\ x &\mapsto f(x) = e^{x} \times \cos(x) .\end{aligned}$.
On a $e^x \times \cos x = e^x \times \Re(e^{ix}) = \Re(e^{x} e^{ix}) = \Re(e^{(1 + i) x})$.
On note la fonction $x \mapsto e^{(1 + i)x}$.

Ainsi, $f^{(n)} = (\Re(g))^{(n)} = \Re(g)^{(n)}$, or avec $\alpha = 1 + i$, $g(x) = e^{\alpha x}$.
Donc, $\forall n \in \mathbb{N}, \forall x \in \mathbb{R}, g^{(n)}(x) = \alpha^n e^{\alpha x}$
$= (1 + i)^n e^{(1 + i)x}$.

Or, $(1 + i)^n = (\sqrt{2} e^{i \frac{\pi}{4}})^n = (\sqrt{2})^n e^{i \frac{n\pi}{4}}$,
donc $g^{(n)}(x) = \sqrt{2}^n e^{x} e^{i (x + \frac{n\pi}{4})}$.

Ainsi, $f^{(n)} = \Re(g^{(n)})$ donne
$\forall x \in \mathbb{R}, f^{(n)}(x) = \sqrt{2}^n e^{x} \cos(x + \frac{n\pi}{4})$.

#### Preuve
$\varphi = f + ig$ où $f: I \to \mathbb{R}$, $g: I \to \mathbb{R}$
(avec $f = \Re(\varphi)$ et $g = \Im(\varphi)$).
Alors $\varphi' = f' + ig'$. On veut dériver $e^{\varphi} = e^{f + ig}$
$= e^{f}(\cos g + i \sin g)$. On a alors
$\Re(e^{\varphi}) = e^{f} \cos g$ et
$\Im(e^{\varphi}) = e^f \sin g$.

Alors $\Re(e^{\varphi})' = f' e^{f} \cos g + e^f \times (-g' \sin g) = e^f (f' \cos g - g' \sin g)$,
et $\Im(e^{\varphi})' = f' e^{f} \sin g + e^f \times (g' \cos g) = e^f (f' \sin g + g' \cos g)$,
donnant $\Re(e^\varphi)' + i\Im(e^\varphi)' = e^f \times \[\cos g \times (f' + ig') + i \sin g \times (f' + ig')\]$
$= e^f \times \varphi' \times (\cos g + i \sin g) = e^f \times \varphi' \times e^{ig}$
$= \varphi' \times e^{f + ig}$.
