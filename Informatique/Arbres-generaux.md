# Arbres généraux
## Extension de la définition des structure inductives
On peut définir des structures mutuellement inductives, c'est-à-dire
que leurs constructeurs peuvent prendre des arguments de cette même structure ou
d'une autre structure.

Le théorème d'induction structurelle s'applique encore sur l'union de ces
structures mutuellement inductives et donc aussi sur chacune prise
individuellement.

On définit les arbres avec deux structures mutuellement inductives, les arbres
et les forêts :
- La forêt vide est une forêt
- `Noeud(x, F)`, où `x` est une étiquette et `F` une forêt, est un arbre.
- `a::F`, avec `a` un arbre, est une forêt
