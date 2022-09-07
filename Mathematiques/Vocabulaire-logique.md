# Vocabulaire logique général en mathématiques
Logique : Relations autour du concept de vérité

## Propositions logiques
### Assertion
> Une assertion est une phrase mathématique à laquelle on peut donner deux valeurs de vérité possibles (vraie ou fausse)

Une phrase mathématique est une phrase contenant :
- des constantes;
- des variables;
- des ensembles;
- des fonctions (opérations, "macros" et fonctions transcendantes) (informatiquement, une fonction renvoyant un objet, souvent de même nature/type);
- des relations (qui sont l'opération qui donne la vérité d'une assertion) (informatiquement, une fonction renvoyant une valeur de vérité);
- des connecteurs logiques (opérations booléennes, implication, équivalence);
- des quantificateurs (universels ou quantitatifs), comme $\exists$ et $\forall$

###### Exemple : "Pour tout réel x, x est un carré", soit $\forall x \in \mathbb{R} , \exists y \in \mathbb{R} , x = y^2$
Cette assertion est d'ailleurs fausse (du moins pour y réel), et comme le quantificateur est universel, il suffit de produire un contre-exemple (x = -1)
Une assertion vraie serait $\forall x \in \mathbb{R}^{+} , \exists y \in \mathbb{R} , x = y^2$
Une autre est $\forall z \in \mathbb{C} , \exists z' \in \mathbb{C} , (z')^2 = z$
(l'écriture exponentielle des complexes n'est possible que pour les complexes non nuls)

### Déclaration
Les variables introduites dans une assertion doivent être quantifiées
> Principe de tiers exclus : pour toute assertion P, on a que l'assertion P est vraie ou que l'assertion (non P) est vraie (!P, not(P)).
> Ainsi, toute assertion est vraie ou fausse.

###### Exemple : $\forall (a, b) \in \mathbb(R)^2, ab = 0 \Rightarrow (a = 0, b = 0)$
Soient a et b deux réels tels que ab = 0, par disjonction de cas:
- si a = 0, alors (a = 0 ou b = 0) est vraie
- sinon, $a \ne 0$. Or ab = 0, donc b = 0, donc (a = 0, b = 0) est vraie.

### Connecteurs logiques
(mots à prendre au sens informatique)
- Conjonction : ET, vrai uniquement si les deux assertions données sont vraies
- Disjonction : OU, vrai uniquement si au moins l'une des deux assertions est vraie
- Négation : NON, vrai seulement si l'assertion donnée est fausse

Ces trois connecteurs logiques sont les connecteurs de base. Un opérateur qui permet d'émuler ces trois opérateurs est dit former un système complet (voir opérateur de Scheffer).

Tables de vérité :

Connecteur | 0 0 | 0 1 | 1 0 | 1 1
---        | --- | --- | --- | ---
ET         | 0   | 0   | 0   | 1
OU         | 0   | 1   | 1   | 1

Connecteur | 0   | 1
---        | --- | ---
NON        | 1   | 0

> Deux assertions sont équivalentes si elles ont la même table de vérité, on
> note alors $P \equiv Q$

Un exemple d'équivalence est deux programmes, écrits éventuellement différement mais qui fournissent toujours le même résultat pour la même entrée

###### Exemple : $\text{NON (NON P)} \equiv P$ car leurs tables de vérité sont identiques.
De plus, $\text{P OU NON(P)} \equiv V$ (toujours vrai) (tautologie), et
$\text{P ET NON(P)} \equiv F$ (toujours faux) (contradiction ou antilogie)

#### Lois de Morgan :
- $\text{NON} \, (P\,\text{ET}\,Q) \equiv (\text{NON}\,P) \,\text{OU}\, (\text{NON}\, Q)$
- $\text{NON} \, (P\,\text{OU}\,Q) \equiv (\text{NON}\,P) \,\text{ET}\, (\text{NON}\, Q)$

Vérifiable par tables de vérité.
###### Exemple : Contraire de $2 \leq x \lt 3 \equiv 2 \leq \text{ET} x \lt 3$, ce qui mène avec
les lois de Morgan à $(\text{NON}2 \leq x) \text{OU} (\text{NON}x \lt 3) \equiv (2 \gt x) \text{OU} (x \gt 3)$

#### Propriétés triviales (vérifiables par tables de vérité) :
- $P \text{ET} P \equiv P \equiv P \text{OU} P$
- $P \text{ET} Q \equiv Q \text {ET} P$ (commutativité)
- $P \text{OU} Q \equiv Q \text {OU} P$ (commutativité)
- $(P \text{ET} Q) \text{ET} R \equiv P \text{ET} (Q \text{ET} R)$ (associativité)
- $(P \text{OU} Q) \text{OU} R \equiv P \text{OU} (Q \text{OU} R)$ (associativité)
- $P \text{ET} (Q \text{OU} R) \equiv (P \text{ET} Q) \text{OU} (P \text{ET} R)$ (distributivité)
- $P \text{OU} (Q \text{ET} R) \equiv (P \text{OU} Q) \text{ET} (P \text{OU} R)$(distributivité)

Puisque ET et OU sont associatifs, on peut enlever les parenthèses dans les groupes

#### Implication
$P \Rightarrow Q$ signifie "si P alors Q", ou encore "P donc Q"
L'implication est définie par la table de vérité :

P   | Q   | $P \Rightarrow  Q$
--- | --- | ---
V   | V   | V
V   | F   | F
F   | V   | V (bien que le raisonnement soit inutile)
F   | F   | V (bien que le raisonnement soit inutile)

Remarque : Ainsi, le contraire de $P \Rightarrow Q$ est $P \text{ET} (\text{NON} Q)$,
et on a $(P \Rightarrow Q) \equiv (\text{NON} P) \text{OU} Q$

> Lorsque $P \Rightarrow Q$ est vérifiée, on dit que P est une condition suffisante pour Q et que Q est une condition nécessaire pour P

> La réciproque de $P \Rightarrow Q$ est $Q \Rightarrow P$
> La contraposée de $P \Rightarrow Q$ est $\text{NON} Q \Rightarrow \text{NON} P$

Proposition : toute implication est équivalente à sa contaposée, soit
$\text{NON} Q \Rightarrow \text{NON} P$
$\text{NON} Q \Rightarrow \text{NON} P  \equiv \text{NON} (\text{NON} Q)$
$\text{OU} (\text{NON} P)$
$\equiv Q \text{OU} \text{NON} P$
$\equiv P \Rightarrow Q$

Attention : Pas de lien ente la proposition et sa réciproque, si la relation n'est que dans un sens elle est d'ailleurs souvent fausse

Exercice : Table de vérité de $(\text{NON} P) \Rightarrow (P \Rightarrow Q)$

P   | Q   | NON P | $P \Rightarrow Q$ | $(\text{NON} P) \Rightarrow (P \Rightarrow Q)$
--- | --- | ---   | ---                   | ---
V   | V   | F     | V                     | V
V   | F   | F     | F                     | V
F   | V   | V     | V                     | V
F   | F   | V     | V                     | V

Traduction : d'une hypothèse fausse, on peut déduire n'importe quelle assertion.
Ainsi, en pratique, les formes $P \Rightarrow Q$ s'utilisent dans les
raisonnements tels que  $[ P \text{ET} (P \Rightarrow Q) ] \Rightarrow Q$ (on déduit, parce qu'on a une règle et une proposition qui la respecte, l'application de la règle)

#### Opérateur de Sheffer
Aussi appelé nand, il est représenté par $\uparrow$, et correspond à $\text{NON} ( A \text{ET} B )$
Cet opérateur peut former un système complet.

#### Équivalence
L'assertion $P \Leftrightarrow Q$ est définie par $(P \Rightarrow Q) \text{ET} (Q \Rightarrow P)$
(il s'agit d'une double implication, dans les deux sens)
La table de vérité est donc :

P   | Q   | $P \Rightarrow Q$ | $Q \Rightarrow P$ | $P \Leftrightarrow Q$
--- | --- | ---                   | ---                   | ---
V   | V   | V                     | V                     | V
V   | F   | F                     | V                     | F
F   | V   | V                     | F                     | F
F   | F   | F                     | F                     | V

$P \Leftrightarrow Q$ est vraie si et seulement si les assertions P et Q prennent la même valeur de vérité

### Quantificateurs
> Une phrase mathématique contenant une variable x est appelée prédicat, et est
> notée $P(x)$ (voir predicats en LisP, fonction prenant un objet et renvoyant un booléen)

Si P(x) est un prédicat et si la variable x est prise à valeurs dans un ensemble E, les deux phrases suivante sont des assertions :
- $\forall x \in E , P(x)$ (assertion universelle)
- $\exists x \in E , P(x)$ (assertion existentielle)

- $\forall x \in E , P(x)$ est vraie lorsque pour chaque élément x de E, l'assertion P(x) est vérifiée
- $\exists x \in E , P(x)$ est vraie lorsqu'il existe (au moins) un élément x de E tel que P(x) est vérifiée

Attention : les quantificateurs ont un ordre et dépendent des variables précédemment définies

Négations :
$\text{NON} (\forall x \in E , P(x)) \equiv \exists x \in E , \text{NON} P(x)$
$\text{NON} (\exists x \in E , P(x)) \equiv \forall x \in E , \text{NON} P(x)$

Remarque : si E est l'ensemble vide ( $\emptyset$ )
$\forall x \in E , P(x)$ est toujours vraie
$\exists x \in E , P(x)$ est toujours faux

Paradoxe : Soit E un ensemble non vide, que dire de la proposition $\exists x \in E , P(x) \Rightarrow (\forall y \in E , P(y))$

Raccourci syntaxique : on note "il existe un unique élément de E tel que" sous
la forme $\exists !x \in E$

On note aussi "tel que" sous la forme $\mid$, / ou , . Souvent, les problêmes
utilisant cette nomenclature nécessitent de formaliser un ensemble qui respecte
la condition (si ce n'est pas le cas, il s'agit d'une sorte d'implication).

## Raisonnements usuels
### Raisonnement direct
Pour montrer un théorème do la forme $H \implies C$ (H : "hypothèse", C :
"conclusion"), on suppose que H est vraie et on procède par des déductions
successives : $H \implies P_1 ;\: P_1 \implies P_2 ; \ldots ;\: P_k \implies C$,
donc C est vraie.

Pour appliquer une règle, on applique la formule du *modus ponens*, qui revient
à $(A \,\text{ET}\, (A \implies B)) \implies B$ 

### Raisonnement par disjonction de cas
Pour montrer un énoncé P, on effectue une disjonction de cas selon qu'un autre
énoncé Q est réalisé ou non. Avec les 2 cas :
- Si $Q$ est vraie, alors ... , donc $P$
- Si $\,\text{NON}\,Q$ est vraie, alors ... , donc $P$
De façon logique, on a la règle : (avec P qui dépend forcément de Q)
$[(Q \implies P) \,\text{ET}\, (\,\text{NON}\,Q \implies P)] \implies P$ 

La disjonction de cas s'utilise dans de nombreux cas avec des possibilités limitées et
exhaustifs.

### Raisonnement par l'absurde
Pour montrer un énoncé $P$, on suppose $\,\text{NON}(P)$ et on en déduit une
contradiction (toujours fausse), ce qui se résume par :
$[\text{NON}(P) \implies \text{Faux}] \equiv P$

###### Exemple : On veut montrer $\forall n \in  \mathbb{N}^{\ast}, n^2 + 1 \ne p^2$ (cet
énoncé se trouve souvent sous la forme "il n'existe pas", et peut se traduire
par un quantificateur universel avec une opération négative).
On suppose que $\exists  n \in  \mathbb{N}^{\ast}, n^2 = p^2$ (ce qui nous intéresse
avec cette méthode n'est pas tant l'existence de x que de l'utiliser dans
d'autres opération pour aboutir à une contradiction). Ainsi, on a $1 = p^2 - n^2
= (p - n)(p + n)$, or $p > n$ (car $p^2 = n^2 + 1 > n^2$ et $n, p \ge 1$).
Ainsi, $p-m \in \mathbb{N} \,\text{ET}\, p + m \in \mathbb{N}$, donc $p - m = p + m = 1$, alors
 $n = 0$, ce qui est contraire à l'hypothèse.
En conclusion,  $\text{NON}(\exists p \in \mathbb{N}, n^2 + 1 = p^2)$ est vraie par
tiers exclu.

### Raisonnment par contraposée
Pour montrer $P \implies Q$, on peut montrer sa contraposée $(\text{NON}\, Q) \implies (\text{NON}\, P)$ 

###### Exemple : Soit $a \in \mathbb{R}$. Montrer $(a = 0) \Leftrightarrow \forall \varepsilon > 0, |a| \le \varepsilon$
On raisonne par double implication : Si $|a| = 0$, soit $\varepsilon > 0$, alors
$|a| = 0 \le  \varepsilon$.
On a bien $(a = 0) \implies (\forall \varepsilon > 0, |a| \le  \varepsilon)$
Raisonnons par contraposée. On cherche à montrer :
$(a \neq 0) \implies (\exists \varepsilon > 0, |a| > \varepsilon)$
Supposons $a \neq  0$, et posons $\varepsilon = \frac{|a|}{2}$, on a bien
$\varepsilon > 0$ et $\varepsilon = \frac{|a|}{2} < |a|$. On peut conclure que
$\forall \varepsilon > 0, |a| \le \varepsilon$.

### Raisonnement par équivalence
Montrer $P \Leftrightarrow Q$. Généralement, en fait une double implication ( $P \implies Q \,\text{ET}\, Q \implies P$ )

###### Exemple : Résolution d'équation ou d'inéquation, on écrit
$f(x) = 0 \Leftrightarrow \ldots \Leftrightarrow x = 1 \,\text{OU}\, x = -3$ 

### Raisonnement par Analyse-Synthèse : "Trouver toutes les solutions du problème"
On va d'abord supposer qu'une solution existe et trouver une expression plus
explicite, c'est-à-dire des **conditions nécessaires** (phase d'analyse du
problème) (on trouve que $P \implies Q$).
Ensuite, on part de ces conditions pour vérifier qu'elles sont suffisantes, et
on utilise les conditions trouvées pour essayer d'atteindre la condition
originale (phase de synthèse du problème) (On montre que $Q \implies P$, donc
que $P \Leftrightarrow Q$).

Notation : Les fonctions de $\mathbb{R}$ dans $\mathbb{R}$ se notent $F(\mathbb{R}, \mathbb{R}) ou \mathbb{R}^{\mathbb{R}}$

###### Exemple
Montrer que la fonction exponentielle s'écrit de manière unique comme
la somme d'une fonction paire et d'un fonction impaire (g est le cosinus
hyperbolique et h le sinus hyperbolique).
On veut montrer que $\exists !(g,h) \in F(\mathbb{R},\mathbb{R})^2$ tel que
$\forall x \in \mathbb{R}, \left{\begin{matrix} g(-x) = g(x) \\ h(-x) = -h(x) \\ \exp(x) = g(x) + h(x) \end{matrix}\right.$

Analyse : Supposons g paire, h impaire telles que exp = g + h.
Ainsi, $\forall k inn \mathbb{R}, e^x = g(x) + f(x)$.
Alors, $\forall x \in \mathbb{R}, e^{-x} = g(x) - h(x)$, donc $e^x + e^{-x} =2g(x)$
et $e^x - e^{-x} = 2h(x)$.
On peut conclure que $\forall x \in  \mathbb{R}, \left{\begin{matrix} g(x) = \frac{1}{2} (e^x + e^{-x}) \\ h(x) = \frac{1}{2} (e^x - e^{-x}) \end{matrix}\right.$
On prouve ainsi l'unicité de ces deux fonctions (sous réserve d'existence).

Synthèse : On vérifie que h est impaire, g est paire, et h + g = exp
$g(-x) = \frac{e^{-x} + e^{x}}{2} = g(x)$ (donc bien paire)
$h(-x) = \frac{e^{-x} - e^{x}}{2} = -h(x)$ (donc bien impaire)
$g(x) + h(x) = \frac{1}{2}(2e^x) = e^x$

###### Exemple : Trouver tous les couples $(n, z) \in \mathbb{Z} \times \mathbb{C}$
tels que $z^n = (z-1)^n = 1$
On a donc un système $\left{\begin{matrix} z^n = 1 \\ (z-1)^n = 1 \end{matrix}\right.$
Par analyse, soit $\exists (n, z) \in \mathbb{Z} \times \mathbb{C} \mid z^n = (z-1)^n = 1$, on recherche des particularités de n et z.
On sait tout d'abord que n = 0 fonctionne.
On recherche des modules et arguments de z qui permettent de faire fonctionner
cette relation. Avec $n \in  \mathbb{Z}, n \neq 0$, $|z^n| = |1|$, donc  $|z|^n = 1$
Comme $|z| \in \mathbb{R}^{\ast}_{+}$ (on peut donc lui appliquer des
logarithmes). Ainsi, $\ln(|z|^n) = \ln(1)$, donc $n \ln(|z|) = 0$, donc $|z| = 1$,
soit z est sur le cercle de centre 0 et de rayon 1.
De même, $(z-1)^n = 1$, donc $|z-1| = 1$, donc z est sur le cercle de centre 1
et de rayon 1.
z est à l'intersection des deux cercles, donc $\Re(z) = \frac{1}{2}$ et
$\Im(z) = \pm \frac{\sqrt{3}}{2}$, donc $arg(z) = \pm \frac{\pi}{3}$ (modulo
$2\pi$), donc $z = e^{\pm i \frac{\pi}{3}} = \frac{1}{2} \pm i \frac{\sqrt{3}}{2}$ 
On continue l'analyse en cherchant n. $(e^{i \frac{\pi}{3}})^n = e^{i \frac{n\pi}{3}}$, or on veut
$z^n = 1$. Il faut que  $e^{i\frac{n\pi}{3}} = 1$, donc $\frac{n\pi}{3} \equiv0[2\pi]$, donc $n \equiv 0[6]$.
$\frac{n\pi}{3} = 2\pi k$ avec $k \in \mathbb{Z}$, donc n = 6k.
De même, $(e^{i\frac{i\pi}{3}} -1)^{6k} =  (e^{i\frac{i\pi}{3}} -1)^{6k}$

Si $z^n = (z-1)^n = 1$, en conjugant, on trouve que $\overline{z}$ est aussi
solution.
On vérifie l'équivalence par synthèse, et on conclut :
$(n,z) \in  {0} \times \mathbb{C} \cup {6k, e^{\pm i \frac{\pi}{3}}, k \in \mathbb{Z}^{\ast}}$

## Les entiers naturels et la récurrence
### L'ensemble $\mathbb{N}$
On suppose construit $\mathbb{N}$ avec ses opérations addition (+) et
multiplication ($\times$) (opérations qui ne peuvent pas sortir de l'ensemble)

Soient $m,n,p \in \mathbb{N}$ :
- $b + p = n + p \implies m = n$
- $p \neq 0 \,\text{ET}\,mp = np \implies m = n$
- $mn = 0 \implies (m = 0) \,\text{OU}\,(n = 0)$
- $mn = 1 \implies m = n = 1$

Relation d'ordre sur $\mathbb{N}$ : $\mathbb{N}$ est muni d'un ordre total $\leq$ qui vérifie les
propriétés :
1. Toute partie non vide de $\mathbb{N}$ admet un plus petit élément
2. Toute partie non vide majorée de $\mathbb{N}$ admet un plus grand élément
3. $\mathbb{N}$ ne possède pas de plus grand élément

Remarque : $\mathbb{N}$ étant une partie non vide de $\mathbb{N}$, elle admet un
plus petit élément, noté 0

- Soit $n \in \mathbb{N}$, prenons $A = {p \in \mathbb{N} \mid p > n}$. A est
  une partie non vide de $\mathbb{N}$, donc elle admet un plus petit élément,
  qui est ici n+1

##### Exemple : Il n'existe pas de suite infinie d'entiers naturels strictement décroissante.
Par l'absurde, donnons une suite $(u_{n})_{n \in \mathbb{N}}$, avec $\forall n \in \mathbb{N}, u_n \in \mathbb{N} \,\text{ET}\, u_{n+1} < u_n$.
Prenons $A = {u_{n}, n \in \mathbb{N}}$ (l'ensemble des termes de la suite). A
étant une partie non vide de $\mathbb{N}$, elle admet un plus petit élément :
$\exists p \in \mathbb{N}, u_p \in A \,\text{ET}\,u_p = min A$, donc
$\forall n \in \mathbb{N}, u_p \leq u_{n}$. Or u étant décroissante, $u_{p+1} < u_p$
et avec $n = p+1, u_p \leq u_{p+1}$, ce qui est absurde

### Récurrence
Pour montrer un énoncé de la forme $[\forall n \in \mathbb{N}, P(n)]$
__Thèse__ (récurrence) : Soit P un prédicat défini sur $\mathbb{N}$.
Si $P(0)\,\text{(Initialisation)}\,\text{ET}\,[\forall n \in \mathbb{N}, P(n) \implies P(n+1)]\,\text{(Hérédité)}$
alors $[\forall n \in  \mathbb{N}, P(n)]$.

__Preuve__ : On suppose (I) et (H) (les propositions ci-dessus). Par l'absurde,
supposons $\exists n_0 \in \mathbb{N}, \,\text{NON}\,P(n_0)$.
Soit $A = {n \in \mathbb{N} \mid \neg P(n)}$, A doit admettre un plus petit
élément, puisque A doit être non vide. Il admet alors un élément p, tel que
$p \geq n_0$

Ainsi, P(p) est fausse, or P(0) est vraie (I), donc $p \geq 1$, donc $p - 1 \in \mathbb{N}$.
Comme $p = min A$, alors $p-1 \not\in A$ alors $P(p-1)$ est vraie.
Enfin par (H), $[P(p-1) \implies P(p)]$ est vraie, on en conclut que P(p) est
vraie, ce qui est absurde.

###### Exemple
$\forall n \in \mathbb{N}, \sum\limits_{k=0}^{n} k^2 = \frac{n(n+1)(2n+1)}{6}$
Raisonnons par récurrence par n.
Initialisation : Au rang 0, $\sum\limits_{k = 2}^{0}k^2 = 0$ et $0 \times \ldots = 0$
Hérédité : Soit $n \in  \mathbb{N}$ tel que $\sum\limits_{k = 0}^{n} k^2 = \frac{n(n+1)(2n+1)}{6}$.
$\sum\limits_{k=0}^{n+1}k^2 = (\sum\limits_{k=0}^{n}k^2) + (n+1)^2$
$= \frac{n(n+1)(2n+1)}{6} + (n+1)^2$
$= \frac{n+1}{6} [n(2n+1) + 6(n+1)]$
$= \frac{n+1}{6} [2n^2 + 7n + 6]$
$= \frac{n+1}{6} (n+2)(2n+3)$, ce qui prouve $P(n+1)$
On en conclut qu'on a prouvé ce résultat par récurrence pour tout n.

### Variantes du raisonnement par récurrence
#### Récurrence à partir d'un rang $n_0$
- initialisation : $P(n_0) vraie$
- hérédité : $\forall n \geq n_0, P(n) \implies P(n+1)$
- conclusion : $\forall n \geq n_0, P(n)$

#### Récurrence finie
On se fixe N, et on veut prouver $\forall n \in  [O,N]_{\mathbb{N}}, P(n)$
- initialisation : $P(n_O)$ vraie
- hérédité : $\forall n \in [O, N-1]_{\mathbb{N}}, P(n) \implies P(n+1)$
- conclusion : $\forall n \in [O, N+1]_{\mathbb{N}}, P(n)$

Cf invariant de boucle

#### Récurrence double
- initialisation : $P(0) et P(1)$ vraies
- hérédité : $\forall n \in \mathbb{N}, (P(n) \land P(n+1)) \implies P(n+2)$
- conclusion : $\forall n \in  \mathbb{N}, P(n)$

#### Récurrence forte
- initialisation : $P(0)$ vraie
- hérédité : $\forall n\in \mathbb{N}, [P(0) \land P(1) \land \ldots \land P(n)] \implies P(n+1)$
- conclusion : $\forall n \in \mathbb{N}, P(n)$

L'hérédité peut aussi se noter $\forall n\in \mathbb{N}, [\forall k \in [0, N]_{\mathbb{N}}, P(k)] \implies P(n+1)$

###### Exemple : Récurrence sur une suite (récurrence double)
Soit $F(n)_{n \in \mathbb{N}}"$ la suite de Fibonacci, définie par
$\left{\begin{matrix} F_0 = 0, F_1 = 1 \\ \forall n \in \mathbb{N}, F_{n+2} = F_{n+1} + F_n \end{matrix}\right.$.
On pose $\phi = \frac{1+\sqrt{5}}{2}$ et $\psi = \frac{1-\sqrt{5}}{2}$.
On cherche à montrer que $\forall n \in \mathbb{N}, F(n) = \frac{\phi^n - \psi^n}{\sqrt{5}}$.
On note $P(n) : F(n) = \frac{\phi^n - \psi^n}{\sqrt{5}}$. Par récurrence double :
- Initialisation : $\frac{\phi^0 - \psi^0}{\sqrt{5}} = 0 = F_0$ et
  $\frac{\phi - \psi}{\sqrt{5}} = \frac{\sqrt{5}}{\sqrt{5}} = 1 = F_1$.
  Remarque : $\phi + \psi = 1$ et $\psi \times \phi =
  \frac{(1-\sqrt{5})(1+\sqrt{5})}{4} = -1$. Le polynôme $(x-\phi)(x-\psi)$ a
  pour racines $\phi$ et $\psi$, or $(x-\phi)(x-\psi) = x^2 - (\phi + \psi)x + \psi\phi = x^2 - x - 1$.
  Ainsi, $\phi$ et $\psi$ sont les racines du polynôme $x^2 - x - 1$, et on a
  donc $\phi^2 - \phi - 1 = 0$ et $\psi^2 - \psi - 1$.
- Hérédité : Soit $n \in \mathbb{N}$ tel que $P(n)$ et $P(n+1)$, alors
  $F_{n+2} = F_{n+1} + F_n = \frac{\phi^{n+1} - \psi^{n+1}}{\sqrt{5}} + \frac{\phi^{n}-\psi^n}{\sqrt{5}}$
  $= \frac{1}{\sqrt{5}} [\phi^n \times (\phi + 1) - \psi^n \times (\psi + 1)]$,
  or $\phi + 1 = \phi^2$ et $\psi + 1 = \psi^2$, donc
  $= \frac{1}{\sqrt{5}}(\phi^{n+2} - \psi^{n+2})$ d'où $P(n+2)$ (conclusion).

###### Exemple : somme de tous les termes précédents (récurrence forte)
Soit $(u_{n \in \mathbb{N}})$ définie par $\left{\begin{matrix} u_0 = 1 \\ \forall n \in \mathbb{N}, u_{n+1} = \sum\limits_{k=0}^n u_k \end{matrix}\right.$,
on cherche à donner $u_n$ en fonction de n.
On conjecture le résultat $u_n = 2^{n-1}$ avec $n \geq 1$ à partir du calcul,
bien que cette formule ne fonctionne pas pour 0, qui est un cas particulier.
On montre par récurrence forte :
- Initialisation : $u_1 = 2^0 = 1$
- Hérédité : Soit $n \in \mathbb{N}^{\ast}$ tel que $P(1) \land P(2) \land \ldots \land P(n)$,
  $\forall k \in [1,n]_{\mathbb{N}}, u_k = 2^{k-1}$.
  Alors, $u_{n+1} = \sum\limits_{k=1}^{n} u_k = u_0 + \sum\limits_{k = 1}^{n} 2^{k-1}$
  $= 1 + (2^0 + 2^1 + \ldots + 2^{n-1}) = 1 = \frac{1 - 2^n}{1-2} = 1 + 2^n - 1$
  $= 2^n$, d'oû $P(n+1)$ est vraie.
- Conclusion : la proposition originale est bien vraie.

Méthode 2 : $\forall n \in \mathbb{N}, u_{n+1} = \sum\limits_{k = 0}^{n} u_k$
$= (\sum\limits_{k = 0}^{n-1} u_k) + u_{n} = 2u_{n}$.
Ici, $\left{\begin{matrix} U_1 = 1 \\ \forall n \geq 1, u_{n+1} = 2u_{n} \end{matrix}\right.$,
qui est une suite géométrique de raison 2, soit
$\forall n \geq 1, u_{n} = 2^{n-1} \times u_1 = 2^{n-1}$, ce qui nous permet de
conclure de la mêbe façon que la première méthode.

###### Exemple : récurrence avec une variable
On cherche à montrer que $\forall x > -1, \forall n \in \mathbb{N}, (1+x)^n \geq 1 + nx$.
On montre par récurrence simple $P(n) : \forall x > -1, (1+x)^n \geq 1 + nx$
- Initialisation : Pour $x > -1$, $(1+x)^0 = 1 \geq 1$, donc $P_0$ est vraie
- Hérédité : Soit $n \in \mathbb{N}$ tel que $P(n)$, pour $x > -1, (1+x)^n \geq 1 + nx$,
  or $1 + x > 0$, donc $(1 + x) \times (1 + x)^n \geq (1 + x) \times (1+nx)$,
  donc $(1 + x)^{n+1} \geq 1 + x + nx + nx^2$, et sachant que $nx^2 \geq 0$,
  on a $(1 + x)^{n+1} \geq 1 + (n+1)x$, donc $P(n+1)$ est vérifiée.
- Conclusion : par récurrence simple, $\forall n \in \mathbb{N} P(n)$

###### Exemple : littéraire
On cherche à montrer que dans une trousse, tous les crayons sont de la même
couleur. Soit $P(n) : \text{"Dans toute trousse à n crayons, tous les crayons sont de la même couleur"}$
On montre par récurrence :
- Initialisation : $n=1$, Dans une trousse à 1 crayon tous sont de la même
  couleur, donc $P_1$
- Hérédité : Soit $n \geq 1$ tel que $P(n)$ est vraie, on cherche à montrer $P(n+1)$.
  Soit une trousse à (n+1) crayons $C_1, C_2, \ldots, C_{n+1}$. On prend $(C_1, \ldots C_n)$.
  C'est une trousse à n crayons, danc par $P_n$, ils sont de la même couleur. En
  prenant $(C_2, \ldots, C_{n+1})$, c'est aussi ine trousse à n crayons, donc
  ils sont tous de la même couleur (par $P(n)$).
  Or $C_n$ est dans les deux trousses, donc tous sont de la même couleur, donc
  $P(n+1)$ est vraie.

On ne peut néanmoins pas conclure, car l'hérédité ne peut pas être appliquée
avant $n \geq 2$, puisque sinon il n'y a pas de crayon commun entre les deux
parties.

On observe ainsi que si l'on ne peut pas établir de lien entre l'initialisation
et l'hérédité, le raisonnement ne peut conclure.
