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
- des quantificateurs (universels ou quantitatifs), comme $\exists$ et $\forall$

Exemple : "Pour tout réel x, x est un carré", soit $\forall x \in \mathbb{R} , \exists y \in \mathbb{R} , x = y^2$
Cette assertion est d'ailleurs fausse (du moins pour y réel), et comme le quantificateur est universel, il suffit de produire un contre-exemple (x = -1)
Une assertion vraie serait $\forall x \in \mathbb{R}^{+} , \exists y \in \mathbb{R} , x = y^2$
Une autre est $\forall z \in \mathbb{C} , \exists z' \in \mathbb{C} , (z')^2 = z$
(l'écriture exponentielle des complexes n'est possible que pour les complexes non nuls)

### Déclaration
Les variables introduites dans une assertion doivent être quantifiées
> Principe de tiers exclus : pour toute assertion P, on a que l'assertion P est vraie ou que l'assertion (non P) est fausse (!P, not(P)) 
> Ainsi, toute assertion est vraie ou fausse.

Exemple : $\forall (a, b) \in \mathbb(R)^2, ab = 0 \Rightarrow (a = 0, b = 0)$
Soient a et b deux réels tels que ab = 0, par disjonction de cas:
- si a = 0, alors (a = 0 ou b = 0) est vraie
- sinon, $a \ne 0$. Or ab = 0, donc b = 0, donc (a = 0, b = 0) est vraie.

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
