# Bases de données
## Modèle entité-association et modèle relationnel
(Le premier théorisé en 1976 par Chen, et le second par Codd en 1969)

Dans le modèle entité-association, les entités de chaque type sont caractérisées
par des attributs et sont reliées à des entités d'autres types ou du même par
des associations. Ces associations sont des relations binaires au sens
mathématique. Elles sont caractérisées par leur cardinalité (relation de 1 à n,
de 1 à 1, de 0..1 à n, de n à n ...).

On veut éviter que l'information se répète et faciliter les modifications de ces
relations. On relie donc des relations de base plus petites, reliées entre elles
par des clés étrangères dans le modèle relationnel. On appelle table ou relation
un ensemble de $n$-uplets, dont chaque coordonnée est appelée attribut ou
colonne, et porte un nom et a un domaine (type). Chaque élément de la relation
est appelé une ligne. La clé primaire d'une relation est un sous-ensemble de ses
attributs tel que la projection de la relation sur sa clé primaire soit
injective.

On choisit cette clé comme unique et immuable, et on choisit donc en général un
identifiant numérique dédié pour chaque type d'entité, souvent des nombres dans
l'ordre croissant.

Une clé étrangère de $R$ faisant référence à $R'$ est un ensemble d'attributs de
$R$ qui prennent des valeurs prises par la clé primaire de $R'$. On peut ainsi
l'utiliser pour représenter une fonction de $R$ vers $R'$. Si cette clé
étrangère peut être absente, c'est une fonction partielle.

## Requêtes SQL
On peut récupérer les lignes d'une table par l'expression `SELECT a1, ..., an
FROM t`, en adjoignant `WHERE P(b1, ..., bn)` si l'on souhaite filtrer par
satisfaction d'un prédicat `P` du premier ordre (avec les tables qui
correspondent aux constante).
