# Nombres complexes et trigonométrie
## Rappels
### Trigonométrie
> Soient $a,b \in \mathbb{R}$ et $x,y \in \mathbb{R}$, on dit que x est congru à y
> modulo a ($x \equiv y[a]$) si $\exists x \in \mathbb{Z}, \exists x \in \mathbb{Z}, x = y + ka$.

Remarque : soient $(a,b) \in \mathbb{R}^2$ fixés, on a
$\{x \in \mathbb{R} \mid x \equiv b[a]\}$\
$= \{b + ka, k \in \mathbb{Z}\}$\
$= b + a \mathbb{Z}$

##### Exemple : Multiples de $2 \pi$
$\{x \in \mathbb{R} \mid x \equiv 0[2\pi]\}$\
$= \{2\pi x, x \in \mathbb{Z}\} = 2 \pi \mathbb{Z}$

#### Cosinus et sinus
Le cercle trigonométrique
$\mathcal{C}(0,1) = \{(x,y) \in \mathbb{R}^2 \mid x^2 + y^2 = 1\}$
de centre $(0,0)$ et de rayon 1 a
$\forall (x,y) \in \mathcal{C}(0,1), \exists \Theta \in \mathbb{R}, \left\{\begin{matrix} x = \cos \Theta \\ y = \sin \Theta \end{matrix}\right.$.
Ainsi, $\forall \Theta \in \mathbb{R}, \cos^2 \Theta + \sin^2 \Theta = 1$.

#### Cosinus
En tant que fonctions, $\cos$ et $\sin$ sont $(2\pi)$-périodiques. On a ainsi
les propriétés suivantes :
- $\cos(x) = 1 \Leftrightarrow x \equiv 0[2 \pi ] \Leftrightarrow x \in 2 \pi \mathbb{Z}$
- $\cos(x) = 0 \Leftrightarrow x \equiv \pm \frac{\pi}{2} [2 \pi]$\
  $\Leftrightarrow x \equiv \frac{\pi}{2} [\pi]$\
  $\Leftrightarrow (x \in \frac{\pi}{2} + \pi \mathbb{Z})$
- $\forall x \in \mathbb{R}, \cos(x + \pi) = -\cos(x)$
- $\forall k \in \mathbb{Z}, \cos(x + k \pi) = (-1)^k \cos(x)$,
  en particulier $\cos(x \pi) = (-1)^k$.

La fonction $\cos: \mathbb{R} \to \mathbb{R}$ est paire, $2 \pi$-périodique,
dérivable sur $\mathbb{R}$ et $\cos' = -\sin$.

On a le tableau de valeurs courantes suivant :

x         | 0   | $\frac{\pi}{6}$      | $\frac{\pi}{4}$      | $\frac{\pi}{3}$ | $\frac{\pi}{2}$
---       | --- | ---                  | ---                  | ---             | ---
$\cos(x)$ | 1   | $\frac{\sqrt{3}}{2}$ | $\frac{\sqrt{2}}{2}$ | $\frac{1}{2}$   | 0

#### Sinus
Pour sinus, on obtient les propriétés suivantes :
- $\sin(x) = 0 \Leftrightarrow x \equiv 0[\pi] \Leftrightarrow x \in \pi \mathbb{Z}$
- $\sin(x) = 1 \Leftrightarrow x \equiv \frac{\pi}{2} [2 \pi]$\
  $\Leftrightarrow (x \in \frac{\pi}{2} + 2 \pi \mathbb{Z})$
- $\forall x \in \mathbb{R}, \sin(x + \pi) = -\sin(x)$
- $\forall k \in \mathbb{Z}, \sin(x + k \pi) = (-1)^k \sin(x)$,
  en particulier $\sin(x \pi) = 0$.

La fonction $\sin: \mathbb{R} \to \mathbb{R}$ est impaire, $2 \pi$-périodique
dérivable et $\sin' = \cos$. De plus, on a $\lim_{x \to 0} \frac{\sin(x)}{x} = 1$,
ce qui permet d'avoir $\sin(x) \approx x$ si $x \ll 1$.
De plus, $\forall x \in \mathbb{R}, |\sin(x)| \leq |x|$.

On a le tableau de valeurs courantes suivant :

x         | 0   | $\frac{\pi}{6}$ | $\frac{\pi}{4}$      | $\frac{\pi}{3}$      | $\frac{\pi}{2}$
---       | --- | ---             | ---                  | ---                  | ---
$\sin(x)$ | 0   | $\frac{1}{2}$   | $\frac{\sqrt{2}}{2}$ | $\frac{\sqrt{3}}{2}$ | 1

#### Relations
- $\sin(a+b) = \cos(a)\sin(b) + \sin(a)\cos(b)$
- $\cos(a+b) = \cos(a)\cos(b) - \sin(a)\sin(b)$

### Complexes
Soit $\mathbb{C}$ l'ensemble des complexes, $\mathbb{R} \subset \mathbb{C}$, et
cet ensemble défini par $\left\{\begin{matrix} a + ib \in \mathbb{C} \\ a, b \in \mathbb{R} \land i^2 = -1 \end{matrix}\right.$. Cet ensemble ne possède pas d'ordre (il n'est donc pas possible de comparer par l'inégalité $\leq$).
On peut aussi le définir par compréhension tel que
$\mathbb{R}^2 = \{(x,y), x,y \in \mathbb{R}\}$.

$\mathbb{C}$, comme $\mathbb{R}$, fait partie des corps ($\mathbb(K)$), c'est à
dire que les opérations d'addition, de multiplication, de soustraction et de
division sont possibles avec les mêmes propriétés que dans $\mathbb{R}$.

On a ainsi pour l'addition $(x,y) + (x',y') = (x + x', y + y')$.
La valeur nulle, ici $(0,0) = 0 + 0i$ (qui peut être noté 0), est aussi
l'élément neutre de l'addition.

On a aussi la multiplication telle que
$(x,y) \times (x',y') = (xx' - yy', x'y + xy')$. De plus, celle-ci est toujours
commutative, associative, et distributive sur l'addition.

On a $\forall z \in \mathbb{C}, \exists! (a,b) \in \mathbb{R}^2, z = a +ib$.
On note $\left\{\begin{matrix} a = \Re(z) \,\text{(partie réelle de z)} \\ b = \Im(z) \,\text{(partie imaginaire de z)} \end{matrix}\right.$.

On représente graphiquement les complexes sur le plan comme un point, avec pour
tout $z$ $\Re(z)$ l'abscisse et $\Im(z)$ l'ordonnée.
On a la droite des abscisses la droite des réels, et celle des ordonnées la
droite des imaginaires purs, soit pour les ensembles ci-avant $\mathbb{R} \cap i\mathbb{R} = \{0\}$ et
$\left\{\begin{matrix} \mathbb{R} \subset \mathbb{C} \\ i\mathbb{R} \subset \mathbb{C} \end{matrix}\right.$,
et donc $\left\{\begin{matrix} \forall z \mid \Im(z) = 0 \Leftrightarrow z \in \mathbb{R} \\ \forall z \mid \Re(z) = 0 \Leftrightarrow z \in i\mathbb{R}\end{matrix}\right.$.

Soient $\left\{\begin{matrix} z = a + ib \\ z' = c + id \end{matrix}\right.$, on
a $\Re(z + z') = \Re(z) + \Re(z')$ et $\Im(z + z') = \Im(z) + \Im(z')$. De plus,
si $d \in \mathbb{R}, dz = d\Re(z) + d\Im(z)$.
Le produit de deux complexes ne permet pas ces simplifications.

On peut facilement développer pour ces démonstrations
$\forall z \in \mathbb{C}, z = \Re(z) + i\Im(z)$, avec
$\Re(z) \in \mathbb{R}$ et $\Im(z) \in \mathbb{R}$.

#### Interprétation géométrique
Soit $(O, \overrightarrow{\rm e_x}, \overrightarrow{\rm g_x})$ un repère orthonormé direct du plan. Soit $M$ un point du plan de
coordonnées $(a,b) \in \mathbb{R}^2$, $\overrightarrow{\rm OM} = a\overrightarrow{\rm e_x} + b\overrightarrow{\rm g_x}$.
Le complexe $z$ est dit d'affixe $\overrightarrow{\rm OM}$ ou $M$.

On peut ainsi voir l'addition de deux complexes comme l'addition de leurs
vecteurs affixes. De plus, on peut voir qu'avec $d \in \mathbb{R}$ et $\overrightarrow{\rm u}$ le vecteur d'affixe
$z$, le vecteur $d \overrightarrow{\rm u}$ est d'affixe $dz$.

#### Opérations sur les complexes
> La conjugaison est l'opération qui à tout $z = a + ib$ associe $a - ib$, et est
> notée $\overline{z}$. On a ainsi $\left\{\begin{matrix} \Re(\overline{z}) = \Re(z) \\ \Im(\overline{z}) = -\Im(z) \end{matrix}\right.$.
> Géométriquement, il s'agit du symétrique au vecteur ou a point affixe de $z$ par
> l'axe des abscisses.

On a ainsi $\forall z \in \mathbb{C}, \frac{z + \overline{z}}{2} = \Re(z)$ et
$\forall z \in \mathbb{C}, \frac{z - \overline{z}}{2i} = \Im(z)$. On peut de
plus poser les équivalences $z = \overline{z} \Leftrightarrow z \in \mathbb{R}$
et $z = -\overline{z} \Leftrightarrow z \in i\mathbb{R}$.

On peut aussi vérifier par le calcul que $\forall (z,z') \in \mathbb{C}^2$ :
- $\overline{z + z'} = \overline{z} + \overline{z'}$
- $\overline{z \times z'} = \overline{z} \times \overline{z'}$
- Si $z' \neq 0$, $\overline{(\frac{z}{z'})} = \frac{(\overline{z})}{\overline{z'}}$

Identité remarquable : Soient $(a, b) \in \mathbb{C}^2, a^2 + b^2 = (a - ib)(a + ib) = z \times \overline{z}$.

> Le module d'un complexe $z$, noté $|z|$, est défini par
> $|z| = \sqrt{\overline{z}z} = \sqrt{\Re(z)^2 + \Im(z)^2}$. Soit M un point du
> plan d'affixe $z$, on a $\lVert \overrightarrow{\rm OM} \rVert = |z|$.

Puisque, si $z \in \mathbb{R}, |z| = \sqrt{\Re(z)^2} = \sqrt{z^2}$, on a le
module qui prolonge sur $\mathbb{C}$ l'application de la valeur absolue dans $\mathbb{R}$.

De plus, puisque $\forall z \in \mathbb{C} \setminus \{0\}, |z| \in \mathbb{R}_{+}^{\ast}$,
on a $z \times \overline{z} = |z|^2 \Rightarrow z \times \frac{\overline{z}}{|z|^2} = 1$.
Ainsi, tout complexe $z$ non nul possède un inverse dans $\mathbb{C}$,
et $\frac{1}{z} = \frac{\overline{z}}{|z|^2}$.

On remarque aussi l'égalité $z z' = |z|^2$.

On a alors les propriétés suivantes $\forall (z, z') \in \mathbb{C}^2$ :
- $|z \times z'| = |z| \times |z'|$
- si $z' \neq 0$, $|\frac{z}{z'}| = \frac{|z|}{|z'|}$
- $\forall k \in \mathbb{Z}, |z'^k | = |z'|^k$
- $\Re(z) \leq |\Re(z)| \leq |z|$
- $\Im(z) \leq |\Im(z)| \leq |z|$

##### Résultat : inégalité triangulaire
Avec $M$ un point affixe d'un complexe $z$, un triangle $O, M, \Re(z)$,
on vérifie $\forall (z,z') \in \mathbb{C}, |z+z'| \leq |z| + |z'|$.
De plus, il y a égalité si et seulement si $z$ et $z'$ sont colinéaires et de
même sens, soit $z = 0 \lor \exists \lambda \in \mathbb{R}_{+}, z' = \lambda z$.

Corollaire 1 : $| |z| - |z'| | \leq |z - z'|  \leq |z| + |z'|$

Corollaire 2 : $\forall n \in \mathbb{N}^{\ast}$ et $\forall (z_1, \ldots, z_n) \in \mathbb{C}^n$,
$|\sum\limits_{k = 1}^{n} z_k | \leq \sum\limits_{k = 1}^{n} |z_k|$

##### Preuve
Inégalité triangulaire : On a $|z + z'|^2 = (z + z') \times \overline{(z + z')}$\
$= (z + z') \times (\overline{z} + \overline{z'})$\
$= z \overline{z} + z \overline{z'} + z' \overline{z} + z' \overline{z'}$\
$= |z|^2 + z \overline{z'} + \overline{z \overline{z'}} + |z'|^2$ (à l'aide de l'identité remarquable)\
$= |z|^2 + \Re(z \overline{z'}) + |z'|^2$\
Or $\Re(z \overline{z'}) \leq |\Re(z \overline{z'})| \leq |z \overline{z'}|$
et $|z \overline{z'}| = |z| \times |\overline{z'}| = |z| \times |z'|$.
Ainsi, $|z|^2 + 2 \Re(z \overline{z'}) + |z'|^2 \leq |z|^2 + 2 |z| |z'| + |z'|^2$,
d'où $|z + z'|^2 \leq (|z| + |z'|)^2$. Par croissance de $\sqrt{  }$ sur $\mathbb{R}_{+}$,
$|z + z'| \leq |z| + |z'|$.

On a ainsi les cas d'égalité quand $z = 0$, car
$|z + z'| = |z'| = |0| + |z'|$, et lorsque
$\exists \lambda \in \mathbb{R}_{+}, z' = \lambda z$ car par analyse
on a $|z + z'| = |z + \lambda z|$\
$= |(\lambda + 1) z|$\
$= |\lambda + 1| \times |z|$\
$= (\lambda + 1) \times |z|$ (car $\lambda \in \mathbb{R}_{+}$)\
$= \lambda |z| + |z|$\
$= |\lambda z| + |z|$\
$= |z'| + |z|$\
On vérifie enfin par synthèse cette même propriété. Si on a égalité, alors on a
$\Re(z \overline{z'}) = |\Re(z \overline{z'})| = |z \overline{z'}|$.
Ainsi, on a $z \times \overline{z'} \in \mathbb{R}_{+}$. Avec $\mu = z \overline{z'} \in \mathbb{R}_{+}$,
$z' \mu = z \overline{z'} z' = z \times |z'|^2$.
**Finir exercice**

Corollaire 2 : *laissé comme exercice*

Corollaire 1 : $|z - z'| = |z + (-z')| \leq |z| + |-z'| = |z| + |z'|$.
On a $z = (z - z') + z'$, et avec $a = z - z'$ et $b = z'$, et selon l'inégalité
triangulaire, $|a + b| \leq |a| + |b|$.
On obtient donc $|z| \leq |z - z'| + |z'|$, soit $|z| - |z'| \leq |z - z'|$.
En échangeant le rôle de $z$ et de $z'$, on retrouve la formule
$|z'| - |z| \leq |z - z'|$.

#### Module géométrique
$|z - z'|$ est la distance entre les points d'affixes $z$ et $z'$.
On définit ainsi un cercle de centre $\Omega$, $\omega$ et de rayon r par
(avec $\omega \in \mathbb{C}$ et $r \in \mathbb{R}^{\ast}_{+}$) :
$\mathcal{C}(\omega , r) = \{z \in \mathbb{C} \mid |z- \omega| = r\}$.

On définit de même la boule fermée telle que
$\mathcal{C}(\omega , r) = \{z \in \mathbb{C} \mid |z- \omega| \leq r\}$
et la boule ouverte telle que
$\mathcal{C}(\omega , r) = \{z \in \mathbb{C} \mid |z- \omega| < r\}$.

#### Représentations
L'écriture algébrique d'un complexe, la forme $z = a + ib$, est utilisée pour
les sommes, le placement sur le plan directement, et la multiplication par des
réels.

L'écriture trigonométrique d'un complexe est la forme $z = |z| \cos \Theta + |z| i \sin \Theta$,
avec un angle $\Theta \in \mathbb{R}$.

La notation exponentielle, la forme $z = e^{i \Theta}$, est utilisée pour les
produits et les quotients, ainsi que pour les puissances grâce aux propriétés
représentées par l'exponentielle. Elle est équivalente à la forme
trigonométrique $z = \cos \Theta + i \sin \Theta$ lorsque ses facteurs sont de
1, et on multiplie par le module pour obtenir tout autre nombre complexe.

## Complexes de module 1 et trigonométrie
### Cercle trigonométrique
> $\mathcal{C}(0,1) = \{z \in \mathbb{C} \mid |z| = 1\}$ est noté $\mathbb{U}$,
> l'ensemble des complexes de module 1.

$\mathbb{U}$ est stable par produit, passage à l'inverse et conjugaison,
$\forall (z, z') \in \mathbb{U}^2$ :
- $z \times z' \in \mathbb{U}$
- $\frac{1}{z} \in \mathbb{U}$
- $\overline{z} \in \mathbb{U}$

En effet, si $|z| = 1 = |z'|$, alors $|z \times z'| = |z| \times |z'| = 1$,
$|\frac{1}{z}| = \frac{1}{|z|} = 1$ et $|\overline{z}| = |z| = 1$.

Fait important, $\forall z \in \mathbb{U}, \frac{1}{z} = \overline{z}$, puisque
$z \overline{z} = |z|^2 = 1$.

On sait que $\mathbb{U} = \{z \in \mathbb{C}, |z| = 1\}$\
$= \{x + iy \in \mathbb{C}, x^2 + y^2 = 1\}$\
$= \{\cos^2 \Theta + \sin^2 \Theta = 1, \Theta \in \mathbb{R}\}$

On note, avec les propriétés du cercle trigonométrique,
$\forall (\Theta, \phi) \in \mathbb{R}, e^{i \Theta} \times e^{i \varphi} = e^{i( \Theta + \varphi )}$.
On peut le prouver par le calcul en repassant par la forme trigonométrique.
De plus, on peut ainsi prouver les formules d'addition sur les cosinus et sinus
à l'aide de cette formule, ainsi que les formules de duplication.

On a de plus (vérifiables par la forme trigonométrique) $e^{-i \Theta} = \overline{e^{i \Theta}} = \frac{1}{e^{i \Theta}}$.

On vérifie alors, lorsque $e^{i \Theta} = e^{i \varphi} \Leftrightarrow \left\{\begin{matrix} \cos \Theta = \cos \varphi \\ \sin \Theta = \sin \varphi \end{matrix}\right.$,
que $\Theta \equiv \varphi [2 \pi]$.

À partir des formules d'addition et de leurs inverses ($\cos(a-b)$), on peut facilement obtenir des formules de
linéarisation, soit $\left\{\begin{matrix} \cos(a+b) = \cos(a)\cos(b) - \sin(a)\sin(b) \\ \sin(a+b) = \sin(a)\cos(b) + \cos(a)\sin(b) \end{matrix}\right.$ :
- $\cos(a)\cos(b) = \frac{1}{2} (\cos(a+b) + \cos(a-b))$
- $\sin(a)\sin(b) = \frac{1}{2} (\cos(a-b) + \cos(a+b))$
- $\sin(a)\cos(b) = \frac{1}{2} (\sin(a + b) + \sin(a-b))$

#### Technique de l'arc-moitié
$\left\{\begin{matrix} \cos p + \cos q = \Re(e^{ip} + e^{iq}) \\ \sin p + \sin q = \Im(e^{ip} + e^{iq}) \end{matrix}\right.$\
On force l'apparition de l'angle $\frac{p + q}{2}$ :
$e^{ip} + e^{iq} = e^{i(\frac{p + q}{2})} \times [e^{i\frac{p-q}{2}} + e^{i \frac{q-p}{2}}]$.
On voit alors apparaître $e^{i \Theta} + e^{-i \Theta}$ (qui sont un nombre et
son conjugué), soit $e^{i \Theta} + e^{-i \Theta} = 2 \Re(e^{i \Theta}) = 2 \cos \Theta$.
On peut ainsi dégager $e^{ip} + e^{iq} = e^{i (\frac{p+q}{2})} \times 2 \cos (\frac{p-q}{2})$
$= [\cos(\frac{p+q}{2}) + i \sin(\frac{p+q}{2})] \times 2 \cos (\frac{p-q}{2})$

On obtient ainsi $\Re(e^{ip} + e^{iq}) = 2 \cos (\frac{p+q}{2}) \cos(\frac{p-q}{2}) = \cos p + \cos q$,
et $\Im(e^{ip} + e^{iq}) = 2 \cos(\frac{p-q}{2}) \times \sin(\frac{p+q}{2}) = \sin p + \sin q$.

On a ainsi les formules d'Euler : $\forall \Theta \in \mathbb{R}, \left\{\begin{matrix} \cos \Theta = \frac{e^{i \Theta} + e^{-i \Theta}}{2} \\ \sin \Theta = \frac{e^{i \Theta} + e^{-i \Theta}}{2i} \end{matrix}\right.$

On procède de même pour $e^{ip}- e^{iq}$.
$e^{ip} - e^{iq} = e^{i \frac{p+q}{2}} \times [e^{i \frac{p-q}{2}} - e^{i \frac{q-p}{2}}]$ (qui est équivalent à $z - \overline{z} = 2 \Im(z)$),
$e^{i \frac{p+q}{2} \times 2 i \sin(\frac{p-q}{2})}$,
donc $\Re(e^{ip} - e^{iq}) = \cos p - \cos q = -2 \sin(\frac{p+q}{2}) \sin(\frac{p-q}{2})$
et $\Im(e^{ip} - e^{iq}) = \sin p - \sin q = 2\cos(\frac{p+q}{2}) \sin(\frac{p-q}{2})$

Cette méthode est ainsi utilisable dans la plupart des cas ou on retrouve $e^{ip} \pm e^{iq}$.

#### Formule de Moivre
> $\forall \Theta \in \mathbb{R}, \forall n \in \mathbb{Z}, (\cos \Theta + i \sin \Theta)^n = \cos(n \Theta) + i \sin(n \Theta)$

Preuve : $(e^{i \Theta})^n = e^{i (n \Theta)}$

##### Application
Exprimer $\cos(5 x)$ et $\sin(5 x)$ en fonction uniquement de $\cos x$ et $\sin x$.

Idée : $\cos(5x) + i \sin(5x) = e^{i 5x} = (e^{ix})^5 = (\cos x + i \sin x)^5$\
Binôme de Newton : $[\cos^5(x) - 10\cos^3 x \sin^2 x + 5 \cos x \sin^4 x] + i[5\cos^4 x \sin x - 10 \cos^2 x \sin^3 x + \sin^5 x]$\
Donc $\cos(5x) = \cos^5(x) - 10 \cos^3(x) [1-\cos^2 x] + 5\cos x [1 - \cos^2 x]^2 = 16 \cos^5 x - 20 \cos^3 x + 5 \cos x = P(\cos x)$,
avec $P(X) = 16 X^5 - 20 X^3 + 5X$, un polynôme en $\cos x$ (cf Tchebychev).

##### Propriété
Exprimer $\cos(nx)$ comme un polynôme en $\cos x$ ($P_n | \forall x \in \mathbb{R}, \cos(nx) = P_n(\cos x)$).
$\cos(nx) = \Re(e^{inx}) = \Re((\cos x + i \sin x)^n) = \Re(\sum\limits_{k = 0}^{n}\binom{n}{k} (i \sin x)^k \cos(x)^{n-k})$.
On sait que $(i \sin x)^k \in \mathbb{R}$ si et seulement si k est pair, donc on
sépare les indices de la somme et on ne conserve que les pairs. Ainsi,
$\cos(nx) = \sum\limits_{0 \leq k \leq m}\binom{n}{k} (i \sin x)^k (\cos x)^{n-k}$ pour tout k pair.
On pose $k = 2p$ où $0 \leq 2p \leq n$, $p \in \mathbb{N}$ donc $0 \leq p \leq \left\lfloor \frac{n}{2} \right\rfloor$,
soit
$\cos(nx) = \sum\limits_{p = 0}^{\left\lfloor \frac{n}{2} \right\rfloor} \binom{n}{2p} (i \sin x)^{2p} (\cos x)^{n-2p}$.
Cela donne donc $\cos(nx) = P_n(\cos x)$, avec $P_n(X) = \sum\limits_{k = 0}^{\left\lfloor \frac{n}{2} \right\rfloor} \binom{n}{2k} (-1)^k (1 - X^2)^x X^{n-2k}$ (n-ième polynôme de Tchebychev).

#### Chemin inverse
On cherche par exemple à calculer $\int\limits_{0}^{\pi} (\sin (t))^2 dt$. On
décide d'abord d'appliquer une stratégie de linéarisation :
$\cos(2t) = 1 - 2 \sin^2(t)$, donc $\sin^2(t) = \frac{1 - \cos 2t}{2}$,
donc $\int\limits_{0}^{\pi} \frac{1 - \cos 2t}{2} dt = \frac{\pi}{2} \int\limits_{0}^{\pi} \frac{\cos(2t)}{2} dt$.

Les primitives sont néanmoins difficiles à retrouver dans certains cas.

__Stratégie universelle de linéarisation :__ On remplace
$\cos(t)^m \times \sin(t)^n$ par des sommes de termes en $\cos(kt)$ et $\sin(kt)$.
Cette stratégie est utile pour les calculs de primitives ou de dérivées
multiples.
On a ainsi la formule d'arrivée $\sum\limits_{k = 0}^{y} (a_k \sin(kt) + b_t \cos(kt))$

On peut aussi passer par les formules d'Euler. En effet, on a $\cos(t)^m \times \sin(t)^n = [\frac{e^{it} + e^{-it}}{2}]^m \times [\frac{e^{it} + e^{-it}}{2i}]^n$.
En développant tout massivement par binôme et distribution, il restera des
termes de la forme $e^{ikt}$ et $e^{-ikt}$ et les formules d'Euler
reconstruisent les $\cos(kt)$ et $\sin(kt)$.

##### Exemple d'application avec Euler
$(\sin t)^4 = (\frac{e^{it} - e^{-it}}{2i})^4$ (Euler) $= \frac{1}{(2i)^4} (e^{4it} - 4 e^{2it} + 6 e^{i 0 t} - 4 e^{-2it} + e^{-4it})$ (Binôme)
$= \frac{1}{8} (2 \cos(4t) - 4 \times 2 \cos(2t) + 6)$

#### Application en Physique
On cherche souvent en physique à retrouver une formule sous la forme $C \cos(t + \varphi)$,
avec C une amplitude et $\varphi$ un déphasage, à partir d'une forme $a \cos(t) + b \sin(t)$

> Transformation de Fresnel : Soit $(a,b) \in \mathbb{R}^2 \setminus \{(0,0)\}$,\
> $\exists A \in \mathbb{R}_{+}, \exists \Theta \in \mathbb{R}, \forall t \in \mathbb{R}, a \cos(t) + b \sin(t) = A \cos(t - \Theta)$

L'idée est ici de $(\frac{a}{\sqrt{a^2 + b^2}})^2 + (\frac{b}{\sqrt{a^2 + b^2}}) = 1$ (car $\frac{a^2 + b^2}{a^2 + b^2} = 1$ ).
On pose alors $A = \sqrt{a^2 + b^2}$ (l'amplitude). $a \cos t + b \sin t = A \times [\frac{a}{A} \cos t + \frac{b}{A} \sin t]$,
or $(\frac{a}{A})^2 + (\frac{b}{A})^2 = 1$, donc le couple $(\frac{a}{A}, \frac{b}{A})$ est sur le cercle trigonométrique.
On en déduit que $\exists \Theta \in \mathbb{R}^{\ast}, \left\{\begin{matrix} \cos \Theta = \frac{a}{A} \\ \sin \Theta = \frac{b}{A} \end{matrix}\right.$.
Ainsi $a \cos t + b \sin t = A[\cos \Theta \cos t + \sin \Theta \sin t] = A \cos(t-\Theta)$.

##### Exemple : $\forall x \in \mathbb{R}, |\cos(x) + \sin(x)| \leq \sqrt{2}$
On applique la transformation de Fresnel, et on obtient ainsi
$\cos(x) + \sin(x) = \sqrt{2}(\frac{\sqrt{2}}{2} \cos(x) + \frac{\sqrt{2}}{2} \sin(x))$
$= \sqrt{2}(\cos(\frac{\pi}{4}) \cos(x) + \sin(\frac{\pi}{4}) \sin(x))$
$= \sqrt{2} \cos(x - \frac{\pi}{4})$.
Or $-1 \leq \cos(x) \leq 1$, donc $|\cos(x)| \leq 1$, d'où le résultat.

On peut aussi résoudre cet exemple en remplaçant les premières étapes par une
écriture développée du module (qui est ici une valeur absolue), ce qui mène à
une réduction de $\cos^2 + \sin^2$.

### Fonction tangente
> Pour tout $x \in \mathbb{R} \setminus \{\frac{\pi}{2} + k\pi , k \in \mathbb{Z}\}$ (les réels où cosinus est non nul),
> on définit $\tan(x) = \frac{\sin x}{\cos x}$.

Géométriquement, il s'agit de la taille du côté opposé à l'angle dans le cercle
trigonométrique du triangle rectangle formé par le segment de l'origine au point
0 et par l'angle. Puisque le segment de l'origine au point 0 est de taille 1, on
a bien $\frac{\sin x}{\cos x} = \frac{\tan x}{1}$.

On remarque que l'ensemble de définition de la tangent peut aussi s'écrire comme
la réunion d'intervalles $\bigcup\limits_{k \in \mathbb{Z}} ]\frac{-\pi}{2} + k\pi , \frac{\pi}{2} + k\pi[$

On a le tableau de valeurs remarquables :

x        | 0   | $\frac{\pi}{6}$      | $\frac{\pi}{4}$ | $\frac{\pi}{3}$ | $\frac{\pi}{2}$
---      | --- | ---                  | ---             | ---             | ---
$\tan x$ | 0   | $\frac{1}{\sqrt{3}}$ | 1               | $\sqrt{3}$      | X

#### Variations
$\tan$ est dérivable sur tout intervalle $I_k = ]\frac{-\pi}{2} + k\pi , \frac{\pi}{2} + k\pi [$,
et $\tan' = (\frac{\sin}{\cos})' = \frac{\sin' \cos - \sin \cos'}{\cos^2} = \frac{\cos^2 + \sin^2}{\cos^2}$
$ = \frac{1}{\cos^2} = 1 + \tan^2$.

> $\tan' = \frac{1}{\cos^2} = 1 + \tan^2$

Ainsi tan est strictement croissante sur chaque intervalle $I_k$.

#### Symétrie/Périodicité
$\tan(-x) = \frac{\sin(-x)}{\cos(-x)} = \frac{-\sin x}{\cos x} = -\tan x$

De plus, pour tout x appartenant au domaine de définition de tan, -x en fait
aussi partie, car $x \not\equiv \frac{\pi}{2}[\pi] \Rightarrow -x \not\equiv \frac{-\pi}{2}[\pi] \Leftrightarrow x \not\equiv \frac{\pi}{2}[\pi]$.

> La fonction tan est donc impaire

On a $\pi$ -périodique, car $\tan(x + \pi) = \frac{\sin(x + \pi)}{\cos(x + \pi)} = \frac{-\sin(x)}{-\cos(x)} = \tan x$
et $x + \pi$ appartenant au domaine de définition de tan pour tout $x$ y
appartenant, car  $x \not\equiv \frac{\pi}{2}[\pi] \Rightarrow x + \pi \not\equiv \frac{-\pi}{2}[\pi]$

> La fonction tan est $\pi$ -périodique

#### Représentation graphique
Pour représenter la fonction tan, on l'étudie sur $[0, \frac{\pi}{2}[$, puis on
obtient $]\frac{-\pi}{2}, 0]$ par imparité et le reste par $\pi$ -périodicité.

Puisque $\tan'(0) = 1$ et $\tan(0) = 0$, on a une droite tangente à la courbe en
0 d'équation $y = i$, et on a la limite de tan vers $\frac{\pi}{2}$ qui tend
vers $+\infty$. On a donc la forme de la fonction tangente :

> Insérer image

On remarque aussi que l'application $\tan$ sur l'un de ses intervalles de
définition vers $\mathbb{R}$ est bijective, car l'ensemble image de $\tan$ est $\mathbb{R}$
(surjectivité) et tan est strictement monotone (injectivité).

Ainsi, tout réel est une tangente :
$\forall y \in \mathbb{R}, \exists! x \in ]\frac{-\pi}{2}, \frac{\pi}{2}[, \tan(x) = y$

### Formulaire
Pour $\Theta \not\equiv \frac{\pi}{2}[\pi]$
- $\tan(-\Theta) = -\tan(\Theta)$
- $\tan(\Theta + \pi) = \tan(\Theta)$
- $\tan(\Theta - \pi) = \tan(\Theta)$

Pour $\Theta \not\equiv 0[\frac{\pi}{2}]$
- $\tan(\Theta + \frac{\pi}{2}) = \frac{-1}{\tan \Theta}$
- $\tan(\frac{\pi}{2} - \Theta) = \frac{-1}{\tan \Theta}$

Pour $a, b, a+b \not\in \frac{\pi}{2} + \pi \mathbb{Z}$ :
- $\tan(a+b) = \frac{\sin a \cos b + \cos a \sin b}{\cos a \cos b - \sin a \sin b}$
  $= \frac{\cos a \cos b [\frac{\sin a}{\cos a} + \frac{\sin a}{\cos b}]}{\cos a \cos b [1 - \frac{\sin a \sin b}{\cos a \cos b}]}$, soit
  $\tan(a+b) = \frac{\tan(a) + \tan(b)}{1 - \tan(a) \times \tan(b)}$.
- $\tan(a-b) = \frac{\tan(a) - \tan(b)}{1 + \tan(a) \tan(b)}$

De même, avec $b = a$ :
- $\tan(2a) = \frac{2 \tan(a)}{1 - \tan^2(a)}$

On remarque que, soit $\left\{\begin{matrix} u \not\equiv \pi[2\pi] \\ u \not\equiv \frac{\pi}{2}[\pi] \end{matrix}\right.$,
$\tan(u) = \tan(2 \times \frac{u}{2}) = \frac{2 \tan(\frac{u}{2})}{1 - \tan^2(\frac{u}{2})}$, soit
$\tan(u) = \frac{2t}{1 - t^2}$ en posant $t = \tan(\frac{u}{2})$.
À l'aide de la dérivée de tan, on sait que $1 + \tan^2 = \frac{1}{\cos^2}$, et
on exprime ainsi $\cos(u) = 2 \cos^2(\frac{u}{2}) - 1 = 2(\frac{1}{1 + \tan^2(\frac{u}{2})}) - 1$
$= \frac{1 - \tan^2(\frac{u}{2})}{1 + \tan^2(\frac{u}{2})} = \frac{1 - t^2}{1 + t^2}$.
Enfin, puisque $\sin(u) = \tan(u) \times \cos(u) = \frac{2t}{1 + t^2}$.
On a donc pu exprimer le sinus, le cosinus et la tangente de $u$ uniquement en
fonction de $t = \tan(\frac{u}{2})$ (la tangente de l'angle-moitié).

##### Calculer $\tan(\frac{\pi}{8})$
On pose $t = \tan(\frac{\pi}{8})$. On a alors $\tan(\frac{\pi}{4}) = \frac{2t}{1 - t^2}$,
donc $2t = 1 - t^2$ (car $\tan(\frac{\pi}{4}) = 1$), donc on a le polynôme
$t^2 + 2t - 1 = 0$, qui a les racines $-1 \pm \sqrt{2}$. Or, $\frac{\pi}{8} \in [0, \frac{\pi}{2}[$,
donc $\tan(\frac{\pi}{8}) > 0$, donc $\tan(\frac{\pi}{8}) = \sqrt{2} - 1$

### Équations trigonométriques
- $\sin x = \sin y \Leftrightarrow (x \equiv y[2\pi] \lor x \equiv \pi - y [2\pi])$
- $\cos x = \cos y \Leftrightarrow (x \equiv y[2\pi] \lor x \equiv -y [2\pi])$
- $\sin x = \sin y \Leftrightarrow x \equiv y[\pi]$

On effectuera souvent ces opérations pour vérifier des solutions ou les
énumérer.

Attention, les calculs sur les congruences dans les réelles ne permettent plus
un grand nombre de propriétés qu'on trouve dans les entiers.
On peut néanmoins appliquer $\left\{\begin{matrix} a \equiv b[c] \\ a' \equiv b'[c] \end{matrix}\right. , a + a' \equiv b + b'[c]$.
On a aussi, avec $\lambda \in \mathbb{R}^{\ast}, a \equiv b [c] \Leftrightarrow \lambda a \equiv \lambda b [\lambda c]$.

## Formes trigonométriques et exponentielles d'un complexe
Soit $z \in \mathbb{C}$, on pose $r = |z|$.
- Soit $r = 0 \Leftrightarrow z = 0$
- Soit $r \neq 0$, alors le complexe $\frac{z}{r}$ est de module 1
  ( $| \frac{z}{r} | = \frac{|z|}{|r|} = \frac{r}{r} = 1$ ).
  Il existe donc $\Theta \in \mathbb{R}$ tel que $z = r e^{i \Theta}$

> $\forall z \in \mathbb{C}^{\ast}, \exists! r \in \mathbb{R}^{\ast}_{+}, \exists \Theta \in \mathbb{R}, z = r e^{i \Theta}$

On a $r = |z|$ le module de $z$. $\Theta$ est un argument de $z$, noté $arg(z)$,
et on a $arg(z) \equiv \Theta[2\pi]$.

On a le $\Theta \in ]-\pi , \pi]$, on parle d'argument principal de $z$.

On peut en déduire la représentation polaire du point d'affixe $z$ sur le plan,
à partir du vecteur depuis l'origine de norme $|z|$ et d'angle avec l'axe des
abscisses $arg(z)$.

Ainsi, pour $z \in \mathbb{C}^{\ast}$, $z = \Re(z) + i \Im(z)$
$= |z| \times e^{i arg(z)} = |z| \times (\cos(arg(z)) + i \sin(arg(z)))$,
donc $\Re(z) = |z| \times \cos(arg(z))$ et $\Im(z) = |z| \times \sin(arg(z))$.

On peut trouver l'égalité entre des nombres complexes avec cette forme :
$z_1 = z_2 \Leftrightarrow \left\{\begin{matrix} |z_1| = |z_2| \\ arg(z_1) = arg(z_2) \end{matrix}\right.$

On a les propriétés suivantes sur l'argument, soit $z \in \mathbb{C}^{\ast}$ :
- $z \in \mathbb{R} \Leftrightarrow arg(z) \equiv 0[\pi]$
- $z \in i\mathbb{R} \Leftrightarrow arg(z) \equiv \frac{\pi}{2}[\pi]$
- $z \in \mathbb{R}_{+} \Leftrightarrow arg(z) \equiv 0[2\pi]$

Remarque : $e^{i k \pi} = (-1)^k$ et $e^{2i \pi k} = 1$ (avec $k \in \mathbb{Z}$)

- $arg(z) \equiv -arg(z) [2\pi]$
- $arg(-z) \equiv (\pi + arg(z)) [\pi]$
- $arg(z_1 z_2) \equiv arg(z_1) + arg(z_2) [2\pi]$
- $arg(\frac{1}{z}) \equiv -arg(z) [2\pi]$
- Soit $n \in \mathbb{Z}$, $arg(z^n) \equiv n arg(z) [2\pi]$

##### Preuve de la dernière propriété
- Si $n \in \mathbb{N}$, on effectue une récurrence en utilisant $arg(z_1 z_2) \equiv arg(z_1) + arg(z_2) [2\pi]$
- Si $n \in \mathbb{Z}$ avec $n < 0$ : $z^n = \frac{1}{z^{-n}}$ (sachant que
  $-n \in \mathbb{N}$), $arg(z^n) \equiv -arg(z^{-n})[2\pi] \equiv -(-n)arg(z)[2\pi]$
  $\equiv n arg(z)[2\pi]$.

## Exponentielle complexe
> Soit $z \in \mathbb{C}$ un complexe quelconque de forme algébrique $z = a + ib$,
> avec $(a,b) \in \mathbb{R}^2$. On pose $e^z = e^a \times e^{ib}$
> $= e^a \cos(b) + i e^a \sin(b)$.

On remarque donc que $e^z = e^{\Re(z)} \cos(\Im(z)) + i e^{\Re(z)} \sin(\Im((z)))$.

Ainsi, $\exp: \mathbb{C} \to \mathbb{C}$ est un prolongement de $\exp: \mathbb{R} \to \mathbb{R}$
et de $\exp: i\mathbb{R} \to \mathbb{C}$.

On a $\forall (z_1,z_2) \in \mathbb{C}^2, e^{z_1 + z_2} = e^{z_1} \times e^{z_2}$.

##### Preuve
Si $z_1 = a_1 + i b_1$ et $z_2 = a_2 + i b_2$, avec $a_1, b_1, a_2, b_2 \in \mathbb{R}$,
on a $e^{z_1} \times e^{z_2} = e^{a_1} e^{i b_1} e^{a_2} e^{i b_2}$
$= e^{a_1 + a_2} e^{i (b_1 + b_2)} = e^{(a_1 + a_2) + i (b_1 + b_2)}$
$= e^{z_1 + z_2}$.

### Module et argument de l'exponentielle
Soit $z \in \mathbb{C}$, $\Re(e^z) = e^{\Re(z)} \times \cos(\Im(z))$ et
$\Im(e^z) = e^{\Re(z)} \times \sin(\Im((z)))$. On a donc
$|e^z| = e^{\Re(z)}$ et $arg(e^z) \equiv \Im(z)[2\pi]$.

Remarque : $|e^z| = e^{\Re(z)} \in \mathbb{R}^{\ast}_{+}$ pour tout $z \in \mathbb{C}$,
donc $|e^z| \neq 0$, donc $e^z \neq 0$. On a pas d'antécédent par $\exp$.
Ainsi, $\exp: \mathbb{C}  \to \mathbb{C}^{\ast}$. Cette application n'est pas
injective car $e^0 = 1 = e^{2i \pi}$.
$\exp(z + 2i \pi) = e^z \times e^{2i \pi} = e^z \times 1 = e^z$ donc $\exp$
est $2 i \pi$ -périodique.
On a donc $\exp: \mathbb{C} \to \mathbb{C}^{\ast}$ surjective.

##### Preuve de la surjectivité
Soit $z = x + iy$ où $(x,y) \in \mathbb{R}^2$, on a
$e^z = e^x e^{iy}$. On pose $a = re^{i \Theta}$ où
$\left\{\begin{matrix} r = |a| > 0 \\ \Theta = arg(a) \end{matrix}\right.$.

$e^z = a \Leftrightarrow e^x e^{iy} = r e^{i\Theta}$\
$\Leftrightarrow \left\{\begin{matrix} e^x = r \\ y \equiv \Theta [2\pi] \end{matrix}\right.$\
$\Leftrightarrow \left\{\begin{matrix} x = \ln(r) \\ \exists k \in \mathbb{Z}, y = \Theta + 2 \pi k \end{matrix}\right.$\
Les solutions sont $z = \ln(r) + i\Theta + 2\pi ik, k \in \mathbb{Z}$.
