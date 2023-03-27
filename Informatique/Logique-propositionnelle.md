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
