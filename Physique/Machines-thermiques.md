# Machines thermiques
## Bilan énergétique
### Cadre de l'étude
Dans un système fermé fonctionnant de manière cyclique, on appelle selon $W$ le
travail associé au système, le système un moteur pour $W < 0$ ou un récepteur
pour $W > 0$.

### Application du premier principe
D'après le premier principe de la thermodynamique,
$\Delta(E_m^{\text{masse}} + U) = W + Q$,
avec $E_m^{\text{masse}}$ la possibilité de mouvement.

On appelle alors un cycle des états tels que $\Delta U = 0$, et donc $W + Q = 0$.
La chaleur étant extensive, s'il y a plusieurs sources de chaleur, on les somme.

### Application du second principe
Dans un cycle, $\Delta S = 0$, donc comme $S_c \geq 0$
on aura toujours $S_e \leq 0$. Si la source de chaleur est un thermostat de
température $T_i$, on a $S_e = \int \sum\limits_{i} \frac{\delta Q_i}{T_i}$.

> Inégalité de Clausius : $S_e = \sum\limits_{i} \frac{Q_i}{T_i} = - S_c \leq 0$.

## Machines thermique monothermes et dithermes
### Machines monothermes
> Dans une machine monotherme, le système échange de l'énergie avec une seule
> source de chaleur. Le système reçoit un travail $W$ et un transfert thermique $Q$ d'une source à la température $T_e$.

Ainsi, dans les cycles, $W + Q = 0$ et $\frac{Q}{T_e} \leq 0$. Comme $W > 0$,
on a nécessairement $Q < 0$, ce qui signifie que le machine ne peut que
chauffer.

### Machines dithermes
> Pour une machine ditherme, le système échange de l'énergie avec deux sources de
> chaleur. Le système reçoit un travail $W$, un transfert thermique $Q_c$ d'une
> source chaude à la température $T_c$ et un transfert thermique $Q_f$ d'une
> source froide à la température $T_f$.

#### Les moteurs
> Un moteur est une machine telle que $W < 0$, $Q_f < 0$ et $Q_c > 0$.

Par convention, on dit que le système reçoit de la chaleur quand $Q > 0$
et fournit de la chaleur quand $Q < 0$.

> Le rendement d'un moteur $\eta = |\frac{\text{grandeur énergétique valorisée}}{\text{coût énergétique}}| = |\frac{\text{énergie utile}}{\text{énergie coûteuse}}|$.

On a donc $\eta = \frac{-W}{Q_c}$. On sait que $-W = Q_c + Q_f$, donc
$\eta = 1 + \frac{Q_f}{Q_c}$. Par l'inégalité de Clausius, $\frac{Q_f}{Q_c} \leq \frac{-T_f}{T_c}$,
donc $\eta \leq \eta_\text{max} = 1 - \frac{T_f}{T_c}$.

> Rendement de Carnot : $\eta_\text{max} = 1 - \frac{T_f}{T_c}$.

#### Les réfrigérateurs
> Les réfrigérateurs sont des machines dithermes telles que $W > 0$, $Q_f > 0$,$Q_c < 0$.

> L'efficacité correspond à $e = |\frac{\text{grandeur énergétique valorisée}}{\text{coût énergétique}}|$.

On peut donc avoir $e \geq 1$

On a donc $e = \frac{Q_f}{W}$, $-W = Q_c + Q_f$. On a donc $e = \frac{-Q_f}{Q_c + Q_f}$
$= \frac{-1}{1 + \frac{Q_c}{Q_f}} \leq \frac{T_f}{T_c - T_f}$. Ainsi, $e \leq e_\text{max} = \frac{T_f}{T_c - T_f}$.

> Efficacité de Carnot : $e_\text{max} = \frac{T_f}{T_c - T_f}$.

#### Les pompes à chaleur
> Les pompes à chaleur sont des machines dithermes telles que $W > 0$, $Q_f > 0$,$Q_c < 0$.

L'efficacité est ici $e = \frac{-Q_c}{W} = \frac{Q_c}{Q_c + Q_f} \leq \frac{T_c}{T_c - T_f}$.

> Efficacité de Carnot pour les pompes à chaleur : $e_\text{max} = \frac{T_c}{T_c - T_f}$.
