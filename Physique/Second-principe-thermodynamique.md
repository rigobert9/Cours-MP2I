# Second principe de la thermodynamique
## L'entropie
### Pourquoi un second principe ?
Le premier principe de la thermodynamique correspond à une conservation de
l'énergie, et il nous faut maintenant constater les évolutions des systèmes,
notamment le sens de la transformation (travail vers chaleur, ou l'inverse).

#### Non-équivalence du travail et du transfert thermique
La plupart du temps, on peut constater que l'équilibre mécanique est atteint
plus rapidement que l'équilibre thermique.

#### Sens naturel d'une d'une transformation
Dans l'expérience de Joule-Gay-Lussac, l'énergie est conservée et la différence
d'énergie interne est nulle, mais les deux états sont bien différents. On peut
alors se demander s'il est possible d'inverser la transformation.

#### Vers le second principe
On introduit une nouvelle fonction d'état, l'entropie $S$ :
- $S$ doit être une fonction d'état extensive
- Elle doit différer entre les deux états de l'expérience de Joule-Gay-Lussac
- $S$ doit donner un rôle différent à $W$ et à $Q$

### Énoncé du second principe de la thermodynamique
> $dS = \delta S_e + \delta S_c$,
> avec $\delta S_e$ l'entropie élémentaire échangée par le système,
> $\delta S_e = \frac{\delta Q}{T_\text{ext}}$, et $\delta S_c$ l'entropie
> élémentaire créée, supérieure ou égale à $0$.

Son unité est en $J \cdot K^{-1}$.

On peut réécrire la forme intégrale : $\Delta S = S_e + S_c$ avec
$S_e = \int\limits_{\text{État initial}}^{\text{État final}} \frac{\delta Q}{T_\text{ext}}$
et $S_c = \int\limits_{\text{État initial}}^{\text{État final}} \delta S_c \geq 0$

### Premiers exemples
#### Cas d'un système isolé
Dans un système isolé, $Q = 0$ donc $S_e = 0$, et $W = 0$.
D'après le premier principe de la thermodynamique, $\Delta U = 0$.
D'après le second principe de la thermodynamique, $\Delta S = S_c \geq 0$.

> Pour un système isolé, l'énergie interne se conserve, mais l'entropie augmente
> nécessairement.

#### Transformation adiabatique réversible
Dans un système adiabatique, $\delta Q = 0$ et donc
$\delta S_e = 0$.

> Une transformation réversible est caractérisée par $\delta S_c = 0$. L'entropie
> est alors constante.

> Un système adiabatique et réversible est appelé isentropique. L'entropie est
> alors constante.

## Calcul d'entropie
### Phase condensée incompressible et indilatable
Le volume $V$ est constant, $C_v = C_p = C$, et $\Delta H \approx \Delta U = C \Delta T$.
Soit un chemin réversible fictif entre deux états,
$(T_1,P_1,V_1) \to (t_2,P_2,V_2 = V_1)$.
On a $d U^{\text{fictif}} = C d T$. D'après le premier principe de la
thermodynamique, $d U^\text{fictif} = \delta W^\text{fictif} + \delta Q^\text{fictif}$,
et comme la transformation est isochore, $\delta W^\text{fictif} = 0$.

D'après le second principe de la thermodynamique, $d S^\text{fictif}$
$= \delta S_e^\text{fictif} + \delta S_c^\text{fictif}$.
Puisque la transformation est réversible, $\delta S_c^\text{fictif} = 0$,
et il y a uniformité de la température entre le système et le milieu extérieur,
donc $T_\text{ext} = T$, donnant $\delta S_e^\text{fictif} = \frac{\delta Q^\text{fictif}}{T_\text{ext}}$
$= \frac{C d T}{T}$.

En intégrant entre état initial et état final, $\Delta S = S_e^\text{fictif} = C \ln(\frac{T_2}{T_1})$.

> Pour un phase condensée incompressible et indilatable évoluant de $T_1$ à $T_2$,
> on a $\Delta S = C \ln(\frac{T_2}{T_1})$.

Dans un calorimètre, avec les masses d'eau $\Sigma_1$ de masse $m$ à $T_1$ et $\Sigma_2$ de masse
$m$ à $T_2$, avec à l'état final la température $T_F$.

Puisque $\Delta H = 0$, $\Delta H_1 = - \Delta H_2$, et on a
$\Delta H_1 + \Delta H_2 = m c_\text{eau} (T_F - T_1) + m c_\text{eau} (T_F - T_2) = 0$,
donc $T_F = \frac{T_1 + T_2}{2}$.
Comme il s'agit de PCII, par extensivité $\Delta S = \Delta S_1 + \Delta S_2$
$= m c_\text{eau} \ln(\frac{T_F}{T_1}) + m c_\text{eau} \ln(\frac{T_F}{T_2})$
$= m c_\text{eau} \ln\frac{T_F^2}{T_1 T_2}$.
Comme $\frac{T_F^2}{T_1 T_2} = 1 + \frac{(T_1 - T_2)^2}{4 T_1 T_2}$,
donc $S_c > 0$ si $T_1 \neq T_2$.\
La transformation est donc irréversible.

### Évolution en contact avec un thermostat
#### Variation d'entropie d'un thermostat
Soit une PCII dans un thermostat de capacité thermique très grande
$C_0$. On a $\Delta S = C_0 \ln(\frac{T_2}{T_1})$, avec $Q_0$ le transfert
thermique reçu par le thermostat.
En utilisant de le premier principe,
$Q_0 = C_0 (T_2 - T_1) \Leftrightarrow T_2 = T_1 + \frac{Q_0}{C_0}$,
donc $\Delta S = C_0 \ln(1 + \frac{Q_0}{C_0 T_1})$. Comme $C_0$ est très grande,
$\frac{Q_0}{C_0 T_1} \ll 1$. On applique donc un DL, donnant
$\Delta S \approx \frac{Q_0}{T_0}$.

#### Évolution d'un système au contact d'un thermodynamique
Soit $\Sigma_1$ à la température $T_1$ et de capacité thermique $C_1$,
et $\Sigma_0$ un thermostat à la température $T_0$. À l'état final, $T_F = T_0$.
Pour $\Sigma_0$ un PCII, $\Delta S_1 = C_1 \ln(\frac{T_0}{T_1})$, et
$\Delta S_1 = \frac{Q_0}{T_0}$. Dans le système $\Sigma = \Sigma_0 + \Sigma_1$,
$\Delta S = C_1 \ln(\frac{T_0}{T_1}) + \frac{Q_0}{T_0}$. D'après le second
principe, $\Delta S = S_e + S_c$. Soit $Q_0$ le transfert thermique
avec le thermostat, comme $\Sigma_1$ est contact avec $\Sigma_0$,
$Q_1 = - Q_0$. D'après le premier principe,
$\Delta U_1 = W_1 (= 0) + Q_1 = C_1 (T_0 - T_1)$,
donc $\Delta S = C_1 \ln(\frac{T_0}{T_1}) + C_1 \frac{T_1 - T_0}{T_0}$.
Or, le système est isolé donc $S_e = 0$, donc $S_c$
$= \Delta S = C_1 (\frac{T_1 - T_0}{T_0} - \ln(\frac{T_1}{T_0}))$,
donc $x = \frac{T_1}{T_0}$, $S_c = C_0(x - 1 - \ln(x))$.
Comme $x - 1 \geq \ln x$

### Gaz parfait
#### Entropie d'un gaz parfait
Pour un gaz parfait, $d U = C_V d T = \frac{n R}{\gamma - 1} dT$,
$d H = C_P dT = \frac{\gamma n R}{\gamma - 1} dT$ et
$\gamma = \frac{C_P}{C_V}$.

On prend un chemin fictif de transformation de $n$ moles de gaz
$(T_1,P_1,V_1) \to (T_2,P_2,V_2)$. On sépare ce chemin entre une transformation
$A$ réversible isochore, de l'état initial à $(T_2,P_i,V_1)$, et une
transformation réversible $B$ allant à l'état final depuis ce dernier.
- Sur la transformation $A$, d'après le premier principe de la thermodynamique,
  $d U_A = \delta W_A + \delta Q_A$. Comme elle est isochore, $\delta W_A = 0$,
  donc $d U_A = Q_A = C_V d T$. D'après le second principe,
  $d S_A = \frac{\delta Q_A}{T} + \delta S_{c,A}$. Comme la transformation
  est réversible, $\delta S_{c,A} = 0$, donc $d S_A = \frac{C_V dT}{T}$,
  donc $\Delta S_A = C_V \ln(\frac{T_2}{T_1})$.
- Sur la transformation $B$, qui est isotherme, $d U_B = 0$,
  donnant $\delta Q_B = - \delta W_B = P dV$. D'après le second principe,
  $d S_B = \frac{\delta Q_B}{T} + \delta S_{c,B}$. Comme la transformation est
  réversible, $d S_B = \frac{PdV}{T}$, donnant par les gaz parfait,
  $d S_B = nR \frac{dV}{V}$, donnant en intégrant, $\Delta S_B = n R \ln(\frac{V_2}{V_1})$.

> Pour un gaz parfait on a les identités :
> - $\Delta S = \frac{nR}{\gamma - 1} \ln(\frac{T_2}{T_1}) + n R \ln(\frac{V_2}{V_1})$
> - $\Delta S = \frac{\gamma n R}{\gamma - 1} \ln(\frac{T_2}{T_1}) - n R \ln(\frac{P_2}{P_1})$
> - $\Delta S = \frac{nR}{\gamma - 1} \ln(\frac{P_2}{P_1}) + \frac{\gamma n R}{\gamma - 1} \ln(\frac{V_2}{V_1})$

#### Identité thermodynamique
Soit une transformation élémentaire réversible,
d'après le premier principe de la thermodynamique,
$d U = \delta W + \delta Q$, donc $d U = -P dV + \delta Q$, et d'après le
second,
$d S = \frac{\delta Q}{T}$. On obtient ainsi
$d U = - P dV + T dS$.

> $d U = - P dV + T dS$

Puisque $S$ est une fonction $U$ et $V$, on a
$d S = (\frac{\partial S}{\partial U})_V d U + (\frac{\partial S}{\partial V})_U dV$,
soit $d S = \frac{1}{T} d U + \frac{P}{T} dV$.

> La température thermodynamique est définie comme $\frac{1}{T} = (\frac{\partial S}{\partial U})_V$.

> La pression thermodynamique est définie comme $\frac{P}{T} = (\frac{\partial S}{\partial V})_U$.
