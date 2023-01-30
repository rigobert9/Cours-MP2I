# Limites et continuité
## Limites
On étend les résultats sur les suites réelles aux fonctions réelles.

On appelle un voisinage de $a \in \mathbb{R}$ est $[a - \eta, a + \eta]$,
avec $\eta > 0$. Un voisinage de $+\infty$ est $[A, +\infty[$, avec $A \in \mathbb{R}$.

### Définition de la limite
> Limite finie : Soit $f: I \to \mathbb{R}$, avec $f$ définie au voisinage de $a$
> où $a \in \overline{\mathbb{R}}$, on dira que $f$ tend vers $\ell \in \mathbb{R}$
> en $a$ si
> $\forall \varepsilon > 0, \exists V \text{ un voisinage de } a \mid \forall x \in I, x \in V \Rightarrow |f(x) - \ell| \leq \varepsilon$.
> On note $f(x) \xrightarrow[x \to a]{} \ell$.

En détail, si $a \in \mathbb{R}$ est fini, alors on a l'équivalence de $f(x) \xrightarrow[x \to a]{} \ell$ avec
$\forall \varepsilon > 0, \exists \eta > 0, \forall x \in I, |x - a| \leq \eta \Rightarrow |f(x) - \ell| \leq \varepsilon$.

> Si $f(a)$ est déjà définie et si $f(x) \to \ell$, alors nécessairement $\ell = f(a)$.

En effet, avec $x = a$, $\forall \varepsilon > 0, \exists \eta > 0, a \in I, |a - a| \leq \eta \Rightarrow |f(a) - \ell| \leq \varepsilon$,
donc $|f(a) - \ell| = 0$.

Dans le cas de $a = +\infty$, $f(x) \xrightarrow[x \to \infty]{} \ell$ avec $\ell \in \mathbb{R}$,
on a l'équivalence
$\forall \varepsilon > 0, \exists A \in \mathbb{R}, \forall x  \in I, x \geq A \Rightarrow |f(x) - \ell| \leq \varepsilon$.

Dans le cas de $a = -\infty$, $f(x) \xrightarrow[x \to \infty]{} \ell$ avec $\ell \in \mathbb{R}$,
on a l'équivalence
$\forall \varepsilon > 0, \exists A \in \mathbb{R}, \forall x  \in I, x \leq A \Rightarrow |f(x) - \ell| \leq \varepsilon$.

Dans le cas d'une limite infinie, les définitions ont un équivalent différent.
On dit ainsi que $f$ tend vers $+\infty$ en $a$ si
$\forall M \in \mathbb{R}, \exists V \text{ un voisinage de } a \mid \forall x \in I, x \in V \Rightarrow f(x) \geq M$.,
aussi équivalent à
$\forall M \in \mathbb{R}, \exists \eta > 0, \forall x \in I, |x - a| \leq \eta =. f(x) \geq M$,
ou encore
$\forall M \in \mathbb{R}, \exists A \in \mathbb{R}, \forall x \in I, x \geq A \Rightarrow f(x) \geq M$.
On peut définir de même avec $f(x) \leq M$ les caractérisations de la limite
infinie négative.

### Caractérisation séquentielle
> Soit $f: I \to \mathbb{R}$ définie au voisinage de $a \in \overline{\mathbb{R}}$, soit
> $\ell \in \overline{\mathbb{R}}$. On a l'équivalence entre les affirmations :
> 1. $f(x) \xrightarrow[x \to a]{} \ell$
> 2. $\forall (x_n)_n \in I^{\mathbb{N}} \mid (x_n) \to a, f(x_n) \xrightarrow[n \to +\infty]{} \ell$

__Preuve :__
- (1. $\to$ 2.) On suppose $f(x) \xrightarrow[x \to a]{} \ell$. Soit $(x_n)_n \in I^{\mathbb{N}} \mid x_n \to a$.
  On se place dans le cas où $\ell \in \mathbb{R}$ et $a \in \mathbb{R}$.
  Soit $\varepsilon > 0$, on sait que $\exists \eta > 0 \mid \forall x \in I, |x - a| \leq \eta \Rightarrow |f(x) - ll| \leq \varepsilon$.
  De plus, en prenant $x_n \xrightarrow[x \to \infty]{} a$, avec $\eta$ (au lieu
  de $\varepsilon$), $\exists n_0, \forall n \geq n_0, |x_n - a| \leq \eta$.
  Ainsi, $x_n \in I$.
  $|x_n - a| \leq \eta$, donc $|f(x_n) - \ell| \leq \varepsilon$.
  On a montré $\forall \varepsilon > 0, \exists n_0, \forall in \geq n_0, |f(x_n) - \ell| \leq \varepsilon$, c'est-à-dire
  $f(x_n) \xrightarrow[x \to \infty]{} \ell$.
- (2. $\to$ 1.) On prouve par contraposée, en supposant que $f \not\rm \xrightarrow[x \to a]{} \ell$.
  On a alors
  $\exists \varepsilon > 0, \forall \eta > 0, \exists x \in I, |x - a| \leq \eta \land |f(x) - \ell| > \varepsilon$.
  On construit pour chaque $n \in \mathbb{N}$, et on choisit $\eta_n = \frac{1}{n + 1}$,
  $\eta > 0$, donc il existe $x_n \in I \mid |x_n - a| \leq \frac{1}{n + 1}$
  et $|f(x_n) - \ell| > \varepsilon$.
  Ainsi, la suite $(x_n)_{n \in \mathbb{N}} \in I^{\mathbb{N}}$ et
  $\forall n \in \mathbb{N}, |x_n - a| \leq \frac{1}{n + 1} \land |f(x_n) - \ell| > \varepsilon$.
  La contraposée est donc terminée.

Ces caractérisation permettent de grandes conséquences : l'équivalence dans le
premier sens prouve le théorème de composition des limites, et le second sens
permet de montrer l'absence de limite (par exemple pour $\cos x$).

### Limites à gauche et à droite
Soit $f:D \to \mathbb{R}$, et $a \in D$, on définit
$\left\{\begin{matrix} D^{+} = D \cap ]a,+\infty[ \\ D^{-} = D \cap ]-\infty, a[ \end{matrix}\right.$.
Si $f\restriction_{D^{+}}$ admet une limite en $a$, on appelle limite à droite
en $a$ cette limite. En détail, on écrira
$f(x) \xrightarrow[x \to a, x > a]{} \ell_d$ si
$\forall \varepsilon > 0, \exists \eta > 0, \forall x \in D^{+}, |x - a| \leq \eta \Rightarrow |f(x) - \ell_d| \leq \varepsilon$,
soit $\forall x \in D, a < x \leq x + \eta$.
On note $f(x) \xrightarrow[x \to a, x > a]{} \ell_d$ comme
$f(x) \xrightarrow[x \to a^{+}]{} \ell_d$. On écrit parfois
$\ell_d = f(a^{+})$.

Les définitions sont identiques à gauche, et on note
$f(x) \xrightarrow[x \to a^{-}]{} \ell_g$

Soit $f: D \to \mathbb{R}$ et $a \in D$ intérieur :
- Si $f \xrightarrow[x \to a]{} \ell$ alors $f \xrightarrow[x \to a^{+}]{} \ell$
  et $f \xrightarrow[x \to a^{-}]{} \ell$
- Inversement, si la limite à droite et à gauche sont identiques,
  et que cette valeur est celle de $f(\ell)$, alors la limite a la même valeur
- Si la fonction n'est pas définie en ce point, et que la limite à droite et à
  gauche du point est la même, alors la limite de la fonction en ce point
  est identique

### Fonction monotones
> Soit $f: ]a,b[ \to \mathbb{R}$ monotone, avec $a,b \in \overline{\mathbb{R}} \mid a < b$,
> alors $f$ possède une limite en $a$ et un limite en $b$.

Précisément, si $f$ est croissante sur $]a,b[$, la limite à gauche en $a$ est la
limite en $a$, et est la borne inférieure de la fonction $f$; idem pour la
limite à droite/borne supérieure en $b$.
Si $f$ est décroissante, les résultats sont les mêmes dans l'autre sens.

__Preuve :__ Soit $f$ croissante sur $]a,b[$, on regarde la limite en $b$ :
- Si $f$ est majorée sur $]a,b[$, on note $\ell = \text{sup}(]a,b[) f \in \mathbb{R}$.
  Soit $\varepsilon > 0$, $\ell - \varepsilon < \ell$, donc $\ell - \varepsilon$
  n'est pas la borne supérieure et $\ell - \varepsilon$ n'est pas un majorant.
  Ainsi, $\exists x_0 \in ]a,b[, \ell - \varepsilon < f(x_0)$. Par croissance
  de $f$ sur $[x_0,b[$, $\forall x \in [x_0,b[$,
  $\ell - \varepsilon < f(x_0) \leq f(x) \leq \ell$,
  donc $|f(x) - \ell| \leq \varepsilon$.
  Ainsi, pour tout $\varepsilon > 0$, $\exists v$ un voisinage de $b$ tel que
  $\forall x \in ]a,b[, x \in v \Rightarrow |f(x) - \ell|$,
  donc $\lim\limits_{x \to b} f = \ell$.
- Si $f$ n'est pas majorée sur $]a,b[$, alors
  $\text{sup}(]a,b[) f = +\infty$. On montre alors
  que $\lim\limits_{b} f = +\infty$, soit
  $M \in \mathbb{R}$, $M$ n'est pas un majorant de $f$,
  donc $\exists x_0 \in ]a,b[ \mid f(x_0) > M$, or $f$ est croissante
  donc $\forall x \in [x_0,b[, f(x_0) \leq f(x)$,
  $\forall x \in [x_0,b[, f(x) > M$, donc
  $\lim\limits_{b} f = +\infty$.

> Corollaire : Toute fonction monotone sur un intervalle $I$ admet des limites à
> gauche et à droite en tout point intérieur de $I$ et une limite à droite en son
> extrémité gauche et une limite à gauche en son extrémité droite.

Plus précisément, si $f$ est croissante sur $I$ et $a \in I$,
on a $f(a^{-}) \leq f(a) \leq f(a^{+})$.

## Continuité
### Définition
> Soit $f: D \to \mathbb{R}$ et $a \in D$,
> $f$ est continue sur en $a$ si $f(x) \xrightarrow[x \to a]{} f(a)$.

> $f$ est continue en $D$ si $f$ est continue en tout point de $D$.

Cette propriété est donc équivalente à
$\forall a \in D, \forall \varepsilon > 0, \exists \eta > 0, \forall x \in D, |x - a| \leq \eta \Rightarrow |f(x) - f(a)| \leq \varepsilon$.

On a l'équivalence, comme la dernière fois, avec une interprétation
séquentielle, entre ces deux propositions :
- $f$ est continue en $a$
- Pour toute suite $(x_n)_n$ qui converge vers $a$, la suite
  $(f(x_n))_n$ converge vers $f(a)$.

> $f$ est continue à droite en $a$ si $f(x) \xrightarrow[x \to a, x > a]{} f(a)$,
> et de même à gauche.

La fonction est continue en un point si et seulement si elle est continue à
gauche et à droite en ce point.

### Fonction lipschitziennes
> Soit $f: I \to \mathbb{R}$, avec $I$ un intervalle de $\mathbb{R}$, on dit que
> $f$ est lipschitzienne sur $I$ si
> $\exists K > 0, \forall (x,y) \in I^2, |f(x) - f(y)| \leq K \times |x - y|$.

> Toute fonction lipschitzienne sur $I$ est continue sur $I$

__Preuve :__ Soit $f: I \to \mathbb{R}$, on a $\exists K > 0, \forall (x,y) \in I^2, |f(x) - f(y)| \leq K \times |x - y|$.
Soit $a \in I$ et $\varepsilon > 0$. On cherche $\eta > 0$ tel que
si $|x - a| \leq \eta$ alors $|f(x) - f(a)| \leq \varepsilon$.
On choisit $\eta = \frac{\varepsilon}{K}$.
$\forall x \in I, |f(x) - f(a)| \leq K |x - a|$, et si $|x - a| \leq \frac{\varepsilon}{K}$,
alors $|f(x) - f(a)| \leq K |x - a| \leq K \times \frac{\varepsilon}{K} = \varepsilon$.
On obtient donc bien la caractérisation de la continuité de $f$ sur $I$.

> On dit que $f$ est $k$-lipschitzienne sur $I$ si
> $\forall (x,y) \in I^2, |f(x) - f(y)| \leq k \times |x - y|$.

> Toute fonction $k$-lipschitzienne sur $I$ est lipschitzienne sur $I$.

La fonction valeur absolue est $1$-lipschitzienne sur $\mathbb{R}$,
$\sin$ est $1$-lipschitzienne sur $\mathbb{R}$.

__Preuve :__ $\sin x - \sin y = 2 \cos(\frac{x + y}{2}) \sin(\frac{x - y}{2})$.
De plus, $|\sin(t)| \leq |t|$, donc $|\sin(x) - \sin(y)| \leq 2 |\cos(\frac{x + y}{2})| \times |\sin(\frac{x - y}{2})|$
$\leq 1 \times |x - y|$.

La fonction racine carrée sur $\mathbb{R}_{+}$ n'est pas lipschitzienne,
car par l'absurde s'il existe $k > 0$ tel que
$\forall (x,y) \in \mathbb{R}_{+}, |\sqrt{x} - \sqrt{y}| \leq k |x - y|$,
alors your $y = 0$, $\forall x \in \mathbb{R}_{+}, \sqrt{x} \leq k x$,
donc $\forall x > 0, \frac{1}{\sqrt{x}} \leq k$, or
$\lim\limits_{x \to 0^{+}} +\infty$. En revanche, pour tout
$a > 0$, la racine carrée est lipschitzienne sur
$[a, +\infty[$, car $\forall (x,y) \in [a, +\infty[^2$,
$\sqrt{x} - \sqrt{y} = \frac{x - y}{\sqrt{x} + \sqrt{y}}$,
or $\sqrt{x} + \sqrt{y} \geq 2 \sqrt{a} > 0$, donc
$\frac{1}{\sqrt{x} + \sqrt{y}} \leq \frac{1}{2 \sqrt{a}}$,
donc $\forall (x,y) \in [a,+\infty[^2, |\sqrt{x} - \sqrt{y}| \leq \frac{1}{2 \sqrt{a}} \times |x - y|$.
Ainsi, la racine carrée est $\frac{1}{2 \sqrt{a}}$-lipschitzienne
sur $[a,+\infty[$, pour $a > 0$.

La fonction carrée n'est pas lipschitzienne sur $\mathbb{R}$. On le prouve par
l'absurde : on prend un $k > 0$ qui fonctionne. Pour $y = 0$,
$\forall x \in \mathbb{R}_{+}^{\ast},x^2 \leq k x \Leftrightarrow x \leq k$,
et $\mathbb{R}_{+}^{\ast}$ n'est par majoré.
En revanche, $x \mapsto x^2$ est lipschitzienne sur tout segment
$[-M,M]$ avec $M \in \mathbb{R}_{+}^{\ast}$. En effet,
$x^2 - y^2 = (x - y)(x + y)$, or $|x + y| \leq |x| + |y| \leq 2M$,
pour $(x,y) \in [-M,M]^2$. Finalement,
$\forall (x,y) \in [-M,M]^2, |x^2 - y^2| \leq 2M |x - y|$.
La fonction est donc $2M$-lipschitzienne sur cet intervalle.

> Si $f: I \to \mathbb{R}$ est $k$-lipschitzienne sur $I$ et
> $g: J \to \mathbb{R}$ est $k'$-lipschitzienne sur $I$,
et $\lambda \in \mathbb{R}$, alors $f + g$ est
$(k + k')$-lipschitzienne sur $I$ et $\lambda f$ est
$(\lambda k)$-lipschitzienne sur $I$.

....

__Preuve :__

> Si $f: I \to \mathbb{R}$ est $k$-lipschitzienne sur $I$ et
> $g: J \to \mathbb{R}$ est $k'$-lipschitzienne sur $J$,
> et $f(I) \subset J$, alors $g \circ f$ est
> $kk'$-lipschitzienne sur $I$.

__Preuve :__ $\forall (x,y) \in I^2, |g \circ f(x) - g \circ (y)|$
$= |g(f(x)) - g(f(y))| \leq k' |f(x) - f(y)| \leq k'k |x - y|$.

### Théorème des valeur intermédiaires
> Soit $I$ un intervalle et $f: I \to \mathbb{R}$ continue sur $I$,
> soient $a,b \in I$ avec $a < b$, tels que $f(a) \times f(b) < 0$,
> alors $\exists c \in [a,b] \mid f(c) = 0$.

__Preuve :__ On prouve cette propriété constructivement, par dichotomie.
On pose deux suites $(a_n)_n$ et $(b_n)_n$, avec $a_0 = a$ et $b_0 = b$.
Soit $n \in \mathbb{N}$ tel que $a_n$ et $b_n$ sont construits,
avec $f(a_n) f(b_n) \leq 0$. On pose $C_n = \frac{a_n + b_n}{2}$.
Si $f(a_n) \times f(c_n) \leq 0$, on pose
$\left\{\begin{matrix} a_{n+1} = a_n \\ b_{n+1} = c_n \end{matrix}\right.$,
et sinon $\left\{\begin{matrix} a_{n+1} = c_n \\ b_{n+1} = b_n \end{matrix}\right.$.
Ainsi, $\forall in \in \mathbb{N}, f(a_n) \times f(b_n) \leq 0$. De plus,
$(a_n)_n$ est croissante, $(b_n)_n$ est décroissante,
et $b_{n+1} - a_{n+1} = \frac{b_n - a_n}{2}$, géométrique de raison $\frac{1}{2}$,
$\forall n, b_n - a_n = \frac{b - a}{2^{n}}$, et tend donc vers $0$.
Ainsi, $(a_n)_n$ et $(b_n)_n$ sont des suite adjacentes, et convergent donc vers
une même limite, notée $c$. De plus $\forall n, a_n \in [a,b]$, donc
$c \in [a,b]$. Or, $f$ est continue sur cet intervalle, donc en $c$,
et donc $a_n \xrightarrown[n \to \infty]{} c$ et donc
$f(a_n) \xrightarrow[+\infty]{} f(c)$, et pareil pour $b_n$.
Or, $\forall n \in \mathbb{N}, f(a_n) f(b_n) \leq 0$. À la limite,
$f(c)^2 \leq 0$, donc $f(c) = 0$.

> __Corollaire :__ Si $f$ est continue sur $I$ à valeurs dans $\mathbb{R}$
> et si $a,b \in I$ avec $f(a) \leq f(b)$, alors tout $y \in [f(a), f(b)]$
> possède un antécédent par $f$ dans $[a,b]$.

__Preuve :__ Soit $y \in [f(a), f(b)]$, on pose $g(x) = f(x) - y$.

> __Corollaire :__ Si $f$ est continue sur $I$ et ne s'annule par sur $I$, alors
> $f$ est de signe constant.

Cette propriété se prouve par la contraposée du théorème des valeurs
intermédiaires.

> __Corollaire topologique :__ L'image par une fonction continue d'un intervalle
> est un intervalle.

__Preuve :__ Soit $f: I \to \mathbb{R}$ continue, on veut montrer que son image
$f(I)$ est un intervalle.
On va montrer que si $\alpha < \beta$ avec $\alpha, \beta \in f(I)$,
alors $[\alpha,\beta] \subset f(I)$
(caractérisation des intervalles de $\mathbb{R}$ par les parties convexes).
Si $\alpha,\beta \in f(I)$, alors il existe $a,b \in I$,
$\left\{\begin{matrix} \alpha = f(a) \\ \beta = f(b) \end{matrix}\right.$.
Par théorème des valeurs intermédiaires, tout point de
$[f(a),f(b)]$ possède un antécédent dans $[a,b]$ par $f$,
donc $[f(a),f(b)] \subset f([a,b]) \subset f(I)$.

##### Exercice : TVI généralisé
Soit $f$ continue sur un intervalle $I$ d'extrémités $a$ et $b$,
si $f$ admet des limites (dans $\overline{\mathbb{R}}$) en $a$ et en
$b$, alors tout point strictement compris entre ses limites admet
un antécédent par $f$ dans $I$.
Grâce aux définitions des limites, on fixe par exemple
$\ell_1 < \ell_2$ et $y \in ]\ell_1, \ell_2[$. Comme
$f  \xrightarrow[a]{} \ell_1 < y$, $\exists u \mid f(u) < y \land u \in I$.
De même, $\lim\limits_{b} f = \ell_2 > y$,
$\exists v \in I \mid f(v) > y$.
Ainsi, $y \in [f(a), f(b)]$ et $f$ étant continue sur $I$, elle l'est
sur $[u,v]$, donc $y$ admet un antécédent par $f$ dans $[u,v]$,
donc dans $I$.
