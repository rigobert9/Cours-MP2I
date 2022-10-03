# Chapitre 5 : Représentation des flottants
## Principe
Les nombre réels étant une infinité dans tout intervalle (non vide ou réduit à
une seul nombre), on ne peut pas comme pour les entiers positifs prendre les
$2^n$ réels réels les plus proches de 0 pour les représenter sur N bits.

On pourrait utiliser une intervalle fixe mais alors on aurait une précision
inutilement trop élevée pour les grandes valeurs.

L'idée est proche de la notation scientifique : le premier bit est le signe,
puis une suite de bits représentent l'exposant, et le reste représentent la
mantisse, les décimales binaires après le 1 de notre nombre.

Ces représentations sont standardisées par l'ISO :
- Sur 32 bits : 8 bits d'exposant et 23 de mantisse
- Sur 64 : 11 bits d'exposant et 52 de mantisse
- Sur 128 bits : 15 bits d'exposant et 112 de mantisse

## Flottants non normalisés 
Avec ce système, on ne peut pas représenter 0 (car
la mantisse commence par 1). De plus, il n'est possible de le représenter par
uniquement des zéros dans l'exposant, puisque cela représente quelque chose. En
pratique, on choisit de ne pas pouvoir représenter $2^{-D} \times \,\text{mantisse}$
(qu'on approche uniquement avec le nombre le plus proche)
pour pouvoir représenter 0 avec tous les bits à 0.

On a aussi des flottants non normalisés, qui possèdent tous leur exposant avec
tous les bits à 1 et toute la mantisse à 0 :
- Celui qui a le signe à 0 est $+ \infty$
- Celui qui a le signe à 1 est $- \infty$

Une autre valeur est souvent disponible avec tout son exposant à 1, un signe
quelconque et une mantisse non nulle, pour représenter NàN (la valeur renvoyée
par une opération qui ne peut aboutir).
