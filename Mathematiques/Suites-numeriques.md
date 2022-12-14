# Suites numériques
## Généralités sur les suites réelles
### Définitions, opérations
> Une suite est une famille de réels indexées par $\mathbb{N}$, c'est à dire
> une application de $\mathbb{N}$ dans $\mathbb{R}$.

> Soit $u \in \mathbb{R}^{\mathbb{N}}$, $u$ est une suite réelle
> $\begin{aligned} u: \mathbb{N} &\to \mathbb{R} \\ n &\mapsto u_n .\end{aligned}$,
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

#### Suites adjacentes
> Soient $u,v \in \mathbb{R}^{\mathbb{N}}$, on dira que u et v sont adjacentes si
> - l'une est croissante
> - l'autre est décroissante
> - $(u-v)$ converge vers $0$

> Si $u$ et $v$ sont deux suites adjacentes, alors ells convergent vers la même
> limite.

__Preuve :__ On suppose $u$ croissante et $v$ décroissante, alors $v - u = v + (-u)$
est la somme de deux suites décroissantes donc la suite $(v - u)$ est
décroissante. Or, $\lim (v-u) = 0$. Ainsi, $\forall n \in \mathbb{N}, v_n - u_{n} \geq 0$.
On a donc $\forall n \in \mathbb{N}, u_{n} \leq v_n$, or $u$ est croissante,
donc minorée par $u_0$, et v étant décroissante, elle est majorée par $v_0$.

Ainsi, $u_0 \leq u_1 \leq u_2 \ldots  \leq u_{n} \leq v_n \leq \ldots \leq v_0$.
En particulier, la suite $u$ est majorée par $v_0$ et la suite $v$ est minorée
par $u_0$. Par limites monotones, $u$ et $v$ convergent. Comme $\lim (v - u) = 0$, alors
$\lim v = \lim (v - u) + \lim u$, donc $\lim v = \lim u$.

__Remarque :__ En notant $\ell$ la limite commune des deux suites adjacentes, on
a alors $u_0 \leq u_{1} \leq \ldots \leq u_{n} \leq \ell \leq v_n \leq \ldots v_1 \leq v_0$.
Ainsi, les valeurs des deux suites respectives sont des approches de la limite,
l'une par défaut et l'autre par excès : $\forall n \in \mathbb{N},\ell \in [u_{n},v_n]$
et $(v-u)$ converge vers $0$.

##### Exemple
$\forall n \in \mathbb{N}, \left\{\begin{matrix} u_{n} = \sum\limits_{k = 0}^{n} \frac{1}{k!} \\ v_n = u_{n} + \frac{1}{n!} \end{matrix}\right.$

On cherche à montrer que $u$ et $v$ convergent vers la même limite :
- $v_n - u_{n} = \frac{1}{n!}$ donc $\lim\limits_{n \to + \infty} (v_n - u_{n}) = 0$
- $u_{n+1} - u_{n} = \frac{1}{(n+1)!} > 0$, donc $u$ est croissante.
- $v_{n+1} - v_{n} = (u_{n+1} + \frac{1}{(n+1)!}) - (u_{n} + \frac{1}{n!})$\
  $= (u_{n+1} - u_{n}) + \frac{1}{(n + 1)!} - \frac{1}{n!}$\
  $= \frac{2}{(n+1)!} - \frac{1}{n!} \times \frac{n + 1}{n + 1}$\
  $= \frac{2 - (n+1)}{(n + 1)!} = \frac{1 - n}{(n + 1)!}$

$\forall n \geq 1, (v_{n+1} - v_{n}) \leq 0$. La suite $v$ est décroissante à
partir d'un certain rang.
Ainsi, $u$ et $v$ sont adjacentes, et convergent donc vers une limite commune.

##### Irrationalité de $e$
__Culture :__ $e = \exp(1) = \sum\limits_{k = 0}^{+\infty} \frac{1}{k!}$

Ici, on a donc $\forall n \geq 2$, $u_{n} < e < v_{n}$. Ces valeurs approchées
sont avec une erreur de l'ordre de $\frac{1}{n!}$.

On cherche à prouver que $e \not\in \mathbb{Q}$. Par l'absurde, si $e = \frac{p}{q}$ avec
$p,q \in \mathbb{N}^{\ast}$, et on regarde le rang $q$ : $u_q < e < v_q$,
donc $\sum\limits_{k = 0}^{q} < e < \sum\limits_{k = 0}^{q} \frac{1}{k!} + \frac{1}{q!}$.
En multipliant par $q!$, on obtient $\sum\limits_{k = q}^{n} \frac{q!}{k!} < q!
e < \sum\limits_{k = 0}^{q} \frac{q!}{k!} + 1$.

Or, $\sum\limits_{k = 0}^{q}  \in \mathbb{N}$ car $\frac{q!}{k!} \in \mathbb{N}$
pour $0 < k \leq q$. On pose enfin $N < eq! < n + 1$
$\Leftrightarrow n < \frac{p}{q} \times q! < n + 1$
$\Leftrightarrow n < p \times (q-1)! < n + 1$, et tous ces trois expressions
sont donc toutes entières, ce qui est absurde.

#### Suites extraites
> Soit $u \in \mathbb{R}^{\mathbb{N}}$, on dit que $v \in \mathbb{R}^{\mathbb{N}}$
> est une suite extraite de $u$ s'il existe une application strictement croissante
> extractrice $\varphi: \mathbb{N} \to \mathbb{N}$, telle que $\forall n \in \mathbb{N},v_n = u_{\varphi(n)}$.

__Exemples classiques :__
- $v = (u_{2n})_{n \in \mathbb{N}}$ est extraite de $u$ car
  $\begin{aligned} \varphi: \mathbb{N} &\to \mathbb{N} \\ n &\mapsto 2n =  .\end{aligned}$
  est bien strictement croissante ($v$ est la sous-suite d'indices pairs de $u$)
- $w = (u_{2n + 1})_{n \in \mathbb{N}}$ est une suite extraite de $u$ avec
  $\varphi: n \mapsto 2n + 1$ strictement croissante. $w$ est la sous-suite de
  $u$ des termes d'indices impairs.
- $u_{n+1}$ est extraite de $u$ avec $\varphi: n \mapsto n+1$.

> Si $u$ converge vers $\ell \in \mathbb{R}$, alors toute suite extraite de u
> converge vers $\ell$.

__Application :__ si $\lim\limits_{n \to + \infty} u_{n} = \ell$,
alors $\lim\limits_{n \to + \infty} (u_{2n + 1}) = \ell$,
$\lim\limits_{n \to + \infty} (u_{n^2}) = \ell$,
$\lim\limits_{n \to + \infty} (u_{n+1}) = \ell$.

__Preuve :__ Soit $u \in \mathbb{R}^{\mathbb{N}}$ qui converge vers $\ell$
et $v$ une suite extraite de $u$.
Il existe $\varphi:\mathbb{N} \to \mathbb{N}$ extractrice (strictement croissante)
telle que $\forall n \in \mathbb{N},v_{n} = u_{\varphi(n))}$.

Soit $\varepsilon > 0, \exists n_0,\forall n \geq n_0, |u_{n} - \ell| \leq \varepsilon$
(puisque $u \to \ell$), or $\varphi(n) \geq n$.
Ainsi, pour tout entier $n \geq n_0$, on a bien $\varphi(n) \geq n \geq n_0$,
donc pour cet indice $\varphi(n)$ : $|u_{\varphi(n)} - \ell| \leq \varepsilon$,
c'est-à-dire $|v_{n} - \ell| \leq \varepsilon$, donc $v \to \ell$.

__Application :__ Pour montrer qu'une suite diverge (sans limite), on peut en
extraire deux sous-suites qui convergent vers des limites différentes.
Par exemple, pour $((-1)^n)_{n \in \mathbb{N}}$, $u_{2n} \to 1$ et $u_{2n + 1} \to -1$, donc $u$ diverge.

> Soit $u \in \mathbb{R}^{\mathbb{N}}$ et $\ell \in \mathbb{R}$.
> Si $(u_{2n})$ et $(u_{2n + 1})$ convergent tous deux vers $\ell$, alors la suite
> $u$ converge vers $\ell$.

> Bolzano - Weierstrass : Toute suie réelle bornée admet (au moins) une sous-suite
> convergente.

__Preuve :__ Soit $u \in \mathbb{R}^{\mathbb{N}}$ bornée, $\exists n \in \mathbb{R}_{+} \mid n \in \mathbb{N}, |u_{n}| \leq M$.
On construit des segments $[a_n,b_n]$ de la façon suivante :
$\left\{\begin{matrix} a_0 = -M \\ b_0 = +M \end{matrix}\right.$.
On pose $A_n = \{k \in \mathbb{N} \mid u_k \in [a_n,b_n]\}$.
On pose de même $C_n = \frac{a_n + b_n}{2}$ le milieu de $[a_n,b_n]$,
et $A^d_n = \{k \in \mathbb{N} \mid u_k \in [c_n,b_n]\}$,
$A^g_n = \{k \in \mathbb{N} \mid u_k \in [a_n, c_n]\}$,
$A_n = A_n^g \cup A_n^d$.

On en conclut $a_{n+1}$ et $b_{n+1}$,
$a_{n+1} = \left\{\begin{matrix} C_n \text{ si } A_n^d \text{ est infini} \\ a_n \text{ sinon} \end{matrix}\right.$ et
$a_{n+1} = \left\{\begin{matrix} b_n \text{ si } A_n^d \text{ est infini} \\ C_n \text{ sinon} \end{matrix}\right.$.
Ainsi, $A_{n+1}$ est infini.

$a_n \leq C_n = \frac{a_n + b_n}{2} \leq b_n$. Ainsi, $\forall n \in \mathbb{N}, \left\{\begin{matrix} a_{n+1} \geq a_n \\ b_{n+1} \leq b_n \end{matrix}\right.$,
donc $a$ est croissante et $b$ est décroissante. De plus,
$b_{n+1} - a_{n+1} = \left\{\begin{matrix} C_n - a_n \\ \text{ou} \\ b_n - Cn \end{matrix}\right.$, donc
$b_{n+1} - a_{n+1} = \frac{b_n - a_n}{2}$. $b-a$ est donc géométrique de raison
$\frac{1}{2}$. $\forall n, b_n - a_n = \frac{1}{2^n} (b_0 - a_0)$, donc
$\lim\limits_{n \to + \infty} (b_n - a_n) = 0$.

On en conclut enfin que $a$ et $b$ sont deux suites adjacentes, donc elles
convergent vers la même limite $\ell$. On construit une suite extraite de $u$
qui converge vers ce $\ell$, avec $\varphi : \mathbb{N} \to \mathbb{N}$ :
- On pose $\varphi(0) = 0$, $\varphi(0) \in A_0$ donc $a_0 \leq u_{\varphi(0)} \leq b_0$
- Soit $n \in \mathbb{N} \mid \varphi(0) < \varphi(1) < \varphi(2) \ldots < \varphi(n)$ sont déjà construits

On pose $\varphi(n + 1) = \text{min}(A_{n+1} \setminus [0,\varphi(n)]_{\mathbb{N}})$,
et ainsi $\varphi(n + 1) > \varphi(n)$ et $a_{n+1} \leq u_{\varphi(n + 1)} \leq b_{n+1}$.

Ainsi, $\varphi : \mathbb{N} \to \mathbb{N}$ est strictement croissante et
$\forall n \in \mathbb{N}, a_n \leq u_{\varphi(n)} \leq b_n$, or
$\lim a = \lim  b = \ell$, donc on conclut par théorème d'encadrement que
$(u_{\varphi(n)})_{n \in \mathbb{N}}$ converge vers $\ell$.

### Caractérisations séquentielles
#### Partie dense dans $\mathbb{R}$
> Soit $A \subset \mathbb{R}$, $A$ est dense dans $\mathbb{R}$ si
> $\forall x \in \mathbb{R},\forall \varepsilon > 0, \exists y \in A, |x - y| \leq \varepsilon$.

> $A$ est dense dans $\mathbb{R}$ si et seulement si $AAx \in \mathbb{R}, \exists (a_n)_{n \in \mathbb{N}} \in A^{\mathbb{N}}, \lim\limits_{n \to + \infty} a_n = x$.

__Preuve :__\
$\Rightarrow$ On suppose $\forall x \in \mathbb{R}, \forall \varepsilon > 0, \exists a \in A, |x - a| \leq \varepsilon$.
Soit $x \in \mathbb{R}$, pour tout $n \in \mathbb{N}$, on pose
$\varepsilon_n = \frac{1}{n + 1} > 0$. Ainsi, il existe $a_n  \in A \mid |x - a_n| \leq \varepsilon_n$,
donc on a $(a_n)_{n \in \mathbb{N}} \in A^{\mathbb{N}}$ telle que $\forall n \in \mathbb{N},|x - a_n| \leq \frac{1}{n+1}$,
donc $\lim\limits_{n \to + \infty} a_n = x$.\
$\Leftarrow$ On suppose $\forall x \in \mathbb{R}, \exists (a_n)_{n \in \mathbb{N}} \in A^{\mathbb{N}}$
tel que $a_n \to_{n \to +\infty} x$. Soit $x \in \mathbb{R}$ et $\varepsilon > 0$,
$a_n \to x \Rightarrow \exists n_0,\forall \geq n_0,|a_n - x| \leq \varepsilon$.
Ainsi, $a_{n_0} \in A$ et $|a_{n_0} - x| \leq \varepsilon$.

##### Exemple : densité de $\mathbb{Q}$ dans $\mathbb{R}$
Puisque pour tout $x \in \mathbb{R}$, on peut poser $d_n = \frac{\left\lfloor x \times 10^n \right\rfloor}{10^n} \in \mathbb{Q}$
et $\forall n \in \mathbb{N}$, $d_n \leq x < d_n + \frac{1}{10^n}$.
Enfin, $\forall n \in \mathbb{N},|x - d_n| \leq \frac{1}{10^n}$,
donc $d_n  \to_{n \to +\infty} x$.

#### Caractérisation de la borne supérieure
> Soit $A \subset \mathbb{R}$ non vide majoré, alors $A$ possède une borne supérieure
> $\alpha = \text{sup}(A)$.

> $\alpha$ est la borne supérieure si et seulement si $\left\{\begin{matrix} \forall \varepsilon > 0, \exists a \in A, \alpha - \varepsilon < a \\ \forall a \in A, a \leq \alpha \end{matrix}\right.$.

> Soit $\alpha \in \mathbb{R}$ et $A \subset \mathbb{R}$ non vide majorée, $\alpha = \text{sup}(A)$
> si et seulement si $\alpha$ est un majorant de $A$ et il existe une suite
> $(a_n)_{n \in \mathbb{N}} \in A^{\mathbb{N}}$ qui converge $\alpha$.

__Preuve :__\
$\Rightarrow$ On suppose $\alpha$ majorant de $A$ et $\forall \varepsilon > 0, \exists a \in A, \alpha - \varepsilon < a$.
Pour tout $n \in \mathbb{N}$, on prend $\varepsilon_n = \frac{1}{2^n} > 0$.
Avec cet $\varepsilon_n > 0$, il existe $a_n \in A \mid \alpha - \varepsilon_n < a_n$.
Ainsi, $(a_n)_{n \in \mathbb{N}} \in A^{\mathbb{N}}$ vérifie
$\forall n \in \mathbb{N}, \alpha - a_n \leq \frac{1}{2^n}$. De plus,
$\alpha$ est majorant de $A$, donc $\forall n \in \mathbb{N}, a_n \leq \alpha$.
Finalement, $\forall n \in \mathbb{N}, 0 \leq \alpha - a_n \leq \frac{1}{2^n}$.
Par encadrement, $\lim\limits_{n \to + \infty} a_n = \alpha$.\
$\Leftarrow$ On suppose $\alpha$ majorant de $A$ et il existe $(a_n)_n \in A^{\mathbb{N}}$
qui converge vers $\alpha$. Soit $\varepsilon > 0$,
$\exists n_0 \in \mathbb{N}, \forall n \geq n_0, |a_n - \alpha| \leq \varepsilon$.
$\forall n \geq n_0, \alpha - \frac{\varepsilon}{2} \leq a_n \leq \alpha + \frac{\varepsilon}{2}$.
En particulier, $a_{n_0} \in A$ et $\alpha - \frac{\varepsilon}{2} \leq a_{n_0}$,
$\alpha - \varepsilon < \frac{-\varepsilon}{2}$,
donc $\alpha - \varepsilon < \alpha - \frac{\varepsilon}{2} \leq a_{n_0}$.

## Suites à valeurs complexes
> Soit $u \in \mathbb{C}^{\mathbb{N}}$. On définit :
> - $\Re(u) = (\Re(u_{n}))_{n \in \mathbb{N}} \in \mathbb{C}^{\mathbb{N}}$
> - $\Im(u) = (\Im(u_{n}))_{n \in \mathbb{N}} \in \mathbb{C}^{\mathbb{N}}$
> - $|u| = (|u_n|)_{n \in \mathbb{N}} \in \mathbb{R}_{+}^{\mathbb{N}}$
> - $\overline{u} = (\overline{u_{n}})_{n \in \mathbb{N}} \in \mathbb{C}^{\mathbb{N}}$

Ainsi, $u = \Re(u) + i \Im(u)$, $\overline{u}^2 = u \overline{u} = \Re(u)^2 + \Im(u)^2$,
$\Re(u) = \frac{1}{2} (u + \overline{u})$ et $\Im(u) = \frac{1}{2i} (u - \overline{u})$.

Soit $u \in \mathbb{C}^{\mathbb{N}}$, $u$ est bornée si
$\exists M, \forall n \in \mathbb{N}, |u_{n}| \leq M$.

> Si $u,v \in \mathbb{C}^{\mathbb{N}}$ bornées et $\lambda \in \mathbb{C}$,
> alors $u + v$, $u \times v$ et $\lambda u$ sont bornées.

> Soit $u \in \mathbb{C}^{\mathbb{N}}$ et $\ell \in \mathbb{C}$,
> $u$ converge vers $\ell$ si $\forall \varepsilon > 0, \exists n_0, \forall n \geq n_0, |u_{n} - \ell| \leq \varepsilon$.

> Le théorème d'unicité de la limite a le même énoncé que pour les suites réelles

> Si et seulement si $u$ converge vers $\ell$, $\Re(u)$ converge vers
> $\Re(\ell)$ et $\Im(u)$ converge vers $\Im(\ell)$.

__Preuve :__ $u - \ell = (\Re(u) + i \Im(u)) - (\Re(\ell) + i \Im(\ell))$\
$\Leftrightarrow u - \ell = (\Re(u) - \Re(\ell)) + i(\Im(u) - \Im(\ell))$\
$\Leftrightarrow |u - \ell| \leq |\Re(u) - \Re(\ell)| + |\Im(u) - \Im(\ell)|$\
Cette inégalité prouve le sens $\Leftarrow$.
On prouve $\Rightarrow$ avec $|\Re(z)| \leq |z|$ et $|\Im(z)| \leq |z|$.
Ainsi, $|\Re(u) - \Re(\ell)| = |\Re(u - \ell)| \leq |u - \ell|$,
et de même avec les parties imaginaires.

> Si $u \to \ell$ et $v \to \ell'$ avec $\ell,\ell' \in \mathbb{C}$, alors
> on obtient les mêmes propriétés que dans $\mathbb{R}^{\mathbb{N}}$.

> $u$ diverge si $u$ ne converge pas

> Toute suite convergente est bornée (même preuve que pour les réels)

> (Admis) Toute suite de $\mathbb{C}^{\mathbb{N}}$ bornée admet une sous-suite convergente
