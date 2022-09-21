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

On a de plus (vérifiables par la forme trigonométrique) $e^{-i \Theta} = \overline{e^{i \Theta}} = \frac{1}{e^{i \Theta}}$.

On vérifie alors, lorsque $e^{i \Theta} = e^{i \varphi} \Leftrightarrow \left\{\begin{matrix} \cos \Theta = \cos \varphi \\ \sin \Theta = \sin \varphi \end{matrix}\right.$,
que $\Theta \equiv \varphi [2 \pi]$.
