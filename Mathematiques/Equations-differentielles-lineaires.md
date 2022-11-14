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
