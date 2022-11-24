# Suites numériques
## Généralités sur les suites réelles
### Définitions, opérations
> Une suite est une famille de réels indexées par $\mathbb{N}$, c'est à dire
> une application de $\mathbb{N}$ dans $\mathbb{R}$.

> Soit $u \in \mathbb{R}^{\mathbb{N}}$, $u$ est une suite réelle
> $\begin{aligned} u: \mathbb{N}^{\ast} &\to \mathbb{R} \\ n &\mapsto u_n .\end{aligned}$,
> qu'on note plutôt $u = (u_0, u_1, u_2,\ldots) = (u_n)_{n \in \mathbb{N}}$,
> la suite $(u_n)$.

Pour chaque $n \in \mathbb{N}$, le réel $u_n$ est appelé terme général (d'indice
n).

La définition d'une suite peut s'effectuer à partir d'un certain rang. On note
dans ce cas pour un rang $n_0 \in \mathbb{N}$ fixe : la suite
$u = (u_n)_{n \geq n_0}$ est bien définie à partir du rang $n_0$.

On dira qu'une suite $u$ vérifie une propriété $P$ à partir d'un certain rang
(APCR) si
$\exists n_0 \in \mathbb{N},\forall n \geq n_0, P(n)$. Il est parfois suffisant
de laisser le flou sur ce rang en particulier dans des formalisations,
l'importance étant que ce rang existe (par exemple en analyse asymptotique).

> Soient $u,v \in \mathbb{R}^{\mathbb{N}}$ et $\lambda \in \mathbb{R}$, on définit
> les suites suivantes :
> - somme : $w = u + v \Leftrightarrow \left\{\begin{matrix} w \in \mathbb{R}^{\mathbb{N}} \\ \forall n \in \mathbb{N}, w_n = u_n + v_n \end{matrix}\right.$
> - produit : $w = u \times v \Leftrightarrow \left\{\begin{matrix} w \in \mathbb{R}^{\mathbb{N}} \\ \forall n \in \mathbb{N}, w_n = u_n \times v_n \end{matrix}\right.$
> - multiplication par un scalaire $\lambda$ : $w = \lambda u \Leftrightarrow \left\{\begin{matrix} w \in \mathbb{R}^{\mathbb{N}} \\ \forall n \in \mathbb{N}, w_n = \lambda u_n \end{matrix}\right.$

On peut ainsi conclure que le groupe des suites peut être un espace vectoriel et
un anneau.

Soit $u \in \mathbb{R}^{\mathbb{N}}$ :
- $u$ est constante si $\forall n \in \mathbb{N}, u_{n + 1} = u_n$ (puisqu'on a
  des indices naturels), ou $\forall n \in \mathbb{N}, \forall m \in \mathbb{N},$
  $u_n = u_m$ (plus général), ou encore pour identifier la valeur de la
  constante $\exists C \in \mathbb{R},\forall n \in \mathbb{N}, u_n = C$.
  En pratique, on applique la première méthode pour les suites exprimées sous
  leur forme récurrente, puis on conclut $u_n = u_0$.
- $u$ est stationnaire si elle est constante à partir d'un certain rang.
- $u$ est périodique si $\exists k \in \mathbb{N}^{\ast},\forall n \in \mathbb{N}^{\ast},u_{n + k} = u_n$

### Suites usuelles
#### Suite arithmétique de raison $r$
$\left\{\begin{matrix} u_0 \in \mathbb{R}, \forall n \in \mathbb{N}, u_{n + 1} = u_n + r \end{matrix}\right.$

On peut aussi écrire de façon explicite $\forall n \in \mathbb{N}, u_n = u_0 + nr$,
ou $\forall p \in \mathbb{N}, \forall n \geq p, u_n = u_p + (n-p) r$.

On peut facilement prouver ceci par télescopage, puisque $u_{k + 1} - u_k = r$,
on somme pour $k \in [p,n-1]_{\mathbb{N}}$
$\sum\limits_{k = p}^{n-1} (u_{k + 1} - u_k) = \sum\limits_{k = p}^{n-1} r = (n-p) r$.

#### Suites géométrique de raison $q$
$\left\{\begin{matrix} u_0 \in \mathbb{R} \\ \forall n \in \mathbb{N}, u_{n + 1} = q \times u_n \end{matrix}\right.$

On peut aussi écrire de façon explicite
$\forall n \in \mathbb{N}, u_n = q^n \times u_0$ ou
$\forall p \in \mathbb{N}, \forall n \geq p, u_n = q^{n - p} \times u_p$.

#### Suites arithmético-géométriques
Avec $(q,r) \in \mathbb{R}^2$, $\left\{\begin{matrix} u_0 \in \mathbb{R} \\ \forall n \in \mathbb{N}, u_{n + 1} = q u_n + r \end{matrix}\right.$

On devine une suite constante solution telle que $\forall n \in \mathbb{N}, u_n = K$,
qui est telle que $K = qK + r \Leftrightarrow (1 - q) K = r$. Si $q = 1$,
on a la suite $(u_n)$ une suite arithmétique de raison $r$, et sinon on pose
$K = \frac{r}{1 - q}$, donnant $K = qK + r$, et puisque $\forall n \in \mathbb{N}$,
$u_{n+1} = q u_{n} + r$, par soustraction donnant
$\forall n \in \mathbb{N}, u_{n+1} - K = q(u_{n} - K)$. La suite $(u - K)$ est
ainsi géométrique de raison $q$.

On trouve enfin une forme explicite de la suite, donnant
$\forall n \in \mathbb{N}, (u_{n} - K) = q^n \times (u_0 - K)$.
On a donc $\forall n \in \mathbb{N}, u_{n} = K + q^n \times (u_0 - K)$
avec $K = \frac{r}{1 - q}$.

### Ordre et suites
> Soit $u \in \mathbb{R}^{\mathbb{N}}$ :
> - $u$ est majorée si $\exists M \in \mathbb{R}, \forall n \in \mathbb{N}, u_{n} \leq M$
> - $u$ est minorée si $\exists m \in \mathbb{R}, \forall n \in \mathbb{N}, u_{n} \geq m$
> - $u$ est bornée si $u$ est majorée et minorée

Si $|u|$ est majorée, alors $u$ est bornée.

> Soient $u,v \in \mathbb{R}^{\mathbb{N}}$ et $\lambda \in \mathbb{R}$, avec $u$
> et $v$ bornées, $u + v$, $u \times v$ et $\lambda u$ sont bornées.

En effet, si $\exists M_1,M_2 \in \mathbb{R} \mid \forall n \in \mathbb{N}, |u_{n}| \leq M_1 \land |v_n| \leq M_2$,
alors :
- $|u_{n} + v_n | \leq |u_{n}| + |v_n| \leq M_1 + M_2$
- $|u_n \times v_n| = |u_{n}| \times |v_n| \leq M_1 \times M_2$
- $|\lambda u_{n}| = |\lambda| \times |u_{n}| \leq |\lambda| M_1$

Soit $u \in \mathbb{R}^{\mathbb{N}}$ :
- $u$ est (strictement) croissante si $\forall n \in \mathbb{N}, u_{n+1} \geq (>) u_{n}$
- $u$ est (strictement) décroissante si $\forall n \in \mathbb{N}, u_{n+1} \leq (<) u_{n}$
- $u$ est (strictement) monotone si $u$ est (strictement) croissante ou
  décroissante.

On peut aussi chercher à obtenir ces propriétés à partir d'un certain rang.

__Cas favorable d'étude :__ Soit $u \in \mathbb{R}^{\mathbb{N}}$, on définit
$S = (S_{t})_{n \in \mathbb{N}}$ comme $S_n = \sum\limits_{k = 0}^{n} u_k$, et
on recherche la monotonie de la suite $S$.\
$S_{n+1} - S_n = \sum\limits_{k = 0}^{n + 1} u_k - \sum\limits_{k = 0}^{n} u_k = u_{n+1}$.\
$S$ est croissante si et seulement si $\forall n \in \mathbb{N}, u_{n+1} \geq 0$
si et seulement si $u$ est positive à partir du rang $1$, et $S$ est
décroissante si et seulement si $u$ est négative à partir du rang $1$.

__Autre cas favorable :__ Si $u$ est définie par une fonction de $n$,
$\forall n \in \mathbb{N},u_{n} = f(n)$ où $f: \mathbb{R}_{+} \to \mathbb{R}$,
si $f$ est une fonction monotone sur $\mathbb{R}_{+}$, alors la suite $u$ sera
monotone de même ordonnée.

## Limite d'une suite
### Convergence : limite finie
> Soit $u \in \mathbb{R}^{\mathbb{N}}$ et $\ell \in \mathbb{R}$, on dit que la suite
> $u$ converge vers $\ell$ (ou $u_{n}$ tend vers $\ell$ lorsque $n$ tend vers
> $+\infty$) si
> $\forall \varepsilon > 0, \exists n_0 \in \mathbb{N}, \forall n \in n_0, |u_{n} - \ell| \leq \varepsilon$
> (ou $u_{n} \in [\ell - \varepsilon, \ell + \varepsilon]$).

On peut remarquer que le centre de cette formule comprend une condition
"à partir d'un certain rang".

Toute suite stationnaire est convergente.

- $(1^n)_{n \in \mathbb{N}}$, constante égale à 1
- $((-1)^n)_{n \in \mathbb{N}}$ ne converge pas

> Soit $u \in \mathbb{R}^{\mathbb{N}}$ et $\ell \in \mathbb{R}$ :
> "$u$ converge vers $\ell$" est équivalente à
> "$|u-\ell|$ converge vers $0$".

> Si $u \to \ell$, alors $|u| \to |\ell|$

En effet, $||u_{n}| - |\ell|| \leq |u_{n} - \ell|$, et donc puisque $u \to \ell$,
$\forall \varepsilon > 0, \exists n_0,\forall n \geq n_0, ||u_{n}| - |\ell|| \leq |u_{n} - \ell| \leq \varepsilon$,
donc $\lim\limits_{n \to + \infty} |u_{n}| \to |l|$.

La réciproque est fausse avec la suite $u_{n} = (-1)^n$.

*Méta-théorème* : toute proposition partant d'une suite bornée doit être
éprouvée par $u_{n} = (-1)^n$, qui est bornée mais diverge, et ne marche jamais.

> Unicité de la limite : Soit $u \in \mathbb{R}^{\mathbb{N}}$ et $\ell_1,\ell_2 \in \mathbb{R}$,
> si $u_{n} \to_{n \to +\infty} \ell_1$ et $u_{n} \to_{n \to +\infty} l_2$ alors $l_1 = l_2$.

Dorénavant, si $u$ converge vers $\ell$, on dira que $\ell$ est *la* limite de
la suite $u$ et on notera $\ell = \lim u = \lim\limits_{n \to + \infty} u_{n}$.

On prouve cette unicité par l'absurde, en proposant que $\ell_1 \neq \ell_2$, en
imposant $\ell_1 < \ell_2$. Soit $\varepsilon = \frac{1}{3}(\ell_2 - \ell_1) > 0$,
par définition de la la limite,
$\exists n_1, \forall n \geq n_1, |u_{n} - \ell_1| \leq \varepsilon$ et
$\exists n_2, \forall n \geq n_2, |u_{n} - \ell_2| \leq \varepsilon$,
et donc pour $n_0 = \text{max}(n_1,n_2)$, on a
$\forall n \geq n_0, \left\{\begin{matrix} |u_{n} - \ell_1| \leq \varepsilon \\ |u_{n} - \ell_2| \leq \varepsilon \end{matrix}\right.$.
Or, $|\ell_1 - \ell_2| = |\ell_1 - u_{n} + u_{n} - \ell_2| \leq$ (par inégalité
triangulaire) $|\ell_1 - u_{n}| + |u_{n} - \ell_2| \leq 2\varepsilon$,
donc $|\ell_1 - \ell_2| = 3\varepsilon \leq 2\varepsilon$, ce qui est absurde.

> Soit $u \in \mathbb{R}^{\mathbb{N}}$ et $\ell \in \mathbb{R}$ :
> - si $u \to \ell$, on dit que la suite converge
> - sinon, on dit qu'elle diverge

> Toute suite convergente est bornée.

##### Preuve
Soit $u$ convergente, on note $\ell \in \mathbb{R}$ sa limite.
Comme $u \to \ell$, on prend $\varepsilon = 1 > 0$.
$\exists  n_0, \forall n \geq n_0, |u_{n} - \ell| \leq 1$.
Ainsi, $\forall n \geq n_0, |u_{n}| = |u_{n} - \ell + \ell|$
$\leq |u_{n} - \ell| + |\ell| \leq 1 + |\ell|$.
En posant $M = \text{max}(|u_0|,|u_1|,\ldots|u_{n_0 - 1}|, 1 + |\ell|)$,
on a bien $\forall n \in \mathbb{N}, |u_{n}| \leq M$.

### Limite infinie
> $u$ tend vers $+\infty$ (en notant $u_{n} \to_{n \to +\infty} +\infty$)
> si $\forall A \in \mathbb{R},\exists n_0, \forall n \geq n_0, u_{n} \geq A$.

> $u$ tend vers $-\infty$ (en notant $u_{n} \to_{n \to +\infty} -\infty$)
> si $\forall A \in \mathbb{R},\exists n_0, \forall n \geq n_0, u_{n} \leq A$.

> Si $u \to +\infty$ ou $u \to -\infty$, on dit quand même que $u$ diverge.

### Limite et ordre
Soit $u \in \mathbb{R}^{\mathbb{N}}$ et $\ell \in \mathbb{R}$, soit
$v \in \mathbb{R}^{\mathbb{N}}$ qui converge vers $0$, si à partir d'un certain
rang, $|u_{n} - \ell| \leq v_n$, alors $u$ converge vers $\ell$.

__Preuve :__ Soit $\varepsilon > 0$, on sait que
$\exists n_1, \forall n \geq n_1, |u_{n} - \ell| \leq v_n$. De plus, $v \to 0$,
donc : $\exists n_2, \forall n \geq n_2, |v_n| \leq \varepsilon$.
On pose $n_0 = \text{max}(n_1,n_2)$,
$\forall n \geq n_0, |u_{n} - \ell| \leq v_n  \leq \varepsilon$.
On a donc $|u - \ell| \to 0 \Leftrightarrow u \to \ell$.

Il s'agit d'ailleurs d'une version allégée du théorème d'encadrement.

> Soit $u \in \mathbb{R}^{\mathbb{N}}$ qui converge vers $\ell \in \mathbb{R}$,
> soit $a \in \mathbb{R}$ :
> - si $\ell > a$ alors, à partir d'un certain rang, $u_{n} > a$
> - si $\ell < a$ alors, à partir d'un certain rang, $u_{n} < a$
> - si $\ell \neq a$ alors, à partir d'un certain rang, $u_{n} \neq a$

De plus, si $u \to \ell$ avec $\ell > 0$, alors à partir d'un certain rang, $u_{n} > 0$,
et si $u \to \ell$ avec $l \neq 0$, alors à partir d'un certain rang, $u_{n} \neq 0$,
donc $\frac{1}{u_{n}}$ a un sens.

> Soient $u,v \in \mathbb{R}^{\mathbb{N}}$, convergentes avec $u \to \ell$
> et $v \to \ell'$, et que de plus $u_{n} \leq v_n$ à partir d'un certain rang.
> On a alors $\ell \leq \ell'$.

__Preuve :__ Par l'absurde, on suppose que $\ell > \ell'$, et on applique les
définitions de la limite à $\frac{\ell + \ell'}{2}$.

### Opérations sur les limites
#### Somme et produit sur une suite tendant vers 0
> 1. Si $u \to 0$ et $v \to 0$, alors $u + v \to 0$
> 2. Si $u \to 0$ et $v$ bornée, alors $u \times v \to 0$
> 3. Si $u \to 0$ et $\lambda \in \mathbb{R}$ bornée, alors $\lambda u \to 0$

##### Preuve
1. Soit $\varepsilon > 0$, on applique la définition avec $\frac{\varepsilon}{2} > 0$ :
  $\exists n_1,\exists n_2,\forall n \geq n_1,|u_{n}| \leq \frac{\varepsilon}{2}$
  et $\forall n \geq n_1,|v_n| \leq \frac{\varepsilon}{2}$, et on a donc
  $\forall n \geq \text{max}(n_1,n_2), |u_{n} + v_n| \leq |u_{n}| + |v_n| \leq \varepsilon$.
2. Puisque $v$ est bornée, on a $\exists M \in \mathbb{R}^{\ast}_{+}, \forall n \in \mathbb{N},|v_n| \leq M$
  Soit $\varepsilon > 0$, on applique la définition avec $\frac{\varepsilon}{M} > 0$,
  on obtient le résultat attendu.
3. Soit $\varepsilon > 0$, avec $\lambda \in \mathbb{R}^{\ast}$, puisque
  $u \to 0$, $\exists n_1,\forall n \geq n_0,|u_{n}| \leq \frac{\varepsilon}{|\lambda|}$
  $\Leftrightarrow |\lambda u_{n}| \leq \varepsilon$.

#### Somme et produit sur toutes les suites
> Si $u \to \ell \in \mathbb{R}$, et $v \to \ell' \in \mathbb{R}$, alors
> pour $\lambda,\mu \in \mathbb{R}$ :
> - $(\lambda u + \mu v)$ converge vers $\lambda \ell + \mu \ell'$
> - $u \times v$ converge vers $\ell \ell'$

__Preuve :__ $\lambda u + \mu v - (\lambda \ell + \mu \ell') = \lambda (u - \ell) + \mu (v - \ell')$
et $uv - \ell \ell' = u \times (v - \ell') + \ell' \times (u - \ell.)$.

- Si $u$ et $v$ convergent, alors $u + v$ converge
- Si $u$ converge et $v$ diverge, alors $u + v$ diverge

Soient $u,v$ deux suites, où $u \to +\infty$ :
- Si $v$ est minorée, alors $u + v \to +\infty$
- Si $v$ est minorée à partir d'un certain rang par un réel strictement positif,
  alors $u \times v \to +\infty$

__Preuve :__
- Soit $A  \in \mathbb{R}, \exists m \in \mathbb{R}, \forall n  \in \mathbb{R},$
  $\forall n \in \mathbb{N}, v_n \geq m, u_{n} \geq A - m$,
  alors $\forall n \geq n_0, u_{n} + v_n \geq A$.
- Soit $A \in \mathbb{R}_{+}, \exists m > 0, \exists n_1, \forall n \geq n_1, v_n \geq m > 0$.
  De plus, $\exists n_2,\forall n \geq n_2,u_{n} \geq \frac{A}{m} \geq 0$

> Si $u \to \ell \in \overline{\mathbb{R}}$ et $v \to \ell' \in \overline{\mathbb{R}}$,
> avec $\ell + \ell'$ [$\ell \times \ell'$] bien défini dans $\overline{\mathbb{R}}$,
> alors $u + v \to \ell + \ell'$ [$u \times v \to \ell \times \ell'$].

#### Inverse
> Si $u \to \ell \in \mathbb{R}^{\ast}$, alors $\frac{1}{u} \to \frac{1}{\ell}$.

__Preuve :__ Comme $\ell \neq 0$, alors à partir d'un certain rang, $u_{n} \neq 0$,
donc à partir d'un certain rang, $\frac{1}{u_{n}}$ est bien définie.
$\exists n_0,\forall n \geq n_0,u_{n} \neq 0$,
$|\frac{1}{u_{n}} - \frac{1}{\ell}| = |\frac{\ell - u_{n}}{u_{n} \times \ell}|$
$= |x|$ À COMPLÉTER

$u \to \ell$ donc $(u - \ell) \to 0$, donc $\exists n_2,\forall n \geq n_2$,
$|u_{n} - \ell| \leq \varepsilon \times \frac{|l|^2}{2}$.
On pose $N = \text{max}(n_0,n_1,n_2)$, $\forall n \geq N$,
$|\frac{1}{u_{n}} - \frac{1}{\ell}| \leq \frac{|\ell - u_{n}|}{|\ell|} \times \frac{1}{|u_{n}|}$
$\leq \frac{|\ell - u_{n}|}{|\ell|} \times \frac{2}{|\ell|} \leq \varepsilon$

> Soit $|u| \to +\infty$, alors $\frac{1}{u} \to 0$.

__Preuve :__ Soit $\varepsilon > 0$, on pose $M = \frac{1}{\varepsilon}$, et on
a bien $\exists n_0,\forall n \geq n_0,|u_{n}| \geq M > 0$,
donc $\forall n \geq n_0, |\frac{1}{u_{n}}| \leq \frac{1}{M} = \varepsilon$.

> - Si $u \to 0$ et qu'à partir d'un certain rang, $u_{n} > 0$ (on le note $u \to 0^{+}$),
>   alors $\frac{1}{u} \to +\infty$.
> - Si $u \to 0$ et qu'à partir d'un certain rang, $u_{n} < 0$ (on le note $u \to 0^{-}$),
>   alors $\frac{1}{u} \to -\infty$.

Cette preuve est ainsi non valide pour une suite qui ne reste pas du même côté
de 0, comme $u_{n} = \frac{(-1)^n}{n}$.

__Preuve :__ On suppose $u \to 0^{+}$, $\exists n_0, \forall n \geq n_0, u_{n} > 0$.
Soit $M \in \mathbb{R}^{\ast}_{+}$, on pose $\varepsilon = \frac{1}{M}$.
Comme $u \to 0$, $\exists n_1,\forall n \geq n_1,|u_{n}| \leq \varepsilon - \frac{1}{M}$.
Ainsi, $\forall n \geq \text{max}(n_0,n_1), 0 < u_{n} \leq \frac{1}{M}$,
donc $\frac{1}{u_{n}} \geq M$.

### Théorèmes d'existence des limites
#### Théorème d'encadrement (gendarmes)
> Si $u$ et $w$ convergent vers la même limite $\ell \in \mathbb{R}$,
> et si à partir d'un certain rang, $u_{n} \leq v_n \leq w_n$,
> alors la suite $v$ converge vers $\ell$.

Ce théorème donne l'existence et la valeur de la limite.

__Preuve :__ $\exists n_0,\forall n \geq n_0, u_{n} \leq v_n \leq w_n$,
donc $0 \leq v_n - u_{n} \leq w_n - u_n \Leftrightarrow |v_n - u_{n}| \leq |w_n - u_n|$,
et puisque la suite $|w - u|$ converge vers $0$, par une propriété précédente,
$v - u$ converge en 0.
Par somme des suites convergentes, $v = (v - u) + u$ converge et
$\lim\limits_{n \to + \infty} v = \lim\limits_{n \to + \infty} (v - u) + \lim\limits_{n \to + \infty} u$
$= 0 + \ell = \ell$.

> __Ajout : Inégalité triangulaire sur les intégrales :__ Soit $f \in \mathcal{C}([a,b],\mathbb{K})$
> avec $a < b$, $|\int\limits_{a}^{b} f(t) dt| \leq \int\limits_{a}^{b} |f(t)| dt$.

#### Théorème de comparaison (minoration/majoration)
> Si à partir d'un certain rang, $u_{n} \leq v_n$ :
> - si $u \to +\infty$, alors $v \to +\infty$
> - si $v \to -\infty$, alors $u \to -\infty$

__Preuve :__ Immédiate par définition de $u \to +\infty$

Exemple : $\sum\limits_{k = 1}^{n} \frac{1}{\sqrt{k}}$, minoré par $\sum\limits_{k = 1}^{n} \frac{1}{n}$.

#### Théorème de la limite monotone
> Si $u \in \mathbb{R}^{\mathbb{N}}$ est monotone, alors $u$ possède une limite
> dans $\overline{\mathbb{R}}$. Plus exactement :
> - si $u$ est croissante et majorée, elle converge vers sa borne supérieure
> - si $u$ est croissante et non majorée, elle diverge vers $+\infty$
> - si $u$ est décroissante et minorée, elle converge vers sa borne inférieure
> - si $u$ est décroissante et non minorée, elle diverge vers $-\infty$

Si $u$ est croissante, $\lim\limits_{n \to + \infty} u = \text{sup}(u) \in \overline{\mathbb{R}}$,
et si $u$ est décroissante, $\lim\limits_{n \to + \infty} u = \text{inf}(u) \in \overline{\mathbb{R}}$.

__Preuves :__
- On suppose $u$ croissante et majorée. L'ensemble $\{u_{n},n \in \mathbb{N}\}$ est majoré,
  et sous-ensemble non vide de $\mathbb{R}$, donc il possède une borne supérieure dans $\mathbb{R}$.
  Soit $\varepsilon > 0$, on a $\ell - \varepsilon < \ell = \text{sup}(u)$.
  $\ell - \varepsilon$ n'est pas un majorant de $\{u_{n},n \in \mathbb{N}\}$, et
  donc $\exists n_0, u_{n_0} > \ell - \varepsilon$.
  Or, $u$ est croissante, donc $\forall n \geq n_0, u_{n} \geq u_{n_0} > \ell - \varepsilon$,
  or $\ell = \text{sup}(u)$ donc $u_{n} \leq \ell$.
  $\forall n \geq n_0,\ell - \varepsilon \leq u_{n} \leq \ell < \ell + \varepsilon$,
  donc $|u_{n} - \ell| \leq \varepsilon$.
- On suppose $u$ croissante et non majorée, soit $M \in \mathbb{R}$, puisque
  $u$ est non majorée, $\exists n_0, u_{n_0} > M$, et puisque $u$ est croissante
  $\forall n \geq n_0, u_{n} \geq u_{n_0} > M$.
