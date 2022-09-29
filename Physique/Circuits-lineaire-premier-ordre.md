# Chapitre 4 : Circuits linéaires du 1er ordre
## Condensateur électrique
### Définition et propriétés
> Dans un condensateur, la charge $q_t$ d'une armature et la tension $u_t$ qui en
> résulte vérifient la relation constitutive $q_t = c u_t$. $c$ est la capacité
> d'un condensateur, mesurée en farad (F).

Condensateurs | Valeurs
---|---
Condensateur de TP | $1 nF$
Condensateur avec isolant en céramique | $1 \mu F$ à $100 \mu F$
Électrochimique | $1 mF$

Un condensateur est déchargé s'il n'y a pas de différence de charge aux armatures.

Représentation schématique : deux barres parallèles et séparées, toutes deux
perpendiculaires au circuit.

> Pour un condensateur en convention récepteur, on a l'égalité $i(t) = c \frac{d u(t)}{dt}$.

La tension aux bornes d'un condensateur est une fonction continue du temps.

On dit qu'un circuit électrique est en régime stationnaire si toutes les
tensions et tous les courants ne dépendent pas du temps (donc sont constants).

En régime stationnaire, $t \to \infty$, $i = c \frac{du}{dt} \to 0$.

> En régime stationnaire, un condensateur est équivalent à un interrupteur ouvert (donc à ouvrir le circuit).

### Aspect énergétique
En convention récepteur, $P_\text{reçue} = u(t) \cdot i(t)$. Or, $i(t) = c \frac{d u(t)}{dt}$, donc
$P_\text{reçue} = u(t) c \frac{d u(t)}{dt}$. Celle ci est ainsi égale à
$P_\text{reçue} = \frac{d}{dt} [\frac{1}{2} c u(t)^2]$ (en reconnaissant
l'identité $(f^2)' = 2 f' f$).

$\frac{1}{2} c u(t)^2$ est l'énergie électrique du condensateur.

### Associations de condensateurs
#### Condensateurs en parallèle
Soient N condensateurs en parallèle, $C_\text{éq} = \sum\limits_{k = 1}^{N} C_k$.

#### Condensateurs en série
Soient N condensateurs en série, $\frac{1}{C_\text{éq}} = \sum\limits_{k = 1}^{N} \frac{1}{C_R}$.

## Bobine d'induction
### Définition et propriétés
> Une bobine est un dipôle constitué d'un fil (souvent en cuivre) enroulé sur
> lui-même ou autour d'un noyau magnétique.

En convention récepteur, la relation constitutive de la bobine est $u(t) = L \frac{d i(t)}{dt}$.
La valeur $L$ correspond à l'inductance, mesurée en henry (H).

Une bobine typique de TP aura une inductance de $10$ à $100 mH$.

L'intensité qui traverse une bobine est une fonction continue du temps.

> Pour une bobine en régime stationnaire, $u = L \frac{di}{dt} = 0$. La bobine est
> alors équivalente à une fil.

Une bobine réelle est constituée d'une bobine idéale (vérifiant la relation
constitutive), mise en série avec une résistance $r$.

### Associations de bobines
#### Bobines en parallèle
Soit N bobines en parallèle, $\frac{1}{L_\text{éq}} = \sum\limits_{k = 1}^{N} \frac{1}{L_k}$.

#### Bobines en série
Soit N bobines en série, $L_\text{éq} = \sum\limits_{k = 1}^{N} L_k$
