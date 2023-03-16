# Convexité
En géométrie, une partie $A$ est convexe si pour toute paire de points $M,N$ de
$A$, le segment $[M,N]$ est inclus dans $A$.

Les parties convexes de $\mathbb{R}$ sont les intervalles, c'est à dire que soit
$I \subset \mathbb{R}$, $I$ est un intervalle si et seulement si
$\forall x,y \in I \mid x < y, [x,y] \subset I$.

La paramétrisation d'un segment entre $0$ et $1$ se fait par la fonction
$\begin{aligned} f: [0,1] &\to [x,y] \\ t &\mapsto x + t (y - x) .\end{aligned}$,
donnant ainsi $[x,y] = f([0,1]) = \{x + t (y - x) \mid t \in [0,1]\}$
$= \{(1 - t) x + t y \mid t \in [0,1]\}$. On va pouvoir utiliser ce parcours
pour définir une caractérisation de la convexité.

Soit $f : I \to \mathbb{R}$ quelconque, on pose une droite qui passe par
$(x,f(x))$ et $(y,f(y))$ qu'on appelle sécante, dont le coefficient directeur
est $\frac{f(y) - f(x)}{y - x}$, et qui est donc d'équation
$z \mapsto \frac{f(y) - f(x)}{y - x} \times (z - x) + f(x)$.
La portion de cette droite reliant les points $(x,f(x))$ et $(y,f(y))$
est appelée corde.

> Soit $f : I \to \mathbb{R}$, avec $I$ un intervalle, on dit que $f$ est
> convexe (concave) sur $I$ si son graphe est situé au-dessus (en-dessous) de ses
> cordes :
> $\forall (x,y) \in I^2, \forall \lambda \in [0,1], f((1 - \lambda) x + \lambda y) \leq (\geq) (1-\lambda) f(x) + \lambda f(y)$.

> Position d'une fonction convexe vis-à-vis de ses sécantes : soit $f : I \to \mathbb{R}$
> convexe, et $\left\{\begin{matrix} x,y \in I \\ x < y \end{matrix}\right.$,
> le graphe de $f$ est situé sous la sécante sur $[x,y]$ et au-dessus de la
> sécante sur $I \setminus [x,y]$.

__Preuve :__ Soit $t \in [y,+\infty[$, on veut montrer que $f$ est au-dessus de
sa sécante, donc pour $t \geq y$, $f(t) \geq \frac{f(y) - f(x)}{y - x} (t - y) + f(y)$\
$\Leftrightarrow (y - x) f(t) \geq (f(y) - f(x)) (t - y) + f(y) (y - x)$\
$\Leftrightarrow (y - x) f(t) \geq (t - x) f(y) - (t - y) f(x)$\
$\Leftrightarrow (t - y) f(x) + (y - x) f(t) \geq (t - x) f(i)$\
$\Leftrightarrow \frac{t - y}{t - x} f(x) + \frac{y - x}{t - x} f(t) \geq f(y)$\
On a bien $\frac{t - y}{t - x} + \frac{y - x}{t - x} = 1$,
donc $\frac{y - x}{t - x} = 1 - \frac{t - y}{t - x}$, dans $[0,1]$.
On peut alors redévelopper l'expression de la convexité. $f$ étant convexe,
c'est vrai.

> Caractérisation par croissance des pentes :
> $f$ est convexe sur $I$ si et seulement si pour tout
> $a \in I$, la fonction
> $\begin{aligned} \tau_a: I \setminus \{a\} &\to \mathbb{R} \\ x &\mapsto \frac{f(x) - f(y)}{x - y} .\end{aligned}$
> est croissante.

C'est une version sans la limite du résultat qu'on obtient par la positivité de
la double dérivée si et seulement si $f$ est convexe.

__Preuve :__ $\Rightarrow$ Si $f$ est convexe, on fixe $a \in I$, et
on montre que $\tau_a$ est croissante. On prend $x < y$ et
$\left\{\begin{matrix} x \neq a \\ y \neq a \end{matrix}\right.$,
et on essaie de montrer $\tau_a(x) \leq \tau_a(y)$.
La sécante qui passe par $(a,f(a))$ et $(x,f(x))$
a pour définition $t \mapsto \frac{f(x) - f(a)}{x - a} (t - a) + f(a)$.
- Si $y > a$, comme $y > x$, $y$ est hors du segment $[x,a]$ ou $[a,x]$, donc
  $f(y)$ est au-dessus de la sécante ($f(y) \geq \tau_a(x) \times (y - a) + f(a)$),
  donc $\tau_a(y) \geq \tau_a(x)$.
- Si $y < a$, donc $x < y < a$, $y \in [x,a]$, donc $f(y)$ est sous la sécante,
  donc $\tau_a(y) \geq \tau_a(x)$.

$\Leftarrow$ Si pour tout $a \in I$, $\tau_a$ est croissante. Pour montrer $f$
convexe sur $I$, on se donne $\left\{\begin{matrix} x,y \in I \\ \lambda \in [0,1] \end{matrix}\right.$,
on peut se restreindre à $\lambda \in ]0,1[$ et $x < y$. On va poser $a = (1 - \lambda) x + \lambda y$,
donc $x < a < y$. $\tau_a$ est supposée croissante donc
$\frac{f(x) - f(a)}{x - a} \leq \frac{f(y) - f(a)}{y - a}$, avec
$x - a < 0$ et $y - a > 0$, donnant $(y - a) (f(x) - f(a)) \geq (x - a) (f(y) - f(a))$,
donc $(y - a) f(x) + (a - x) f(y) \geq (y - x) f(a)$, donc
$\frac{y - a}{y - x} f(x) + \frac{a - x}{y - x} f(y) \geq f(a)$,
or $\frac{y - a}{y - x} = \frac{y - (1 - \lambda) x - \lambda y}{y - x}$
$= \frac{(y - x) - \lambda (y - x)}{y - x} = 1 - \lambda$
et $\frac{a - x}{y - x} = \frac{(1 - \lambda) x + \lambda y - x}{y - x} = \lambda$,
montrant finalement $(1 - \lambda) f(x) + \lambda f(y) \geq f((1 - \lambda) x + \lambda y)$,
donc $f$ est convexe.

> Caractérisation des fonctions dérivables convexes :
> Soit $f : I \to \mathbb{R}$ dérivable,  $f$ est
> convexe sur $I$ si et seulement si $f'$ est croissante sur $I$
> si et seulement si le graphe de $f$ est situé au-dessus de ses tangentes.

__Preuve :__ $1 \Rightarrow 2$ Soient $x < y$, pour tout $t \in ]x,y[$, les
pentes croissantes donnent immédiatement $f'(x) \leq \frac{f(y) - f(x)}{y - x} \leq f'(y)$,
donc $f'$ est croissante.
