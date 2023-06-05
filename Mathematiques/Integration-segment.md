# Intégration (de Riemann) sur un segment
On cherche dans ce chapitre à définir l'aire sous une courbe d'une fonction
continue par morceaux sur un segment, soit pour $f \in \mathcal{CM}([a,b], \mathbb{R})$,
on cherche à définir le réel $\int\limits_{[a,b]} f$.

L'idée de l'intégrale de Riemann est d'approcher la fonction par une fonction en
escalier (des rectangles horizontaux) qui se somme facilement et s'approche de
plus en plus des valeurs de la fonction. Cette fonction est construite à chaque
portion (en largeur) comme étant assez proche (à $\varepsilon$ près sur la borne
supérieure de cette différence sur la largeur en question), et en réduisant les
largeurs à chaque fois.


## Approximation uniforme par les fonctions en escalier des fonction continues par morceaux sur un segment
### Continuité uniforme
Se référer à la définition de la continuité.

La définition classique de la continuité vérifie en chaque point la cohérence en
un voisinage de la fonction et sa convergence. On choisit ici une définition
plus contraignante.

> On dit que $f: I \to \mathbb{K}$ est uniformément continue sur $I$ si
> $\forall \varepsilon > 0, \exists \nu > 0, \forall (x,y) \in I^2, |x - y| \leq \nu \Rightarrow |f(x) - f(y)| \leq \varepsilon$.

La continuité uniforme implique la continuité.

Si $f$ est lipschitzienne sur $I$, elle est uniforme continue sur $I$.

> Théorème de Heine : Toute fonction continue sur un segment est uniformément
> continue.

__Preuve :__ Soit $f$ continue mais pas uniformément continue, alors
$\exists \varepsilon > 0, \forall \nu > 0, \exists (x,y) \in I^2, |x - y| \leq \nu \land |f(x) - f(y)| > \varepsilon$.
On fixe un tel $\varepsilon > 0$, et pour tout $n \in \mathbb{N}$, on pose
$\nu_n = \frac{1}{n + 1}$. Pour cette valeur, il existe
$(x_n,y_n) \in I^2 \mid |x_n - y_n| \leq \frac{1}{n + 1}$
et $|f(x_n) - f(y_n)| > \varepsilon$. Ainsi, on a construit deux suites
$(x_n)_n$ et $(y_n)_n$ à valeurs dans $I$, ici $I = [a,b]$.\
$(x_n)_n$ est alors une suite bornée, et par Bolzano-Weierstrass, il existe une
sous-suite convergente. On note $\varphi: \mathbb{N} \to \mathbb{N}$ strictement
croissante et $(x_{\varphi(n)})_n$ converge. On note $\ell = \lim\limits_{n \to + \infty} x_{\varphi(n)}$.
Or, $\forall n, x_{\varphi(n)} \in [a,b]$ donc $\ell \in [a,b]$.
Or, $\forall n \in \mathbb{N}, |x_{\varphi(n)} - y_{\varphi(n)}| \leq \frac{1}{\varphi(n) + 1}$,
donc par encadrement, $x_{\varphi(n)} - y_{\varphi(n)} \xrightarrow[n \to \infty]{} 0$,
donc $y_{\varphi(n)}$ est aussi convergente et $y_{\varphi(n)} = (y_{\varphi(n)} - x_{\varphi(n)}) + x_{\varphi(n)} \xrightarrow[n \to +\infty]{} 0 + \ell = \ell$.\
Or, par caractérisation séquentielle de la continuité, $f$ est continue en $\ell$, donc les limites de $f$
en $x_{\varphi(n)}$ et $y_{\varphi(n)}$ sont de $f(\ell)$, ce qui voudrait dire
dans le voisinage que $0 \geq \varepsilon$, ce qui est absurde.\

### Fonctions en escalier
On travaille sur le segmente $[a,b]$ avec $a < b$.

> Une subdivision du segment $[a,b]$ est une séquence $s = (a_0,a_1,\ldots,a_n)$
> où $a_0 = a$ et $a_n = b$ avec $(n + 1)$ points.

On définit la subdivision régulière en $n$ parts comme celle qui a un pas de $\frac{b - a}{k}$
entre chaque point successif de la subdivision.

> $f$ est dite en escalier sur $[a,b]$ s'il existe une subdivision
> $s = (a_0,a_1,\ldots,a_n)$ telle que la restriction $]a_i,a_{i + 1}[$ soit constante.

> On note $\zeta([a,b],\mathbb{R})$ l'ensemble des fonctions en escalier. Ces
> fonctions forment une $\mathbb{R}$-algèbre pour les opérations point à
> point usuelles.

### Fonction continues par morceaux sur $[a,b]$
> $f: [a,b] \to \mathbb{R}$ est continue par morceaux s'il existe une subdivision $s = (a_0,a_1,\ldots,a_n)$
> telle que la restriction de $f$ à chaque $]a_i;a_{i + 1}[$ est
> continue et peut se prolonger continument sur $[a_i;a_{i + 1}]$.

> Toute fonction continue par morceaux sur $[a,b]$ est bornée.

__Preuve :__ $|f|$ est encore continue par morceaux sur $[a,b]$, et on prend
$s = (a_0,a_1,\ldots,a_n)$ une subdivision adaptée. Par compacité, $|f|\restriction_{]a_i;a_{i + 1}[}$
se prolonge en fonction continue sur $[a_i;a_{i + 1}]$ donc est bornée.

### Approximation uniforme
> Si $f$ est continue par morceaux sur $[a;b]$, on note
> $\lVert f \rVert_\infty  = \text{sup} \{|f(t)|, t \in [a;b]\}$.

Toute fonction continue par morceaux sur $[a,b]$ est limite uniforme d'une suite
de fonctions en escaliers, soit pour tout $f \in \mathcal{CM}([a;b],\mathbb{R})$,
pour tout $\varepsilon > 0$, il existe $\varphi \in \zeta([a;b],\mathbb{R})$
telle que $\lVert f - \varphi \rVert \leq \varepsilon$.

__Preuve :__ Si $f$ est continue sur le segment $[a,b]$,
soit $\varepsilon > 0$, par théorème de Heine, $f$ est uniformément continue sur
$[a,b]$. En prenant $\nu > 0$ tel qu'on obtient la conséquence de la continuité
uniforme, et on prend un $n \in \mathbb{N}$ suffisamment grand tel que
$\frac{b - a}{n} < \nu$ (ce qui est toujours possible puisque $\frac{b - a}{n} \xrightarrow[n \to +\infty]{} 0$).
On fixe $n$, et on construit la subdivision régulière de $[a,b]$ avec un pas $\frac{b - a}{n}$,
avec $a_k = a + k \frac{b - a}{n}$. On pose $\varphi: x \mapsto \left\{\begin{matrix} f(a_{i - 1}) \text{ si } x \in [a_{i - 1}; a_i] \\ f(b) \text{ si } x = b \end{matrix}\right.$,
et on obtient bien le respect des contraintes souhaitées.

## Construction de l'intégrale
### Intégrale des fonctions en escalier
L'intégrale des fonctions en escalier correspond à l'aire des rectangles qui la
composent (donc leur hauteur fois leur largeur). On note alors pour $f$ une
fonction en escalier $\int\limits_{[a;b]} f = \sum\limits_{i = 1}^{n} h_i (a_i - a_{i - 1})$.
On ne s'occupe pas des valeurs sur les bords des rectangles, seulement de leur
hauteurs.

On obtient des propriétés classiques de l'intégrale : inégalité triangulaire
(qui revient à celle sur les sommes finies), positivité, et croissance, ainsi
que linéarité. On obtient aussi la relation de Chasles.

On peut remarquer que si $f$ est en escalier, positive et d'intégrale nulle,
alors elle est nulle sauf en un nombre fini de points (on coupe sur des points
qui constituent seuls leur propre membre de la subdivision choisie).

### Intégrale d'une fonction continue sur $[a,b]$
On encadre la fonction par une fonction en escalier toujours au-dessus de la
fonction, et par une fonction toujours en dessous, et on fait arbitrairement
(par $\varepsilon$) décroître la différence entre les deux fonctions.

> Soit $f \in \mathcal{CM}([a,b],\mathbb{R})$, on note $A = \{\varphi \in \mathcal{E}([a,b],\mathbb{R}) \mid \varphi \leq f\}$
> et $B = \{\psi \in \mathcal{E}([a,b],\mathbb{R}) \mid f \leq \psi\}$, et alors
> les réels suivants existent et sont égaux :
> $\alpha = \text{sup} \{\int\limits_{[a,b]} \varphi \mid \varphi \in A\}$
> et $\beta = \text{inf} \{\int\limits_{[a,b]} \psi \mid \psi \in B\}$.
> Cette valeur commune est appelée intégrale de $f$ sur $[a,b]$.

__Preuve :__ Comme $f$ est continue par morceaux, elle est bornée,
et on peut la majorer par des fonctions en escalier la minorant et la majorant.
L'ensemble $A$ est majoré aussi et $B$ est minoré, tout en étant toujours
l'un plus petit que l'autre. Ainsi, $A$ et $B$ possèdent respectivement une
borne supérieure et inférieure.\
Puisqu'on peut minorer $\beta$ par l'intégrale de n'importe quelle fonction en
escalier inférieure à la fonction, on a bien $\alpha \leq \beta$.
On fixe $\varepsilon > 0$. Par approximation uniforme, $\exists \varphi \in A, \exists \psi \in B \mid \varphi \leq f \leq \psi \land |\psi - \varphi| \leq \varepsilon$,
donnant $\int\limits_{[a,b]} \psi \leq \int\limits_{[a,b]} \varphi + \varepsilon$,
soit $\beta \leq \alpha + \varepsilon (b-a)$, permettant de conclue que
$\beta \leq \alpha$. On peut ainsi conclure que $\alpha = \beta$.

Il suffit de passer à la limite dans les propriétés de $\int\limits_{[a,b]}$ des
fonctions en escalier pour obtenir ces mêmes propriétés sur les fonction
continues par morceaux.

### Extension à $\mathbb{C}$
On sépare la fonction en valeurs complexes et réelles et on utilise la
linéarité. On ne peut pas conserver les propriétés de positivité et autres,
mais on conserve bien la relation de Chasles et la linéarité.

On obtient aussi toujours une inégalité triangulaire
$|\int\limits_{[a,b]} f| \leq \int\limits_{[a,b]} |f|$
pour $f \in \mathcal{CM}([a,b], \mathbb{C})$.

### Intégrale de deux bornes
> Soit $I$ un intervalle quelconque, on dit que $f$ est
> $\mathcal{CM}$ sur $I$ si $f$ est $\mathcal{CM}$ sur chaque segment
> $[a,b] \subset I$.

On peut ainsi dire que des fonctions sont continue par morceaux sur
$\mathbb{R}$.

> Soit $f \in \mathcal{CM}(I,\mathbb{K})$, et $(a,b) \in I^2$.
> $I$ étant un intervalle, on a bien le segment reliant
> $a$ à $b$ inclus dans $I$. On définit
> $\int\limits_{a}^{b} f(t) dt = \left\{\begin{matrix} \int\limits_{[a,b]} f \text{ si } a \leq b \\ - \int\limits_{[b,a]} f \text{ si } a \geq b \end{matrix}\right.$

On peut aussi en définir que l'intégrale est nulle en un point unique.

## Somme de Riemann
Pour approcher l'intégrale d'une fonction, on propose un procédé plus pratique
d'approche par une subdivision régulière
$(a_k = a + k \frac{b - a}{n})_{k \in [\![0;n]\!]}$.

On approche donc par la somme de Riemann à gauche
$S_n^{-}(f) = \frac{b - a}{n} \sum\limits_{k = 0}^{n - 1} f(a_k)$
et la somme de Riemann à droite $S_n^{+}(f) = \frac{b - a}{n} \sum\limits_{k = 1}^{n} f(a_k)$.
On ne maîtrise plus si on est au-dessus ou en-dessous de la fonction, et on ne
peut pas connaître l'erreur de notre fonction.

> Si $f$ est continue sur $[a,b]$, alors les suites des sommes de Riemann à gauche
> et à droite convergent vers $\int\limits_{a}^{b} f(t) dt$. De plus, si $f$ est
> $\mathcal{C}^{1}([a,b], \mathbb{R})$, on a $\forall n \in \mathbb{N}^{\ast},
> |\int\limits_{a}^{b} f(t) dt - S_n^{+ / -}(f)| \leq \frac{(b - a)^2}{2n} \| f' \|_\infty$.

Ici, $\| f' \|_\infty$ est la borne supérieure et donc par compacité le maximum
de $|f'|$.

__Preuve :__ On commence par prouver la deuxième affirmation.
Par relation de Chasles, $\int\limits_{a}^{b} f(t) dt = \sum\limits_{k = 1}^{n} \int\limits_{a_{k-1}}^{a_k} f(t) dt$.
De plus, $S_n^{-}(f) = \frac{b - a}{n} \sum\limits_{k = 0}^{n} f(a_{k-1}) = \sum\limits_{k = 1}^{n} \int\limits_{a_{k-1}}^{a_k} f(a_{k-1}) dt$.
Ainsi, $\int\limits_{a}^{b} f(t) dt - S_n^{-}(f) = \sum\limits_{k = 1}^{n} \int\limits_{a_{k-1}}^{a_k} (f(t) - f(a_{k-1})) dt$.
On estime l'erreur $f(t) - f(a_{k-1})$ pour $t \in [a_{k-1};a_k]$.\
On fait entrer la supposition de $f \in \mathcal{C}^{1}([a,b])$, donnant par
compacité que la dérivée y est majorée par $M = \| f' \|_\infty$
($f'$ étant $\mathcal{C}^{0}$ sur $[a,b]$). Par théorème des accroissements
finis,
$\forall (x,y) \in [a,b]^2, |f(x) - f(y)| \leq M |x - y|$.
Ainsi, $\forall t \in [a_{k-1}, a_k]$, $|f(t) - f(a_{k-1})| \leq M \times |t - a_{k-1}|$.
De plus, par une inégalité triangulaire, on a
$|\int\limits_{a_{k-1}}^{a_k} (f(t) - f(a_{k-1})) dt| \leq \int\limits_{a_{k-1}}^{a_k} |f(t) - f(a_{k-1})| dt$,
le tout majoré par croissance par $\int\limits_{a_{k-1}}^{a_k} M \times |t - a_{k-1}| dt$.
Or $\int\limits_{a_{k-1}}^{a_k} M \times (t - a_{k-1}) dt = [M \frac{(t - a_{k-1})^2}{2}]_{a_{k-1}}^{a_k}$
$= M \frac{(a_k - a_{k-1})^2}{2} = \frac{M}{2} (\frac{b - a}{n})^2$.\
Finalement, pour $n \in \mathbb{N}^{\ast}$,
$|\int\limits_{a}^{b} f(t) dt - S_n(f)| \leq \sum\limits_{k = 1}^{n} \frac{M}{2} (\frac{b - a}{n})^2$
$\leq n \times \frac{M}{2} \frac{(b - a)^2}{n^2} \leq \frac{M (b - a)^2}{2n} = O(\frac{1}{n})$.\

Pour les fonctions seulement continues mais pas dérivables ($\mathcal{C}^{0}$),
on a toujours $|\int\limits_{a}^{b} f(t) dt - S_n^{-}(f)| \leq \sum\limits_{k = 1}^{n} \int\limits_{a_{k-1}}^{a_k} |f(t) - f(a_{k-1})| dt$.
$f$ étant continue sur le segment $[a,b]$, elle est donc uniformément continue
sur $[a,b]$, donc $\forall \varepsilon > 0, \exists \nu > 0, \forall (x,y) \in [a,b]^2, |x - y| \leq \nu \Rightarrow |f(x) - f(y)| \leq \varepsilon$.
On fixe $\varepsilon > 0$, et on pend $n$ suffisamment grand tel que $\frac{b - a}{n} \leq \nu$.
Ainsi, $\forall k, \forall t \in [a_{k-1},a_k], |t - a_{k-1}| \leq \frac{b - a}{n} \leq \nu$,
donc $|f(t) - f(a_{k-1})| \leq \varepsilon$.\
Ainsi, $\forall \varepsilon > 0, \exists n_0, \forall n > n_0, |\int\limits_{a}^{b} f - S_n^{-}(f)| \leq \sum\limits_{k = 1}^{n} \int\limits_{a_{k-1}}^{a_k} \varepsilon dt$
$\leq \int\limits_{a}^{b} \varepsilon dt \leq \varepsilon (b - a)$, donc la
suite $(S_n^{-}(f))_n$ converge vers $\int\limits_{a}^{b} f$.
