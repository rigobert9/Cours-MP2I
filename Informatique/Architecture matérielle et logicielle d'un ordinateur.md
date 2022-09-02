# Architecture matérielle et logicielle d'un ordinateur
## Définition d'un ordinateur
Un ordinateur est un appareil qui est en mesure d'ordonner des données
automatiquement. Dès le début du 19ème siècle, on commence à standardiser
l'information dans de nombreux domaines (mesures, mais aussi mise en forme de
l'information pour faciliter le traitement), permettant d'opérer sur une
information ou un outil avec plusieurs machines identiques, ou même différentes.

Les métiers Jacquard, machines à tisser qui peut produire différentes
tapisseries ou des comportements précis, donnant naissance au premier exemple de
programmation (c'est d'ailleurs une machine semblable qui intéresseront Charles Babbage
et Ada Lovelace).

Ainsi, on considère qu'un ordinateur doit recevoir des données en entrée, qui
traite ces données selon des règles prédéfinies, et renvoie un résultat. Mais
ces contraintes ne sont pas suffisantes, et le métier à tisser pourrait ainsi
être considéré comme un ordinateur, tout comme un thermostat d'ambiance, etc...

Selon Turing, un ordinateur doit pouvoir simuler n'importe quel autre machine
(Turing-completeness) (c'est alors une machine de Turing). Les ordinateurs
doivent donc être des machines universelles, et qui ne sont pas limitées par
leur spécialisation.

En 1834, Charles Babbage invente sa machine analytique, le prototype d'une
machine universelle, qu'il ne réussira pas à construire par désorganisation et
manque de moyens technologiques. Son fils construira un morceau plus tard, et la
machine ne sera complétée que bien plus tard.
Ada Lovelace rencontrera Charles Babbage et s'interessera à la machine,
comprenant bien mieux l'intérêt de la machine analytique. Dans sa traduction
d'un résumé d'une conférence de Babbage, lourdement annotée, elle réalise qu'une
telle machine est capable de conditionnalité et de déplacement dans le programme
(goto, les deux créant essentiellement une boucle while). Elle écrit un
programme permettant de calculer séquentiellement les nombres de Bernoulli. La
machine fonctionne à partir de rouages actionnés par des cartes perforées,
chaque trou correspondant à un opcode.

Le programme d'Ada Lovelace consiste uniquement en de l'informatique théorique.
On recherchera à la même époque la notion d'algorithme, et de décidabilité :
tous les problèmes sont-ils résolvables par une machine ?
Le mathématicien Hilbert demande si tout problème est résolvable informatique.

Définition d'un algorithme selon Donald Knuth : En prérequis
- Entrées : des quantités, prises dans un ensemble spécifié qui sont données
	avant qu'un algorithme commence
- Sorties : des quantités ayant une relation spécifiée avec les entrées
- Finitude : un algorithme doit toujours se terminer après un nombre fini
	d'étapes (souvent un problème dans la théorie contre la pratique, par exemple
	dans la production d'un nombre au hasard entre 1 et 7)
- Définition précise : chaque étape d'un algorithme doit être définie
	précisément et sans ambiguîté (limite entre les mathématiques et
	l'informatique : )
- Rendement : toutes les opérations que l'algorithme doit accomplir doivent être
	suffisamment basiques pour pouvoir être en principe réalisées dans une durée
	finie par un humain utilisant un papier et un crayon

Le modèle de la machine de Turing est l'un des modèles de l'ordinateur, un
algorithme travaillant sur un ruban infini, qui permet d'écrire un programme,
quand bien même celui-ci soit contradictoire et mathématiquement invalide
(comme le problème de décision, Entscheidungsproblem). À chaque machine de
Turing se terminant correspond un algorithme, et à chaque machine de Turing
correspond un algorithme. De plus, à chaque machine de Turing correspond un
programme et inversement.

Alonzo Church (lambda calculus) comme Alan Turing (la machine de Turing)
résolvent le problème d'Hilbert, prouvant que certains problèmes sont
mathématiquement impossibles, bien que des programmes puissent tourner dans
cette contradiction.

En 1941, la première machine de Turing électromécanique est construite, et la
première entièrement éléctronique, l'ENIAC, est construite en 1943, et devient
programmable en 1945.

## Architecture d'un ordinateur
L'architecture de la plupart des ordinateurs respecte l'architecture Von Neumann
: une unité de contrôle, qui peut modifier les données et les exploiter; une
unité arithmétique et logique qui effectue des opérations à partir de données en
entrée et en sortie, parfois à travers des périphériques; et une mémoire qui
contient les données récupérées et utilisées.
Les deux unités, contrôle et logique, forment aujourd'hui le processeur.

La mémoire est organisée en adresses, qui correspondent à des cases de la
mémoire physique, organisée en pratique en bytes (8 bits) et en pratique
aujourd'hui en mot (maintenant de 64 bits). La mémoire n'effectue pas de
calculs, n'a pas de sens a priori (l'information entrée n'a pas de sens à même
la mémoire). Les adresses de mémoire sont à accès direct, à partir de leur
adresse. La RAM est une mémoire d'accès rapide, mais volatile et limité (mais
moins rapide que la mémoire cache qui la copie directement dans le processeur
avec quelques entrées, qu'il faut souvent prendre en compte aujourd'hui).

L'accès à la RAM est aujourd'hui la plupart du temps régi par le système
d'exploitation : il alloue au processus des blocs de mémoire, l'alloue et la
libère, et parfois envoie dans la mémoire de masse des blocs de RAM en cas de
manque de place (swapping).

Les processeurs possèdent des dizaines ou centaines de registres, qui peuvent
stocker des mots mémoire et effectuer des opérations arithmétiques et logiques
de base, souvent en s'échangeant les informations (une opération sur deux
registres peut envoyer son résultat dans l'un des deux, voire dans un troisième
sur certaines architectures). Certains ont des rôles particuliers, comme le
registre d'instruction (IR) qui contient l'instruction, ou le compteur de programme
(PC) qui contient l'adresse en mémoire de la prochaine instruction (%rip en x86-64).
