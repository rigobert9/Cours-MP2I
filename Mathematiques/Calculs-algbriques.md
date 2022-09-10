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

###### Exemple de réduction par changement d'indice (formule de la somme d'une suite géométrique)
$(1 - q) \times \sum\limits_{k = 0}^{n}q^k = \sum\limits_{k = 0}^{n}(1 - q)q^k$
$= \sum\limits_{k = 0}^{n}(q^k - q^{k+1}) = (\sum\limits_{k = 0}^{n}q^k) - (\sum\limits_{k = 0}^{n}q^{k+1})$
$= \sum\limits_{k = 0}^{n}q^k - \sum\limits_{k = 1}^{n + 1}q^k$.
$= q^0 + \sum\limits_{k = 1}^{n}q^k - \sum\limits_{k = 1}^{n}q^k - q^{n+1}$.
$= 1 - q^{n+1}$

###### Exemple
Soit $p \leq n$ et $m \geq n$, $\sum\limits_{k = p}^{m}a_{m-k} = \sum\limits_{j = m-p}^{m-p}a_j$

###### Exemple : Somme usuelle des entiers (formule de la somme d'une suite arithmétique)
Somme usuelle des entiers $\sum\limits_{k = 0}^{n}k = S_n$.
On peut voir que $2S_n = 0 + 1 + \ldots + n\: + n + n-1 + \ldots + 0$, ce qui
donne $2S_n = n \times (n+1)$.

De façon plus rigoureuse, on peut ainsi noter :
$2S_n = \sum\limits_{k = 0}^{n}k + \sum\limits_{k = 0}^{n}k$
$= \sum\limits_{k = 0}^{n}k + \sum\limits_{j = 0}^{n}(n-j)$
$= \sum\limits_{k = 0}^{n}(k + (n-k))$
$= \sum\limits_{k = 0}^{n}n = (n+1) \times n$ (car n+1 est le nombre de termes).

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
$\sum\limits_{k = p}^{n}(U_{k+1} - U_k) = \sum\limits_{k = p}^{n}u_{k+1} - \sum\limits_{k = p}^{n}u_k$
$= \sum\limits_{j = p+1}^{n+1}U_j - \sum\limits_{k = p}^{n}U_k$
$= U_{n+1} + \sum\limits_{k = p+1}^{n}u_k - U_p - \sum\limits_{k = p+1}^{n}U_k$
$= U_{n+1} + U_p$

On peut facilement appliquer ce raisonnement à la formule de la somme d'une
suite géométrique de l'exemple plus haut, avec $U_k = q^k$.

###### Exemple de télescopage
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

###### Exemple : somme de logarithmes
$S_n = \sum\limits_{k = 1}^{n}\ln(1 + \frac{1}{k})$
$= \sum\limits_{k = 1}^{n}\ln(\frac{k+1}{k})$
$= \sum\limits_{k = 1}^{n}[\ln(k+1) - \ln(k)]$
$= \ln(n+1) - \ln(1) = \ln(n+1)$

Remarque : $\prod\limits_{k = 1}^{n}\frac{k+1}{k} = \frac{n+1}{1} = n+1$.
En prenant le ln, $\ln(n+1) = \ln(\prod\limits_{k = 1}^{n}\frac{k+1}{k}) = \sum\limits_{k = 1}^{n}\ln(\frac{k+1}{k}) = S_n$

Remarque : Soit $a_1, a_2, \ldots a_n \in \mathbb{R}^{\ast}\_{+}$,
$\ln(\prod\limits_{k = 1}^{n}ak) = \sum\limits_{k = 1}^{n}\ln(a_k)$ et
$\exp(\sum\limits_{k = 1}^{n}b_k) = \prod\limits_{k = 1}^{n}\exp(b_k)$.
Ces formules permettent de simplifier de nombreuses expressions avec des
puissances ou des logarithmes/exponentielles.

### Sommes usuelles
- $\forall n \in \mathbb{N}, \sum\limits_{k = 1}^{n}k = \frac{n(n+1)}{2}$
- $\forall n \in \mathbb{N}, \sum\limits_{k = 1}^{n}k^6 = \frac{n(n+1)(2n+1)}{6}$
- $\forall n \in \mathbb{N}, \sum\limits_{k = 1}^{n}k^3 = (\frac{n(n+1)}{2})^2$

Formule des suites géométriques : Soit $(p,n) \in \mathbb{N}^2$ avec $p \leq n$
et $q \in \mathbb{C}$, $\sum\limits_{k = p}^{n}q^k = q^p \times \sum\limits_{k = 0}^{n-p}q^k$
(stratégie de factorisation par le premier terme)
$= q^p \times \frac{1-q^{n-p+1}}{1-q}$ (quand $q \neq 1$) ou
$= n-p+1$ (quand $q = 1$)

###### Exemples
$\sum\limits_{k = 1}^{n}k \times (n-k-1) = \sum\limits_{k = 1}^{n}(nk - k^2 + k)$
$= \sum\limits_{k = 1}^{n}(n+1)k - \sum\limits_{k = 1}^{n}k^2$
$= (n+1) \sum\limits_{k = 1}^{n}k - \sum\limits_{k = 1}^{n}k^2$
$= (n+1) \frac{n(n+1)}{2} - \frac{n(n+1)(2n+1)}{6}$
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

###### Exemple : double somme de minimums
$S_n = \sum\limits_{1 \leq i,j \leq n} min(i,j)$
$= \sum\limits_{i = 1}^{n} \sum\limits_{j = 1}^{n} min(i,j)$
$= \sum\limits_{i = 1}^{n} (\sum\limits_{j = 1}^{i} min(i,j) + \sum\limits_{j = i+1}^{n} min(i,j))$
$= \sum\limits_{i = 1}^{n} (\sum\limits_{j = 1}^{i} j + \sum\limits_{j = i+1}^{n} i$
$= \sum\limits_{i = 1}^{n} (\frac{i(i+1)}{2} + i \times (n-i))$
$= \sum\limits_{i = 1}^{n} (i^2 \times \frac{-1}{2} + i \times (\frac{1}{2} + n))$
$= (\frac{-1}{2}) \sum\limits_{i = 1}^{n}i^2 + (n + \frac{1}{2}) \times \sum\limits_{i = 1}^{n} i$
$= (\frac{-1}{2}) \frac{n(n+1)(2n+1)}{6} + (\frac{2n+1}{2}) \times \frac{n(n+1)}{2}$
$= \frac{n(n+1)(2n+1)}{12} (-1 + 3)$
$= \frac{n(n+1)(2n+1)}{6}$
