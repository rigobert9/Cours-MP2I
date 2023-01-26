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
