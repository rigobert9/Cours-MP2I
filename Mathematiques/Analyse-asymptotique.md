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
- $\exp(h) \sim 1 + h$
- $\sin(h) = h$
- $\sqrt{1 + h} \sim 1 + \frac{1}{2} h$
- $(1 + h)^{\alpha} \sim 1 + \alpha h$

En physique, ce premier ordre suffira largement pour des simplifications ou des
équations différentielles. En mathématiques, on pourra aller plus loin dans
l'inspection du $o(h)$ en utilisant Taylor.

## Comparaison de fonctions
On adapte les notations $o$, $O$ et $\sim$ aux fonctions. Soit $I$ un
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
- $f(x) \underset{a}{\sim} o(g(x))$ si $\lim\limits_{x \to a} \frac{f}{g} = 1$

> $f \underset{a}{\sim} g \Leftrightarrow g =_a g + o(g)$

En effet, $f \underset{a}{\sim} g \Leftrightarrow \lim\limits_{a} \frac{f}{g} = 1 \Leftrightarrow \lim\limits_{a} (\frac{f}{g} - 1)$
$\Leftrightarrow (f - g) =_a o(g)$.

On a les mêmes théorèmes sur les opérations que pour les suites (on remplace simplement $n \to +\infty$
par $x \to a$).

*Il n'y a pas de somme d'équivalents, ni de compositions.*

En revanche, on peut opérer un changement de variable : comme $\sin(x) \underset{x \to 0}{\sim} x$
et $\frac{x^2}{\pi} \xrightarrow[x \to 0] 0$, donc $\sin(\frac{x^2}{\pi}) \underset{x \to 0}{\sim} \frac{x^2}{\pi}$.

On liste aussi des équivalents usuels en $0$:
- $(e^{x} - 1) \underset{x \to 0}{\sim} x$ (car on a $e^{x} \underset{x \to 0}{=} 1 + x + o(x)$)
- $\ln(1 + x) \underset{x \to 0}{\sim} x$
- $\ln(x) \underset{x \to 1}{\sim} (x - 1)$ (car $\ln(x) \underset{x \to 1}{=} (x - 1) + o(x - 1)$)
- $\alpha \in \mathbb{R}, ((1 + x)^{\alpha} - 1) \underset{x \to 0}{\sim} \alpha x$
  (car $(1 + x)^{\alpha} \underset{x \to 0}{=} 1 + \alpha x + o(x)$)
  (de même, $\sqrt{1 + x} \underset{x \to 0}{=} 1 + \frac{1}{2} x + o(x)$)
- $(1 - \cos(x)) \underset{x \to 0}{\sim} \frac{x^2}{2}$ (car $\cos(x) \underset{x \to 0}{=} 1 - \frac{x^2}{2} + o(x^2)$)
- $(\cosh(x) - 1) \underset{x \to 0}{\sim} \frac{x^2}{2}$ (car $\cosh(x) = 1 + \frac{x^2}{2} + o(x^2)$)

De plus, on a les approximations sur les fonction trigonométriques au voisinage de $0$ :
- $\sin(x) \underset{x \to 0}{\sim} x$
- $\sinh(x) \underset{x \to 0}{\sim} x$
- $\tan(x) \underset{x \to 0}{\sim} x$
- $\tanh(x) \underset{x \to 0}{\sim} x$
- $\arcsin(x) \underset{x \to 0}{\sim} x$
- $\arctan(x) \underset{x \to 0}{\sim} x$

En pratique, on se ramène toujours à une quantité qui tend vers $0$, afin d'appliquer les équivalents
usuels en $0$ et les approximations au voisinage de $0$.

## Développement limités
### Développement limité, troncature, unicité
> Soit $f: I \to \mathbb{R}, a \in \mathbb{R}$ où $a \in I$ ou
> $a$ est une extrémité de $I$. $f$ admet un développement limité en $a$ d'ordre
> $n$ ($\text{DL}_n(a)$) si $\exists (\alpha_0, \alpha_1,\ldots,\alpha_n) \in \mathbb{R}^{n+1}$
> et $\exists \varepsilon$ une fonction tendant vers $0$ en $a$, tels que
> $\forall x \in I, f(x) = \alpha_0 + \alpha_1 (x - a) + \alpha_2 (x-a)^2 + \ldots + \alpha_n (x - a)^{n} + (x - a)^{n+1} \times \varepsilon(x)$.

Le terme d'erreur $(x - a)^{n+1} \times \varepsilon(x)$ est ainsi égal à $o((x - a)^n)$.

$f$ admet donc un $\text{DL}_n(a)$ si $f(x) \underset{x \to a}{=} \sum\limits_{k = 0}^{n} \alpha_k (x - a)^k + o((x - a)^n)$.

> Si $f$ admet un $\text{DL}_n(a)$ et si $p < n$, alors $f$ admet un
> $\text{DL}_p(a)$, obtenu par troncature du $\text{DL}$ à l'ordre $n$ en ne
> conservant que les $(p + 1)$ premiers termes.

En effet, si $n > p$ et $f(x) = \sum\limits_{k = 0}^{n} \alpha_k (x - a)^k + o((x-a)^n)$
$= \sum\limits_{k = 0}^{p} \alpha_k (x-a)^k + \sum\limits_{k = p + 1}^{n} \alpha_k (x-a)^k + o((x-a)^n)$,
on a la somme des deux derniers termes qui sont égaux à $o((x-a)^p)$.

> Si $f$ admet un $\text{DL}_n(a)$, avec $f(x) = \sum\limits_{k = 0}^{n} \alpha_k (x - a)^k + o((x-a)^n)$,
> alors les coefficients $(\alpha_0, \alpha_1,\ldots,\alpha_n) \in \mathbb{R}^{n+1}$ sont uniques.

__Preuve :__ On suppose que $f$ admette deux $\text{DL}_n(a)$, donnant
$f = \sum\limits_{k = 0}^{n} \alpha_k (x - a)^k + o((x - a)^n) = \sum\limits_{k = 0}^{n} \beta_k (x - a)^k + o((x - a)^n)$.
On suppose que les $\alpha_i$ et les $\beta_i$ sont différents. Soit
$p = \text{min}(k \in [0,n]_{\mathbb{N}}, \alpha_k \neq \beta_k)$, alors
$\alpha_p \neq \beta_p$ et $\forall k < p, \alpha_k = \beta_k$.
Ainsi, les deux sommes sont les mêmes de $k = 0$ à $p - 1$,, et on tronque les
$\text{DL}$ à l'ordre $p$, donc $\alpha_p (x-a)^p + o((x - a)^p) = \beta_p (x - a)^p + o((x - a)^p)$.
On divise par $(x - a)^p$, et on obtient $\alpha_p + o(1) = \beta_p + o(1)$,
donnant $\alpha_p = \beta_p$ en approchant $a$, ce qui est absurde.

##### Exemple
On cherche à montrer que $f: x \mapsto \frac{1}{1 - x}$ possède un $\text{DL}_n(0)$ pour tout $n \in \mathbb{N}$.
Or, $\forall x \in ]-1,1[, \sum\limits_{k = 0}^{n} x^k = \frac{1 - x^{n+1}}{1 - x}$,
donc $\frac{1}{1 - x} = \sum\limits_{k = 0}^{n} x^k + \frac{x^{n+1}}{1 - x}$,
or ce dernier terme est égal à $o(x^n)$ car $\lim\limits_{n \to 0} \frac{x}{1 - x} = 0$.

$\frac{1}{1 - x} \underset{x \to 0}{=} \sum\limits_{k = 0}^{n} x^k + o(x^n)$,
vrai pour tout $n \in \mathbb{N}$.

#### Lien entre $\text{DL}_n(a)$ et $\text{DL}_n(0)$ (DL à l'origine)
Si $f$ admet $\text{DL}_n(a)$ telle que $f(x)  \underset{x \to a}{=} \sum\limits_{k = 0}^{n} \alpha_k (x-a)^k ) o((x-a)^n)$,
on pose $g: h \to f(a+h)$, et lorsque $x \to a, x - a \to 0$. Ainsi,
$g(h) = f(a + h) \underset{h \to 0}{=} \sum\limits_{k = 0}^{n} \alpha_k h^k + o(h^n)$.

> Si $f$ admet un $\text{DL}_n(a)$ tel que $f(a + h) \underset{h \to 0}{=} \sum\limits_{k = 0}^{n} \alpha_k h^k + o(h^n)$,
> on pose $p = \text{min}\{k \mid \alpha_k \neq 0\}$ (s'il existe).
> On a alors $\alpha_0 = \alpha_1 = \ldots = \alpha_{p - 1} = 0$ et $\alpha_p \neq 0$,
> permettant de noter $f(a + h) = h^p \times [\alpha_p + \alpha_{p + 1} h + \ldots + \alpha_n h^{n-p} + o(h^{n-p})]$
> qui est la forme normalisée du $\text{DL}_n(a)$.

Ainsi, on a $f(a + h) \underset{h \to 0}{\sim} \alpha_p h^p$.

Cela donne le comportement local de $f$ au voisinage de $a$. Lorsque $\alpha_p > 0$,
si $p$ est paire, alors la fonction est paire, et sinon elle est impaire.

### DL et parité ou imparité
Si $f$ admet un $\text{DL}_n(0)$, alors $f(x) \underset{x \to 0}{=} \sum\limits_{k = 0}^{n} \alpha_k x^k + o(x^n)$.
Puisque $-x \xrightarrow[x \to 0] 0$ et $o((-x)^n) = o(x^n)$, $f(-x) \underset{x \to 0}{=} \sum\limits_{k = 0}^{n} \alpha_k (-x)^k + o(x^n)$
$= \sum\limits_{k = 0}^{n} \alpha_k (-1)^k x^k + o(x^n)$.

Si $f$ est paire, $f(-x) = f(x)$. Par unicité du DL, les coefficients sont
égaux, et $\forall k \in [\![0,n]\!] \alpha_k = (-1)^k \alpha_k$, ce qui impose
que tous les coefficients d'indice impairs soient nuls.\
Si $f$ est impaire, $f(-x) = -f(x)$. Par unicité du DL, les coefficients sont
égaux, et $\forall k \in [\![0,n]\!] - \alpha_k = (-1)^k \alpha_k$, ce qui impose
que tous les coefficients d'indice pairs soient nuls.

##### Exemple
$\tan(x) \underset{x \to 0}{\sim} x$, donc $\tan(x) \underset{x \to 0}{=} x + o(x)$,
or $\tan$ est impaire, donc le coefficient devant $x^2$ est nul dans son DL.
Ainsi, $\tan(x) = x + o(x^2)$ (ce qui est une amélioration de la précision,
plutôt que de mettre $o(x)$).

### Existence d'un développement limité
> Soit $f: I \to \mathbb{R}$ une fonction de classe $\mathcal{C}^n$ sur $I$, alors
> $f$ admet un $\text{DL}_n(a)$ en $a$ pour tout point $a \in I$.
> $f(x) \underset{x \to 0}{=} \sum\limits_{k = 0}^{n} \frac{f^{(x)}(a)}{k!} (x - a)^k + o((x - a)^n)$.

Forcément, dériver ça coûte cher, donc on va y passer l'exponentielle. En
pratique, on l'utilise pour des fonctions qui sont $\mathcal{C}^n$ en $0$.

De plus, on retrouve dans cette formule l'approximation linéaire : un $\text{DL}_1(a)$
de $f$ est $f(a) + f'(a)(x - a) + o(x - a)$.

### DL et dérivabilité
#### DL d'ordre 0
> Si $f$ admet un $\text{DL}_0(a)$, alors :
> - si $f$ était définie en $a$, $\exists \alpha_0 \in \mathbb{R}, f(x) \underset{x \to a}{=} \alpha_0 + o(1)$
> - si $f$ n'était pas définie en $a$, $\lim\limits_{x \to a} f(x) = \alpha_0$

Si $f$ n'est pas définie au point $a$, on peut alors prolonger par continuité
$f$ en $a$. Si elle était déjà définie, alors si $f$ est continue en $a$,
$f(x) \underset{x \to a}{=} f(a) + o(1)$

Réciproquement, si $f$ est une fonction continue en $a$, alors
$f(x) \xrightarrow[x \to a] f(a)$, donc $f(x) \underset{x \to a}{=} f(a) + o(1)$,
donc $f$ admet un $\text{DL}_0(a)$.

##### Exemple
$f: x \mapsto \frac{\sin x}{x}$ pour $x \in ]0,\pi[$. Peut-on prolonger $f$
continument en $0$ ?\
On observe son $\text{DL}_0(a)$ : $\sin(x) \underset{x \to 0}{=} x + o(x)$,
donc $\frac{\sin x}{x} \underset{x \to 0}{=} 1 + o(1)$, donc $f$ se prolonge
en $0$ en posant $f(0) = 1$.

#### DL d'ordre 1
> Si $f$ admet un $\text{DL}_1(a)$, alors $\exists \alpha_0, \alpha_1$ tels que
> $f(x) \underset{x \to a}{=} \alpha_0 + \alpha_1 \times (x-a) + o(x-a)$,
> $f$ admet les mêmes propriétés que pour une $\text{DL}_0(a)$ (par troncature),
> et $f$ est dérivable en $a$ et $f'(a) = \alpha_1$.

Ainsi, $f(x) \underset{x \to a}{=} f(a) + f'(a) (x-a) + o(x-a)$.

Réciproquement, si $f$ est dérivable en $a$,
$\frac{f(x) - f(a)}{x - a} \xrightarrow[x \to a] f'(a)$,
et donc $\frac{f(x) - f(a)}{x - a} = f'(a) + o(1)$,
donc $f(x) - f(a) = (x - a) f'(a) + o(x-a)$,
donc $f(x) = f(a) + (x - a) f'(a) + o(x-a)$ donc $\text{DL}_1(a)$.

#### Le reste
Bien que le $\text{DL}_0(a)$ soit directement connecté à la continuité de la
fonction, et que le $\text{DL}_1(a)$ soit directement connecté à la dérivabilité
de la fonction, les autres rangs de développements limités n'ont pas de
propriétés similaires.

En revanche, on pourra déduire d'un DL d'ordre supérieur que la fonction admet
un DL d'ordre 1 et 0 par troncature, donnant les propriétés recherchées.

##### Exemple
On cherche à montrer que $f = \left\{\begin{matrix} \frac{\sin x}{x}, x \in ]0,\pi[ \\ 1, x = 0 \end{matrix}\right.$ est dérivable en $0$.
On sait que $\sin(x) \underset{x \to 0}{=} x + 0 \times x^2 + o(x^2)$,
donc $\frac{\sin x}{x} = 1 + 0 \times x + o(x)$, donc $f$ est dérivable
en $f'(0) = 0$.

#### Taylor avec reste intégral
> Soit $f \in \mathcal{C}^{n+1}(I,\mathbb{K})$, et soient $a,b \in I$,
> $f(b) = \sum\limits_{k = 0}^{n} \frac{f^{k}(a)}{k!} (b - a)^k + \int\limits_{a}^{b} \frac{(b-t)^n}{n!} f^{n+1}(t) dt$

Le reste intégral peut être remplacé par un $o((b - a)^n)$ lorsque $b \to a$,
nous donnant la formule de Taylor-Young.

__Preuve : récurrence sur $n$ :__\
Initialisation : Pour $n = 0$, si $f \in \mathcal{C}^1$,
$\int\limits_{a}^{b} f'(t) dt = f(b) - f(a)$ (par théorème fondamental de
l'analyse), donc $f(b) = f(a) + \int\limits_{a}^{b} f'(t) dt$.\
Hérédité : Soit $n \in \mathbb{N}$ et $f$ de classe $\mathcal{C}^{n+2}$,
on suppose le rang $n$ vérifié, on étudie le reste intégral :
$\int\limits_{a}^{b} \frac{(b-t)^n}{n!} f^{n + 1}(t) dt$, qu'on approche par
IPP avec $u'(t) = \frac{(b - t)^n}{n!}$, $u(t) = \frac{1}{n!} \times (-1) \times \frac{(b-t)^{n+1}}{n + 1}$,
$v(t) = f^{n+1}(t)$ et $v'(t) = f^{n+2}(t)$ ($u$ et $v$ sont bien de classe
$\mathcal{C}^{n+1}$, car $f \in \mathcal{C}^{n+2}$) :\
$\int\limits_{a}^{b} \frac{(b-t)^n}{n!} f^{n + 1}(t) dt = [\frac{- (b - t)^{n+1}}{(n+1)!} f^{n+1}(t)]_a^b$
$+ \int\limits_{a}^{b} \frac{(b-t)^{n+1}}{(n+1+!)} \times f^{n+1}(t) dt$
$= \frac{(b - a)^{n+1}}{(n+1)!} f^{n+1}(a)$
$+ \int\limits_{a}^{b} \frac{(b-t)^{n+1}}{(n+1+!)} \times f^{n+1}(t) dt$

### Opérations sur les DL
On regardera uniquement le cas des $\text{DL}_n(0)$, auxquels on se ramène de
façon générale.

#### Somme et combinaison linéaire
> Si $f$ et $g$ admettent un $\text{DL}_n(0)$ et si $\lambda,\mu \in \mathbb{R}$,
> alors $\lambda f + \mu g$ admet un $\text{DL}_n(0)$ obtenu
> par combinaison linéaire des parties régulières de $f$ et $g$.

En détail, si $f(x) \underset{x \to 0}{=} P(x) + o(x^n)$ et
$g(x) \underset{x \to 0}{=} Q(x) + o(x^n)$, avec $P$ et $Q$ des polynômes
qu'on appelle "parties régulières", alors $\lambda f(x) + \mu g(x)$
$= \lambda P(x) + \mu Q(x) + o(x^n)$ (avec ce terme $o$ qui regroupe la
combinaison linéaire des termes d'erreur).

##### Exemples
$\cosh(x) = \frac{e^x + e^{-x}}{2} = \frac{1}{2} (\sum\limits_{k = 0}^{2n} \frac{x^k}{k!} + o(x^{2n}))$
$= \sum\limits_{p = 0}^{n} \frac{x^{2p}}{(2p)!} + o(x^{2n})$.
Puisque $\sinh(x) + \cosh(x) = e^x \Leftrightarrow \sinh(x) = \sum\limits_{p = 0}^{n} \frac{x^{2p + 1}}{(2p + 1)!} + o(x^{2n + 1})$.

On fait de même avec $\cos x$ qui est la somme des indices pairs (réels) de
$\sum\limits_{k = 0}^{n} \frac{i^k}{k!} x^k + o(x^n)$.

##### Exemple : $\text{DL}_4(\frac{\pi}{4})$ de $\sin(x)$
$\sin(x) \underset{x \to \frac{\pi}{4}}{=} \sin(\frac{\pi}{4} + h)$
$\underset{h \to 0}{=} h = x - \frac{\pi}{4}$,
$\sin(\frac{\pi}{4} + h) = \frac{\sqrt{2}}{2} (\cos(h) + \sin(h))$\
$= \frac{\sqrt{2}}{2} (1 - \frac{h^2}{2} + \frac{h^{4}}{+!} + o(h^4) + h - \frac{h^3}{3!} + o(h^4))$\
Donc $\sin(x) \underset{x \to \frac{\pi}{4}}{=} \frac{\sqrt{2}}{2} + \frac{\sqrt{2}}{2}(x - \frac{\pi}{4}) \ldots$.

#### Produit de DLs
> Si $f$ admet un $\text{DL}_n(0)$ et $g$ admet un $\text{DL}_n(0)$,
> alors $f \times g$ admet un $\text{DL}_n(0)$, qu'on obtient par produit des
> parties régulières en tronquant à précision $o(x^n)$.

En détail, si $f(x) \underset{x \to 0}{=} P(x) + o(x^n)$ et
$g(x) \underset{x \to 0}{=} Q(x) + o(x^n)$, avec $P$ et $Q$ des polynômes,
$f(x) \times g(x) = P(x) \times Q(x) + P(x) \times o(x^n) + Q(x) \times o(x^n) + o(x^n) \times o(x^n)$,
or $P(x) = a_0 + \ldots \Leftrightarrow P(x) \times o(x^n) = o(x^n) + \ldots$,
et de même pour $Q(x)$.\
Ainsi, $P(x) \times Q(x) = (\sum\limits_{i = 0}^{n} a_i x^i) \times (\sum\limits_{j = 0}^{n} b_j x^j)$
$= \sum\limits_{0 \leq i,j \leq n} a_i b_i x^{i + j}$, dont on ne conserve que
les indices avec $i + j \leq n$ et dont on rassemble le reste dans $o(x^n)$.

On utilisera en général les formes normalisées des DL pour le produit, car on a
alors pour un $\text{DL}_p(0)$ de $f$ et un $\text{DL}_q(0)$ de $g$,
$\text{DL}_{n+p}(0) = x^{p+q} \times [\text{DL}_n \times \text{DL}_n]$ (voir
exemple).

##### Exemple
Soit $f(x) = (\sin x - x) (\cos x - 1 + \frac{x^2}{2})$, on cherche un $\text{DL}_8(0)$
La fonction étant impaire, les coefficients pairs sont nuls, et on a
$\sin(x) - x = \frac{-x^3}{6} + \ldots$ et
$(\cos x) - 1 + \frac{x^2}{2} = \frac{x^4}{24} + \ldots$,
permettant de trouver $f(x) \underset{x \to 0}{\sim} \frac{-x^7}{6 \times 24}$
(un DL d'ordre de 7 de $f(x)$), soit $f(x) \underset{x \to 0}{=} \frac{-x^7}{24 \times 6} + o(x^7)$.
Comme la fonction est impaire, on a immédiatement le DL d'ordre 8,
$f(x) \underset{x \to 0}{=} \frac{-x^7}{24 \times 6} + o(x^8)$.

#### Compositions de DLs
> Si $g$ admet un $\text{DL}_n(0)$ et si $\lim\limits_{x \to 0} f(x) = 0$,
> alors $g(f(x)) = a_0 + a_1 f(x) + a_2 (f(x))^2 + \ldots + n(f(x))^n$.
> Si $f$ admet aussi un $\text{DL}_n(0)$, on remplace les termes afin d'obtenir un
> DL de la composition.

##### Exemple
On cherche le $\text{DL}_3(0)$ de $\exp(\frac{1}{1 + x})$.
$\frac{1}{1 + x} = \frac{1}{1 - (-x)} = 1 - x + x^2 - x^3 + o(x^3)$,
et $e^{u} = 1 + u + \frac{u^2}{2} + \frac{u^3}{6} + o(u^3)$.
Or $(\frac{1}{1 + x})^2 = 1 - 2x + 3 x^2 - 4x^3 + o(x^3)$,
et $(\frac{1}{1 + x})^3 = 1 - 3x + 6x^2 - 10x^3 + o(x^3)$.

On obtient ainsi $e^{1} \times \exp(-x + x^2 - x^3 + o(x^3))$, et la partie
intérieure de la seconde exponentielle converge bien vers $0$.
On obtient finalement $f(x) \underset{x \to 0}{=} e - ex + \frac{3}{2} e x^2 - \frac{13}{6} e x^3 + o(x^3)$.

#### Inverse d'un DL
On recherche le $\text{DL}_3(0)$ de $\frac{1}{\cos(x)}$. On a
$\cos(x) \underset{x \to 0}{=} 1 - \frac{x^2}{2} + o(x^3)$, et donc
$\frac{1}{\cos x} = \frac{1}{1 - \frac{x^2}{2} + o(x^2)}$.
On a l'expression $\frac{x^2}{2} + o(x^3)$ qui tend vers $0$,
or $\frac{1}{1 - u} \underset{x \to 0}{=} 1 + u + u^2 + u^3 + o(u^3)$.
Avec ce $u(x)$, on obtient enfin $\frac{1}{\cos(x)} \underset{x \to 0}{=} 1 + \frac{x^2}{2} + o(x^3)$.

> Pour calculer l'inverse d'un DL, tel que $\frac{1}{f(x)}$,
> avec $f(x) = x^p \times [a_0 + a_1 x + \ldots + a_n x^n + o(x^n)]$,
> on écrit $\frac{1}{f(x)} = \frac{1}{x^p} \times \frac{1}{[\ldots]}$
> $= \frac{1}{x^p} \times \frac{1}{a_0 [1 + u(x)]}$, avec
> $u(x) \xrightarrow[x \to 0] 0$, et on applique le DL de $\frac{1}{1 + u}$.

#### Primitive d'un DL
> Si $f$ admet un $\text{DL}_n(0)$, en notant $F$ une primitive de $f$,
> $F$ aura un $\text{DL}_{n+1}(0)$ tirée du DL de $f$.

En détail, si $f(x) \underset{x \to 0}{=} \sum\limits_{k = 0}^{n} a_k x^k + o(x^n)$,
alors $F(x) = \int\limits_{0}^{x} f(t) dt = 0 + \sum\limits_{k = 0}^{n} a_k \frac{x^{k + 1}}{k + 1} + o(x^{n+1})$.

__DL de $\ln(1 + x)$ en $0$ :__
$f(x) = \ln(1  +x)$ et $f'(x) = \frac{1}{1 + x} \underset{x \to 0}{=} 1 - x + x^2 - x^3 \ldots + (-1)^n x^n + o(x^n)$,
et on primitive, donnant $\ln(1 + x) = x - \frac{x^2}{2} + \frac{x^3}{3} \ldots + (-1)^n \frac{x^{n+1}}{n + 1} + o(x^{n+1})$.

#### Équations différentielles pour générer des DL
Les équations différentielles permettent de calculer des DLs à une classe
presque infinie, en obtenant le DL d'un terme puis en primitivant à répétition.
Par exemple, on peut obtenir plusieurs rangs à chaque itération en travaillant
sur $\tan' = 1 + \tan^2$
