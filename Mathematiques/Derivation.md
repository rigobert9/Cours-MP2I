# Dérivation
## Dérivabilité
> Soit $f: I \to \mathbb{R}$ et $a \in I$, avec $I$ un intervalle, $f$ est
> dérivable en $a$ si son taux d'acroissement en $a$ possède une limite finie.

> Le taux d'accroissement de $f$ en $a$ est $\tau_a(x) = \frac{f(x) - f(a)}{x - a}$,
> pour tout $x \in I \setminus \{a\}$.

Si $\tau_a(x) \xrightarrow[x \to a]{} \ell \in \mathbb{R}$, on note $f'(a) = \ell = \lim\limits_{x \to a} \tau_a(x)$
le nombre dérivé de $f$ en $a$.

On rappelle que la tangente en $a$ de la courbe d'une fonction ($\text{DL}_{1}(a)$ par
Taylor-Young) est $y = f'(a) (x - a) + f(a)$. On a de plus l'équivalence entre
l'existence de ce $\text{DL}_{1}(a)$ avec la dérivabilité de $f$ en $a$.

Si $f$ est dérivable en $a$, on a $f'(a) = \lim\limits_{x \to a} \frac{f(x) - f(a)}{x - a}$
$= \lim\limits_{h \to 0} \frac{f(a + h) - f(a)}{h}$.

> Si $f$ est dérivable en $a$, alors $f$ est continue en $a$.

En effet, $f$ possède alors un $\text{DL}_{1}(a)$, qu'on peut tronquer en un $\text{DL}_{0}(a)$,
qui est équivalent à la continuité de $f$ en $a$.

On note la dérivée en $a$ d'une fonction $f$ sous l'une des formes
$f'(a)$, $D(f)$, $\frac{d f}{dx}(a)$, $\dot{f}(a)$, $f^{(1)}(a)$.

Si $\tau_a(x) \xrightarrow[x \to a]{} \pm \infty$, alors $f$ n'est pass
dérivable en $a$ et possède une tangente verticale en $a$.
Si elle n'a pas de limite finie, la fonction n'est pas dérivable en ce point.
Par exemple, $x \mapsto |x|$ n'est pas dérivable en $0$.

> Soit $f: I \to \mathbb{R}$, $f$ est dérivable sur $I$ si $f$ est dérivable en $a$, pour tout $a \in I$.
> Dans ce cas, on définit la fonction dérivée $\begin{aligned} f': I &\to \mathbb{R} \\ x &\mapsto f'(x) = \lim\limits_{y \to x} \frac{f(y) - f(x)}{y - x} .\end{aligned}$.

On note l'ensemble des fonctions dérivables sur $I$ $\mathcal{D}(I,\mathbb{R})$
et l'ensemble des fonctions continues sur $I$ $\mathcal{C}(I, \mathbb{R})$. On
a ainsi $\mathcal{D}(I,\mathbb{R}) \subset \mathcal{C}(I,\mathbb{R})$.

On définit de plus la dérivée à gauche et à droite de $f$ en $a$, au cas où le
taux d'acroissement ait une limite différente de chaque côté.

> $f$ est dérivable à droite en $a$ si $f_{I \cap [a,+\infty[}$ est dérivable en
> $a$, et on note $f'_d(a) = \lim\limits_{x \to a^{+}} \tau_a(x)$. On définit de
> même la dérivabilité à gauche.

On définit ainsi avec le $\text{DL}_{1}(a)$ les demi-tangentes à droite et à
gauche de la fonction.

> Ainsi, $f$ est dérivable en un point intérieur $a$ si et seulement si
> $f$ est dérivable à gauche et à droite en $a$, et que ces dérivées sont égales.

> $f$ est $\mathcal{C}^n$ sur $I$ signifie que $f$ est $n$ fois dérivable sur $I$,
> et que $f^{(n)}$ est continue sur $I$.

Lorsque c'est le cas pour un nombre infinie de dérivations, on note $\mathcal{C}^{\infty}(I,\mathbb{R})$.
De plus, on a toujours $\mathcal{C}^{n} \subset \mathcal{D}^n \subset \mathcal{C}^{n+1} \subset \mathcal{D}^{n+1} \subset \ldots \subset \mathcal{C}^{\infty} \subset \mathcal{D}^{\infty}$.

> $(\mathcal{D}(I,\mathbb{R}), +, \times)$ forme un anneau.

> Si $f \in \mathcal{D}(I,\mathbb{R})$ et $g \in \mathcal{D}(J,\mathbb{R})$,
> avec $f(I) \subset J$, alors $g \circ f \in \mathcal{D}(I,\mathbb{R})$
> et $(g \circ f)' = f' \times (g' \circ f)$.

__Preuve :__ Pour $a \in I$, si $f$ est dérivable en $a$, il existe un
$\text{DL}_{1}(a)$, et de même pour $g$ si elle est dérivable en $f(a)$.
Ainsi, pour $y = f(x)$, $g(f(x)) \underset{x \to a}{=} g(f(a)) + g'(f(a)) \times (f(x) - f(a)) + (f(x) - f(a)) \times \varepsilon_1(f(x))$.
Or, $f(x) - f(a) = f'(a) (x-a) + (x - a) \varepsilon(x)$, donc
$(g \circ f)(x) = (g \circ f)(a) + (g' \circ f)(a) \times f'(a) \times (x-a) + (x-a) \varepsilon(x) + (x-a)[f'(a) + \varepsilon(x)] \varepsilon_1(f(x))$.
Ainsi, $g \circ f$ admet un $\text{DL}_{1}(a)$, et est donc dérivable en $a$.
Son nombre dérivé est le coefficient devant $(x-a)$.

> $(\mathcal{C}^{n}(I,\mathbb{R}), +, \times)$ et $(\mathcal{C}^{\infty}(I,\mathbb{R}), +, \times)$ sont des anneaux.

Ainsi, on conserve ces classes par combinaison linéaire. De plus, la dérivée
d'une combinaison linéaire est la combinaison linéaire des dérivées (morphisme
d'espace vectoriel), et on a la formule de Leibniz pour la multiplication :
$(f \times g)^{(n)} = \sum\limits_{k = 0}^{n} \binom{n}{k} f^{(k)} \times g^{(n-k)}$.

> Si $f$ est $\mathcal{C}^n$ et $g \in \mathcal{C^n}$ et ne s'annule pas, alors
> $\frac{f}{g} \in \mathcal{C}^n$.

> Si $f$ est $\mathcal{C}^n(I,\mathbb{R})$ et $g \in \mathcal{C}^n(J,\mathbb{R})$,
> avec $f(I) \subset J$, alors $g \circ f \in \mathcal{C}^n(I,\mathbb{R})$.

##### Exercice
Soit $\varphi \in \mathcal{C}^{\infty}(\mathbb{R},\mathbb{R})$ et
$f: I \to \mathbb{R}$ telle que
$\forall x \in I, f'(x) = \varphi(f(x))$. Montrer que si $f$ est solution,
alors $f$ est $\mathcal{C}^{\infty}$.

On a déjà $f$ dérivable sur $I$, or $\varphi$ est dérivable, donc $\varphi \circ f$
est dérivable, donc $f'$ est dérivable, et on itère le raisonnement.

#### Dérivée de la réciproque
> Soit $f: I \to J$ une bijection dérivable et si $f'$ ne s'annule pas sur $I$,
> alors $f^{-1}: J \to I$ est une bijection dérivable et
> $(f^{-1})' = \frac{1}{f' \circ f^{-1}}$.

Ainsi, si $f$ est une bijection $\mathcal{C}^n$ sur $I$,
et $f'$ ne s'annule pas sur $I,$ alors $f^{-1}$ est une bijection $\mathcal{C}^n$
sur $J$.

## Théorème de Rolle et accroissements finis
### Extremum local
> Soit $f: i \to \mathbb{R}$ et $a \in I$, $f$ admet un maximum local sur si
> $\exists \nu > 0 \mid f\restriction_{I \cap [a - \nu; a + \nu]}$
> possède un maximum en $a$.

On réécrit cette propriété comme $\exists \nu > 0, \forall x \in I, |x - a| \leq \nu \Rightarrow f(x) \leq f(a)$.

On définit de même les minimums locaux. Les maximums et minimums locaux
constituent ensemble des extremums locaux.

> Soit $f: I \to \mathbb{R}$ et $a \in I$ un point intérieur de $I$,
> si $f$ est dérivable en $a$ et si $f$ admet un extremum local en $a$, alors
> $f'(a) = 0$.

__Preuve :__ On suppose que $f$ admette un maximum local en $a$.
$\exists \nu > 0, \forall x \in [a - \nu; a + \nu] \cap I, f(x) \leq f(a)$.
Comme $a$ est un point intérieur de $I$, $\exists \nu' < \nu, [a - \nu'; a + \nu'] \subset I$.
Ainsi, $\forall x \in [a - \nu', a + \nu'], f(x) \leq f(a)$.
Or, $f$ est dérivable en $a$, donc $\lim\limits_{x \to a^{+}} \frac{f(x) - f(a)}{x - a} = f'(a)$,
or $\left\{\begin{matrix} f(x) - f(a) \leq 0 \\ x - a > 0 \end{matrix}\right.$,
donc $\forall x \in ]a, a + \nu']$, $\frac{f(x) - f(a)}{x - a} \leq 0$,
à la lime quand $x \to a^{+}, f'(a) \leq 0$.
De même à gauche, $\forall x \in [a - \nu', a[$, $f'(a) \geq 0$, donc $f'(a) = 0$,
et $a \in I$ est un point intérieur de $I$.

### Théorème/Lemme de Rolle
> Soit $f$ continue sur $[a,b]$ à valeurs dans $\mathbb{R}$ et dérivable sur
> $]a,b[$. Si $f(a) = f(b)$, alors $\exists c \in ]a,b[, f'(c) = 0$.

__Preuve :__ $f$ continue sur le segment $[a,b]$, donc par compacité, $f$ admet
des extrema atteints : $\exists c,d \in [a,b], \forall x \in [a,b], f(c) \leq f(x) \leq f(d)$.
- Soit $c$ et $d$ sont aux extrémités de $[a,b]$, alors $f(c) = f(a) = f(b) = f(d)$,
  donc $f$ est constante sur $[a,b]$, donc $f'$ est nulle sur $]a,b[$, donc
  toute valeur $c \in ]a,b[$ convient.
- Soit $c$ et $d$ ne sont pas des extrémités de $[a,b]$, donc il existe un
  extremum en un point intérieur de $]a,b[$ là où $f$ est dérivable, donc $f'$
  s'annule en ce point intérieur dans $]a,b[$ (par le théorème précédent).

##### Exercice
Soit $f$ une fonction $n$ fois dérivable sur un intervalle $I$, telle que $f$
s'annule en $n + 1$ points distincts. On cherche à montrer que $f^{(n)}$
s'annule.

On sélectionne l'hypothèse de récurrence $H_k$ que $f^{(k)}$ s'annule $n + 1 - k$ fois.
On procède par récurrence sur $k \in [\![0,n]\!]$, et $H_0$ est vraie.
Pour $H_k$ vraie, on prend les $x_i$ les points d'annulation de $f^{(k)}$. Pour
tout $i \in [\![0, n - k - 1]\!]$, on applique le théorème de Rolle à
$f^{(k)}$ (dérivable une fois car $k < n$) sur le segment $[x_i, x_{i + 1}]$,
car $f^{(k)}(x_i) = f^{(k)}(x_{i + 1}) = 0$. On a donc bien $H_{k + 1}$
vérifiée.

### Théorème des accroissements finis
> Soit $f$ continue sur $[a,b]$ à valeur dans $\mathbb{R}$ et dérivable sur
> $]a,b[$, il existe $c \in ]a,b[ \mid f'(c) = \frac{f(b) - f(a)}{b - a}$.

__Preuve :__ On pose $g: x \mapsto f(x) - (x - a) \frac{f(b) - f(a)}{b - a}$.
Ainsi, $g(a) = f(a)$ et $g(b) = f(a)$, donc par lemme de Rolle, puisque $g$ est
continue sur $[a,b]$, donc sur $]a,b[$, $\exists c \in ]a,b[, g'(c) = 0$.
Or, $g'(x) = f'(x) - \frac{f(b) - f(a)}{b - a}$, d'où
$f'(c) = \frac{f(b) - f(a)}{b - a}$.

### Inégalité des accroissements finis
> Soit $f: I \to \mathbb{R}$ dérivable telle que $\exists m,M \in \mathbb{R}, \forall x \in I, m \leq f'(x) \leq M$,
> alors pour tout $a,b \in I$ avec $a < b$, on a $m (b - a) \leq f(b) - f(a) \leq M (b - a)$.

__Preuve :__ Par le théorème des accroissements finis sur $[a,b]$,
$\exists c \in ]a,b[, f'(c) = \frac{f(b) - f(a)}{b - a}$,
or $m \leq f'(c) \leq M$, d'où le résultat.

__Corollaire :__ Si $f$ est dérivable sur $I$ et si $f'$ est bornée sur $I$,
alors $f$ est lipschitzienne sur $I$. En détail, $\exists K > 0$,
$\forall x \in I, |f'(x)| \leq K$.

On a alors $\forall (a,b) \in I^2, |f(b) - f(a)| \leq K \times |b - a|$,
et $f$ est $K$-lipschitzienne.

Avec $K_0 = \text{sup}_I |f'|$, sous réserve d'avoir $f'$ bornée sur $I$,
on a $\forall x \in I, |f'(x)| \leq K_0$, donc $f$ est $K_0$-lipschitzienne.
On note alors $\text{sup}_I |f'| = \| f' \\restriction_{\infty}$.

## Conséquences du T.A.F.
### Fonctions dérivables monotones
> Soit $f: I \to \mathbb{R}$ dérivable :
> 1. $f$ est croissante sur $I$ si et seulement si $f'$ est positive sur I
> 2. $f$ est décroissante sur $I$ si et seulement si $f'$ est négative sur I

__Preuve :__ Dans le second cas, on applique juste le premier cas à $-f$.\
$\Rightarrow$ Soi t $a \in I$, $\forall x \in ]a;a + \nu] \cap I, \left\{\begin{matrix} f(a) \leq f(x) \\ a \leq x \end{matrix}\right.$,
donc $\frac{f(x) - f(a)}{x - a} \geq 0$, donc pour $x \to a^{+}$, $f'(a) \geq 0$.\
$\Leftarrow$ Soient $a,b \in I$ avec $a < b$. $f$ est continue sur $[a;b]$,
dérivable sur $]a,b[$, donc avec le TAF
$\exists c \in ]a,b[, \frac{f(b) - f(a)}{b - a} = f'(c)$,
or $f'(c) \geq 0$ et $b - a \geq 0$, donc $f(a) \leq f(b)$,
donc $f$ est croissante sur $I$.

__Corollaire :__ Si $f' > 0$ alors $f$ est strictement croissante,
et si $f' < 0$ alors $f$ est strictement décroissante.

__Preuve :__ On applique la preuve précédente avec $f'(c) > 0$ ou $< 0$.

> Soit $f: I \to \mathbb{R}$ dérivable, si $f' \geq 0$ sur $I$, et $f'$
> s'annule un nombre fini de fois sur $I$, alors $f$ est strictement croissante.

__Preuve :__ On applique le résultat précédent sur chaque intervalle $J$ où $f' > 0$.

### Étude d'une suite récurrente
Soit $\forall n \in \mathbb{N}, \left\{\begin{matrix} u_0 = 0 \\ u_{n+1} = \exp(\frac{-1}{2} u_n^2) \end{matrix}\right.$.
On étudie $(u_n)_n$, avec la fonction $\begin{aligned} f: \mathbb{R} &\to \mathbb{R} \\ x &\mapsto f(x) = \exp(\frac{-x^2}{2}) .\end{aligned}$,
donnant bien $\forall n \in \mathbb{N}, u_{n+1} = f(u_n)$. Ainsi, si $(u_n)_n$
converge vers $\ell$, et comme $f$ est continue, on aurait $f(\ell) = \ell$.
On peut montrer par le TVI et la stricte monotonie de $f$ que
$e^{\frac{-x^2}{2}} = x$ admet une unique solution $\ell \in ]0,1[$. De plus,
$f(\mathbb{R}) \subset ]0,1]$, donc $\forall n \in \mathbb{N}, u_n \in ]0,1]$,
donc $(u_n)$ est bornée.

$\forall x \in \mathbb{R}, f'(x) = -x e^{\frac{-x^2}{2}}$, on veut borner
$|f'|$ sur $[0,1]$, et montrer que $f$ est $k$-lipschitzienne avec $k < 1$.
$\forall x \in [0,1], e^{\frac{-x^2}{2}} \leq 1$, donc $|f'(x)| \leq |x| \leq 1$.
On a $f([0;1]) \subset [e^{\frac{-1}{2}};1]$ et $f([e^{\frac{-1}{2}};1]) \subset [e^{\frac{-1}{2}};1]$.
Donc $\forall n \geq 2, u_n \in [e^{\frac{-1}{2}}]$.

Ainsi, $k = e^{\frac{-1}{2} e^{-1}}$ tel que $\forall x \in [e^{\frac{-1}{2}};1], |f'(x)| \leq k$.
Par inégalité des accroissements finis, $f$ est $k$-lipschitzienne sur $[e^{\frac{-1}{2}};1]$.
Avec $n \geq 2, u_{n} \in [e^{\frac{-1}{2}};1]$, on l'applique avec $u_{n}$ et
$\ell$, donnant $\forall n \geq 2, |f(u_{n}) - f(\ell)| \leq k |u_{n} - \ell|$
$\Leftrightarrow \forall n \geq 2, |u_{n + 1} - \ell| \leq k |u_{n} - \ell|$.
Par récurrence, on peut alors montrer que $\forall n \geq 2, |u_{n} - \ell| \leq k^{n-2} |u_2 - \ell|$,
donc que comme $k^{n-2} \xrightarrow[n \to \infty]{} 0$, $(u_{n})_n$ converge
vers $\ell$.

### Théorème de la limite de la dérivée
> Soit $f: I \to \mathbb{R}$, avec $a \in I$. On suppose $f$ continue sur $I$ et
> $f$ dérivable sur $I \setminus \{a\}$. Si $\lim\limits_{x \to a} f'(x) = \ell$
> avec $\ell \in \overline{\mathbb{R}}$, alors :
> 1. si $\ell \in \mathbb{R}$, alors $f$ est dérivable en $a$ et $f'(a) = \ell$
> 1. si $\ell = \pm \infty$, alors $f$ n'est pas dérivable en $a$ (tangente
>    verticale en $a$)

Si $\ell$ est finie, on a $\lim\limits_{x \to a} f'(x) = \ell = f'(a)$, donc $f'$ est continue en $a$,
soit $f \in \mathcal{C}^1$ en $a$.

__Preuve :__ On a $f'(x) \xrightarrow[x \to a]{} \ell \in \overline{\mathbb{R}}$, et donc
pour $x \in I \setminus \{a\}$ :
- si $x > a$, $f$ est continue sur $[a,x]$ et est dérivable sur $]a,x[$. Ainsi,
  le théorème des accroissement finis donne $\exists c_x \in ]a,x[, f'(c_x) = \frac{f(x) - f(a)}{x - a}$.
  Si $x \to a^{+}$, comme $a < c_x < x$, alors $\lim\limits_{x \to a^{+}} c_x = a$.
  Par composition, $\lim\limits_{x \to a^{+}} f'(c_x) = \ell$, donc le taux d'accroissement
  est de limite finie.
- si $x < a$, on procède de même.

> Théorème de prolongement $\mathcal{C}^1$ : Soit $f: I \setminus \{a\} \to \mathbb{R}$
> avec $a \in I$, on suppose $f$ de classe $\mathcal{C}^1$ sur
> $I \setminus \{a\}$. Si $f(x) \xrightarrow[x \to a]{} \ell_0 \in \mathbb{R}$
> et si $f'(x) \xrightarrow[x \to a]{} \ell_1 \in \mathbb{R}$, alors $f$ se
> prolonge par continuité sur $I$ en posant $f(a) = \ell_0$, et ce prolongement
> est $\mathcal{C}^1$ sur $I$ avec $f'(a) = \ell_1$.

__Preuve :__ $\begin{aligned} \tilde{f}: I &\to \mathbb{R} \\ x &\mapsto \tilde{f}(x) = \left\{\begin{matrix} f(x) \text{ si } x \neq a \\ \ell_0 \text{ si } x = a \end{matrix}\right. .\end{aligned}$.
$\tilde{f}$ est alors continue sur $I$, et donc $\tilde{f}$ vérifie les
conditions du théorème précédent, et est donc dérivable en $a$ et $\tilde{f}''(a) = \ell_1$.
Ainsi, $\tilde{f}$ est $\mathcal{C}^1$ en $a$, donc $\mathcal{C}^1$ sur $I$.

> Théorème de prolongement $\mathcal{C}^n$ : Soit $f: I \setminus \{a\} \to \mathbb{R}$
> avec $a \in I$, on suppose $f$ de classe $\mathcal{C}^n$ sur
> $I \setminus \{a\}$.
> Si pour chaque $i \in [\![0,n]\!]$, $f^{(i)}$ admet une limite finie $\ell_i$ en
> $a$, alors en prolongeant $f$ par continuité en posant $f(a) = \ell_0$,
> on obtient une fonction $f$ de classe $\mathcal{C}^n$ sur $I$, avec
> $\forall i, f^{(i)}(a) = \ell_i$.

__Preuve :__ On procède par récurrence sur $n$. En $n = 0$, on utilise le
théorème de prolongement par continuité. Pour tout $n$ avec la propriété vraie,
soit $f \in \mathcal{C}^{n+1}$ sur $I \setminus \{a\}$ tel que
$\forall i \in [\![0,n+1]\!], f^{(i)} \xrightarrow[a]{} \ell_i \in \mathbb{R}$.
On prolonge $f$ par continuité en posant $f(a) = \ell_0$. Le rang $n$ prouve que
$f$ est $\mathcal{C}^n$ sur $I$ et $\forall i \in [\![0,n]\!], f^{(i)}(a) = \ell_i$.
Or, $f^{(n)}$ est continue sur $I$, et est donc $\mathcal{C}^1$ sur $I \setminus \{a\}$,
et $(f^{(n)})' = f^{(n+1)} \xrightarrow[a]{} \ell_{n+1}$. On peut appliquer le
théorème de prolongement $\mathcal{C}^1$ sur $f^{(n)}$. Ainsi,
$f$ devient $\mathcal{C}^{n+1}$ sur $I$ et $f^{(n+1)}(a) = \ell_{n+1}$.

On rappelle que si $f$ est $\mathcal{C}^n$ en $a$, alors $f$ admet un $\text{DL}_{n}(a)$, local en $a$.
On a ainsi les formules de Taylor-Young et de Taylor avec reste intégral :
$\forall x \in I, f(x) = \sum\limits_{k = 0}^{n} \frac{f^{(k)}(a)}{k!} (x - a)^k + \int\limits_{a}^{x} \frac{(x-t)^n}{n!} f^{(n+1)}(t) dt$.
On peut aussi exprimer l'inégalité de Taylor-Lagrange.

> Taylor-Lagrange : Soit $f \in \mathcal{C}^{n + 1}(I, \mathbb{K})$, avec $f^{(n+1)}$ bornée sur $I$.
> Soit $a \in I$ et $x \in I$,
> $|f(x) - \sum\limits_{k = 0}^{n} \frac{f^{(k)}(a)}{k!} (x - a)^k| \leq \frac{|x - a|^{n+1}}{(n+1)!} \text{sup}\restriction_{I} |f^{(n+1)}|$.

Avec $a,x \in I$ avec $a < x$, on reprend le reste intégral.
$f^{(n+1)}$ est continue sur le segment $[a,x]$ donc
$|f^{(n+1)}|$ atteint son maximum sur $[a,x]$, qu'on note $M_{n+1}$.
$\forall t \in [0,x]$, $|f^{(n+1)}(t)| \leq M_{n+1}$. Ainsi, $x - t > 0$
par croissance de l'intégrale sur les termes positifs, donnant
$|\int\limits_{a}^{x} \frac{(x-t)^n}{n!} f^{(n+1)}(t) dt| \leq \int\limits_{a}^{x} \frac{(x - t)^n}{n!} M_{n+1} dt$
par inégalité triangulaire. Ce second membre est égal à
$[\frac{- (x - t)^{n+1}}{(n+1)!}]_a^x M_{n+1} = \frac{(x - a)^{n+1}}{(n+1)!} M_{n+1}$, la majoration du reste intégral.

##### Exemples
Soit $x \in \mathbb{R}$ fixé et $a = 0$, $\exp$ est $\mathcal{C}^{\infty}$ sur
$\mathbb{R}$. L'inégalité de Taylor-Lagrange donne :
$\forall n \in \mathbb{N}, |e^{x} - \sum\limits_{k = 0}^{n} \frac{e^{k}(0)}{k!} x^k| \leq \frac{|x|^{n+1}}{(n+1)!} \text{sup}\restriction_{[0,x]} |e^{n+1}|$.\
$\forall x \leq 0, e^{x} \leq 1$ et $\forall x > 0, \forall t \in [0,x], e^{t} \leq e^{x}$.
Avec $x \in \mathbb{R}$ fixé, $\text{sup}\restriction_{[0,x]} \exp \leq \text{max}(1,e^{x})$.
Finalement, à $x$ fixé, $\forall n \in \mathbb{N}, |e^{x} - \sum\limits_{k = 0}^{n} \frac{x^k}{k!}| \leq \frac{|x|^{n+1}}{(n+1)!} \text{max}(1,e^{x})$.\
Or,  $x^{n+1} \underset{n \to +\infty}{=} o((n+1)!)$,
$\lim\limits_{n \to + \infty} \frac{|x|^{n+1}}{(n+1)!} \text{max}(1, e^{x}) = 0$, donc
par théorème d'encadrement,
$\lim\limits_{n \to + \infty} (\sum\limits_{k = 0}^{n} \frac{x^k}{k!}) = e^{x}$
pour $x \in \mathbb{R}$.
