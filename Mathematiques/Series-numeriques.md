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
