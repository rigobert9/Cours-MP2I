# Logique propositionnelle
## Formule propositionnelles
> On se donne $V$ un ensemble infini dénombrable de variables propositionnelles
> (en pratique notées par des lettres), on appelle ensemble des formules propositionnelles
> sur $V$ l'ensemble inductif $\mathcal{F}$ défini par $\mathcal{F} = V \mid \top \mid \bot$
> $\mid \neg (\mathcal{F}) \mid \land(\mathcal{F} \times \mathcal{F}) \mid \lor(\mathcal{F} \times \mathcal{F})$,
> où $\neg$ est un constructeur d'arité $1$ et $\land$, $\lor$ sont des
> constructeurs d'arité $2$ (éventuellement enrichis des constructeurs d'arité $2$
> $\Rightarrow$ et $\Leftrightarrow$).

$V \cup \{\top; \bot\}$ est l'ensemble des constructeurs constants.

Une formule est donc par exemple $\Rightarrow(A, \land(\Leftrightarrow(\land(B;\top);A);C))$.

On peut réécrire cette définition plus mathématiquement, comme le plus petit
ensemble de mot de l'alphabet $V \cup \{\top;\bot;\neg;\land;\lor;\Rightarrow;\Leftrightarrow;(;)\}$,
tel que $V \cup \{\top;\top\} \subset \mathcal{F}$ et que les formules formées
autour de chaque connecteur soient inclues dans $\mathcal{F}$.

Cette définition des formules logiques comme des mots sur un alphabet correspond
à l'approche historique de la logique propositionnelle, mais n'est pas la plus
simple à manipuler et n'offre pas beaucoup de propriétés.

> Étant donnée une formule propositionnelle, construite avec l'approche
> historique, il existe une unique formule sous forme d'arbre.

$V$ est supposé infini car ceci permet pour toute formule (nécessairement finie)
d'avoir une variable $X \in V$ non utilisée dans la formule.

On suivra ici les conventions suivantes :
- On ne note pas les parenthèse extérieures
- On utilise l'ordre de priorité suivant : $\neg, \land \text{ et } \lor, \Leftrightarrow, \Rightarrow$
- Parmi les opérateurs de même priorité, on prend la priorité à gauche

> On appelle sous-formule immédiate de $f \in \mathcal{F}$ un des sous-termes
> immédiats (dans une approche d'ensemble inductif). On appelle sous-formule l'un
> de ses sous-termes.

> Soit $f \in \mathcal{F}$, on appelle taille de $f$ le nombre de connecteurs
> logiques de $f$ (le nombre de constructeurs non constants). On appelle hauteur
> de $f$ la hauteur de son arbre. On appelle variables de $f$ les variables qui en
> font partie, ensemble qu'on pout définir récursivement sur la formule.

## Sémantique des formules propositionnelles
On note $\mathbb{B} = \{V;F\}$ l'ensemble des booléens.

> On appelle valuation une fonction $v: V \to \mathbb{B}$.

Soit $v$ une valuation et $f$ une formule, on appelle valeur de vérité de $f$
sous la valuation $v$ $[f]_v$, le booléen correspondant à l'application des
tables de vérité sur les valuations des variables des connecteurs logiques de la
formule.

> Soit $f \in \mathcal{F}, v, v' \in \mathbb{B}^{V}$,
> si $v\restriction_{\text{Var}(f)} = v'\restriction_{\text{Var}(f)}$, alors
> $[f]_v = [f]_{v'}$.

__Preuve :__ Par induction structurelle sur $\mathcal{F}$, en initialisant sur
$\top, \bot$ ou une variable unique.\
Soit $f \in \mathcal{F} \setminus (V \cup \{\top,\bot\})$, on suppose que pour
tout sous-terme immédiat de $f$, la propriété est vraie.
- Si $f = \neg f'$, alors $\text{Var}(f) = \text{Var}(f')$,
  par hypothèse d'induction, comme les restrictions sont égales, on a
  $[f']_v = [f']_{v'}$. Ainsi,
  $[f]_v = \overline{[f']_v} = \overline{[f']_{v'}} = [f]_{v'}$.
- Et on recommence pour tous les connecteurs ...

> Soit $f \in \mathcal{F}$, on définit $T_f: \mathbb{B}^{\text{Var}(f)} \to \mathbb{B}$ la table de vérité de $f$ par
> $\forall v \in \mathbb{B}^{V}, T_f(v\restriction_{\text{Var}(f)}) = [f]_v$.

> Pour tout $f \in \mathcal{F}$, $T_f$ est bien définie et est unique.

__Preuve :__ Soit $w \in \mathbb{B}^{\text{Var}(f)}, v, v' \in \mathbb{B}^{V}$
tels que $v\restriction_{\text{Var}(f)} = v'\restriction_{\text{Var}(f)} = w$,
alors d'après ce qui précède, $[f]_v = [f]_{v'}$, $T_f(w)$ est bien définie. De
plus, pour tout $w \in \mathbb{B}^{\text{Var}(f)}$, on peut prolonger $w$ à $V$
en posant $v: X \in V \to \left\{\begin{matrix} w(x) \text{ si } X \in \text{Var}(f) \\ F \text{ sinon.} \end{matrix}\right.$.
$T_f(v)$ est donc uniquement définie pour tout $w \in \mathbb{B}^{\text{Var}(f)}$, donc $T_f$ est unique.

> Pour $v \in \mathbb{B}^{V}$, si $[f]_V = \top$, on dit que $v$ est un modèle de
> $f$. On note $\text{Mod}(f)$ les modèles de $f$, ou $v \models f$.

> Soit $f \in \mathcal{F}$, on dit que $f$ est :
> - satisfiable si $\text{Mod}(f) \neq \emptyset$
> - tautologique si $\text{Mod}(f) = \mathbb{B}^{V}$ (toujours vraie)
> - antilogique si $\text{Mod}(f) = \emptyset$
> - contingente si elle n'est ni tautologique ni antilogique

> Soient $f,f' \in \mathcal{F}$, on dit que $f$ et $f'$ sont équivalentes et on
> note $f \equiv f'$ si $\forall v \in \mathbb{B}^{V}, [f]_v = [f']_v$.

> $\equiv$ est une relation d'équivalence sur $\mathcal{F}$.

$f \in \mathcal{F}$ est une tautologie si et seulement si $f \equiv \top$.
$f \in \mathcal{F}$ si et seulement si $f \equiv \bot$.

> Soient $f,f' \in \mathcal{F}$, si $\text{Var}(f) = \text{Var}(f')$
> alors $T_f = T_{f'} \Leftrightarrow f = f'$.

On a les axiomes suivants :
- Les lois de Morgan
- $X \to Y \equiv \neg X \lor Y$
- $X \to Y \equiv \neg Y \to \neg X$
- $(X \land Y) \to Z \equiv X \to (Y \to Z)$ (Curryfication)
- $X \Leftrightarrow Y \equiv (X \to Y) \land (Y \to X)$
- Tiers exclus
- Non-contradiction
- Double négation
- Associativité et commutativité de $\land$ et $\lor$
- Distributivité de $\land$ et $\lor$ l'un sur l'autre
- $\top$ est neutre pour $\land$ et absorbant pour $\lor$
- $\bot$ est neutre pour $\lor$ et absorbant pour $\land$

> Soient $f,g \in \mathcal{F}, X \in V$, on appelle substitution de $X$ par $g$
> dans $f$ la formule ou toutes les occurrences de $X$ sont remplacées par $g$
> (on peut définir ce remplacement rigoureusement par récurrence).

> Soient $f,g_1,g_2 \in \mathcal{F},X \in V$, si $g_1 \equiv g_2$, $f^{\{x \Leftarrow g_1\}} \equiv f^{\{x \Leftarrow g_2\}}$.

> Soient $f_1,f_2,g \in \mathcal{F},X \in V$. Si $f_1 \equiv f_2$, alors $f_1^{x \Leftarrow g} \equiv f_2^{x \Leftarrow g}$.

__Preuve :__ Se réalise par induction structurelle sur $f$.

> On dit que $g$ est une conséquence sémantique du $f$ si $\forall v \in \mathbb{B}^{V}$ telle que $[f]_v = \top$
> $[g]_v = \top$. On note $f \models g$, soit que tout modèle de $f$ est un modèle
> de $g$.

Cette définition peut aussi se généraliser à un ensemble, ce qui signifie que $g$ est vrai quand
tout l'ensemble est vrai.

> Soient $(f_i)_{[\![1;n]\!]}, g, h \in \mathcal{F}, X \in V$,
> si $\{f_i\} \models g$ alors $\{f_i^{\{X \Leftarrow h\}}\} \models g^{\{X \Leftarrow h\}}$.

### Formes normales
> On appelle littéral une formule de la forme $X$ ou $\neg X$, pour $X \in V$.

> On appelle forme normale négative (NNF) une formule qui contient que des
> $\land$, $\lor$, et des littéraux (et parenthèses).

On peut donc avoir un arbre binaire avec des noeuds étiquettés par $\land$
et $\lor$, et dont les feuilles sont des littéraux.

On peut prouver l'existence de cette forme par induction, et qu'elle est bien
équivalente à la formule.

En pratique, cela revient à remplacer les $\Rightarrow$ et $\Leftrightarrow$ par
substitution, lois de Morgan et double négations.

> On appelle forme normale conjonctive (CNF), une formule de la forme
> $\bigwedge\limits_{i = 1}^{n} \bigvee\limits_{j = 1}^{m} \ell_{i,j}$
> avec $\ell_{i,j}$ des littéraux.
> On appelle forme normale disjonctive (DNF), une formule de la forme
> $\bigvee\limits_{i = 1}^{n} \bigwedge\limits_{j = 1}^{m} \ell_{i,j}$
> avec $\ell_{i,j}$ des littéraux.

Soit $f \in \mathcal{F}$, on pose $\{X_i\}_{[\![1;n]\!]} = \text{Var}(f)$, et on
assimile $\mathbb{B}^{\text{Var}(f)}$ à $\mathbb{B}^n$. On pose
$\begin{aligned} \ell: V \times \mathbb{B} &\to \mathcal{F} \\ (X;b) &\mapsto \left\{\begin{matrix} X \text{ si } b = V \\ X \text{ si } b = F \end{matrix}\right. .\end{aligned}$.
Alors $\varphi(f) = \bigvee\limits_{(b_i)_{[\![1;n]\!]} \in T_f^{-1}(\{V\})} \bigwedge\limits_{i = 1}^{n} \ell(X_i;b_i)$
est une DNF équivalente à $f$.

__Preuve :__ Pour construire $\varphi(f)$, on a pris chaque restriction à
$\text{Var}(f)$ d'un modèle $v$ de $f$, et construit une clause conjonctive
dont l'unique modèle restreint à $\text{Var}(f)$ est $v\restriction_{\text{Var}(f)} = (b_i)_{[\![1;n]\!]}$.
Or $v$ est un modèle de $\varphi(f)$ si et seulement si c'est un modèle d'une
des clauses de $\varphi(f)$, donc $v$ est un modèle de $\varphi(f)$ si et seulement si c'est un modèle de $f$.

On peut de même construire une CNF équivalente à $f$.

__Preuve :__ Soit $f \in \mathcal{F}$, $\varphi(\neg f)$ est une DNF équivalente
à $\neg f$, donc $\neg \varphi(\neg f)$ est équivalente par double négation à
$f$, et par les lois de Morgan, est une CNF.

Pour $f \in \mathcal{F}$ donnée, il se peut qu'il n'existe aucune CNF ou DNF
équivalente dont la taille soit majorée par une fonction sous-exponentielle de
la taille de $f$.

## Problème SAT
Le problème SAT consiste à déterminer si une formule $f \in m\mathcal{F}$ est
satisfiable, soit $\text{SAT}(f) \Leftrightarrow f \not\equiv \bot$.

L'algorithme naïf (algorithme de Quine) teste les possibilités de la table de
vérité, et s'arrête quand il trouve un modèle. Il est de complexité
$\Theta(m 2^n)$, avec $n$ le nombre de variable et $m$ la profondeur de la
formule.

Si $f$ est une DNF, on vérifie qu'au moins une clause est satisfiable. Cela peut
se faire en temps $O((l + n) k)$ avec un tableau de taille $n$, ou encore en
temps $O(l \log(l) k)$ en place (avec des formules de taille au plus $l$).

> Soit $f \in \mathcal{F}$ et $X \in \text{Var}(f)$, alors $\text{SAT}(f)$
> si et seulement si $\text{SAT}(\mathfrak{d\{x \Leftarrow \top\}})$
> ou $\text{SAT}(\mathfrak{d\{x \Leftarrow \bot\}})$.

CNF-SAT est le problème SAT restreint sur les formes normales conjonctives. Soit
$k \in \mathbb{N}$ avec $k \geq 2$, $k-\text{SAT}$ est le problème CNF-SAT
restreint aux formules ayant au plus $k$ littéraux.

## Logique du premier ordre
On se donne un domaine $(X,S_f,S_p)$ formé de $3$ ensemble disjoints et de
l'ensemble des connecteurs logique. $X$ est l'ensemble des symboles de variable,
$S_f$ l'ensemble des symboles de fonction (avec parfois un exposant pour
distinguer par arité, $S_f^0$ représentant les termes constants), et $S_p$
est l'ensemble des symboles de prédicats.

$X$ et $S_f$ définissent une structure inductive, les termes, sur lesquels
portent les prédicats.

> On appelle ensemble des termes et on note $T$ la structure inductive définie par
> $X$ et $S_f$, le plus petit ensemble contenant les variables, les constantes, et
> L'application aux fonctions selon leur arité.

> On appelle formule atomique une formule composée d'un prédicat prenant des
> termes selon l'arité du prédicat.

> On appelle $\mathcal{F}$ l'ensemble des formules du premier ordre la structure
> inductive définie comme le plus petit ensemble contenant les formules atomiques,
> et leurs composées par la négation, les connecteur binaires vus précédemment,
> et les quantifications universelles et existentielles des variables.

Une occurrence d'une variable $x \in X$ dans $\varphi$ est dite libre si ni $\exists x$,
ni $\forall x$ n'apparaissent comme ancêtre de la formule atomique où se trouve
cette occurrence dans $\varphi$. Une occurrence d'une variable qui n'est pas
libre est dite liée.

On peut propager par les connecteurs binaires la liaison d'une variable : la
variable est liée dans une conjonction si et seulement si elle l'est dans l'une
des formules. Il en est de même pour la négation. Dans une formule atomique,
toute variable n'est pas liée à même la formule, et elle est libre tant qu'elle
est variable d'un des termes de $\varphi$.
