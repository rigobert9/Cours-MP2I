# Suite récurrentes itérées d'une fonction
Soit une fonction $f: I \to \mathbb{R}$, on définit $(u_n)_n$ une suite
$\left\{\begin{matrix} u_0 \in I \\ \forall n, u_{n+1} = f(u_{n})\end{matrix}\right.$.

On peut aisément représente graphiquement ce genre de suites comme des suite
convergeant de façon non monotone vers un point en "spirale carrée" vers un
point.

## Définition de $(u_n)_n$ et intervalle stable par $f$
> On appelle intervalle stable par $f$ un intervalle $I$ tel que
> $f(I) \subset I$, c'est-à-dire $\forall x \in I, f(x) \in I$.

> Soit $f: I \to \mathbb{R}$ et $I$ stable par $f$, alors la suite
> $\left\{\begin{matrix} u_0 \in I \\ \forall n, u_{n+1} = f(u_{n})\end{matrix}\right.$
> est bien définie et à valeurs dans $I$.

__Preuve :__ Par récurrence simple.

On va alors essayer de choisir des intervalle stables fermés et bornés.

## Points fixes de $f$
> On appelle point fixe de $f$ tout point tel que $f(a) = a$.

> Soit $I$ un intervalle stable fermé de $f$, si $f$ est continue sur
> $I$ et si $u$ converge vers $\ell$, alors $\ell$ est un point fixe de $f$.

__Preuve :__ On a $\forall n, u_{n} \in I$. Si $u_{n} \xrightarrow[+\infty]{} \ell$
et $I$ est fermé, alors $\ell \in I$, et comme $f$ est continue sur $I$ et donc
en $\ell$, par passage à la limite, $u_{n+1} = f(u_{n})$ donne $\ell = f(\ell)$.

## Monotonie de la suite $(u_n)$
> Si $f$ est croissante sur $I$ un intervalle stable, alors la suite $(u_{n})_n$
> sera monotone.

En effet, $f: I \to I$ est croissante, donc pour tout $n$, $f^n = f \circ f \circ \ldots \circ f : I \to I$
est croissante.

- Dans le cas où $u_0 \geq u_1$, alors $f^n(u_0) \geq f^n(u_1)$, donc $u_{n} \geq u_{n+1}$.
- Dans le cas où $u_0 \leq u_1$, alors $u_{n} \leq u_{n+1}$

### Signe de $f(x) - x$
Si $x \mapsto f(x) - x$ est de signe constant sur un intervalle stable $I$,
alors la suite $(u_{n})$ sera monotone.

- Si $\forall x \in I, f(x) - x \geq 0$, alors $\forall n \in \mathbb{N}, f(u_{n}) \geq u_{n}$, donc la suite $(u_{n})$ est croissante.
- Si la $x \mapsto f(x) - x$ est négative sur $I$, $u$ est décroissante.

## Cas de $f$ contractante sur $I$
> $f: I \to I$ est contractante si $f$ est $k$-lipschitzienne sur $I$ avec $k \in [0,1[$.

> Soit $\left\{\begin{matrix} u_0 \in I \\ \forall n, u_{n+1} = f(u_{n})\end{matrix}\right.$ avec $f$
> contractante sur $I$, alors $u$ converge vers l'unique point fixe de $f$.

$\forall (x,y) \in I^2, |f(x) - f(y)| \leq k |x - y|$,
si $\ell_1$ et $\ell_2$ sont deux points fixes,
$|f(\ell_1) - f(\ell_2)| \leq k |\ell_1 - \ell_2|$
$\Leftrightarrow |\ell_1 - \ell_2| \leq k |\ell_1 - \ell_2|$,
or $k \in [0,1[$, donc si $\ell_1 \neq \ell_2$ alors
$k \geq 1$, ce qui est faux, donc $\ell_1 = \ell_2$.

Si ce point fixe existe, alors comme $I$ est stable par $f$,
$\forall n, u_{n} \in I, |f(u_{n}) - f(\ell)| \leq k |u_{n} - \ell|$,
donnant par récurrence
$\forall n, u_{n} \in I, |f(u_{n}) - f(\ell)| \leq k^n |u_{0} - \ell|$,
et comme $k^n \xrightarrow[n \to +\infty]{} 0$, $(u_{n})_n$ converge vers
$\ell$.

Enfin, ce point fixe existe, car si $I = [a,b]$ et $f: [a,b] \to [a,b]$,
puisque $f$ est lipschitzienne et donc continue, on peut appliquer le
TVI sur $g(x) = f(x) - x$. Si $I$ est un intervalle ouvert,
$\forall x,y \geq a, |f(x) - f(y)| \leq k |x - y|$. On fixe $y = a$,
et on a alors $k (a - x) \leq f(x) - f(y) \leq k (x - a)$,
donc $f(x) - x \leq k x - k a + f(a) - x$
$\Leftrightarrow f(x) - x \leq (k-1) x + f(a) - ka$.
Puisque $f(a) - ka$ est fini, et que $(k-1)x \xrightarrow[x \to \infty]{} -\infty$,
$\lim\limits_{x \to + \infty} (f(x) - x) = -\infty$, donc $\exists c \mid f(c) - c \leq 0$,
or $f(a) - a \geq 0$. On applique le TVI.

## Méthode de Newton
Soit $f$ de classe $\mathcal{C}^2$ sur $[a,b]$, avec $f'$ et $f''$ sont
strictement positives, et $f(a) < 0$ et $f(b > 0)$. $f$ est alors strictement
croissante et convexe, et est une bijection continue dans $f([a,b]) = [f(a);f(b)]$,
et $0 \in [f(a);f(b)]$. $\exists! c \in ]a,b[ \mid f(c) = 0$.

On prend l'équation de la tangente à $f$ en $b$, $y = f(b) + f'(b) (x - b)$.
L'intersection avec l'axe des abscisses $y = 0$ donne le point $d$, tel que
$0 = f(b) + f'(b) (d - b)$, donc $d = b - \frac{f(b)}{f'(b)}$.

On pose alors $x_0 = b$ et $x_{n+1} = \varphi(x_n)$,
avec $\varphi: t \mapsto t - \frac{f(t)}{f'(t)}$.
Par opérations, $\varphi$ est $\mathcal{C}^1$, donc
$\varphi'(t) = 1 - \frac{(f'(t))^2 - f(t) \times f''(t)}{(f'(t))^2}$
$= \frac{f(t) \times f''(t)}{(f'(t))^2}$.
Comme sur $]c,d]$, $f'$ est strictement positive, $f$ est strictement croissante
sur l'intervalle. Or, $\varphi(b) = d$ et $\varphi(c) = c - \frac{f(c)}{f'(c)} = c$.
Ainsi, $\varphi([c,b]) = [c,d]$, et comme $d = b - \frac{f(b)}{f'(b)} < b$,
$\varphi([c,b]) \subset [c,b]$, donc $[c,b]$ est stable par $\varphi$.

Ainsi, la suite $(x_n)_n$ est à valeurs dans $[c,d]$, et est donc bornée.
Elle est monotone car $\varphi$ est croissante, et $x_0 = b > d = x_1$, donc
$(x_n)_n$ est strictement décroissante. Ainsi, $(x_n)_n$ converge vers une
limite $\ell \in [c,b]$, avec $\varphi(\ell) = \ell$. Or, $\varphi(b) = \ell$
$\Leftrightarrow \ell - \frac{f(\ell)}{f'(\ell)} = \ell \Leftrightarrow f(\ell) = 0$
$\Leftrightarrow \ell = c$.

Cette approche est très précise, plus précise que de procéder par dichotomie.
On étudie son erreur, $x_n - c \geq 0$. On fixe donc $x \in [c,b]$,
avec $f$ $\mathcal{C}^2$ sur $[c,x]$. En utilisant Taylor-Lagrange à l'ordre
$1$, on obtient $|f(c) - f(x) - (c - x) f'(x)| \leq $
...

Pour chaque $n \in \mathbb{N}$, on l'applique avec $x_n \in [c,b]$,
donnant $|0 - f(x_n) - (c - x_n) f'(x_n)| \leq \frac{|c - x_n|^2}{2} \text{sup}\restriction_{[x,x_n]} |f^n|$.
Or, $x_{n+1} = \varphi(x_n) = x_n - \frac{f(x_n)}{f'(x_n)}$,
donc $f'(x_n) x_{n+1} = f'(x_n) x_n - f(x_n)$,
donc $|f'(x_n) x_{n+1} - c f'(x_n)| \leq \frac{|c - x_n|^2}{2} M_n$
$\Leftrightarrow |f'(x_n)| |x_{n+1} - c| \leq \frac{|c - x_n|^2}{2} M_n$.
$f'$ étant croissante sur $[c,x_n]$,
$0 < f'(c) \leq f'(x_n)$, donc $\frac{1}{f'(x_n)} \leq \frac{1}{f'(c)}$.
$|x_{n+1} - c| \leq |x_n - c|^2 \times \frac{1}{2 f'(c)} M_n$,
avec $M_n = \text{sup}\restriction_{[c,x_n]} |f'| \leq \text{sup}\restriction_{[c,b]} |f''|$,
donnant bien un $|x_{n+1} - c| \leq |x_n - c|^2 \times K$.

Si à l'itération $n$ on est à une précision $10^{-d}$, c'est-à-dire si
$|x_n - c| \leq 10^{-d}$, alors $|x_{n+1} - c| \leq (10^{-d})^2 \times K \leq K \times 10^{-2d}$.
Le nombre de décimales à l'itération $(n+1)$ est donc de l'ordre $2d$.
On double donc la précision à chaque itération.
