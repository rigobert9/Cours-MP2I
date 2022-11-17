# Équations différentielles linéaires
Soit $\mathbb{K}$ qui soit $\mathbb{R}$ ou $\mathbb{C}$, et
$I$ un intervalle d'intérieur non vide de $\mathbb{R}$, on utilisera des
fonctions de $I$ dans $\mathbb{K}$.

> Une équation différentielle d'ordre $n$ est une équation $(E)$ dont
> l'inconnue est une fonction $x \mapsto y(x)$ et qui fait intervenir
> $y$, $y'$ ... $y^{(n)}$.

> Une solution de $(E)$ sur $I$ est une fonction $f: I \to \mathbb{K}$ telle que
> $f$ est $n$ fois dérivable en $I$ et pour tout $x \in I$, l'équation $(E)$
> est vérifiée avec $f(x)$, $f'(x)$ ... $f^{(n)}(x)$.

##### Exemple
$(E) xy' = y(y + 1) + x^2$ (équadiff d'ordre 1 et d'inconnue y).

On vérifie que $f: ]\frac{-\pi}{2};\frac{\pi}{2}[ \to \mathbb{R}$ telle que
$x \mapsto x \tan(x)$ est solution de $(E)$ sur $]\frac{-\pi}{2};\frac{\pi}{2}[$.
$f$ est bien dérivable sur l'intervalle et $\forall x \in I, f'(x) = \tan(x) + x(1 + \tan^2(x))$.
Ainsi, $x f'(x) = x \tan(x) + x^2 + x^2 \tan^2(x) = x \tan(x) [1 + x \tan(x) + x^2]$
$= f(x) [1 + f(x)] x^2$. $f$ est donc bien solution de l'équadiff sur $I$.

#### Limites du chapitre
On se restreindra dans ce chapitre à :
- Des équations différentielles d'ordre 1 (dans leur cas général)
- Des équations différentielles d'ordre 2 à coefficients constants

## Équation différentielle d'ordre 1
> Soient $\alpha, \beta, \gamma \in \mathcal{C}(I, \mathbb{K})$ fixées, on a une
> toute équation différentielle d'ordre 1 de la forme $\alpha y' + \beta y = \gamma$,
> c'est-à-dire $\forall x \in I, \alpha(x) y'(x) + \beta(x) y(x) = \gamma(x)$.

Pour résoudre cette équation, on procède selon deux cas :
- Si la fonction $\alpha$ ne s'annule pas sur l'intervalle $I$,
  $(E)$ se réécrit $y' + \frac{\beta}{\alpha} y = \frac{\gamma}{\alpha}$
  (ces quotients de fonction restant ainsi continus sur $I$).
  Cette forme est la forme dite normalisée ou réduite, sous la forme
  $y' + ay = b$ avec $a,b \in \mathcal{C}(I,\mathbb{K})$.
- Si $\alpha$ s'annule, on fera cette même étude sur chaque intervalle où $\alpha$ ne s'annule pas

#### Vocabulaire
On appelle $b$ le second membre de l'équation différentielle. Si $b$ est la
fonction nulle, l'équation est dite homogène : $y' + ay = 0$.
$f$ est solution de $(E)$ sur $I$ si et seulement si $f$ est dérivable sur $I$
et $f$ satisfait l'équation différentielle pour tout $x \in I$.

## Structure des solutions
> On note $S_H$ l'ensemble des solutions de l'équation homogène $(H)$
> $y' + ay = 0$.
> $S_H$ vérifie les propriétés suivantes :
> - $\tilde{0} \in S_H$ (la fonction nulle)
> - $\forall (f_1,f_2) \in S_H^2, \forall (\lambda,\mu) \in \mathbb{K}^2, \lambda f_1 + \mu f_2 \in S_H$
>   (stabilité par combinaison linéaire).

$S_H$ est ainsi un espace vectoriel, comme on le verra plus tard dans l'année.

##### Preuve
- $\begin{aligned} \tilde{0}: I &\to \mathbb{K} \\ x &\mapsto \tilde{0}(x) = 0 .\end{aligned}$ vérifie $(H)$
- Soit $(\lambda,\mu) \in \mathbb{K}^2$, soit $(f_1, f_2) \in S_H^2$, on a déjà
  $f_1$ et $f_2$ dérivables sur $I$, et $f_1' + af_1 = 0$ et $f_2' + af_2 = 0$.
  De plus, $\lambda f_1 + \mu f_2$ est dérivable sur $I$ et
  $(\lambda f_1 + \mu f_2)' = \lambda f_1' + \mu f_2'$.
  Ainsi, $(\lambda f_1 + \mu f_2)' + a (\lambda f_1 + \mu f_2) = 0$.

### Solutions à l'aide de la solution particulière
> Soit $f_p \in S_E$ une solution particulière de $(E)$, alors
> $S_E = f_p + S_H = \{f_p + h \mid h \in S_H\}$.

On verra que $S_E$ est un espace affine.

##### Preuve
$S_E = \{y \mid y' + ay = b\}$ et $S_H = \{y \mid y' + ay = 0\}$.
On procède à une double inclusion :
- $f_p + S_H \subset S_E$ ?\
  Soit $h \in S_H$ et $f_p \in S_E$, alors $(f_p + h)' + a(f_p + h)$
  $= (f_p' + a f_p) + (h' + ah) = b$ (donc bien dans $S_E$)
- Autre sens ?\
  Soit $f \in S_E$, regardons $f - f_p$ : $(f - f_p)' + a(f-f_p)$
  $= (f' + af) - (f_p' + a f_p) = 0$, donc $f - f_p \in S_H$.
  Ainsi $f = f_p + (f - f_p)$, et donc
  $\exists h \in S_H, f = f_p + h$, soit $S_E \in f_p + S_H$.

On peut ainsi résoudre $(E): y' + ay = b$ en trouvant $S_H$ toutes les solutions
de $(H): y' + ay = 0$, puis en trouvant $f_p$ une solution particulière de
$(E)$.

### Solutions de $(H)$
> Soit $a \in \mathcal{C}(I,\mathbb{K})$, l'ensemble des solutions de $(H) : y' + ay = 0$
> est $S_H = \{\begin{aligned} I &\to \mathbb{K} \\ x &\mapsto \lambda \exp(-A(x)) .\end{aligned}, \lambda \in \mathbb{K}\}$,
> où $A$ est une primitive de $a$ sur $I$.

Comme $a \in \mathcal{C}(I,\mathbb{K})$, on fixe $x_0 \in I$ et on peut prendre
$\begin{aligned} A: I &\to \mathbb{K} \\ x &\mapsto A(x) = \int\limits_{x_0}^{x} a(t) dt .\end{aligned}$.

##### Preuve
Soit $\varphi$ une fonction dérivables sur $I$, on pose $g = \exp \circ \varphi$,
et alors $g' = \varphi' \times \exp \circ \varphi = \varphi' \times g$.
$g$ est donc solution de $(H)$ si et seulement si $g' + ag = 0$
si et seulement si $(\varphi' + a) \times g = 0$ (or g ne s'annule jamais sur $I$)
si et seulement si $\varphi' + a = 0$ si et seulement si $\varphi' = -a$
si et seulement si $\varphi$ est une primitive de $(-a)$ sur $I$.

Ainsi, toute fonction de la forme $x \mapsto \exp(-A(x))$ est solution de $(H)$.
Par propriété de $S_H$, si $f \in S_H$, alors $\lambda f \in S_H$ pour tout
$\lambda \in \mathbb{K}$, et ainsi
$\{x \mapsto \lambda \exp(-A(x)), \lambda \in \mathbb{K}\} \subset S_H$.

Réciproquement, soit $f \in S_H$, on calcule $\alpha : x \mapsto f(x) \times \exp(A(x))$,
alors $\alpha' = f'(x) \times (\exp \circ A) + a \times f \times \exp \circ A$
$= (f' + af) \times \exp \circ A = 0$, soit $\alpha$ une constante sur $I$.

Ainsi $f: x \mapsto \alpha \times \exp(-A(x))$, où $\alpha$ est une constante.

##### Cas usuel en physique
On obtient l'équadiff $y' + ay = 0$ avec $a \in \mathbb{K}$ une constante.
L'ensemble des solutions est $S_H = \{x \mapsto \lambda e^{-ax}, \lambda \in \mathbb{K}\}$.

__Exemple :__ $(H_1)$ Soit $\alpha \in \mathbb{R}$, $y' + \frac{\alpha}{x} y = 0$.
On se place sur l'intervalle $\mathbb{R}^{\ast}_{-}$ ou sur $\mathbb{R}^{\ast}_{+}$
là où $a: x \mapsto \frac{\alpha}{x}$ est continue.
On pendre *une* primitive de $a$,
$A: x \mapsto \alpha \ln |x|$, et ainsi
$S_H = \{\begin{aligned} I &\to \mathbb{R} \\ x &\mapsto \lambda \exp(-\alpha \ln |x|) .\end{aligned}, \lambda \in \mathbb{R}\}$.
Or, $\lambda e^{-\alpha \ln |x|} = \frac{\lambda}{e^{\ln(|x|^\alpha)}} = \frac{\lambda}{|x|^\alpha}$.

Sur $\mathbb{R}^{\ast}_{+}$, les solutions sont $x \mapsto \frac{\lambda}{x^\alpha}, \lambda \in \mathbb{R}$
Sur $\mathbb{R}^{\ast}_{+}$, les solutions sont $x \mapsto \frac{\lambda}{(-x)^\alpha}, \lambda \in \mathbb{R}$

### Recherche d'une solution particulière de $(E)$
$(E) y' + ay = b$, on cherche $f_p \in S_E$ (une seule suffira).

#### Méthode 1 : second membre constant
On devine une solution constante :
$(E) y' + ay = b$, avec $(a,b) \in \mathbb{R}_{+}^2$.
$y: x \mapsto \frac{b}{a}$ est une solution constante évidente
en $y' = 0$.

#### Méthode 1 bis : Electrical Boogaloo
On devine une solution particulière "évidente", par exemple
$(E) \sin(t)y'(t) - \cos(t)y(t) = 1$. On se place sur
$I = ]0, \pi[$. On a
$(H) y' - \frac{\cos(t)}{\sin(t)} y(t) = 0$,
or $\int \frac{-\cos(t)}{\sin(t)} dt = -\ln(|\sin t|)$.
Ainsi, $S_H = \{t \mapsto \lambda \exp(+ \ln(\sin(t))), \lambda \in \mathbb{R}\}$
$= \{t \mapsto \lambda \sin(t), \lambda \in \mathbb{R}\}$.

On cherche alors la solution $f_p$ pour $(E)$. On devine $f_p(t) = -\cos(t)$,
soit $f_p'(t) = +\sin(t)$ en $\sin^2(t) + \cos^2(t) = 1$ donc $f_p \in S_E$.
On a donc sur $]0;\pi[$ $S_E = \{t \mapsto \lambda \sin(t) - \cos(t), \lambda \in \mathbb{R}\}$.

#### Méthode 2 : variation de la constante
Lors de l'étude de $S_H$, on a les solutions $S_H = \{x \mapsto \lambda \exp(-A(x)), \lambda \in \mathbb{R}\}$.
On pose $h(x) = \exp(-A(x))$.
On va rechercher une fonction $f_p$ de la forme $f_p = \lambda d$ où
$\lambda$ est une fonction dérivable sur $I$.

Ainsi $f_p' = \lambda'h + h\lambda'$, et $f_p$ est solution de $(E)$
si et seulement si $f_p' + af_p = b$
$\Leftrightarrow (\lambda' h + \lambda h') + a \lambda h = b$
$\Leftrightarrow \lambda' h + \lambda (h' + a h) = b$
$\Leftrightarrow \lambda'  \times h = b$
$\Leftrightarrow \lambda' = \frac{b}{h}$ (avec $h = \exp \circ (-A)$ ne
s'annulant jamais).

$\frac{b}{h}$ étant continue sur $I$, $\frac{b}{h}$ admet des primitives sur
$I$.
Ainsi, $\lambda(x) = \int\limits_{?}^{x} \frac{b(t)}{h(t)} dt$ (à une constante
additive près).

#### Cas général
$(E) y' + ay = b$ avec $a,b \in \mathcal{I,\mathbb{K}}$,
$S_E = \{x \mapsto (\lambda + \int\limits_{?}^{x} \frac{b(t)}{h(t)}) \times \exp(- \int\limits_{?}^{x} a(t) dt), \lambda \in \mathbb{R}\}$.

#### Méthode 3 : Principe de superposition
> Si $f_1$ est solution de $(E_1) : y' + a(x) y = b_1(x)$ et $f_2$ est solution
> de $(E_2) : y' + a(x) y = b_2(x)$, alors pour tout $(\lambda,\mu) \in \mathbb{K}^2$,
> la fonction $\lambda f_1 + \mu f_2$ est solution de
> $y' + a(x)y = \lambda b_1(x) + \mu b_2(x)$.

##### Preuve
$(\lambda f_1 + \mu f_2)' + a(x)(\lambda f_1 + \mu f_2)$\
$= \lambda f_1' + \mu f_2' + a(x)(\lambda f_1 + \mu f_2)$\
$= \lambda (f_1' + a(x)f_1) + \mu (f_2' + a(x) f_2)$

##### Exemple
On cherche à résoudre $(E) : y' + y = e^{t} + 3t^2 + t^3 + 4$. On obtient les
solutions homogènes de $(H) : y' + y = 0$ telles que $S_H = \{t \mapsto \lambda e^{-t}, \lambda \in \mathbb{R}\}$.

On cherche maintenant une solution particulière, avec $(E_1) y'+y = e^{t}$ qui a
pour solution évidente $f_1 : t \mapsto \frac{1}{2} e^{t}$, $(E_2) : y' + y = t^2$ qui
a pour solution $f_2 : t \mapsto t^2 - 2t + 2$, $(E_3) : y' + y = 4$ avec pour
solution $f_3 : t \mapsto 4$, et enfin $(E_4) : y' + y = t^3$ avec pour solution
$f_4 : t \mapsto t^3 - 3t^2 + 6t - 6$; on obtient donc la solution particulière
$f_1 + 3f_2 + f_3 + f_4$.

#### Méthode 4 : Cas où $a$ est une fonction constante
Soit $(E) : y' + ay = b(t)$ où $a \in \mathbb{R}^{\ast}$, on obtient les
solutions homogènes de $(H) : y' + ay = 0$, $S_H = \{t \mapsto \lambda e^{-t}, \lambda \in \mathbb{R}\}$.

La solution particulière dépend de la forme du second membre $b$ :
- si $b$ est polynomial, on cherchera $f_p$ sous forme polynomiale
- si $b$ est de la forme "polynôme $\times$ exponentielle" : $b : t \mapsto P(t) e^{\alpha t}$,
  on cherche $f_p$ sous la forme $f_p(t) = Q(t) e^{\alpha t}$ où P et Q sont
  polynomiaux
- si b est périodique, tel que $b(t) = A \cos(\omega t + \varphi) = \Re(Ae^{i\varphi} e^{i \omega t})$,
  on cherche $f_p$ sous la forme $B e^{i \omega t}$ (dans $\mathbb{C}$) ou encore
  $\alpha \cos(\omega t) + \beta \sin(\omega t)$ (dans $\mathbb{R}$).

On a d'ailleurs, si $f$ est solution de $y' + ay = e^{i\omega t}$ avec $a \in \mathbb{R}$,
$\Re(f)$ une solution de $y' + ay = \cos(\omega t)$ et
$\Im(f)$ une solution de $y' + ay = \sin(\omega t)$.

### Problème de Cauchy
> Soit $(x_0, y_0) \in I \times \mathbb{K}$, et $a,b \in \mathcal{C}(I,\mathbb{K})$,
> le problème de Cauchy
> $(C) \left\{\begin{matrix} y' + a(x) y = b(x) \\ y(x_0) = y_0 \end{matrix}\right.$
> possède une unique solution.

##### Preuve
$S_E = \{f_p + h, h \in S_H\}$ et $S_H = \{\lambda \exp(-A), \lambda \in \mathbb{K}\}$.
On pose $h_0 = \exp(-A)$ ne s'annulant pas sur $I$.
Ainsi, $S_E = \{f_p + \lambda h_0, \lambda \in \mathbb{K}\}$.

L'ajout de la condition $f(x_0) = y_0$ donne $f_p(x_0) + \lambda h_0(x_0) = y_0$,
donc $\lambda = \frac{1}{h_0(x_0)} (y_0 - f_p(x_0))$ ($h_0$ ne s'annulant pas),
nous donnant l'existence te l'unicité de la solution au problème de Cauchy
$(C)$.

### Équation non normalisée
On revient au cas général d'une équation différentielle d'ordre 1, de la forme
$\alpha(x) y'(x) + \beta(x) y(x) = \gamma(x)$.

Si la fonction $\alpha$ s'annule en un point $a$, on prendra $\alpha$, $\beta$
et $\gamma$ continues sur un intervalle $I$, et on résoudra l'équation
normalisée sur $I \cap ]a,+\infty[$ et sur $I \cap ]-\infty,a[$.
Pour pouvoir reconstruire des solutions sur $I$ tout entier, il faut que $f$
soit dérivable (et donc continue) sur $I$ tout entier (donc en $a$) et soit
solution sur les deux intersections.

Cette propriété pose la question du recollement en $a$, qui est une question
ouverte dans la généralité.

##### Exemple
Trouver (si elles existent) les solutions sur $\mathbb{R}$ de
$(E) : (1 - x)y' - y = x$. On pose $(E') : y' - \frac{1}{1 - x}y = \frac{x}{1 -x}$,
et on la résout sur $I = ]-\infty,a[$ ou sur $]a,+\infty[$.
On a $S_H = \{x \mapsto \lambda \exp(- \ln(|x - 1|)), \lambda \in \mathbb{R}\}$
$= \{x \mapsto \frac{\lambda}{x - 1}, \lambda \in \mathbb{R}\}$.

On trouve une solution particulière, qui sera nécessairement telle que
$(1 - x)(\frac{\lambda(x)'}{x - 1} - \frac{\lambda(x)}{(x - 1)^2}) - \frac{\lambda(x)}{x - 1} = x$,
et donc telle que $-\lambda(x)' = x$ pour tout $x \in I$. On choisit
$\lambda : x \mapsto \frac{-x^2}{2}$ et on obtient donc $f_p : x \mapsto \frac{-x^2}{2(x - 1)}$.
Ainsi, sur chaque intervalle $]-\infty,1[$ et $]1,+\infty[$, les solutions sur
$I$ sont $\{x \mapsto \frac{\lambda - \frac{x^2}{2}}{x - 1}, \lambda \in \mathbb{R}\}$.

Pour une solution $f$ de $(E)$ sur $\mathbb{R}$, alors
$\forall x \in \mathbb{R}, (1 - x)f'(x) - f(x) = x$ et
$f$ est dérivable sur $\mathbb{R}$. En particulier,
$f$ est solution sur $]-\infty,1[$ et $]1,+\infty[$. Il existe donc
$\lambda_1, \lambda_2 \in \mathbb{R}$ tels que
$\left\{\begin{matrix} \frac{\lambda_1 - \frac{x^2}{2}}{x - 1} \,\text{si x < 1} \\ \frac{\lambda_2 - \frac{x^2}{2}}{x - 1} \,\text{si x > 1} \end{matrix}\right.$.

On doit avoir $f$ continue et dérivable en 1. Or, si $\lambda_1 \neq \frac{1}{2}$, alors $\lim\limits_{x \to 1^{-}} \frac{\lambda_1 - \frac{x^2}{2}}{x - 1} = +\infty$.
Pour avoir la continuité en 1, on a donc nécessairement $\lambda_1 = \frac{1}{2}$.
De même à droite de 1, on a nécessairement $\lambda_2 = \frac{1}{2}$, nous
donnant finalement $\forall x \neq 1, f(x) = \frac{\frac{1}{2}(1 - x^2)}{x - 1} = \frac{-1}{2} (1 + x)$.

Par synthèse, on prend un $f: x \mapsto \frac{-1}{2} (x + 1)$. $f$ est dérivable
sur $\mathbb{R}$, et vérifie $(E)$ sur $]-\infty,1[$ et
$]1,+\infty[$, et aussi en 1 puisque
$(1-1)f'(1) - f(1) = 0$.

Ainsi, $(E)$ possède une unique solution sur $\mathbb{R}$
$x \mapsto \frac{-1}{2} (x + 1)$.

##### Exemple
On cherche les solutions sur $\mathbb{R}$ de $(E): x y' - 2 y = 0$.
On a déjà l'équation homogène, et on la réécrit sous la forme
$(E'): y' - \frac{2}{x}y = 0$, sur les intervalles
$\mathbb{R}^{\ast}_{+}$ et $\mathbb{R}^{\ast}_{-}$.
Or, $\int \frac{-2}{x} dx = -2 \ln(|x|)$, soit
$S_E = \{x \mapsto \lambda \exp(2 \ln |x|), \lambda \in \mathbb{R}\}$
$= \{x \mapsto \lambda x^2, \lambda \in \mathbb{R}\}$.

Pour trouver un recollement en 0, on cherche $f$ solution de (E) sur
$\mathbb{R}$ (donc solution sur $\mathbb{R}^{\ast}_{+}$ et $\mathbb{R}^{\ast}_{-}$),
soit une solution telle que
$\exists \lambda,\mu \in \mathbb{R}, \forall x \in \mathbb{R}^{\ast}, f(x) = \left\{\begin{matrix} \lambda x^2 \,\text{si x > 0} \\ \mu x^2 \,\text{si x < 0} \end{matrix}\right.$.

Par synthèse, pour chaque $(\lambda,\mu) \in \mathbb{R}^2$, en posant un
$f$ tel que précédemment décrit, on a bien
$\lim\limits_{x \to 0^{+}} f = \lim\limits_{x \to 0^{-}} f = 0 = f(x)$
(continuité de $f$ en 0), et
$\lim\limits_{x \to 0^{+}} \frac{f(x)}{x} = 0 = \lim\limits_{x \to 0^{-}} \frac{f(x)}{x}$,
soit $f$ dérivable en $0$.

Il existe donc une infinité de solutions de $(E)$ sur $\mathbb{R}$,
avec deux paramètres.

## Équations différentielles du second ordre à coefficients constants
### Définition
> Une équation différentielle linéaire d'ordre 2 à coefficients constants est de
> la forme $(E): y'' + ay' + by = c(x)$, avec $a, b \in \mathbb{K}$ et
> $c \in \mathcal{C}(I,\mathbb{K})$ où $I$ est un intervalle de $\mathbb{R}$.

Une solution de $(E)$ est alors une fonction $f: I \to \mathbb{K}$ telle que
$f$ est deux fois dérivable sur $I$ et
$\forall x \in I, f''(x) + a f'(x) + b f(x) = c(x)$.

Pour trouver des solutions, on utilise l'équation homogène associée
$(H): y'' + ay' + by = 0$ et l'équation caractéristique
$(EC) : r^2 + ar + b = 0$.

### Structure des solutions
> En notant $S_H$ l'ensemble des solutions de l'équation homogène, qui contient
> $\tilde{0}$ et est stable par combinaison linéaire (un espace vectoriel).

On prouve ces propriétés de la même façon que pour l'ordre 1.

> Soit $f_p$ une solution de $(E)$, alors l'ensemble des solutions de $(E)$ noté
> $S_E = f_p + S_H = \{f_p + h, h \in H\}$ ($S_E$ est un espace affine).

La preuve est la même que pour l'ordre 1.

### Équation homogène
Une idée est de chercher toutes les solutions exponentielles, en utilisant en
fonction $\begin{aligned} \varphi: \mathbb{R} &\to \mathbb{C} \\ x &\mapsto \varphi(x) = e^{rx} .\end{aligned}$
avec $r \in \mathbb{C}$. On cherche une condition nécessaire et suffisante pour
$\varphi \in S_H$. Or, $\varphi'(x) = re^{rx}$ et $\varphi''(x) = r^2 e^{rx}$.

On a alors $\varphi \in S_H$\
$\Leftrightarrow \varphi'' + a \varphi' + b\varphi = 0$\
$\Leftrightarrow \forall x \in \mathbb{R}, r^2 e^{rx} + ar e^{rx} + b e^{rx} = 0$\
$\Leftrightarrow \forall x \in \mathbb{R}, [r^2 + ar + b] e^{rx} = 0$\
$\Leftrightarrow r^2 + ar + b = 0 : (EC)$\
À l'aide de cette équation caractéristique, on la résout à valeurs dans
$\mathbb{C}$. On pose $\Delta = a^2 - 4b$, et on distingue deux cas :
- Si $\Delta \neq 0$, on note $r_1,r_2 \in \mathbb{C}$, $r_1 \neq r_2$ les deux
  racines distinctes de $(EC)$, et on obtient
  $S_H = \{x \mapsto \lambda e^{r_1 x} + \mu e^{r_2 x}, (\lambda,\mu) \in \mathbb{C}^2\}$.
- Si $\Delta = 0$, $(EC)$ a une unique racine double $r_0 = \frac{-a}{2}$
  nous donnant
  $S_H = \{x \mapsto (\lambda x + \mu) e^{r_0 x}, (\lambda,\mu) \in \mathbb{C}^2\}$.

On a toujours $S_H = \{\lambda f_1 + \mu f_2, (\lambda,\mu) \in \mathbb{C}^2\}$
$= \mathbb{C} f_1 + \mathbb{C} f_2$ (un plan vectoriel).

##### Preuve
Soit $r$ une racine de $(EC)$, $f \in S_H$ et $g: x \mapsto e^{-rx} f(x)$.
Ainsi $\forall x \in \mathbb{R}, f(x) = e^{rx} g(x)$,
$f'(x) = r e^{rx} g(x) + e^{rx} g'(x)$, et
$f''(x) = r^2 e^{rx} g(x) + 2r e^{rx} g'(x) + e^{rx} g''(x)$.

On a donc $f \in S_H$ si et seulement si $f'' + af' + bf = 0$,
soit $\forall x \in \mathbb{R}$,
$e^{rx} \times [g''(x) + (2r + a)g'(x) + (r^2 + ar + b)g(x)] = 0$,
soit puisque $r$ est une racine de $(EC)$
$\forall x \in \mathbb{R}, g''(x) + (2r + a)g'(x) = 0$.

On distingue deux cas :
- si $\Delta = 0$, $r = r_0 = \frac{-a}{2} \Leftrightarrow 2r + a = 0$,
  donc $f \in S_H$ si et seulement si $g'' = 0$ ($g$ est affine).
  Ainsi, $\exists (\lambda,\mu) \in \mathbb{K}^2, \forall x \in \mathbb{R}, g(x) = \lambda x + \mu$,
  et donc $f(x) = e^{r_0 x}g(x) = e^{r_0}(\lambda x + \mu)$
- si $\Delta \neq 0$, $f \in S_H \Leftrightarrow g'' + (2r + a) g' = 0$,
  donc $g'$ est solution de l'équation $y' + (2r + a)y = 0$
  (une équation différentielle du premier degré homogène à coefficients
  constants). Ainsi, $\exists \lambda \in \mathbb{K}, \forall x \in \mathbb{R},$
  $g'(x) = \lambda e^{-(2r + a)x}$, donc
  $g(x) = \frac{\lambda}{-(2r + a)} e^{-(2r + a)x}$,
  donnant finalement $f(x) = e^{rx} g(x) = C e^{-(r+a)x} + \mu e^{rx}$.
  Puisque $r^2 + ar + b = 0$ ( $(EC)$ ), on note $r_1,r_2$ les racines de
  $(EC)$, qui sont telles que $r_1 + r_2 = -a \Leftrightarrow r_2 = -a -r_1$
  nous donnant $f: x \mapsto C_1 e^{r_1 x} + C_2 e^{r_2 x}$.

#### Cas particuliers de l'équation homogène
On revient au cas réel ($\mathbb{K} = \mathbb{R}$), et on cherche les solutions
réelles de $(H)$ avec $(a,b) \in \mathbb{R}^2$.

On pose $\Delta = a^2 - 4b$ :
- Si $\Delta > 0$, on note $r_1,r_2$ les racines réelles distinctes, et on a
  $S_H = \{x \mapsto x gl e^{r_1 x} + \mu e^{r_2 x}, (\lambda,\mu) \in \mathbb{R}^2\}$
- Si $\Delta = 0$, on note $r_0 = \frac{-a}{2}$ l'unique racine double de
  $(EC)$, et on a
  $S_H = \{x \mapsto (\lambda x + \mu) e^{r_0 x}, (\lambda,\mu) \in \mathbb{R}^2\}$
- Si $\Delta < 0$, $(EC)$ possède deux racines complexes conjuguées
  $r_{1,2} = \alpha \pm i \beta, (\alpha,\beta) \in \mathbb{R}^2$,
  et on obtient
  $S_H = \{x \mapsto e^{\alpha x} [\lambda \cos(\beta x) + \mu \sin(\beta x)], (\lambda,\mu) \in \mathbb{R}^2\}$

##### Preuve
- Dans les cas où $\Delta \geq 0$, le résultat découle directement du résultat
  dans $\mathbb{C}$
- Dans le cas où $\Delta < 0$, on regarde les solutions complexes :
  on a $\alpha \pm i \beta$ les racines de $(EC)$, donnant
  $f : x \mapsto \lambda e^{\alpha + i \beta} + \mu e^{\alpha - i \beta}$, avec $\lambda,\mu \in \mathbb{C}$.
  On dégage le cas de f à valeurs réelles ($\overline{f} = f$).
  On pose $\exists \lambda,\mu \in \mathbb{C},\forall x \in \mathbb{R}, f(x) = \lambda e^{(\alpha + i \beta)x} + \mu e^{(\alpha - i \beta)x}$;
  or $\overline{f(x)} = f(x)$ soit
  $f(x) = \overline{\lambda} (\overline{e^{(\alpha + i \beta)x}}) + \overline{\mu} (\overline{e^{(\alpha - i \beta)x}})$
  $= \overline{\lambda} e^{(\alpha - i \beta)x} + \overline{\mu} e^{(\alpha + i \beta)x}$,
  nous donnant nécessairement $\lambda = \overline{\mu} \Leftrightarrow \overline{\lambda} = \mu$.
  Finalement, on a $f(x) = \lambda e^{(\alpha + i\beta)x + (\overline{\lambda e^{(\alpha + i\beta)x}})}$
  $= 2\Re(\lambda e^{(\alpha + i\beta)x})$ où $\lambda \in \mathbb{C}$.
  Ainsi, on a bien $f$ de la forme $x \mapsto C_1 e^{\alpha x} \cos(\beta x) + C_2 e^{\alpha x} \sin(\beta x)$,
  avec $C_1,C_2 \in \mathbb{R}$.

##### Exemples
__Oscillateur harmonique :__ $\ddot{\theta} + \omega_0^2 \theta = 0$, avec $\omega \in \mathbb{R}^{\ast}_{+}$.
On a $(EC): r^2 = 0r + \omega_0^2 = 0 \Leftrightarrow r^2 = -\omega_0^2 = (i \omega)^2$.
Deux racines complexes conjuguées de $(EC)$ sont alors $0 \pm i \omega$,
et on trouve les solutions réelles
$S_H = \{t \mapsto e^{0t} (A \cos(\omega t) + B \cos(\omega t)), (A,B) \in \mathbb{R}^2\}$
$= \{t \mapsto A \cos(\omega t) + B \cos(\omega t), (A,B) \in \mathbb{R}^2\}$.

__Pas de sens physique :__ Soit $\omega \in \mathbb{R}^{\ast}_{+}$,
on pose $(E): y'' - \omega^2 y = 0$, et donc on a
$(EC) : r^2 - \omega^2 = 0$, qui a pour racines réelles distinctes
$r = \pm \omega$. Les solutions homogènes sont donc
$S = \{x \mapsto \lambda e^{\omega x} + \mu e^{s\omega x}, (\lambda,\mu) \in \mathbb{R}^2\}$.
Ainsi si $f \in S$, on peut l'écrire sous la forme
$A \cosh(\omega x) + B \sinh(\omega x)$.

__Dernier exemple :__ $(E) : y'' + 2y' + 2y = 0$. On pose
$(EC) : r^2 + 2r + 2 = 0$, et donc $\Delta = -4 = (2i)^2 < 0$.
Les racines sont donc $\frac{-2 \pm 2i}{2} = -1 \pm i$
(on a $\alpha = -1, \beta = 1$).
Les solutions réelles sont alors $\{x \mapsto e^{-x}(\lambda \cos x + \mu \sin x), (\lambda,\mu) \in \mathbb{R}^2\}$.

__Cas général du circuit RLC :__ $\frac{d^2 y}{dt^2} + 2 \lambda \frac{d y}{dt} + \omega_0^2 y = 0$
($\lambda,\omega > 0$).
On pose $(EC) : r^2 + 2 \lambda r + \omega_0^2 = 0$, et donc $\Delta = 4(\lambda^2 - \omega_0^2)$.
On distingue 3 cas :
- $\lambda > \omega_0$ ($\Delta > 0$), on a les racines $-\lambda \pm \sqrt{\lambda^2 - \omega_0^2}$,
  donc les solutions sont de la forme $t \mapsto  Ae^{r_1 t} + Be^{r_2 t}$.
- $\lambda = \omega_0$ ($\Delta = 0$), l'unique racine est $r_0 = - \lambda$,
  et la $t \mapsto (At + B) e^{-\lambda t}$ (régime critique).
- $\lambda < \omega_0$ ($\Delta < 0$), les deux racines complexes conjuguées
  sont $-\lambda \pm i \sqrt{\omega_0^2 - \lambda^2}$, donnant des solutions de
  la forme $t \mapsto e^{-\lambda t} [A \cos(\sqrt{\omega^2 - \lambda^2} t) + B \sin(\sqrt{\omega_0^2 - \lambda^2} t)]$,
  avec $(A,B) \in \mathbb{R}^2$.

### Recherche d'une solution particulière de l'équation
#### Tenter une solution évidente
Par exemple, $y'' - y = \frac{1}{x^2} - \ln(x)$, on trouve pour solution
$x \mapsto \ln(x)$. Cela nous permet de trouver
$S_E = \{x \mapsto \ln(x) + (\lambda e^{x} + \mu e^{-x}), (\lambda,\mu) \in \mathbb{R}^2\}$
sur $I = \mathbb{R}^{\ast}_{+}$.

#### Second membre polynomial
On pose $(E) : y'' + ay' + by = P(x)$ avec $P$ un polynôme.\
On cherche $f_p$ sous la forme (avec $Q$ un polynôme de même degré que P):
- si $a = b = 0$ : $f_p : x \mapsto x^2 \times Q(x)$
- si $b = 0, a \neq 0$ : $f_p: x \mapsto x Q(x)$
- si $b \neq 0$, $f_p: x \mapsto Q(x)$

##### Exemple
En posant $(E): y'' - 3y' + y = x^3 - 2x + 1$, on cherche une solution
particulière : $f_p: ax^3 + bx^2 + cx + d$.
On a $a = 1$ par identification, nous donnant
$f_p'(x) = 3x^2 + 2bx + c$ et $f_p''(x) = 6x + 2b$.
On injecte dans $(E)$, donnant
$\forall x \in \mathbb{R}, x^3 + (x - 9)x^2 + (c - 6b + 6)x + (d - 3c + 2b) = x^3 - 2x + 1$
$\Leftrightarrow \left\{\begin{matrix} b - 9 = 0 \\ c - 6b + 6 = -2 \\ d - 3c + 2b = 1\end{matrix}\right.$,
nous donnant enfin en résolvant le système
$f_p(x) = x^3 + 9x^2 + 46x + 121$.

#### Second membre exponentiel
$(E): y'' + ay' + by = e^{mx}$, avec $m \in \mathbb{C}$.\
On cherche $f_p$ sous la forme :
- si $m$ n'est pas racine de $(EC)$, on pose $f_p: x \mapsto Ae^{mx}$
- si $m$ est racine simple de $(EC)$, on pose $f_p: x \mapsto Ax e^{mx}$
- si $m$ est racine double, on pose $f_p: x \mapsto Ax^2 e^{mx}$

- $f_p(x) = A e^{mx}$, soit $f_p'(x) = Am e^{mx}$ et $f_p''(x) = Am^2 e^{mx}$,
  et on injecte dans $(E)$ : $[Am^2 + a Am + b A] e^{mx} = e^{mx}$
  $\Leftrightarrow [m^2 + am + b] A = 1$, et puisque $m$ n'est pas racine de
  $(EC)$, l'expression entre crochets ne s'annule pas, et $A = \frac{1}{m^2 + am + b}$
- puisque $m$ est racine simple de $(EC)$, on a $m^2 + am + b = 0$ et $2m + a \neq 0$
  (pas une racine double), et on a donc $f_p(x) = Ax e^{mx}$,
  $f_p'(x) = Ax m e^{mx} + Ae^{mx}$ et $f_p''(x) = 2Am e^{mx} + Am^2 x e^{mx}$.\
  On injecte dans $(E)$, et on obtient $A [(m^2 + am + b)x + (a + 2m)] e^{mx} = e^{mx}$,
  donnant dans ces conditions $A [0x + (a + 2m)] = 1$ et donc
  $A = \frac{1}{2b + a}$.
- puisque m est racine double, on a $m^2 + am + b = 0$ et $2m + a = 0$,
  et on a donc $f_p(x) = Ax^2 e^{mx}$, $f_p'(x) = A 2x e^{bx} + Am x^2 e^{mx}$
  et $f_p''(x) = 2A e^{mx} = 4Axm e^{mx} + A m^2 x^2 e^{mx}$.
  On injecte dans $(E)$, donnant
  $e^{mx} = A e^{mx} [(m^2 + am + b) x^2 + 2(2m + a)x + 2]$
  $\Leftrightarrow 1 = A [0 x^2 + 2 \times 0x + 2]$,
  nous donnant finalement $A = \frac{1}{2}$.

#### Second membre trigonométrique
$(E): y'' + ay' + by = \cos(\omega x)$ ou $\sin(\omega x)$.\
On passe en $\mathbb{C}$, et on se ramène au cas exponentiel en posant
$\cos(\omega x) = \Re(e^{i\omega x})$ et $\sin(\omega x) = \Im(e^{i\omega x})$.

#### Superposition des solutions
Comme pour le premier ordre.
