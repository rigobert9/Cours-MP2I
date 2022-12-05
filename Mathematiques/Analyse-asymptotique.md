# Analyse asymptotique
## Comportement sur les suites
Soient $u,v \in \mathbb{K}^{\mathbb{N}}$ avec $\mathbb{K}$ qui est $\mathbb{R}$
ou $\mathbb{C}$. On se place dans l'hypothèse que ces suites ne s'annulent pas à
partir d'un certain rang. Ainsi les suites $\frac{u}{v}$ et $\frac{v}{u}$ sont
bien définies à partir d'un certain rang.

### Suites négligeables, dominées, équivalentes
> On dit que $u$ est dominée par $v$, qu'on note $u = O(v)$
> ou $u_{n} = O(v_{n})$ si la suite $\frac{u}{v}$ est bornée.

On traduit cette condition par l'expression logique
$\exists M \mid \forall n \in \mathbb{N}, |\frac{u_{n}}{v_n}| \leq M$.
On peut aussi comparer $|u_{n}| \leq M \times |v_{n}|$.

Cette notation est aussi valable dans un contexte à partir d'un certain rang.

La relation d'égalité à $O$ est une relation transitive et réflexive. La
relation n'a néanmoins ni symétrie ni antisymétrie.

- Si $u = O(1)$, alors $u$ est bornée et réciproquement
- Soit $K \in \mathbb{R}_{+}^{\ast}$, si $u = O(K)$ alors
  $u = O(1)$.

> On dit que $u$ est négligeable devant $v$, noté $u = o(v)$, lorsque
> $\frac{u}{v} \to 0$.

On peut aussi dire qu'il existe une suite $e_n$ qui converge en $0$ telle que
$\forall n, u_{n} = e_n \times v_{n}$.

> Si $u = o(v)$, alors $u = O(v)$.

La relation d'égalité à $o(v)$ est uniquement transitive.

> On dit que $u$ est équivalente à v si $\frac{u}{v} \to 1$. On
> note $u \sim v$ ou $u_{n} \sim v_{n}$.

> $\sim$ est une relation d'équivalence sur l'ensemble des suites qui ne
> s'annulent pas à partir d'un certain rang.

- $\sim$ est réflexive car $\frac{u_{n}}{u_{n}} = 1 \to 1$
- $\sim$ est transitive car si $u_{n} \sim v_{n}$ et $v_{n} \sim w_n$ alors
  $\frac{u_{n}}{w_n} = \frac{u_n}{v_n} \times \frac{v_{n}}{w_n} \to 1$
- $\sim$ est symétrique, car si $\frac{u_{n}}{v_{n}} \to 1$, alors $\frac{v_n}{u_{n}} \to 1$.

> Soit $u$ une suite qui converge vers $\ell$ et $\ell \neq 0$, alors $u_n \sim \ell$.
> Réciproquement, si $u_{n} \sim \ell$ avec $\ell$ une constante non nulle, alors
> $u$ converge vers $\ell$.

> $u_{n} \sim v_{n} \Leftrightarrow u_{n} - v_{n} = o(v_{n})$

__Preuve :__ $u_{n} \sim v_n \Leftrightarrow \frac{u_{n}}{v_{n}} \to 1$\
$\Leftrightarrow (\frac{u_{n}}{v_{n}} - 1) \to 0$\
$\Leftrightarrow \frac{u_{n} - v_{n}}{v_{n}} \to 0$\
$\Leftrightarrow u_{n} - v_{n} = o(v_{n})$

### Utilisation des notations de Landau
Lien avec les constantes multiplicatives :
- Si $u = o(v)$ et $\lambda \in \mathbb{K}$, alors $\lambda u = o(v)$.
- Si $u = O(v)$ et $\lambda \in \mathbb{K}$, alors $\lambda u = O(v)$.

On pourra ainsi toujours faire disparaître les constantes multiplicatives au
profit de l'unité dans ces notations.

- Si $u = o(w)$ et $v = o(w)$, alors $\lambda u + \mu v = o(w)$.
- Si $u = O(w)$ et $v = O(w)$, alors $\lambda u + \mu v = O(w)$.

### Croissances comparées
Pour $(\alpha, \beta, \gamma) \in (\mathbb{R}_{+}^{\ast})^3$ :
- $\lim\limits_{n \to + \infty} \frac{e^{\gamma n}}{n^{\alpha}} = +\infty$, donc
  $n^{\alpha} = o(e^{\alpha n})$
- $\lim\limits_{n \to + \infty} \frac{n^{\alpha}}{(\ln n)^{\beta}} = +\infty$,
  donc $\ln(n)^\beta = o(n^{\alpha})$ et $\frac{1}{n^{\alpha}} = o(\frac{1}{\ln(n)^{\beta}})$
- $\lim\limits_{n \to + \infty} e^{-\alpha n} \times n^{\alpha} = 0$, donc $e^{-\alpha n} = o(\frac{1}{n^{\alpha}})$

On a de même, en $+\infty$, avec $\alpha > 0$, $\beta > 0$, $q > 1$,
$\ln(n)^{\beta} \ll n^{\alpha} \ll q^{n}$.
En $0$, avec $q \in ]0,1[$, $q^{n} \ll \frac{1}{n^{\alpha}} \ll \frac{1}{\ln(n)^{\beta}}$.

De plus, pour $q > 1$, $q^n = o(n!)$ et $n! = o(n^{n})$.

__Preuve :__\
On pose $u_{n} = \frac{q^{n}}{n!}$, et on montre que $u \to 0$.
$\frac{u_{n+1}}{u_n} = \frac{q}{n+1} \to 0$\
$n! = \prod\limits_{k = 1}^{n} k = 2 \times 3 \times \ldots \times n$,
et $n^{n} = \prod\limits_{k = 1}^{n} n \geq n \times n \times \ldots \times n$,
donc $n^{n} \geq n \times n!$, donc $\frac{n!}{n^{n}} \leq \frac{1}{n}$.

> Théorème de Stirling : $n! \sim n^{n} \times e^{-n} \times \sqrt{2 \pi n}$

### Opérations sur ls équivalences
> Si $u,v \in \mathbb{R}^{\mathbb{N}}$ telles que $u_{n} \sim v_{n}$,
> alors $u_{n}$ et $v_{n}$ sont de même signe à partir d'un certain rang.

__Preuve :__ Si $\frac{u_{n}}{v_{n}} \to 1 > 0$, à partir d'un certain rang $n_0$,
$\forall n \in n_0$, $\frac{u_n}{v_{n}} \geq 0$, donc $u_n$ et $v_{n}$ sont de
même signe.

> Si $u_{n} \sim v_{n}$ et si $\lim v_{n} = \ell \in \mathbb{C}$ ou
> $\overline{\mathbb{R}}$, alors $\lim u_{n} = \ell$.

Attention, la réciproque est partielle : si $\lim u_{n} = \ell$, avec $\ell \in \mathbb{C}$ ou
$\mathbb{R}$, avec $\ell \neq 0$, alors $u_{n} \sim \ell$.

__Preuve :__ Si $u_{n} \sim v_{n}$ et $v_{n} \to \ell$, alors $u_{n} = v_{n} \times \frac{u_{n}}{v_{n}}$,
donc $\lim u_{n} = \ell$.

__Opérations licites :__ Produit, quotient et puissance fixe :
- Si $u_{n} \sim v_{n}$ et $a_n$ une suite, alors :
  - $u_{n} \times a_n \sim v_{n} \times a_n$
  - $\frac{1}{u_{n}} \sim \frac{1}{v_{n}}$
- Si $p \in \mathbb{Z}$ et $u_{n} \sim v_{n}$, alors $(u_{n})^p \sim (v_{n})^p$
- Si $\alpha \in \mathbb{R}$ et $u_{n} \sim v_{n}$ avec $v_{n} > 0$ à partir d'un certain rang
  alors $(u_{n})^\alpha \sim (v_{n})^{\alpha}$

__Preuve :__ si $\frac{u_{n}}{v_{n}} \to 1$, alors
- $\frac{u_{n} a_n}{v_{n} a_n} = \frac{u_{n}}{v_{n}} \to 1$
- $\frac{\frac{1}{u_{n}}}{\frac{1}{v_{n}}} = \frac{v_{n}}{u_{n}} \to 1$
- $\frac{u_{n}^{\alpha}}{v_{n}^{\alpha}} = (\frac{u_{n}}{v_{n}})^{\alpha} \to 1$

La somme d'équivalents est proscrite, ainsi que la composition d'équivalents.

### Limites des taux d'accroissements usuels
> Composition de limites : si $\lim\limits_{x \to a} f(x) = \ell$ et si $\lim\limits_{n \to + \infty} u_{n} = a$,
> alors $\lim\limits_{n \to + \infty} f(u_{n}) = \ell$.

Avec les taux d'accroissements usuels en 0, $\lim\limits_{u \to 0} \frac{f(u) - f(0)}{u} = f'(0)$
(pour une fonction dérivable en $0$) et $\lim\limits_{n \to + \infty} u_{n} = 0$,
on a $\lim\limits_{n \to + \infty} \frac{f(u_n) - f(0)}{u_{n}} = f'(0)$.

Pour $f'(0) \neq 0$, on a $(f(u_{n}) - f(0)) \sim f'(0) \times u_{n}$.

Si $u$ est une suite qui converge vers $0$, $e^{u_{n}} - 1 \sim u_{n}$
et $\ln(1 + u_{n}) \sim u_{n}$.

Pour $\alpha \in \mathbb{R}$, $(1 + u_{n})^{\alpha} - 1 \sim \alpha u_{n}$
et $\sqrt{1 + u_{n}} - 1 \sim \frac{1}{2} u_{n}$.

On a de même :
- $\sin u_{n} \sim u_{n}$
- $\tan u_{n} \sim u_{n}$
- $\sinh u_{n} \sim u_{n}$
- $\tanh u_{n} \sim u_{n}$
- $\arcsin u_{n} \sim u_{n}$
- $\arctan u_{n} \sim u_{n}$
- $\cos u_{n} - 1 \sim \frac{-1}{2} u_{n}^2$
- $\cosh u_{n} - 1 \sim \frac{1}{2} u_{n}^2$

### Développement limité
On a (Développement limité d'ordre 1), $\lim\limits_{h \to 0} f(a + h) = f(a) + h f'(a) + o(h)$,
on peut noter ainsi, lorsque $a = 0$ :
- $\exp(h) \approx 1 + h$
- $\sin(h) = h$
- $\sqrt{1 + h} \approx 1 + \frac{1}{2} h$
- $(1 + h)^{\alpha} \approx 1 + \alpha h$

En physique, ce premier ordre suffira largement pour des simplifications ou des
équations différentielles. En mathématiques, on pourra aller plus loin dans
l'inspection du $o(h)$ en utilisant Taylor.

## Comparaison de fonctions
On adapte les notations $o$, $O$ et $\approx$ aux fonctions. Soit $I$ un
intervalle de $\mathbb{R}$ d'intérieur non vide. On veut étudier le comportement
local d'une fonction $f: I \to \mathbb{K}$ au voisinage d'un point de $I$ ou d'une extrémité de $I$.

> Soit $a \in I$ ou $a$ une extrémité de $I$, et $f: I \to \mathbb{K}$ une
> fonction. On dit que $f$ vérifie une propriété $P$ au voisinage de $a$ si :
> - $a = +\infty$ : $\exists A \in \mathbb{R}, \forall x \in I \cap [A,+\infty[, P(x)$
> - $a = -\infty$ : $\exists A \in \mathbb{R}, \forall x \in I \cap ]-\infty,A], P(x)$
> - $a \in I$ fini : $\exists \eta > 0, \forall x \in I \cap [a - \eta, a + \eta], P(x)$

Ces voisinages sont aux fonction ce que "à partir d'un certain rang" est aux
suites.

### Notations de Landau
Soient $f,g$ définies sur $I \setminus \{a\}$ et qui ne s'annulent pas au
voisinage de $a$ :
- $f(x) =_a O(g(x))$ si $\frac{f}{g}$ est bornée au voisinage de $a$, soit
  $\exists M  \in \mathbb{R}_{+}, \text{ dans un voisinage de a }, |f(x)| \leq M \times |g(x)|$
- $f(x) =_a o(g(x))$ si $\lim\limits_{x \to a} \frac{f}{g} = 0$
- $f(x) \underset{a}{\approx} o(g(x))$ si $\lim\limits_{x \to a} \frac{f}{g} = 1$

> $f \underset{a}{\approx} g \Leftrightarrow g =_a g + o(g)$

En effet, $f \underset{a}{\approx} g \Leftrightarrow \lim\limits_{a} \frac{f}{g} = 1 \Leftrightarrow \lim\limits_{a} (\frac{f}{g} - 1)$
$\Leftrightarrow (f - g) =_a o(g)$.

On a les mêmes théorèmes sur les opérations que pour les suites (on remplace simplement $n \to +\infty$
par $x \to a$).

*Il n'y a pas de somme d'équivalents, ni de compositions.*

En revanche, on peut opérer un changement de variable : comme $\sin(x) \underset{x \to 0}{\approx} x$
et $\frac{x^2}{\pi} \xrightarrow[x \to 0] 0$, donc $\sin(\frac{x^2}{\pi}) \underset{x \to 0}{\approx} \frac{x^2}{\pi}$.

On liste aussi des équivalents usuels en $0$:
- $(e^{x} - 1) \underset{x \to 0}{\approx} x$ (car on a $e^{x} \underset{x \to 0}{=} 1 + x + o(x)$)
- $\ln(1 + x) \underset{x \to 0}{\approx} x$
- $\ln(x) \underset{x \to 1}{\approx} (x - 1)$ (car $\ln(x) \underset{x \to 1}{=} (x - 1) + o(x - 1)$)
- $\alpha \in \mathbb{R}, ((1 + x)^{\alpha} - 1) \underset{x \to 0}{\approx} \alpha x$
  (car $(1 + x)^{\alpha} \underset{x \to 0}{=} 1 + \alpha x + o(x)$)
  (de même, $\sqrt{1 + x} \underset{x \to 0}{=} 1 + \frac{1}{2} x + o(x)$)
- $(1 - \cos(x)) \underset{x \to 0}{\approx} \frac{x^2}{2}$ (car $\cos(x) \underset{x \to 0}{=} 1 - \frac{x^2}{2} + o(x^2)$)
- $(\cosh(x) - 1) \underset{x \to 0}{\approx} \frac{x^2}{2}$ (car $\cosh(x) = 1 + \frac{x^2}{2} + o(x^2)$)

De plus, on a les approximations sur les fonction trigonométriques au voisinage de $0$ :
- $\sin(x) \underset{x \to 0}{\approx} x$
- $\sinh(x) \underset{x \to 0}{\approx} x$
- $\tan(x) \underset{x \to 0}{\approx} x$
- $\tanh(x) \underset{x \to 0}{\approx} x$
- $\arcsin(x) \underset{x \to 0}{\approx} x$
- $\arctan(x) \underset{x \to 0}{\approx} x$

En pratique, on se ramène toujours à une quantité qui tend vers $0$, afin d'appliquer les équivalents
usuels en $0$ et les approximations au voisinage de $0$.
