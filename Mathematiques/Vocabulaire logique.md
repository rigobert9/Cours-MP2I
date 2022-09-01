# Vocabulaire logique général en mathématiques
Logique : Relations autour du concept de vérité

## Propositions logiques
### Assertion
> Une assertion est une phrase mathématique à laquelle on peut donner deux valeurs de vérité possibles (vraie ou fausse)

Une phrase mathématique est une phrase contenant :
- des constantes;
- des variables;
- des ensembles;
- des fonctions (opérations, "macros" et fonctions transcendantes) (informatiquement, une fonction renvoyant un objet, souvent de même nature);
- des relations (qui sont l'opération qui donne la vérité d'une assertion) (informatiquement, une fonction renvoyant une valeur de vérité);
- des connecteurs logiques (opérations booléennes, implication, équivalence);
- des quantificateurs (universels ou quantitatifs), comme \( \exists \) et \( \forall \)

Exemple : "Pour tout réel x, x est un carré", soit \( \forall x \in \mathbb{R} , \exists y \in \mathbb{R} , x = y^2 \)
Cette assertion est d'ailleurs fausse (du moins pour y réel), et comme le quantificateur est universel, il suffit de produire un contre-exemple (x = -1)
Une assertion vraie serait \( \forall x \in \mathbb{R}^{+} , \exists y \in \mathbb{R} , x = y^2 \)
Une autre est \( \forall z \in \mathbb{C} , \exists z' \in \mathbb{C} , (z')^2 = z \)
(l'écriture exponentielle des complexes n'est possible que pour les complexes non nuls)

### Déclaration
Les variables introduites dans une assertion doivent être quantifiées
> Principe de tiers exclus : pour toute assertion P, on a que l'assertion P est vraie ou que l'assertion (non P) est fausse (!P, not(P)) 
> Ainsi, toute assertion est vraie ou fausse.

Exemple : \( \forall (a, b) \in \mathbb(R)^2, ab = 0 \Rightarrow (a = 0, b = 0) \)
Soient a et b deux réels tels que ab = 0, par disjonction de cas:
- si a = 0, alors (a = 0 ou b = 0) est vraie
- sinon, \( a \ne 0 \). Or ab = 0, donc b = 0, donc (a = 0, b = 0) est vraie.

### Connecteurs logiques
(mots à prendre au sens informatique)
- Conjonction : ET, vrai uniquement si les deux assertions données sont vraies
- Disjonction : OU, vrai uniquement si au moins l'une des deux assertions est vraie
- Négation : NON, vrai seulement si l'assertion donnée est fausse

Tables de vérité :

Connecteur | 0 0 | 0 1 | 1 0 | 1 1
---|---|---|---|---
ET | 0 | 0 | 0 | 1
OU | 0 | 1 | 1 | 1

Connecteur | 0 | 1
---|---|---
NON | 1 | 0

> Deux assertions sont équivalentes si elles ont la même table de vérité, on note alors \( P \equiv Q \)

Un exemple d'équivalence est deux programmes, écrits éventuellement différement mais qui fournissent toujours le même résultat pour la même entrée

Exemple : \( \text{NON (NON P)} \equiv P \) car leurs tables de vérité sont
De plus, \( \text{P OU NON(P)} \equiv V \) (toujours vrai) (tautologie), et \( \text{P ET NON(P)} \equiv F \) (toujours faux) (contradiction ou antilogie)

#### Lois de Morgan :
\( \text{NON(P ET Q)} \equiv \text{(NON P) OU (NON Q)} \)
\( \text{NON(P OU Q)} \equiv \text{(NON P) ET (NON Q)} \)
Vérifiable par tables de vérité.
Exemple : Contraire de \( 2 \leq x \lt 3 \equiv 2 \leq \text{ET} x \lt 3 \), ce qui mène avec les lois de Morgan à chercher 

#### Propriétés triviales (vérifiables par tables de vérité) :
\( P \text{ET} P \equiv P \equiv P \text{OU} P \)
\( P \text{ET} Q \equiv Q \text {ET} P \) (commutativité)
\( P \text{OU} Q \equiv Q \text {OU} P \) (commutativité)
\( (P \text{ET} Q) \text{ET} R \equiv P \text{ET} (Q \text{ET} R) \) (associativité)
\( (P \text{OU} Q) \text{OU} R \equiv P \text{OU} (Q \text{OU} R) \) (associativité)
\( P \text{ET} (Q \text{OU} R) \equiv (P \text{ET} Q) \text{OU} (P \text{ET} R) \) (distributivité)
\( P \text{OU} (Q \text{ET} R) \equiv (P \text{OU} Q) \text{ET} (P \text{OU} R) \) (distributivité)

Puisque ET et OU sont associatifs, on peut enlever les parenthèses dans les groupes

#### Implication
\( P \Rightarrow Q \) signifie "si P alors Q", ou encore "P donc Q"
L'implication est définie par la table de vérité :

P | Q | \( P \Rightarrow  Q \)
---|---|---
V | V | V
V | F | F
F | V | V (bien que le raisonnement soit inutile)
F | F | V (bien que le raisonnement soit inutile)

Remarque : Ainsi, le contraire de \( P \Rightarrow Q \) est \( P \text{ET} (\text{NON} Q) \), et on a \( P \Rightarrow Q) \equiv (\text{NON} P) \text{OU} Q\)

> Lorsque \( P \Rightarrow Q \) est vérifiée, on dit que P est une condition suffisante pour Q et que Q est une condition nécessaire pour P

> La réciproque de \( P \Rightarrow Q \) est \( Q \Rightarrow P \)
> La contraposée de \( P \Rightarrow Q \) est \( \text{NON} Q \Rightarrow \text{NON} P \)

Proposition : toute implication est équivalent à sa contaposée, soit \( \text{NON} Q \Rightarrow \text{NON} P \)
\( \text{NON} Q \Rightarrow \text{NON} P  \equiv \text{NON} (\text{NON} Q) \text{OU} (\text{NON} P) \)
\( \equiv Q \text{OU} \text{NON} P \)
\( \equiv P \Rightarrow Q \)

Attention : Pas de lien ente la proposition et sa réciproque, si la relation n'est que dans un sens elle est d'ailleurs souvent fausse

Exercice : Table de vérité de \( (\text{NON} P) \Rightarrow (P \Rightarrow Q) \)

P | Q | NON P | \( P \Rightarrow Q \) | \( (\text{NON} P) \Rightarrow (P \Rightarrow Q) \)
---|---|---|---|---
V | V | F | V | V
V | F | F | F | V
F | V | V | V | V
F | F | V | V | V

Traduction : d'une hypothèse fausse, on peut déduire n'importe quelle assertion.
Ainsi, en pratique, les formes \( P \Rightarrow Q \) s'utilisent dans les raisonnements tels que  \( [ P \text{ET} (P \Rightarrow Q) ] \Rightarrow Q \) (on déduit, parce qu'on a une règle et une proposition qui la respecte, l'application de la règle)

#### Équivalence
L'assertion \( P \Leftrightarrow Q \) est définie par \( (P \Rightarrow Q) \text{ET} (Q \Rightarrow P) \) (il s'agit d'une double implication, dans les deux sens)
La table de vérité est donc :

P | Q | \( P \Rightarrow Q \) | \( Q \Rightarrow P \) | \( P \Leftrightarrow Q \)
---|---|---|---|---
V | V | V | V | V
V | F | F | V | F
F | V | V | F | F
F | F | F | F | V

\( P \Leftrightarrow Q \) est vraie si et seulement si les assertions P et Q prennent la même valeur de vérité

### Quantificateurs
> Une phrase mathématique contenant une variable x est appelée prédicat, et est notée \( P(x) \) (voir predicats en LisP, fonction prenant un objet et renvoyant un booléen)

Si P(x) est un prédicat et si la variable x est prise à valeurs dans un ensemble E, les deux phrases suivante sont des assertions :
- \( \forall x \in E , P(x) \) (assertion universelle)
- \( \exists x \in E , P(x) \) (assertion existentielle)

\( \forall x \in E , P(x) \) est vraie lorsque pour chaque élément x de E, l'assertion P(x) est vérifiée
\( \exists x \in E , P(x) \) est vraie lorsqu'il existe (au moins) un élément x de E tel que P(x) est vérifiée
Attention : les quantificateurs ont un ordre et dépendent des variables précédemment définies

Négations :
\( \text{NON} (\forall x \in E , P(x)) \equiv \exists x \in E , \text{NON} P(x) \)
\( \text{NON} (\exists x \in E , P(x)) \equiv \forall x \in E , \text{NON} P(x) \)

Remarque : si E est l'ensemble vide (\( \emptyset \) )
\( \forall x \in E , P(x) \) est toujours vraie
\( \exists x \in E , P(x) \) est toujours faux

Paradoxe : Soit E un ensemble non vide, que dire de la proposition \( \exists x \in E , P(x) \Rightarrow (\forall y \in E , P(y)) \)
