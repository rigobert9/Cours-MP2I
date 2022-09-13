# Chapitre 2 : Calculs algébriques
La plupart des symboles de notation pour des longues opérations (par exemple la
somme) permettent d'éviter les ellipses ( $\ldots$ ), qui donnent facilement
naissance à des ambiguïtés. De plus, définir ces opérations permet de leur
appliquer des règles nouvelles.

## Sommes et produits
### Symboles $\sum$ et $\prod$
Soit I un ensemble fini d'indices, et $(a_{i \in I})$ une famille de nombres de
d'ensembles $(\mathbb{R}, \mathbb{C})$. La somme des termes de la famille est
$\sum\limits_{i \in I} a_i$ et le produit des termes est noté $\prod\limits_{i \in N} a_i$

En pratique, si $I = [p,n]\_{\mathbb{N}}$ avec $(p,n) \in \mathbb{N}^2, p \leq n$, on note
$\sum\limits_{i \in [p,n]\_{\mathbb{N}}} a_i = \sum\limits_{p \leq i \leq n} a_i = \sum\limits_{i = p}^{n} a_i$
et idem pour le produit. Il faut noter qu'ici la somme contient alors $(n-p+1)$
termes.

Remarque : $[0,N]_{\mathbb{N}}$ contient N+1 entiers.

L'indice i est un indice muet, destiné à être remplacé par des valeurs de
l'ensemble des valeurs dans l'opération (comme les variables initialisées dans
un boucle en programmation).

> Par convention, si $I = \emptyset$ (un ensemble vide d'indices), on choisit
> d'initialiser ces deux opérations à leur valeur identitaire : 0 pour la somme
> et 1 pour le produit. Si $p > n$, on a d'ailleurs un ensemble vide.

La factorielle est un fonction qui se définit, soit $n \in \mathbb{N}^{\ast}$,
comme $factorielle(n) = \prod\limits_{k = 1}^{n} k = 1 \times 2 \times 3 \ldots \times n$,
et est notée $n!$. Par convention, on a $0! = 1$ (voir ensembles vides pour le
produit).

Une série (voir plus tard dans l'année) est une somme aux termes infinis, telle
que $\sum\limits_{k = 0}^{\infty}a_k$.

Règles de calcul : Soient $(a_{i \in I})$ et $(b_{i \in  I})$ deux familles
finies de nombres. Soit $n \in \mathbb{N}^\ast, \lambda \in \mathbb{R} \text{(ou} \mathbb{C} \text{)}$.
1. $\sum\limits_{i \in I}(a_i + b_i) = (\sum\limits_{i \in I}a_i) + (\sum\limits_{i \in I} b_i)$
2. $\prod\limits_{i \in I}(a_i \times b_i) = (\prod\limits_{i \in I}a_i) \times (\prod\limits_{i \in I}b_i)$
3. $\sum\limits_{i \in I}(\lambda \times a_i) = \lambda \times (\sum\limits_{i \in I}a_i)$
4. $\prod\limits_{i \in I}(\lambda \times a_i) = \binom{N}{\lambda} \times \prod\limits_{i \in I}a_i$ (avec N le cardinal, le nombre d'éléments, de I)
5. $\sum\limits_{i \in I}(a_i + \lambda) = \sum\limits_{i \in I}a_i + \lambda \times N$ (avec N cardinal de I)
6. $\prod\limits_{i \in I}(a_i^n) = (\prod\limits_{i \in I}a_i)^n$

Relation de Chasles : Si $n \leq m < p$,
$\sum\limits_{i = n}^{p}a_i = \sum\limits_{i = n}^{m}a_i + \sum\limits_{i = m+1}^{p}$ (la somme de deux parties qui composent l'ensemble entier), et
$\prod\limits_{i = n}^{p}a_i = (\prod\limits_{i = n}^{m}a_i) \times (\prod\limits_{i = m+1}^{p}a_i)$

### Changement d'indice
Soient $p \leq n$ et $m \in \mathbb{N}$, $\sum\limits_{k = p}^{n}a_{k+m} = \sum\limits_{j = p+m}^{n+m}a_j$.
On a opéré un changement d'indice $j = k + m$.
Pour les bornes, si $k = p$, sont $j = p+m$, et si $k = n$, sont $j = n + m$

Il est de façon générale, il s'agit d'un pratique dangereuse de d'effectuer des
changements d'indice autres que tels que le nouvel indice j est égal à
$k + \text{constante}$ ou $-k + \text{constante}$.

##### Exemple de réduction par changement d'indice (formule de la somme d'une suite géométrique)
$(1 - q) \times \sum\limits_{k = 0}^{n}q^k = \sum\limits_{k = 0}^{n}(1 - q)q^k$\
$= \sum\limits_{k = 0}^{n}(q^k - q^{k+1}) = (\sum\limits_{k = 0}^{n}q^k) - (\sum\limits_{k = 0}^{n}q^{k+1})$\
$= \sum\limits_{k = 0}^{n}q^k - \sum\limits_{k = 1}^{n + 1}q^k$.\
$= q^0 + \sum\limits_{k = 1}^{n}q^k - \sum\limits_{k = 1}^{n}q^k - q^{n+1}$.\
$= 1 - q^{n+1}$\

##### Exemple
Soit $p \leq n$ et $m \geq n$, $\sum\limits_{k = p}^{m}a_{m-k} = \sum\limits_{j = m-p}^{m-p}a_j$

##### Exemple : Somme usuelle des entiers (formule de la somme d'une suite arithmétique)
Somme usuelle des entiers $\sum\limits_{k = 0}^{n}k = S_n$.
On peut voir que $2S_n = 0 + 1 + \ldots + n\: + n + n-1 + \ldots + 0$, ce qui
donne $2S_n = n \times (n+1)$.

De façon plus rigoureuse, on peut ainsi noter :
$2S_n = \sum\limits_{k = 0}^{n}k + \sum\limits_{k = 0}^{n}k$\
$= \sum\limits_{k = 0}^{n}k + \sum\limits_{j = 0}^{n}(n-j)$\
$= \sum\limits_{k = 0}^{n}(k + (n-k))$\
$= \sum\limits_{k = 0}^{n}n = (n+1) \times n$ (car n+1 est le nombre de termes).\

###  Sommes télescopiques
On veut calculer $\sum\limits_{k = p}^{n}a_k$ où le terme $a_k$ peut s'écrire
$a_k = U_{k+1} - U_k$.
On est alors en présence d'une "somme télescopique". On pose
$\sum\limits_{k = p}^{n}(U_{k+1} - U_k) = (U_{p+1} - U_p) + (U_{p+2} - U_{p+1}) \ldots$
Chaque terme est ainsi annulé par le suivant à part une partie au début et à la
fin. Ce cas est ainsi résumé par la formule (adaptable) :
$\sum\limits_{k = p}^{n}(U_{k+1} - U_k) = U_{n+1} - U_p$.

On peut le prouver plus rigoureusement par un changement d'indice, de la même
manière que pour la somme usuelle des entiers :
$\sum\limits_{k = p}^{n}(U_{k+1} - U_k) = \sum\limits_{k = p}^{n}u_{k+1} - \sum\limits_{k = p}^{n}u_k$\
$= \sum\limits_{j = p+1}^{n+1}U_j - \sum\limits_{k = p}^{n}U_k$\
$= U_{n+1} + \sum\limits_{k = p+1}^{n}u_k - U_p - \sum\limits_{k = p+1}^{n}U_k$\
$= U_{n+1} + U_p$\

On peut facilement appliquer ce raisonnement à la formule de la somme d'une
suite géométrique de l'exemple plus haut, avec $U_k = q^k$.

##### Exemple de télescopage
Soit $(a,b) \in \mathbb{C}^2$ et $n \in \mathbb{N}$, on cherche à calculer
$S_n = (a-b)\sum\limits_{k = 0}^{n}a^k b^{n-k}$
$= \sum\limits_{k = 0}^{n}(a^{k+1} b^{n-k} - a^k b^{n-k+1})$
On pose $U_k = a^k b^{n-k+1}$, et donc $U_{k+1} = a^{k+1} b^{n-k}$, donc on peut
conclure $S_n = U_{n+1} - U_0 = a^{n+1} - b^{n+1}$.

On peut aussi appliquer cette formule pour factoriser, nous permettant de
reconnaître que $a^{n+1}-b^{n+1} = (a-b)\sum\limits_{k = 0}^{n}a^k b^{n-k}$, qui
se retrouve dans $a^2 - b^2 = (a-b)(a+b)$ et $a^3 - b^3 = (a-b)(a^2 + ab + b^2)$.

###  Produits télescopiques
On veut calculer $\prod\limits_{i = p}^{n}a_i$ où le terme $a_i$ non nul peut s'écrire
$a_i = \frac{U_{i+1}}{U_i}$.
On est alors en présence d'un "produit télescopique". On pose
$\prod\limits_{i = p}^{n}(\frac{U_{i+1}}{U_i}) = (\frac{U_{p+1}}{U_p}) + (\frac{U_{p+2}}{U_{p+1}}) \ldots$
Chaque terme est ainsi annulé par le suivant à part une partie au début et à la
fin. Ce cas est ainsi résumé par la formule (adaptable) :
$\prod\limits_{i = p}^{n}(\frac{U_{i+1}}{U_i}) = \frac{U_{n+1}}{U_p}$.

On peut le prouver plus rigoureusement par un changement d'indice, de la même
manière que pour les sommes télescopiques.

##### Exemple : somme de logarithmes
$S_n = \sum\limits_{k = 1}^{n}\ln(1 + \frac{1}{k})$\
$= \sum\limits_{k = 1}^{n}\ln(\frac{k+1}{k})$\
$= \sum\limits_{k = 1}^{n}[\ln(k+1) - \ln(k)]$\
$= \ln(n+1) - \ln(1) = \ln(n+1)$\

Remarque : $\prod\limits_{k = 1}^{n}\frac{k+1}{k} = \frac{n+1}{1} = n+1$.
En prenant le ln, $\ln(n+1) = \ln(\prod\limits_{k = 1}^{n}\frac{k+1}{k}) = \sum\limits_{k = 1}^{n}\ln(\frac{k+1}{k}) = S_n$

Remarque : Soit $a_1, a_2, \ldots a_n \in \mathbb{R}^{\ast}\_{+}$,
$\ln(\prod\limits_{k = 1}^{n}ak) = \sum\limits_{k = 1}^{n}\ln(a_k)$ et
$\exp(\sum\limits_{k = 1}^{n}b_k) = \prod\limits_{k = 1}^{n}\exp(b_k)$.
Ces formules permettent de simplifier de nombreuses expressions avec des
puissances ou des logarithmes/exponentielles.

### Sommes usuelles
- $\forall n \in \mathbb{N}, \sum\limits_{k = 1}^{n}k = \frac{n(n+1)}{2}$
- $\forall n \in \mathbb{N}, \sum\limits_{k = 1}^{n}k^2 = \frac{n(n+1)(2n+1)}{6}$
- $\forall n \in \mathbb{N}, \sum\limits_{k = 1}^{n}k^3 = (\frac{n(n+1)}{2})^2$

Formule des suites géométriques : Soit $(p,n) \in \mathbb{N}^2$ avec $p \leq n$
et $q \in \mathbb{C}$, $\sum\limits_{k = p}^{n}q^k = q^p \times \sum\limits_{k = 0}^{n-p}q^k$
(stratégie de factorisation par le premier terme)
$= q^p \times \frac{1-q^{n-p+1}}{1-q}$ (quand $q \neq 1$) ou
$= n-p+1$ (quand $q = 1$)

##### Exemples
$\sum\limits_{k = 1}^{n}k \times (n-k-1) = \sum\limits_{k = 1}^{n}(nk - k^2 + k)$\
$= \sum\limits_{k = 1}^{n}(n+1)k - \sum\limits_{k = 1}^{n}k^2$\
$= (n+1) \sum\limits_{k = 1}^{n}k - \sum\limits_{k = 1}^{n}k^2$\
$= (n+1) \frac{n(n+1)}{2} - \frac{n(n+1)(2n+1)}{6}$\
$= \frac{n(n+1)}{6} [3(n+1) - 2(n+1)] = \frac{n(n+1)(n+2)}{6}$

$\sum\limits_{k = p}^{n}q^k = \sum\limits_{k = p}^{n}q^{k-p+p} = q^p \sum\limits_{k = p}^{n}q^{k-p}$
$= q^p \sum\limits_{j = 0}^{n-p}q^j = q^p \times \frac{1-q^{n-p+1}}{1-q}$ si
$q\neq 1$ et $n-p+1$ si $q=1$

Soit $x \in \mathbb{R}, x \neq \pm 1, \sum\limits_{k = 2}^{n-1}\frac{3^{k+1}x^{2k}}{5^{3k-2}}$.
On simplifie l'exposant du bas : $5^{3k+2} = 5^{3k} \times 5^{-2} = (5^{3})^k \times 5^{-2}$,
et ceux du haut : $3^{k+1} = 3^k \times 3$ et $x^{2k} = (x^2)^k$.
On a donc l'expression $\frac{3}{5^{-2}} (\frac{3x^2}{5^3})^k = 3 \times 5^2 \times (\frac{3x^2}{5^3})^k$,
ce qui est de forme $\lambda \times q^k$. Ainsi,
$S_n = 3 \times 5^2 \times \sum\limits_{k = 2}^{n-1}q^k$, soit si $q = 1$,
$75(n-2)$ et sinon $3 \times 5^2 \times q^2 \times \frac{1-q^{n-2}}{1-q}$

## Sommes doubles
Soit $(a_{i,j})_{i \in [1,n]\_{\mathbb{N}}, j \in [1,p]\_{\mathbb{N}}}$ une
famille de nombres. La somme de tous les éléments de cette famille est :
$\sum\limits_{(i,j) \in I}a_{i,j}$, avec $I = [1,n]\_{\mathbb{N}} \times [1, p]\_{\mathbb{N}}$.

On somme ainsi tout un tableau contenant tous les éléments de cette famille.

On a $\sum\limits_{(i,j) \in I}a_{i,j} = \sum\limits_{i = 1}^{n}(\sum\limits_{j = 1}^{p}a_{i,j})$
ou bien en inversant les lignes et les colonnes, $\sum\limits_{j = 1}^{p}(\sum\limits_{i = 1}^{n}a_{i,j})$.

On pourra noter, lorsque $1 \leq i \leq n$ et $1 \leq j \leq n$,
$\sum\limits_{1 \leq i,j \leq n}a_{i,j}$

### Cas particulier : Produit de deux sommes
$(\sum\limits_{i \in I}a_k) \times (\sum\limits_{j \in J}b_k)$
$= \sum\limits_{(i,j) \in I \times J}a_i \times b_j$

Attention à bien utiliser des indices muets différents pour chaque somme afin
d'éviter d'écrire des sommes dépendantes les unes des autres.

### Cas particulier : somme triangulaire
Soit $(a_{i,j})_{1 \leq i\leq n, 1 \leq j \leq p}$. On veut calculer la somme
triangulaire supérieure (c'est à dire avec la contrainte $i \leq j$). On note
$\sum\limits_{1 \leq i \leq j \leq n} a_{i,j}$ ou
$\sum\limits_{i = 1}^{n} \sum\limits_{j = i}^{n} a_{i,j}$ ou
$\sum\limits_{j = 1}^{n} \sum\limits_{i = 1}^{j} a_{i,j}$, etc...

De même, si on impose $i < j$, formant une somme triangulaire strict-supérieure,
on a les sommes :
$\sum\limits_{1 \leq i < j \leq n} a_{i,j}$ ou
$\sum\limits_{i = 1}^{n} \sum\limits_{j = i+1}^{n} a_{i,j}$ ou
$\sum\limits_{j = 1}^{n} \sum\limits_{i = 1}^{j-1} a_{i,j}$ (j commencera
d'ailleurs à 2), etc...

##### Exemple : double somme de minimums
$S_n = \sum\limits_{1 \leq i,j \leq n} min(i,j)$\
$= \sum\limits_{i = 1}^{n} \sum\limits_{j = 1}^{n} min(i,j)$\
$= \sum\limits_{i = 1}^{n} (\sum\limits_{j = 1}^{i} min(i,j) + \sum\limits_{j = i+1}^{n} min(i,j))$\
$= \sum\limits_{i = 1}^{n} (\sum\limits_{j = 1}^{i} j + \sum\limits_{j = i+1}^{n} i$\
$= \sum\limits_{i = 1}^{n} (\frac{i(i+1)}{2} + i \times (n-i))$\
$= \sum\limits_{i = 1}^{n} (i^2 \times \frac{-1}{2} + i \times (\frac{1}{2} + n))$\
$= (\frac{-1}{2}) \sum\limits_{i = 1}^{n}i^2 + (n + \frac{1}{2}) \times \sum\limits_{i = 1}^{n} i$\
$= (\frac{-1}{2}) \frac{n(n+1)(2n+1)}{6} + (\frac{2n+1}{2}) \times \frac{n(n+1)}{2}$\
$= \frac{n(n+1)(2n+1)}{12} (-1 + 3)$\
$= \frac{n(n+1)(2n+1)}{6}$\

## Coefficients binomiaux et sommes
> Rappel : $\left\{\begin{matrix} \forall n \in \mathbb{N}^{\ast}, n! = \prod\limits_{k = 1}^{n}k \\  0! = 1 \end{matrix}\right.$
> (la propriété de la factorielle de 0 n'est qu'un effet de la propriété des
> produits sur un ensemble vide).

> Propriété par relation de Chasles : $\forall n \in  \mathbb{N}^{\ast}, n! = n \times (n-1)!$

Selon cette propriété, on a $\forall n,p \in \mathbb{N}^{\ast}$,
$n \times (n+1) \times \ldots \times (n+p) = \frac{(n+p)!}{(n-1)!}$

##### Exemples
Pour $n \in \mathbb{N}^{\ast}$, on a :
- $2 \times 4 \times 6 \times \ldots \times (2n) = \prod\limits_{k = 1}^{n}(2k)$
  (produit des nombres pairs)
  $= 2^n \times (\prod\limits_{k = 1}^{n}k) = 2^n \times n!$
- Produit des nombres impairs : $1 \times 3 \times 5 \times \ldots \times (2n-1)$
  $= \prod\limits_{k = 1}^{n}(2k-1)$, ce qui est équivalent au produit des k
  consécutifs, sans les nombres pairs, soit $\frac{\prod\limits_{k = 1}^{2n}k}{\prod\limits_{k = 1}^{n}2k}$
  $= \frac{(2n)!}{\prod\limits_{k = 1}^{n}2n} = \frac{(2n)!}{2^n \times n!}$

### Coefficients binomiaux
Soient n et k des entiers, on note $\binom{n}{k}$ (le coefficient binomial "k
parmi n") le nombre de parties à k éléments d'un ensemble à n éléments.

Remarques :
- Pour tout k > n, $\binom{n}{k} = 0$
- Si n = 0, $\binom{0}{k} = 1$
- Pour tout $n \in \mathbb{N}$, $\binom{n}{n} = 1$
- $\forall k \in [0,n]\_{\mathbb{N}}, \binom{n}{k} = \binom{n}{n-k}$ (Symétrie)
  (il s'agit, au lieu d'un choix de k parmi n, d'un choix de ne pas prendre k
  parmi n).

__Définition :__ Pour $k \in [0,n]\_{\mathbb{N}}, \binom{n}{k} = \frac{n!}{k!(n-k)!}$.
On peut dire que la division par $k!$ permet d'enlever les doublons qui sont
tirés parmi tous les tirages (car il s'agit du nombre de permutations possibles
d'un k-uplet), tandis que $\frac{n!}{(n-k)!}$ correspond à tous les tirages
possibles de k éléments parmi n (qui sont autant de k-uplets).

On pourra aussi remarquer que $\binom{n}{k}$ compte aussi le nombre de chemins à
k succès lors de n épreuves de Bernoulli.

### Formule de Pascal : Coefficients binomiaux par récurrence
Pour $n,k \in \mathbb{N}^{\ast}, \binom{n}{k} = \binom{n-1}{k-1} + \binom{n-1}{k}$

#### Preuves de la formule de Pascal
__Preuve :__ $\binom{n-1}{k-1} = \frac{(n-1)!}{(k-1)!(n-k)!}$ et
$\binom{n-1}{k} = \frac{(n-1)!}{k!(n-1-k)!}$. En sommant, on a
$\binom{n-1}{k-1} + \binom{n-1}{k} = \frac{k(n-1)! + (n-k)(n-1)}{k!(n-k)!}$ (en
ayant multiplié $\binom{n-1}{k}$ par $\frac{n-k}{n-k}$), ce qui donne
$\frac{n(n-1)!}{k!(n-k)!} = \binom{n}{k}$.

On peut plus simplement visualiser cette somme par les chemins d'un arbre de
succès d'un épreuve de Bernoulli, avec k succès parmi n expériences : la branche
du premier succès contient encore $k-1$ succès lors de $n-1$ expériences, et
celle du premier échec contient encore $k$ succès parmi $n-1$ expériences.

Enfin, on peut montrer cette formule par l'observation des ensembles : pour
construire une partie à k éléments d'un ensemble à n éléments, on peut
disjoindre les cas où on inclut l'un des éléments x, et celui on l'on n'inclut
pas x. Ces deux cas sont ainsi les choix de k parmi n-1 éléments, et le choix de
k-1 éléments (on en a déjà sélectionné 1) parmi n-1 éléments. Le problème
original regroupe ces deux cas.

#### Triangle de Pascal
La formule précédente permet de calculer tous les coefficients, ligne par ligne,
où n numérote les lignes. On a ainsi un tableau de la forme :

n/k | 0   | 1   | 2   | 3   | 4   | 5   | 6   | ...
--- | --- | --- | --- | --- | --- | --- | --- | ---
0   | 1   | 0   | 0   | 0   | 0   | 0   | 0   | ...
1   | 1   | 1   | 0   | 0   | 0   | 0   | 0   | ...
2   | 1   | 2   | 1   | 0   | 0   | 0   | 0   | ...
3   | 1   | 3   | 3   | 1   | 0   | 0   | 0   | ...
4   | 1   | 4   | 6   | 4   | 1   | 0   | 0   | ...
5   | 1   | 5   | 10  | 10  | 5   | 1   | 0   | ...
6   | 1   | 6   | 15  | 20  | 15  | 6   | 1   | ...
... | ... | ... | ... | ... | ... | ... | ... | ...

On y retrouve toutes les propriétés précédentes, et nous permet de calculer
rapidement avec des opérations peu coûteuses les coefficients binomiaux.

#### Formule "du Chef" (à défaut de ne pas avoir de nom)
$k \times \binom{n}{k} = n \times \binom{n-1}{k-1}$, pour $k, n \in \mathbb{N}^{\ast}$.

__Preuve :__ Avec $k \geq 1, n \geq 1$, $k\binom{n}{k}$
$= k \times \frac{n!}{k!(n-k)!} = \frac{n!}{(k-1)!(n-k)!}$. Or,
$n \times \binom{n-1}{k-1} = \frac{n \times (n-1)!}{(k-1)! \times ((n-1)-(k-1))!}$.

On peut aussi visualiser le problème comme le choix d'un ensemble de k personnes
(une équipe) dont un chef parmi un ensemble de n personnes. Il y a deux
stratégies possibles :
1. Choisir le chef (n possibilités), qui choisit le reste de l'équipe (k-1
   personnes) parmi n-1 personnes, soit $n \times \binom{n-1}{k-1}$
   possibilités.
2. Choisir k personnes parmi n, puis on choisit le chef parmi celle-ci. On a
   donc $k(\binom{n}{k})$ possibilités.

Remarque : en pratique, pour $n, k \geq 1$, $\binom{n}{k} = \frac{n}{k} \times \binom{n-1}{k-1}$

Cette méthode est plus pratique en calcul, mais la formule de Pascal reste plus
simple algorithmiquement.

##### Exercice : Tous les coefficients binomiaux sont entiers
On cherche à montrer $\forall (n,k) \in \mathbb{N}^2$. Par récurrence, on a la
propriété $P(n) : \forall k \in \mathbb{N}, \binom{n}{k} \in \mathbb{N}$.
- Initialisation : Avec $n = 0$, $\binom{0}{0} = 1 \in \mathbb{N}$ et si $k > 0$,
  $\binom{0}{k} = 0 \in \mathbb{N}$, donc $P_0$ vraie.
- Hérédité : Soit $n \in \mathbb{N}^{\ast}$ tel que $P(n-1)$. Si $k = 0$,
  $\binom{n}{0} = 1 \in \mathbb{N}$. Si $k \geq 1, \binom{n}{k}$
  $= \binom{n-1}{k-1} + \binom{n-1}{k}$ (formule de Pascal).
  Par $P(n-1)$, $\binom{n-1}{k-1} \in \mathbb{N}$ et $\binom{n-1}{k} \in \mathbb{N}$,
  donc $\binom{n}{k} \in \mathbb{N}$, d'où $P(n)$ est vraie.

### Binôme de Newton
Pour tout $(a,b) \in \mathbb{C}^2$ et $n \in \mathbb{N}$,
$(a+b)^n = \sum\limits_{k = 0}^{n}\binom{n}{k}a^k b^{n-k}$.

Cette formule se retrouve dans des cas plus simples, comme l'identité
remarquable $(x + y)^2 = x^2 + 2xy + y^2$.

##### Exemples : compositions de cas spéciaux autour du binôme de Newton
$\sum\limits_{k = 0}^{n}\binom{n}{k} = \sum\limits_{k = 0}^{n}\binom{n}{k}1^k 1^{n-k}$
(donc la somme des coefficients binomiaux est un cas particulier du binôme de
Newton), ce qui donne $(1 + 1)^n = 2^n$

Somme alternée des coefficients binomiaux : $\sum\limits_{k = 0}^{n}\binom{n}{k}(-1)^k \times 1^{n-k}$
$= (-1 + 1)^n = 0^n$.

#### Preuve du binôme de Newton
Par récurrence sur n, soit $(a,b) \in \mathbb{C}^2$,
$P(n): [(a+b)^n = \sum\limits_{k = 0}^{n}\binom{n}{k}a^k b^{n-k}]$.
- Initialisation : $(a+b)^0 = 1$ et $\sum\limits_{k = 0}^{0}\binom{0}{k}a^k b^{0-k} = \binom{0}{0}a^0 b^0 = 1 \times 1 = 1$.
- Hérédité : Soit $n \geq 0$ tel que $P(n)$ est vraie, $(a+b)^{n+1} = (a+b) \times (a+b)^n$\
  $= (a+b) \times \sum\limits_{k = 0}^{n}\binom{n}{k}a^k b^{n-k}$\
  $= \sum\limits_{k = 0}^{n}\binom{n}{k}a^{k+1} b^{n-k} + \sum\limits_{k = 0}^{n}\binom{n}{k}a^k b^{n-k+1}$\
  $= \sum\limits_{k = 1}^{n+1}\binom{n}{k-1}a^k b^{n-k+1} + \sum\limits_{k = 0}^{n}\binom{n}{k}a^k b^{n-k+1}$\
  $= \binom{n}{n}a^{n+1} b^0 + \sum\limits_{k = 1}^{n}[\binom{n}{k-1} + \binom{n}{k}]a^k b^{n-k+1} + \binom{n}{0}a^0 b^{n+1}$\
  $= a^{n+1} + \sum\limits_{k = 1}^{n}\binom{n+1}{k}a^k b^{n+1-k} + b^{n+1}$

##### Technique supplémentaire : Sommation par paquets
$\sum\limits_{i \in E}a_i$ avec $E = I \cup J$ et $I \cap J = \emptyset$ (I et J
deux ensembles disjoints).
On a alors $\sum\limits_{i \in E}a_i = \sum\limits_{i \in I}a_i + \sum\limits_{j \in J} a_j$

Cette technique peut se retrouver par exemple dans la séparation de l'ensemble
entre les pairs et les impairs, ou différentes congruences. Il faut néanmoins
bien faire attention aux bornes données aux différentes sommes.
$&=  \\$
