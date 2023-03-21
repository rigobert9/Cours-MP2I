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
donc $f'$ est croissante.\
$2 \Rightarrow 3$ Soit $a \in I$, on pose
$\begin{aligned} \varphi: I &\to \mathbb{R}^{\ast} \\ t &\mapsto f(t) - (f(a) + (t - a) f'(a)) .\end{aligned}$.
Par somme, $\varphi$ est dérivable sur $I$ et $\varphi'(t) = f'(t) - f'(a)$, or
$f'$ est croissante par hypothèse, donc $\varphi$ possède un minimum sur $I$,
atteint en $a$ et $\varphi(a) = 0$, donc $\varphi \geq 0$ sur $I$.\
$3 \Rightarrow 1$ On veut montrer que $f$ est convexe sur $I$. Soient $x,y \in I$
et $\lambda \in [0,1]$, on pose $a = (1 - \lambda) x + \lambda y$. Par
hypothèse, la courbe de $f$ est au-dessus de sa tangente en $a$,
donc pour tout $t \in I$, $f(t) \geq f(a) \geq f(a) + (t - a) f'(a)$,
en particulier pour $t = x$ et $t = y$, donnant
$f(x) \geq f(a) + (x - a) f'(a)$ et $f(y) \geq f(a) (y - a) f'(a)$,
donc $(1 - \lambda) f(x) + \lambda f(y) \geq f(a) + (1 - \lambda) (x - a) f'(a) + \lambda (y - a) f'(a)$.
Ainsi, $(1 - \lambda) f(x) + \lambda f(y) \geq f(a) + f'(a)$,
et comme $(1 - \lambda) x + \lambda y = a$,
on a finalement $f((1 - \lambda) x + \lambda y) \leq (1 - \lambda) f(x) + \lambda f(y)$,
donc $f$ est convexe sur $I$.

> Pour $f$ concave sur $I$, $-f$ est convexe sur $I$.

> Caractérisation des fonctions convexes deux fois dérivables :
> Soit $f : I \to \mathbb{R}$ deux fois dérivable,
> $f$ est convexe si et seulement si $f''$ est positive.

__Preuve :__ Comme $f'$ est dérivable sur $I$, $f'$ est croissante
si et seulement si $f''$ est positive.

> Soit $f : I \to \mathbb{R}$ et $a \in I$, $a$ est un point d'inflexion si la
> fonction $f$ change de convexité/concavité au voisinage de ce point $a$.

Pour une fonction $f$ deux fois dérivable, on caractérise ce point d'inflexion
par un double dérivée nulle et un changement de signe au voisinage du point.

> Inégalité de Jensen : soit $f : I \to \mathbb{R}$ convexe,
> $(x_i)_{[\![1,n]\!]} \in I^n$, et $(\lambda_i)_{[\![1,n]\!]} \in [0,1]^n$
> avec $\sum\limits_{i = 1}^{n} \lambda_i = 1$,
> $f(\sum\limits_{i = 1}^{n} \lambda_i x_i) \leq \sum\limits_{i = 1}^{n} \lambda_i f(x_i)$.

__Preuve :__ On prouve par récurrence sur $n$ le théorème.
Pour $n = 1$, $x \in I, \lambda_1 = 1$, donc $f(1x) \leq 1 f(x)$.
Pour $n = 2$, on développe le théorème en l'expression de la convexité.
Pour tout $n \geq 2$ tel que l'hypothèse soit vraie, soit $(x_i)_{[\![1,n+1]\!]} \in I^{n+1}$,
et $(\lambda_i)_{[\![1,n+1]\!]} \in [0,1]^{n+1}$,
avec $\sum\limits_{i = 1}^{n + 1} \lambda_i = 1$, donc $\sum\limits_{i = 1}^{n} \lambda_i + \lambda_{n+1} = 1$.
Si la somme est nulle, alors $\lambda_{n+1} = 1$, donc l'inégalité est vraie (on
se ramène au premier cas).
Si $\sum\limits_{i = 1}^{n} \lambda_i \neq 0$, on pose $s = \sum\limits_{i = 1}^{n} \lambda_i$,
et $s + \lambda_{n+1} = 1$.\
$f(\sum\limits_{i = 1}^{n + 1} \lambda_i x_i) = f(\sum\limits_{i = 1}^{n} \lambda_i x_i + \lambda_{n+1} x_{n+1})$\
$= f(s \times \sum\limits_{i = 1}^{n} \frac{\lambda_i}{s} x_i + \lambda_{n+1} x_{n+1})$\
$\leq s f(s \times \sum\limits_{i = 1}^{n} \frac{\lambda_i}{s} x_i) + \lambda_{n+1} x_{n+1}$\
$\lambda_i' = \frac{\lambda_i}{s}$, on a bien $\sum\limits_{i = 1}^{n} \lambda_i'$
$= \frac{\sum\limits_{i = 1}^{n} \lambda_i}{s} = 1$. On peut alors appliquer par
hypothèse de récurrence $f(\sum\limits_{i = 1}^{n} \lambda_i' x_i) \leq \sum\limits_{i = 1}^{n} \lambda_i' f(x_i)$,
donnant finalement $f(\sum\limits_{i = 1}^{n+1} \lambda_i x_i) \leq s \times \sum\limits_{i = 1}^{n} \frac{\lambda_i}{s} f(x_i) + \lambda_{n + 1} f(x_{n+1})$
$\leq \sum\limits_{i = 1}^{n + 1} \lambda_i f(x_i)$.

##### Exercice : comparaison de moyennes
On cherche à prouver que pour tout $n \in \mathbb{N}^{\ast}$
et $(x_i)_{[\![1;n]\!]} \in (\mathbb{R}_{+}^{\ast})^n$,
$\frac{n}{\sum\limits_{i = 1}^{n} \frac{1}{x_i}} \leq \sqrt[n]{\prod\limits_{i = 1}^{n} x_i} \leq \frac{1}{n} \sum\limits_{i = 1}^{n} x_i$
(moyenne harmonique, moyenne géométrique et moyenne arithmétique).

Pour la seconde inégalité, on voit que
$\frac{1}{n} \sum\limits_{i = 1}^{n} x_i = \sum\limits_{i = 1}^{n} \frac{1}{n} x_i$
(candidat qui marche pour Jensen). Or, $\ln(\sqrt[n]{\prod\limits_{i = 1}^{n} x_i})$
$= \frac{1}{n} \sum\limits_{i = 1}^{n} \ln(x_i)$, or $\ln$ est concave,
donnant par Jensen $\ln(\sum\limits_{i = 1}^{n} \frac{1}{n} x_i) \geq \sum\limits_{i = 1}^{n} \frac{1}{n} \ln(x_i)$,
ce qui nous donne l'inégalité par composition par l'exponentielle.

Pour la première, on veut prouver $\frac{1}{n} \sum\limits_{i = 1}^{n} \frac{1}{x_i} \geq (\prod\limits_{i = 1}^{n} x_i)^{\frac{-1}{n}}$\
$\Leftrightarrow \ln(\sum\limits_{i = 1}^{n} \frac{1}{x_i} \times \frac{1}{n}) \geq \frac{-1}{n} \sum\limits_{i = 1}^{n} \ln(x_i)$\
$\Leftrightarrow \ln(\sum\limits_{i = 1}^{n} \frac{1}{n x_i}) \geq \sum\limits_{i = 1}^{n} \frac{1}{n} \ln(\frac{1}{x_i})$\
Ce qui donne une inégalité de Jensen avec $\ln$ concave, pour $\lambda_i = \frac{1}{n}$
et $x_i' = \frac{1}{x_i}$.
