# Ensembles et applications
## Ensembles
### Définition
#### Notion d'ensemble
> Un ensemble E est une collection d'objets, qu'on appelle des éléments. On note
> $x \in E$, "l'élément x est dans l'ensemble E" et $E \ni x$, "l'ensemble E
> contient l'élément"

> L'ensemble ne contenant aucun élément est appelé ensemble vide et est noté $\emptyset$

##### Exemples : définitions d'ensembles
- Définition par extension : $P = \{0, 2, 4, \ldots\} = \{2n, n \in \mathbb{N}\}$
- Définition par compréhension : $P = \{n \in \mathbb{N} \mid n \equiv 0[2]\}$
  $= \{n \in \mathbb{N} \mid \frac{n}{2} \in \mathbb{N}\}$
  (Définition par éventuellement un autre ensemble, et un prédicat : tous les
  éléments respectant le prédicat font partie de l'ensemble). On peut définir
  ainsi, à partir des l'ensembles des naturels et des réels les ensembles
  remarquables suivants :
  - Pour les nombres relatifs : $\mathbb{Z} = \{n \mid (n \in \mathbb{N} \lor -n \in \mathbb{N})\}$
  - Pour les rationnels : $\mathbb{Q} = \{\frac{p}{q} \mid p \in \mathbb{Z} \land q \in \mathbb{N}^{\ast}\}$
  - Pour les décimaux : $\mathbb{D} = \{\frac{p}{10^k} \mid p \in \mathbb{Z}^{\ast} \land k \in \mathbb{N}\}$
  - Pour les complexes : $\mathbb{C} = \{a+ib \mid (a,b) \in \mathbb{R}^2\}$

#### Inclusion
> Soient E et F deux ensembles, on dit que E est inclus dans F, noté $E \subset F$
> si $\forall x \in E, x \in F$ (tous les éléments de E sont des éléments de F).
> On dit alors que E est une partie ou un sous ensemble de F.

> On dit que E et F sont égaux si $E \subset F \land F \subset E$. On note $E = F$

On peut alors prouver l'égalité de deux ensembles par double inclusion.

Par définition, on a $E \subset E$ et $\emptyset \subset E$.

Propriétés de l'inclusion :
- Transitivité : Si $E \subset F$ et si $F \subset G$, alors $E \subset G$
- Antisymétrie : Si $E \subset F$ et $F \subset E$, alors $E = F$

##### Preuve de la transitivité
$\forall x \in E, E \subset F \Rightarrow x \in F$\
$\forall y \in F, F \subset G \Rightarrow y \in G$\
$\forall x \in E, x \in F \Rightarrow x \in G$\
$\Leftrightarrow E \subset G$

### Opérations ensemblistes
> Soient E, F deux ensembles :
> - L'union de E et F, notée $E \cup F$ est définie par : $x \in E \cup F \Leftrightarrow (x \in E \lor x \in F)$
> - L'intersection de E et F, notée $E \cap F$ est définie par : $x \in E \cap F \Leftrightarrow (x \in E \land x \in F)$
> - La différence de E et de F, notée $E \setminus F$ ("E privé de F") est définie par : $x \in E \setminus F \Leftrightarrow (x \in E \land x \not\in F)$

> Soit A une partie de E, son complémentaire relativement à E est noté $\overline{A} = E \setminus A$.

##### Exemple : double complémentaire
$\overline{\overline{A}} = \overline{E \setminus A} = E \setminus (E \setminus A)$.
On a alors $x \in \overline{\overline{A}} \Leftrightarrow x \not\in \overline{A}$\
$\Leftrightarrow \neg (x \in \overline{A})$\
$\Leftrightarrow \neg (x \not\in A)$\
$\Leftrightarrow \neg (\neg (x \in A))$\
$\Leftrightarrow x \in A$

#### Lien aux opérations logiques
Lois de Morgan : Soit A et B deux sous-ensembles de E (prouvable par un élément,
comme les autres propriétés) :
- $\overline{A \cup B} = \overline{A} \cap \overline{B}$
- $\overline{A \cap B} = \overline{A} \cup \overline{B}$

Distributivité :
- $A \cap (B \cup C) = (A \cap B) \cup (A \cap C)$
- $A \cup (B \cap C) = (A \cup B) \cap (A \cup C)$

> Union et intersection quelconque : Soit E un ensemble et $(A_i)_{i \in I}$ une famille
> quelconque de parties de E, avec I un ensemble d'indices quelconques.
> - L'union des $A_i$, notée $\bigcup\limits_{i \in I} A_i$, est définie par
>   $x \in \bigcup\limits_{i \in I} A_i \Leftrightarrow \exists i \in I, x \in A_i$
> - L'intersection des $A_i$, notée $\bigcap\limits_{i \in I} A_i$, est définie par
>   $x \in \bigcap\limits_{i \in I} A_i \Leftrightarrow \forall i \in I, x \in A_i$

#### Partition d'un ensemble
> Soit E un ensemble, et $(A_i)_{i \in I}$ une famille de parties de E. On dit que
> $(A_i)_{i \in I}$ est une partition de E si les $A_i$ sont deux à deux
> disjoints, non vides, et de réunion E tout entier.

On peut résumer ces conditions sous la forme :
$\left\{\begin{matrix} \forall i \in I, A_i \neq \emptyset \\ \forall (i,j) \in I^2, i \neq j \Rightarrow A_i \cap A_j = \emptyset \\ \bigcup\limits_{i \in I} A_i = E \end{matrix}\right.$

En probabilité, une telle partition d'un univers est souvent utilisée et est
identique.

### Ensemble des parties
> Soit E un ensemble, on note $\mathfrak{P}(E)$ l'ensemble de tous les sous-ensembles de E.
> Ainsi,pour tout ensemble A, $A \in \mathfrak{P}(E) \Leftrightarrow A \subset E$

On pout remarquer que si E est fini et possède $n \in \mathbb{N}$ éléments,
alors $\mathfrak{P}(E)$ est fini et possède $2^n$.
En effet, pour $k \in [0,n]_{\mathbb{N}}$, on note $\mathfrak{P}_k(E)$ l'ensemble des
parties à k éléments de E (ce qui donne $\mathfrak{P}_0(E) = \{\emptyset\}$ et $\mathcal{P}_n{E} = \{E\}$).
On a alors $\mathfrak{P}(E) = \bigcup\limits_{k = 0}^n \mathcal{P}_k(E)$, et on a donc
$\text{card}(\mathfrak{P}(E)) = \sum\limits_{k = 0}^{n}\text{card}(\mathcal{P}_(E))$\
$= \sum\limits_{k = 0}^{n}\binom{n}{k}$\
$= 2^n$

##### Exemple :
$E = \{a, b, c\}, \mathfrak{P}(E) = \{\emptyset, \{a\}, \{b\}, \{c\}, \{a,b\}, \{a,c\}, \{b,c\}, \{a,b,c\}\}$
$\mathfrak{P}(E)$ contient ici 8 éléments.

### Produit cartésien
> Soient E, F deux ensembles, on appelle couple l'objet $(x,y)$ où $\left\{\begin{matrix} x \in E \\ y \in F \end{matrix}\right.$.
> L'ensemble de tous les couples est le produit cartésien $E \times F$,
> $E \times F = \{(x, y), x \in E \land y \in F\}$.
> Ce produit n'est pas commutatif, et les couples sont ordonnés.

Les couples ne sont égaux que avec $(x,y) = (x', y') \Leftrightarrow \left\{\begin{matrix} x = x' \\ y = y' \end{matrix}\right.$.

> Ne pas confondre une paire (un ensemble à deux éléments) et un couple (2
> coordonées ordonnées).

De façon générale, on a avec $E_1, E_2, \ldots, E_p$ des ensembles, $E_1 \times E_2 \times \ldots E_p$
$= \{(x_1, x_2, \ldots, x_p), \forall i, x_i  \in E_i\}$. On peut aussi noter
$E^p$ l'ensemble des p-uplets de E.

On peut bien noter des produits cartésiens successifs sous la forme
$\prod\limits_{i = 1}^{p} E_i = E_1 \times E_2 \times \ldots \times E_p$, mais
le produit cartésien étant non commutatif, de nombreuses opérations sur les
produits algébriques sont impossibles.

## Applications
### Définition
#### Applications de base
> On appelle application de E dans F toute correspondance entre E et F qui à
> __tout élément__ x de l'ensemble E lui associe un unique élément y dans F

On note alors : $\forall x \in E, \exists! y \in F, y = f(x)$, ce qui donne pour
la fonction f $f: E \to F$, où plus en détail $f: \begin{matrix} E \to F \\ x \mapsto y = f(x) \end{matrix}$.

On dit que $y = f(x)$ est l'image de x par f.

Quand E, F sont des sous-ensembles de $\mathbb{R}$, on confond application et
fonction, ainsi que leur notations. Il faut néanmoins bien les séparer.

> Soit $f: E \to F$, le graphe $\Gamma_f$ de f est défini par $\Gamma_f = \{(x,f(x)) \in E \times F, x \in E\}$.
> $\Gamma_f$ est une partie de $E \times F$.

Pour $(x,y) \in \Gamma_f$, on a :
- $y = f(x)$
- y est l'image de x
- x est un antécédent de y

On note alors $\mathcal{F}(E,F)$ ou $F^E$ l'ensemble des applications de E dans F.

**Égalité** : Soient $f,g \in \mathcal{F}(E,F), f = g \Leftrightarrow \forall x \in E, f(x) = g(x)$

> L'identité de E est la fonction $\begin{aligned} id_E: E &\to E \\ x &\mapsto id_E(x) = x .\end{aligned}$

On note l'application plutôt qu'un fonction, dans le cas d'une fonction $f$, $\tilde{f}$.

Les applications ne se font que d'un seul ensemble à un seul autre ensemble.

##### Exemple
Soit E un ensemble et A une partie de E, on définit
$\begin{aligned} \varphi: \mathfrak{P}(E) &\to \mathcal{P}(E) \\ X &\mapsto \varphi(X) = X \cap A .\end{aligned}$.
On peut montrer que $\forall X \in \mathfrak{P}(E), \varphi(X) \in \mathcal{P}(A)$. En effet,
$\varphi(X) = X \cap A \subset A$ donc $\varphi(X) \in \mathfrak{P}(a)$.

##### Exemple : Fonction indicatrice d'un ensemble
Soit E un ensemble et A une partie de E. On pose
$\begin{aligned} {1}_A: E &\to \{0,1\} \\ x &\mapsto {1}_A(x) = \left\{\begin{matrix} 1 \,\text{si}\, x \in A \\ 0 \,\text{sinon}\, \end{matrix}\right. .\end{aligned}$.
On a $\forall x \in E, x \in A \Leftrightarrow {1}_A(x) = 1$.
La fonction indicatrice ${1}_A$ permet de savoir si un élément de E fait
partie de A (c'est une fonction qui vérifie l'appartenance à un ensemble, comme
des fonction CamL, Python ou les prédicats de LisP vérifient l'appartenance à un
type ou le respect d'une condition).

##### Exemple : Les suites sont des applications
Soit $u = (u_n)_{n \in \mathbb{N}}$ une suite réelle, c'est l'application
$\begin{aligned} u: \mathbb{N} &\to \mathbb{R} \\ n &\mapsto u(n) = u_n .\end{aligned}$.
L'ensemble des suites réelles est donc noté $\mathbb{R}^\mathbb{N}$.

#### Prolongements et restrictions
> Prolongement/restriction : Soient $f: E \to F$, et A une partie de E,
> l'application $\begin{aligned} \tilde{f}: A &\to F \\ x &\mapsto f(x) .\end{aligned}$
> est la restriction de f à A. On la note aussi $f\restriction_A$ ("f restreinte à A").

Soit $f: A \to F$ et avec $A \subset E$, on dit que $g: E \to F$ est un
prolongement de $f$ si $\forall x \in A, f(x) = g(x)$

##### Exemple : la valeur absolue est une restriction du module
$\begin{aligned}  f: \mathbb{R} &\to \mathbb{R}\_{+} \\ x &\mapsto f(x) = |x| .\end{aligned}$ 
et
$\begin{aligned}  g: \mathbb{C} &\to \mathbb{R}\_{+} \\ x &\mapsto f(x) = |x| .\end{aligned}$.
f est une restriction de g en $\mathbb{R}$, $f = g\restriction_\mathbb{R}$

##### Exemple : prolongement continu
$\begin{aligned} f: \mathbb{R}^{\ast}\_{+} &\to \mathbb{R} \\ x &\mapsto f(x) = x\ln(x) .\end{aligned}$, avec f continue sur $\mathbb{R}^{\ast}\_{+}$.
$\lim_{x \to 0^{+}} x\ln(x) = 0$ par croissances comparées. On pose
$\tilde{f}$
...

### Injectivité, Surjectivité et Bijectivité
#### Injectivité
> Soit $f: E \to F$ une application. f est dite injective si 
> $(\forall (x,y) \in E^2, f(x) = f(y) \Rightarrow x = y)$.

La contraposée est aussi vraie : $\forall (x,y) \in E^2, x\neq y \Rightarrow f(x) \neq f(y)$.

Attention, il est important lorsqu'on utilise des fonctions de bien les définir
comme des applications, car la propriété d'injectivité peut être différent selon
les ensembles de départ et d'arrivée de l'application.

On peut formuler cette propriété : Si et seulement f est injective,
tout élément y dans l'ensemble d'arrivée admet __au plus un__ antécédent dans
l'ensemble de départ, soit $\forall y \in F$, l'équation $y = f(x)$ d'inconnue
$x \in E$ admet au plus une solution. Ainsi, par exemple, la fonction identité
est injective.

> Soit $f: I \to \mathbb{R}$, où I est un intervalle de $\mathbb{R}$, si f est
> strictement monotone, alors f est injective.

##### Preuve : Les fonctions monotones sont injectives
Si $(x,y) \in I^2$, avec $x \neq y$. Supposons $x < y$, par stricte monotonie de
f, on aura bien $f(x) \neq f(y)$.
Ainsi, f est injective.

#### Surjectivité
> Soit $f: E \to F$, f est surjective si $\forall y \in F, \exists x \in E, y = f(x)$.
> Tout élément de F (espace d'arrivée) admet donc __au moins un__ antécédent par f
> dans E (l'espace de départ).

Attention ! Cela signifie bien (ne pas faire de raccourcis logiques qui risquent
de ne pas respecter les conditions) que pour tout $y \in F$, l'équation $y = f(x)$ admet
__au moins une__ solution $x \in E$ (elle ne doit pas être hors de E).

#### Bijection
> Soit $f: E \to F$, f est bijective si f est injective __et__ surjective.

Ainsi, f est bijective si et seulement si tout élément de F __admet strictement un__
antécédent, donc $\forall y \in F, \exists! x \in E, y = f(x)$.

On a ainsi l'existence demandée par la surjectivité et l'unicité demandée par
l'injectivité.

##### Exemple : fonctions bijectives
$\sin : [\frac{\pi}{2};\frac{\pi}{2}] \to [-1;1]$ est bijective.
