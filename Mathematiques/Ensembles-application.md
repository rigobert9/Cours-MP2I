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
alors $\mathcal{P}(E)$ est fini et possède $2^n$.
En effet, pour $k \in [0,n]_{\mathbb{N}}$, on note $\mathcal{P}_k(E)$ l'ensemble des
parties à k éléments de E (ce qui donne $\mathcal{P}_0(E) = \{\emptyset\}$ et $\mathcal{P}_n{E} = \{E\}$).
On a alors $\mathcal{P}(E) = \bigcup\limits_{k = 0}^n \mathcal{P}_k(E)$, et on a donc
$\text{card}(\mathcal{P}(E)) = \sum\limits_{k = 0}^{n}\text{card}(\mathcal{P}_(E))$\
$= \sum\limits_{k = 0}^{n}\binom{n}{k}$\
$= 2^n$

##### Exemple :
$E = \{a, b, c\}, \mathcal{P}(E) = \{\emptyset, \{a\}, \{b\}, \{c\}, \{a,b\}, \{a,c\}, \{b,c\}, \{a,b,c\}\}$
$\mathcal{P}(E)$ contient ici 8 éléments.

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

##### Exemple
Soit $\begin{aligned} f: \mathbb{R} &\to \mathbb{R} \\ x &\mapsto f(x) = \frac{e^x - e^{-x}}{e^x + e^{-x}} .\end{aligned}$.
On cherche à montrer que $f$ réalise une bijection de $\mathbb{R}$ dans un
intervalle I à préciser.
Soit $y \in \mathbb{R}$, on résout $y = f(x)$. $y = \frac{e^x - e^{-x}}{e^x + e^{-x}}$\
$\Leftrightarrow (e^x + e^{-x})y = e^x - e^{-x}$\
$\Leftrightarrow \left\{\begin{matrix} X = e^x \\ (X + \frac{1}{X})y = X - \frac{1}{X} \end{matrix}\right.$\
$\Leftrightarrow \left\{\begin{matrix} X = e^x \\ (X^2 + 1)y = X^2 - 1 \end{matrix}\right.$\
$\Leftrightarrow \left\{\begin{matrix} X = e^x \\ X^2(y-1) = -y - 1 \end{matrix}\right.$
(On peut voir ici qu'il n'y a pas de solution en $y = 1$, donc on continue avec
$y \neq 1$. Dans tous les cas, $f$ n'est pas bijective dans $\mathbb{R}$.)\
$\Leftrightarrow \left\{\begin{matrix} X = e^x \\ X^2 = \frac{1 + y}{1 - y} \end{matrix}\right.$\
$\Leftrightarrow \left\{\begin{matrix} y \neq 1 \\ e^{2x} = \frac{1 + y}{1 - y} \end{matrix}\right.$
(on ne trouve ici qu'un seule solution)\
$\Leftrightarrow \left\{\begin{matrix} y \neq 1 \\ \frac{1 + y}{1 - y} > 0 \\ x = \frac{1}{2}\ln(\frac{1+y}{1-y}) \end{matrix}\right.$

On doit donc chercher quand $\frac{1+y}{1-y} > 0$, et on a à l'aide d'un tableau
de signes $\frac{1+y}{1-y} > 0 \Leftrightarrow y \in ]-1;1[$. Ainsi, on a
$\forall y \in ]-1;1[, \exists! x \in \mathbb{R}, y = f(x)$, et $f$ est
bijective de $\mathbb{R}$ dans $]-1;1[$.

On peut voir cette même bijection dans un simple tableau de signes de f, dans
lequel on pourrait voir que f est continue sur $\mathbb{R}$ et que ses bornes
sont en $]-1;1[$.

## Composition
Avec trois ensembles $E,F,G$, une application $f: E \to F$ et une application
$g: F \to G$, on a alors une application composée $g \circ f: E \to G$.

> Soit $f \in \mathcal{F}(E,F)$ et $g \in \mathfrak{F}(F,G)$, la composée de f par
> g, notée $g \circ f$, est l'application $\begin{aligned} g \circ f: E &\to G \\ x &\mapsto g \circ g \circ f(x) = g(f(x)) .\end{aligned}$

On a $\forall x \in E (g \circ f)(x) = g(f(x))$.

- $\circ$ est non commutative dans la plupart des cas : $f \circ g \neq g \circ f$
- $\circ$ est associative : soient $f \in \mathfrak{F}(E,F), g \in \mathfrak{F}(F,G),$
  $h \in \mathfrak{F}(G,H), (h \circ g) \circ f = h \circ (g \circ f)$

##### Preuve de l'associativité de $\circ$
$\forall x \in E, ((h \circ g) \circ f)(x) = (h \circ g)(f(x))$\
$= h(g(f(x))) = h((g \circ f)(x)) = (h \circ (g \circ f))(x)$

### Composition répétée
Ainsi, on pourra écrire sans ambiguité $h \circ g \circ f$.
De plus, quand $f \in \mathfrak{F}(E,E)$, on peut définir $f \circ f$, et donc
$f \circ f \circ \ldots \circ f \,\text{(n fois)}= f^n$ (avec $n \in \mathbb{N}^{\ast}$).

Les fonctions qui ont le même ensemble de départ et d'arrivée ont le préfixe
"endo-".

Avec $f \in \mathfrak{F}(E,F)$, on a $f \circ id_E = f$ et $id_F \circ f = f$
(attentions aux ensembles/types de départ et d'arrivée).
Dans le cas particulier où $f \in \mathfrak{F}(E,E), id_E \circ f = f \circ id_E = f$.
On posera donc $\left\{\begin{matrix} f^0 = id_E \\ f^{n+1} = f^n \circ f, n \in \mathbb{N} \end{matrix}\right.$

### Liens entre injectivité, surjectivité et composition
Soient $f \in \mathfrak{F}(E,F)$ et $g \in \mathfrak{F}(F,G)$ :
1. Si f et g sont injectives, alors $g \circ f$ est injective
2. Si f et g sont surjectives, alors $g \circ f$ est surjective
3. Si f et g sont bijectives, alors $g \circ f$ est bijective

##### Preuve
1. Supposons $f,g$ injectives. On cherche à montrer que $g \circ f$ est
   injective. Avec $a,b \in E$ tels que $(g \circ f)(a) = (g \circ f)(b)$.
   $\Leftrightarrow g(f(a)) = g(f(b))$. Par injectivité de $g$, $f(a) = f(b)$,
   puis par injectivité de f, $a = b$.
2. On suppose $f,g$ surjectives. On cherche à montrer que $g \circ f$ est
   surjective. Soit $z \in G$, comme $g$ est surjective, z admet un antécédent
   dans $F$ par $g$, donc $\exists y \in F, z = g(y)$. Comme f est surjective, y
   admet un antécédent dans E par f, $\exists x \in E, y = f(x)$. Ainsi
   $z = g(y) = g(f(x)) = (g \circ f)(x)$, donc $x$ est un antécédent de $z$ par
   $g \circ f$, et on a montré que $\forall z \in G, \exists x \in E, z = (g \circ f)(x)$.
3. On suppose $f,g$ bijectives. Commes elles sont toutes deux surjectives et
   injectives, on applique les deux preuves ci-dessus.

#### Ces propriétés ne sont pas réciproques
Néanmoins, on a les propriétés suivantes, avec $f \in \mathfrak{F}(E,F)$ et
$g \in \mathfrak{F}(E,F)$ :
1. Si $g \circ f$ est injective, alors $f$ est injective
2. Si $g \circ f$ est surjective, alors $f$ est surjective

##### Preuve
1. On cherche à montrer que $f$ est injective. Soit $(a,b) \in E^2$ tel que
  $f(a) = f(b)$, alors $g(f(a)) = g(f(b))$, donc $(g \circ f)(a) = (g \circ f)(b)$.
  Par injectivité de $g \circ f$, $a = b$, donc $f$ est injective.
2. on cherche à montrer que $g$ est surjective. Soit $z \in G$, par subjectivité
   de $g \circ f$, $\exists x \in E, (g \circ f)(x) = z$ donc $g(f(x)) = z$ et
   $f(x) \in F$ est ainsi un antécédent de $z$ par $g$. On peut poser $y = f(x) \in F$
   et on a bien montré $\forall z \in G, \exists y \in F, g(y) = z$. Ainsi, $g$
   est surjective.

##### Exemple : ensemble des polynômes
Soit $E$ l'ensemble des polynômes réels (fonctions polynomiales de $\mathbb{R}$
dans $\mathbb{R}$).
Soit $\begin{aligned} f: E &\to E \\ P &\mapsto f(P) = P' .\end{aligned}$ et
$\begin{aligned} g: E &\to E \\ P &\mapsto g(P) = \int\limits_{0}^{x} P(t)dt .\end{aligned}$.

- $f$ n'est pas injective car $f(2X + 3) = (2X + 3)' = 2$ et $f(2X+1) = (2X+1)' = 2$.
- Pour ce qui est de la surjectivité, soit $Q$ un polynôme, on cherche s'il
  existe un antécédent $P$ par $f$, soit $P$ tel que $f(P) = Q$.
  On prend $P$ une primitive de $Q$ (qui est bien un polynôme). Explicitement,
  avec $Q = \sum\limits_{k = 0}^{n}a_k K^k$, donc on a
  $P = \sum\limits_{k = 0}^{n}\frac{a_k}{k+1}X^{k+1}$. On a donc bien $P' = Q$,
  donc $f$ est surjective.

- Si $P_1,P_2$ deux polynômes tels que $g(P_1) = g(P_2)$, on a alors
  $\left\{\begin{matrix} (g(h))' = P_1 \,\text{car}\, g(P_1) \,\text{est une primitive de}\, P_1 \\ (g(P_2))' = P_2 \end{matrix}\right.$,
  d'où $P_1 = P_2$ donc $g$ est injective.
- g n'est pas surjective car 1 n'a pas d'antécédent par $g$, car 1 ne s'annule
  pas en 0. Or toutes les images $g(P)$ sont des polynômes qui s'annulent en 0.

On peut voir que $f \circ g = id_E$, car soit $P$ un polynôme, $g(P)$ est la
primitive de $P$ s'annulant en 0 et $f(g(P)) = (g(P))' = P$.

On peut aussi voir que $g \circ f \neq id_E$.
