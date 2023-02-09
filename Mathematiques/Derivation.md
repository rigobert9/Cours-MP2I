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
