# Retour sur trace
Le retour sur trace, ou backtracking, est une technique algorithmique pour
résoudre un problème dont la solution est un tuple respectant des propriétés
faciles à invalider sur une solution partielle.

On peut prendre l'exemple du Sudoku, dans lequel on cherche un 81-tuple tel que
- les cases préremplies sont les bonnes
- les 9 lignes ne contiennent pas de doublon
- les 9 colonnes ne contiennent pas de doublon
- les 9 petits carrés ne contiennent pas de doublon

Ceci signifie que pour des tuples avec de nombreuses inconnues, il est souvent
néanmoins aussi facile de montrer qu'il n'existe aucune valeur des inconnues
qui donne un tuple satisfaisant les propriétés.

Le retour sur trace revient à considérer un arbre dont la racine est un tuple
dont tous les termes sont inconnus et chaque nœud a pour enfants les tuples que
l'on peut obtenir en remplaçant la première inconnue par une des valeurs
possibles. Si un nœud est étiquetté par un tuple qui ne respecte pas les
contraintes, il n'a pas d'enfants.

Le parcours de l'arbre se fait en le construisant au fur et à mesure, tant qu'on
a pas atteint un nœud, on ne se préoccupe pas de son existence. On fait plutôt
ce parcours en profondeur, sans conserver les branches qui n'ont pas d'enfants.

##### Exemple : problème des 8 dames
On veut placer 8 dames sur un échiquier de façon à aucune n'attaque une autre.
Ainsi, on peut remarquer qu'il n'y a qu'une seule dame par ligne, colonne et
diagonale. On reformule donc : on veut trouver $(c_1, c_2, \ldots, c_8) \in [\![1,8]\!]^{8}$
tels que $\forall i \neq j, c_i \neq c_j$ et $|c_j - c_i| \neq |j - i|$.
