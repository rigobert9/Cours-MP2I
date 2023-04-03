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
