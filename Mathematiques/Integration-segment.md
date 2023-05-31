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
