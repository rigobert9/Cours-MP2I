# Programmation fonctionnelle en OCaML
## Paradigme de programmation fonctionnelle
1. Les "variables" sont immuables et affectées seulement la programmation
2. Les fonctions sont des variables comme les autres
3. Le langage est fortement typé et comporte une inférence de type

Ce style de programmation descende du lambda calculus, alternative calculatoire
à la machine de Turing, et du second langage de programmation qui en descend,
LisP.

## Variables immuables
On déclare une variable en OCaML en lui donnant la valeur d'une expression, qui
peut être remplacée. On définit la plupart de ces variables localement, dans une
portée marquée par le mot-clé `in`.
Lorsqu'on déclare une nouvelle variable qui est déjà déclarée, cette nouvelle
variable masque l'ancienne pendant tout sa durée de vie, puis laisse place à
nouveau à l'ancienne variable.

Passage par copie de la valeur : on ne modifie pas la variable sans
réattribution.
