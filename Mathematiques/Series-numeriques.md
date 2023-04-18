# Suites numériques
## Généralités
### Définitions
> Soit $u = (u_n)_{n \in \mathbb{N}} \in \mathbb{K}^{\mathbb{N}}$, on pose $\forall n \in \mathbb{N}, S_n = \sum\limits_{k = 0}^{n} u_k$.
> On appelle $(S_n)_{n \in \mathbb{N}}$ la suite des sommes partielles, ou série
> de terme général $u_n$ que l'on note $\sum u_n$.

$u_n$ est le terme général de la série, et la somme de ces $u_n$ est la somme
partielle d'ordre $n$.

Par exemple, pour la série de terme général $\sum\limits_{n \in \mathbb{N}} n$,
les sommes partielles sont $S_n = \frac{n (n+1)}{2}$.

### Convergence et divergence
> On dit que la série $\sum u_n$ converge si la suite des sommes partielles
> $(S_n)_n$ converge. Dans ce cas, la limite finie de $(S_n)$ est appelée la somme
> de la série : $\lim\limits_{n \to + \infty} (\sum\limits_{k = 0}^{n} u_k) = \sum\limits_{k = 0}^{+\infty} u_k \in \mathbb{K}$.

Sinon, on dit que la série $\sum u_n$. En général, on pose la question de la
nature de la série (convergente (CV) ou divergente (DV)). On fera attention à
distinguer $\sum\limits_{n \in \mathbb{N}} u_n$ la série, $\sum\limits_{k = 0}^{n} u_k$ la somme partielle,
et $\sum\limits_{k = 0}^{+\infty} u_k$ la somme de la série si celle-ci est
finie.

### Reste d'une série convergente
> Si $\sum u_n$ est une série convergente, alors $\forall n \in \mathbb{N}$, la
> série $\sum\limits_{k \geq n+1}^{n} u_k$ est aussi convergente.

On note cette somme le reste $(R_n)$ d'une série convergente. De plus, la suite des restes $(R_n)_n$ converge vers $0$.

On commence une série à partir de l'indice où la suite est définie.

### Série télescopique
#### Séries géométriques
> Soit $q \in \mathbb{C}$, la série géométrique $\sum\limits_{n \in \mathbb{N}} q^n$
> converge si et seulement si $|q| < 1$. De plus, si $|q| < 1$, $\sum\limits_{n = 0}^{+\infty} q^n = \frac{1}{1 - q}$.

__Preuve :__ Si $|q| < 1$, $|\sum\limits_{k = 0}^{n} q^k - \frac{1}{1 - q}|$
$= |\frac{- q^{n+1}}{1 - q}| = \frac{|q|^{n+1}}{|1 - q|} \xrightarrow[n \to \infty]{} 0$,
donc la série $\sum\limits_{n} q^n$ converge et sa somme vaut $\frac{1}{1 - q}$.\
Si $|q| > 1$, $\sum\limits_{k = 0}^{n} q^k = \frac{1 - q^{n+1}}{1 - q}$. Ici, la
suite $(q^{n+1})_n$ diverge donc la série diverge.\
Si $|q| = 1$, si $q = 1$, $\sum\limits_{k = 0}^{n} 1$ est une série divergente,
et sinon, $S_n = \sum\limits_{k = 0}^{n} q^k = \frac{1 - q^{n+1}}{1 - q}$,
on a $S_{n + 1} - S_n = q^{n+1}$, donc $|S_{n+1} - S_n| = |q^{n+1}| = 1$. Par
l'absurde, si $S_n \xrightarrow[n \to \infty]{} L$, alors $|S_{n + 1} - S_n| \xrightarrow[n \to \infty]{} 0$,
donc il y a contradiction.

#### Série exponentielle
$\forall z \in \mathbb{C}, \lim\limits_{n \to + \infty} \sum\limits_{k = 0}^{n} \frac{z^k}{k!} = \exp(z)$,
la série exponentielle $\sum\limits_{n \geq 0} \frac{z^n}{n!}$ converge pour
tout $z \in \mathbb{C}$.

### Condition nécessaire de convergence
Cette condition est uniquement nécessaire, et si elle fonctionne, elle est
souvent inutile (elle ne sert qu'à la contradiction).

> Si la série $\sum u_n$ converge, alors la suite $(u_n)$ converge en $0$.

Il s'agit sensiblement de la même chose que la non-existence de $R_n$ pour une
série divergente.

Si $\sum u_n$ ne converge pas vers $0$ la série diverge grossièrement.

### Opérations sur les séries convergentes
#### Linéarité
> Soient $\sum u_n$ et $\sum v_n$ deux séries convergentes et $\lambda,\mu \in \mathbb{K}$,
> alors $\sum (\lambda u_n + \mu v_n)$ est convergente et
>  $\sum\limits_{n = 0}^{+\infty} (\lambda u_n + \mu v_n) = \lambda \sum\limits_{n = 0}^{+ \infty} u_n + \mu \sum\limits_{n = 0}^{+ \infty} v_n$.

__Preuve :__ Par linéarité de la convergence des suites.

Ainsi, l'ensemble $E$ des suites telles que leur série converge est un SEV de $\mathbb{K}^{\mathbb{N}}$
et la somme set une forme linéaire de $\mathcal{L}(E,\mathbb{K})$.

Attention, la combinaison linéaire d'une série convergente et d'une divergente
diverge, et la combinaison linéaire de deux séries divergentes ne nous permet de
déduire rien du tout.

#### Cas complexe
> Si $\sum u_n$ converge, alors $\sum \overline{u_n}$ converge et
> $\sum\limits_{n = 0}^{+ \infty} \overline{u_n} = \overline{(\sum\limits_{n = 0}^{+ \infty} u_n)}$.

__Preuve :__ Par opération sur les limites des sommes.

> $\sum z_n$ converge si et seulement si $\sum \Re(z_n)$ et $\sum \Im(z_n)$
> convergent, et dans ce cas, $\sum\limits_{n = 0}^{+ \infty} z_n = (\sum\limits_{n = 0}^{+ \infty} \Re(z_n)) + i (\sum\limits_{n = 0}^{+ \infty} \Im(z_n))$.

__Preuve :__ $\Rightarrow$ $\Re(z_n) = \frac{1}{2} z_n + \frac{1}{2} \overline{z_n}$,
et $z_n$ et $\overline{z_n}$ sont les termes généraux de séries convergentes, et
on conclut par linéarité.\
$\Leftarrow$ Par combinaison linéaire de suites convergentes.

## Séries à termes positifs
### Généralité
Soit $(u_{n})_n \in (\mathbb{R}_{+})^{\mathbb{N}}$, on note $S_N = \sum\limits_{n = 0}^{N} u_n$,
on a $S_{N+1} - S_N = u_{N+1} \geq 0$, donc la suite $(S_N)_N$
est croissante.

Il suffit de se poser la question d'une majoration de $S_N$.

> $(\sum u_n)$ converge si $(S_N)_N$ est majorée, et sinon, $\sum u_n$
> diverge et $\lim\limits_{n \to + \infty} \sum\limits_{n = 0}^{N} u_n = +\infty$.

> Soient $u,v \in (\mathbb{R}_{+})^{\mathbb{N}}$ telles que
> $\exists n_0, \forall n \geq n_0, 0 \leq u_n \leq v_n$.
> - Si $\sum v_n$ converge, alors $\sum u_n$ converge
> - Si $\sum u_n$ diverge, alors $\sum v_n$ diverge

__Preuve :__ Pour $N \geq n_0$, en sommant les inégalités, $0 \leq \sum\limits_{n = n_0}^{N} u_n \leq \sum\limits_{n = n_0}^{N} v_n$.
La seconde assertion est la contraposée de la première, et on prouve la première :
Si la série $\sum v_n$ converge, alors $\sum\limits_{n = n_0}^{N} v_n \leq \sum\limits_{n = n_0}^{+\infty} v_n$,
donc la somme partielle $(\sum\limits_{n = n_0}^{N} u_n)_N$ est majorée, or elle
est croissante donc la série $\sum u_n$ converge.

> Comparaison des séries à termes positifs : Soient $u,v \in (\mathbb{R}_{+})^{\mathbb{N}}$
> - si $u_n \underset{n \to +\infty}{=} O(v_n)$, alors $\sum v_n$ converge
>   implique que $\sum u_n$ converge
> - si $u_n \underset{n \to +\infty}{=} o(v_n)$, alors $\sum v_n$ converge
>   implique que $\sum u_n$ converge
> - si $u_n \underset{n \to +\infty}{\approx} v_n$, alors les séries $\sum u_n$ et
>   $\sum v_n$ sont de même nature

__Preuves :__
- $u_n = O(v_n)$ donc à partir d'un certain rang, $u_n \leq M v_n$,
  $\exists M \in \mathbb{R}_{+},\exists n_0 \mid  \forall n \geq n_0, 0 \leq u_n \leq M v_n$
  et on applique la comparaison simple
- $u = o(v) \Rightarrow u = O(v)$
- $u \approx v \Rightarrow \left\{\begin{matrix} u = O(v) \\ v = O(u) \end{matrix}\right.$

On va donc en général comparer une suite positive à une suite de référence pour
obtenir sa nature. Les suites de référence seront principalement la suite
géométrique, la suite exponentielle $\frac{z^n}{n!}$ et les séries de Riemann
$\frac{1}{n^{d}}$.

## Comparaison série intégrale
### Cas général
> Soit $f: \mathbb{R}_{+} \to \mathbb{R}_{+}$ continue et décroissante,
> $\forall k \in \mathbb{N}, f(k + 1) \leq \int\limits_{k}^{k + 1} f(t) dt \leq f(k)$.
> De plus, la série $\sum\limits_{n \geq 0} f(n)$ converge si et seulement si la
> suite $(\int\limits_{0}^{n} f(t) dt)_n$ converge.

__Preuve :__ Pour $k \in \mathbb{N}$, $f$ est décroissante sur $[k;k+1]$,
$\forall t \in [k;k+1], f(k + 1) \leq f(t) \leq f(k)$. Par
croissance de l'intégrale, $\int\limits_{k}^{k+1} f(k+1) dt \leq \int\limits_{k}^{k+1} f(t) dt \leq \int\limits_{k}^{k+1} f(k) dt$,
donnant le résultat par $\int\limits_{a}^{b} \lambda dt = \lambda (b - a)$.\
On pose $S_N = \sum\limits_{k = 0}^{N} f(k)$, et on somme les inégalités pour $k \in [\![0;N-1]\!]$,
$\sum\limits_{k = 0}^{N - 1} f(k + 1) \leq \sum\limits_{k = 0}^{N - 1} (\int\limits_{k}^{k + 1} f(t) dt) \leq \sum\limits_{k = 0}^{N-1} f(k)$.
$S_N - f(0) \leq \int\limits_{0}^{N} f(t) dt \leq S_N - f(N)$.
Ainsi,
- si la série $\sum f(n)$ converge alors $(S_N)_N$ converge,
  donc $\forall N \geq 0, \int\limits_{0}^{N} f(t) dt \leq S_N \leq S_{\infty}$,
  avec $S_{\infty}$ la somme infinie. Or, $f$ est à valeurs positives, donc
  $(\int\limits_{0}^{N} f(t) dt)_N$ est croissante et majorée donc convergente.
- si la suite des intégrales $(\int\limits_{0}^{N}  f(t) dt)_N$ converge vers
  une limite $I$, alors $\forall N, S_N \leq f(0) + \int\limits_{0}^{N} f(t) dt \leq f(0) + I$
  car $(\int\limits_{0}^{N} f(t) dt)_N$ croissante (car $f$ positive).
  $(S_N)_N$ est majorée et croissante donc converge.

En cas de convergence, il faut bien remarquer qu'on obtient $S_\infty - f(0) \leq I \leq S_\infty$
et $I \leq S_\infty \leq I + f(0)$. On peut améliorer en commençant à $n_0$ au
lieu de $0$, donnant $\int\limits_{n_0}^{+\infty} f(t) dt \leq \sum\limits_{n = n_0}^{+\infty} f(n) \leq \int\limits_{n_0}^{+\infty} f(t) dt + f(n)$.

__Application :__ Étude de la série harmonique\
La série harmonique diverge, et la somme partielle a pour équivalente $\ln(n)$.
On a donc le développement asymptotique $H_{n} \underset{n \to +\infty}{=} \ln(n) + \gamma + o(1)$,
avec $\gamma \approx 0.58$ la constante d'Euler.\
On a pu dégager ce développement par la comparaison entre somme et intégrale
car $\frac{1}{x}$ est continue décroissante sur $[1;+\infty[$,
donnant $H_n - 1 \leq \int\limits_{1}^{n} \frac{dt}{t} \leq H_n - \frac{1}{n}$,
donnant $\ln(n) + \frac{1}{n} \leq H_n \leq ln(n) + 1$.
De plus, $\forall n \geq 2, 1 + \frac{1}{n \ln(n)} \leq \frac{H_n}{\ln(n)} \leq 1 + \frac{1}{\ln(n)}$,
donnant par encadrement $\frac{H_n}{\ln(n)} \xrightarrow[n \to \infty]{} 1$.\
Ayant $H_n \underset{n \to \infty}{\sim} \ln(n)$. On montre que la suite $u_n = H_n - \ln(n)$
est convergente, ce qui est équivalente à montrer que la série télescopique
$\sum v_n$ converge, avec $v_n = u_{n+1} - u_{n}$. Pour cela, on étudie un
équivalent de $v_n$, qui est $H_{n+1} - \ln(n + 1) - H_n + \ln(n)$
$= \frac{1}{n + 1} - \ln(\frac{n+1}{n}) = \frac{1}{n + 1} - \ln(1 + \frac{1}{n})$,
or $\frac{1}{n + 1} = \frac{1}{n} \times [1 - \frac{1}{n} + o(\frac{1}{n})] \text{(DL)} = \frac{1}{n} - \frac{1}{n^2} + o(\frac{1}{n^2})$.
De plus, $\ln(1 + \frac{1}{n}) = \frac{1}{n} - \frac{1}{2 n^2} + o(\frac{1}{n^2})$.
Finalement, on a $v_n = \frac{-1}{2 n^2} + o(\frac{1}{n^2})$,
donc $v_n \underset{+\infty}{\sim} \frac{-1}{2 n^2}$,
donc $-v_n$ est équivalent au terme général d'une somme convergente
($\sum \frac{1}{n^2}$). Ainsi, la série de $-v_n$ et donc de $v_n$
converge, donc par série télescopique, $u_n$ converge, donc
$(H_n - \ln(n))_n$ converge. On note $\gamma = \lim\limits_{n \to + \infty} (H_n - \ln(n))$,
donnant le développement de $H_n$ souhaité.\
On pouvait aussi bien ne pas chercher le terme de précision $\frac{1}{n^2}$,
et poser des $O(\frac{1}{n^2})$, qui convergent.

### Application aux séries de Riemann
> La série de Riemann d'ordre $\alpha$ est la série
> $\sum\limits_{n \geq 1} \frac{1}{n^{\alpha}}$ converge
> si et seulement si $\alpha > 1$.

Si $\alpha > 1$, $\zeta(\alpha) = \sum\limits_{n = 1}^{+\infty} \frac{1}{n^{\alpha}}$.
On a de plus $\zeta(2) = \sum\limits_{n = 1}^{+\infty} \frac{1}{n^2} = \frac{\pi^2}{6}$
et $\zeta(4) = \frac{\pi^4}{90}$.

__Preuve :__ Si $\alpha \leq 0$, $\frac{1}{n^{\alpha}}$ ne tend pas vers $0$
et donc la série diverge grossièrement. Si $\alpha = 1$,
on retrouve la série harmonique qui diverge.
Si $0 < \alpha < 1$, $\forall n \geq 1, n \geq n^{\alpha}$,
donc $\frac{1}{n} \leq \frac{1}{n^{\alpha}}$,
or la série harmonique diverge, donc par minoration la série des
$\frac{1}{n^{\alpha}}$ diverge également.\
Pour $\alpha > 1$, par comparaison entre somme et intégrale,
$S_n = \sum\limits_{k = 1}^{n} \frac{1}{k^{\alpha}}$
et la fonction $t \mapsto \frac{1}{t^{\alpha}}$ est décroissante et
continue sur $\mathbb{R}_{+}^{\ast}$, nous donnant
$S_n - f(1) \leq \int\limits_{1}^{n} \frac{dt}{t^{\alpha}} \leq S_n - f(n)$,
or l'intégrale donne $[\frac{t^{-\alpha + 1}}{- \alpha + 1}]_1^n$
$= \frac{1}{-\alpha + 1} (n^{-\alpha + 1} - 1)$
$= \frac{1}{\alpha - 1} (1 - \frac{1}{n^{\alpha - 1}})$,
donc $\frac{1}{n^{\alpha}} \leq S_n \leq 1 + \frac{1 - \frac{1}{n^{\alpha - 1}}}{\alpha - 1}$.
Comme $\alpha > 1$, $\alpha - 1 > 0$, donnant $S_n \leq 1 + \frac{1}{\alpha - 1}$,
donnant que $(S_n)_n$ est majorée et croissante et donc convergente.
Ainsi, la série est convergente, et en passant à la limite on obtient
$\frac{1}{\alpha - 1} \leq \zeta(\alpha) \leq \frac{\alpha}{\alpha - 1}$.

Attention, les séries de Riemann ne sont définies que pour un exposant fixe.

## Séries absolument convergentes
Une nouvelle façon de conclure un convergence : la convergence absolue.

> Soit $u \in \mathbb{K}^{\mathbb{N}}$, on dit que la série $\sum u_n$
> converge absolument si la série $\sum |u_n| \in \mathbb{R}_{+}^{\ast}$ converge.

> Une série absolument convergente converge, et de plus, on a dans ce cas
> $|\sum\limits_{n = 0}^{+\infty} u_n| \leq \sum\limits_{n = 0}^{+\infty} |u_n|$.

__Preuve :__
- Si $u \in \mathbb{R}_{+}^{\mathbb{N}}$, alors $\sum u_n$ CVA (convergente
  absolue) si et seulement si elle converge tout court.
- Si $u \in \mathbb{R}^{\mathbb{N}}$, on introduit $\forall n \in \mathbb{N}$
  les valeurs $u_{n}^{+} = \text{max}(u_{n},0)$
  et $u_{n}^{-} = \text{max}(0,-u_n)$, et ces valeurs sont des suites
  de $\mathbb{R}_{+}^{\mathbb{N}}$. Leur somme est $|u|$ et leur différence est
  $u$. Or, $0 \leq u^{+} \leq |u|$ et $0 \leq u^{-} \leq |u|$.
  On suppose que la série $\sum |u_n|$ à termes positifs,
  donc $\sum (u_{n}^{+} - u_{n}^{-})$ converge, donc $\sum u_{n}$ converge.
  On peut faire une étude similaire pour les suites complexes avec
  en utilisant le module des parties réelles et imaginaires.

La réciproque est fausse, et donc on ne peut utiliser le critère que dans un
sens. Un des imposteurs est $\sum\limits_{n \geq 1} \frac{(-1)^{n-1}}{n}$,
qui converge mais pas absolument.\
On prouve que celle-ci converge en remplaçant $\frac{1}{n}$ par
$\int\limits_{0}^{1} t^{n-1} dt$.

## Séries géométriques dérivées
> Soit $z \in \mathbb{C}$, les séries $\sum\limits_{n \geq 0} z^n$,
> $\sum\limits_{n \geq 0} n z^{n-1}$ et $\sum\limits_{n \geq 0} n (n - 1) z^{n-2}$
> convergente absolument si et seulement si $|z| < 1$,
> et dans ce cas, elles convergente respectivement vers
> $\frac{1}{1 - z}$, $\frac{1}{(1 - z)^2}$
> et $\frac{2}{(1 - z)^3}$.

## Séries alternées
> CSA, critère des séries alternées : Soit $(a_n)_n$ une suite réelle décroissante
> et de limite nulle, la série alternée $\sum\limits_{n \geq 0} (-1)^n a_N$
> converge. De plus, le reste de la série est du signe de son premier terme et il
> est borné par son premier terme : si $R_n = \sum\limits_{k = n+1}^{+\infty} (-1)^k a_k$,
> alors $|R_n| \leq a_{n+1}$.

__Application :__ Formule de Stirling : $n! \underset{n \to \infty}{\sim} \sqrt{2 \pi n} (\frac{n}{e})^n$\
On cherche à montrer qu'il existe $K > 0$ tel que $n! \underset{n \to \infty}{\sim} K \sqrt{n} n^{n} e^{-n}$.
On regarde $u_{n} = \ln(\frac{n!}{\sqrt{n} n^n e^{-n}})$. Celle-ci converge par
la convergence de sa série télescopique. On a l'asymptotique de $u_{n+1} - u_{n}$
$= \ln(\frac{(n+1)!}{\sqrt{n+1} (n+1)^{n+1} e^{-(n+1)}} \times \frac{\sqrt{n} n^n e^{-n}}{n!})$\
$= \ln(\frac{\sqrt{n} n^n e^1}{\sqrt{n+1} (n+1)^n})$\
$= \ln(\frac{n^{n + \frac{1}{2}}}{(n+1)^{n + \frac{1}{2}}} e)$\
$= 1 - (n + \frac{1}{2}) \ln(1 + \frac{1}{n})$\
$= 1 - (n + \frac{1}{2}) [\frac{1}{n} - \frac{1}{2n^2} + O(\frac{1}{n^3})]$\
$= 1 - 1 + \frac{1}{2n} - \frac{1}{2n} + O(\frac{1}{n^2})$,
donc $u_{n+1} - u_{n} \underset{+\infty}{=} O(\frac{1}{n^2})$ donc la série
$\sum (u_{n+1} - u_{n})$ converge absolument et donc la suite $u$ converge.\
On note $\ell = \lim\limits_{n \to + \infty} u_{n}$. Par continuité de
l'exponentielle, $e^{\ell} = \lim\limits_{n \to + \infty} e^{u_{n}} = \lim\limits_{n \to + \infty} (\frac{n!}{\sqrt{n} n^n e^{-n}})$,
donc $n! \underset{\infty}{\sim} e^{\ell} \sqrt{n} n^n e^{-n}$.

On cherche maintenant à déterminer cette constante. On pose $I_n = \int\limits_{0}^{\frac{\pi}{2}} (\sin t)^n dt$,
et alors $I_0 = \frac{\pi}{2}$. $I_{2n+2} = (\sin t) \times (\sin t)^{2n + 1} dt$
$= \,\text{(IPP)}\, [- \cos(t) (\sin(t))^{2n+1}]_0^{\frac{\pi}{2}} - \int\limits_{0}^{\frac{\pi}{2}} (- \cos t) (2n + 1) (\cos t) (\sin t)^{2n} dt$
$= 0 + (2n + 1) (I_{2n} - I_{2n + 1})$, et
donc $(2n + 2) I_{2n + 2} = (2n + 1) I_{2n}$.
Ainsi, $(2n + 2) I_{2n + 2} \times I_{2n + 1} = (2n + 1) I_{2n + 1} I_{2n}$,
donc la suite $((n+1) I_{n+1} I_n)_n$ est constante égale à
$I_1 I_0 = \frac{\pi}{2}$.\
On vérifie que $(I_n)_n$ est décroissante. $\forall t \in [0;\frac{\pi}{2}]$,
$(\sin t)^{n} \geq (\sin t)^{n+1} > 0$. En intégrant, on obtient
$I_n \geq I_{n+1} > 0$, donnant $I_{n-1} \geq I_n \geq I_{n+1}$
$\Rightarrow I_n I_{n-1} \geq I_n^2 \geq I_n I_{n+1}$
$\Rightarrow \frac{\pi}{2n} \geq I_n^2 \geq \frac{\pi}{2 (n+1)}$,
donc $I_n^2 \underset{+\infty}{\sim} \frac{\pi}{2n}$,
donc $I_{n} \underset{\infty}{\sim} \sqrt{\frac{\pi}{2n}}$,
donc $I_{2n} \underset{+\infty}{\sim} \frac{\sqrt{\pi}}{2 \sqrt{n}}$,
or $I_{2n} = \frac{2n - 1}{2n} I_{2n - 2} = \frac{2n - 1}{2n} \times \frac{2n - 3}{2n - 2} I_{2n - 4}$
$= \,\text{(En itérant)}\, \frac{\frac{(2n)!}{2^n n!}}{2^n n!} \frac{\pi}{2}$
$= \binom{2n}{n} \frac{\pi}{2 \times 4^n} \underset{+\infty}{\sim} \frac{\sqrt{\pi}}{2 \sqrt{n}}$.

Or, $n! \underset{+\infty}{\sim} K \sqrt{n} n^n e^{-n}$ donc
$(2n)! \underset{+\infty}{\sim} K \sqrt{2n} (2n)^{2n} e^{-2n}$,
et on a $(n!)^2 \underset{+\infty}{\sim} K^2 n n^{2n} e^{-2n}$
et $(2n)! \underset{+\infty}{\sim} K \sqrt{2n} 2^{2n} n^{2n} e^{-2n}$.
Finalement, $I_{2n} = \frac{(2n)!}{(n!)^2} \frac{\pi}{4^n \times 2} \underset{+\infty}{\sim} \frac{\sqrt{2} \pi}{K \sqrt{n} 2} \underset{+\infty}{\sim} \frac{\pi}{K \sqrt{2n}}$.
Or $I_{2n} \underset{+\infty}{\sim} \frac{\sqrt{\pi}}{2 \sqrt{n}}$ donc $K = \sqrt{2 \pi}$.

## Autres critères
> Critère de D'alembert : Soit $u \in \mathbb{K}^{\mathbb{N}}$ telle que $u$ ne
> s'annule pas à partir d'un certain rang, et telle que $\lim\limits_{n \to + \infty} |\frac{u_{n+1}}{u_{n}}| = \ell \in \mathbb{R}_{+} \cup \{+\infty\}$.
> - Si $\ell < 1$, alors la série converge absolument
> - Si $\ell > 1$ la série diverge grossièrement
> - Si $\ell = 1$, on ne peut pas conclure

__Preuve :__
- Si $\ell < 1$, soit $k = \frac{\ell + 1}{2}$, $\ell < k < 1$, et par
  définition de la limite, $\exists n_0, \forall n \geq n_0, |\frac{u_{n+1}}{u_{n}}| \leq k$.
  En prenant $\varepsilon = \frac{1 - \ell}{2} > 0$. $\forall n \geq n_0$,
  $|u_{n+1}| \leq k |u\bigcap\limits_{i \in  I} |$, donc par récurrence
  $\forall n \geq n_0, |u_{n}n| \leq k^{n - n_0} |u_{n_0}|$.
  $|u_{n}| = O(k^n)$ avec $k < 1$. Or $\sum k^n$ est géométriquement
  convergente, donc par comparaison de sommes à termes positifs, la somme
  absolue converge, donc la série converge absolument.
- Si $\ell > 1$, à partir d'un certain rang, $|\frac{u_{n+1}}{u_{n}}| > 1$,
  donc la suite de la valeur absolue de $u_{n}$ est croissante à partir d'un certain rang
  donc la limite n'est pas nulle, donc $u_{n}$ ne tend pas vers $0$, donc la
  série diverge grossièrement.
- Pour $\ell = 1$ on a les exemples de $u_{n} = n$ qui diverge et $u_{n} = \frac{1}{n^2}$ qui converge,
  donc on ne peut pas conclure.
