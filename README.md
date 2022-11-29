# Cours-MP2I
Notes personnelles de Cours en MP2I. Ces notes sont publiquement disponibles, mais aussi
participatives; n'hésitez pas à apporter des corrections, des additions ou vos
propres cours à ce dépôt (voir "Contribuer" plus bas). Ces notes sont prises personnellement par des élèves,
et ne sont pas le reflet des cours donnés par les professeurs.

## Format
Ces notes sont formatées au format MarkDown, un format de texte lisible pour les
fichiers textes purs, mais qui compte aussi de nombreux lecteurs qui mettent en
forme les divers en-têtes ou ajouts (comme pour la façon dont vous visionnez ce
README.md sur GitHub).

De plus, le programme de MP2I comprenant des études approfondies de
mathématiques et de physique, des formules mathématiques sont insérées dans le
texte sous la forme de formules "inline" en LaTeX, un format document riche
qui peut être converti en PDF ou rendu sur des pages web. Bien que celui-ci soit
lisible par ceux qui comprennent sa syntaxe minimale, il est recommandé
d'utiliser un lecteur qui permet de le rendre à même les lignes, ou de le
compiler en PDF (comme précisé ci-dessous).

## Utilisation
Ces notes sont parfaitement lisibles à elles seules, mais sont bien plus
lisibles à l'aide de divers outils. De plus, les notes sont disponibles
directement sur ce dépôt, compilées à l'aide de la commande :
```bash
pandoc -V geometry:margin=2cm --toc -s -f gfm+tex_math_dollars --resource-path="./"`dirname fichier.md`--mathjax fichier.md --output=fichier.pdf
```

### Lecteurs
Nom | Disponibilité | Mise en page du MarkDown | Rendering des formules LaTeX
---|---|---|---
Vim (voir plus bas) | Local | Partiellement (coloration) | Partiellement (caractères simples et inline)
GitHub (lire les fichiers ici) | Online | Oui | Oui (incomplètement pour les systèmes)
[Zettlr](https://www.zettlr.com/) | Local | Oui | Oui
[Marktext](https://github.com/marktext/marktext) | Local | Oui | Oui
[Apostrophe](https://world.pages.gitlab.gnome.org/apostrophe/) | Local | Oui | Oui

Pour lire ces notes avec une partie des symboles simplifiés, il suffit
d'installer vim avec le plugin
[vim-markdown](https://github.com/preservim/vim-markdown) (voir guide
d'installation sur leur page), puis d'ajouter la ligne
```viml
let g:vim_markdown_math = 1
```
dans le fichier ~/.vimrc (ou tout autre fichier de configuration
selon votre environnement).

Ces deux derniers lecteurs sont des environnements incroyables si vous souhaitez prendre des notes de la même façon, et pour les organiser. Ils permettent aussi de compiler sans problème les documents.

### Compilateurs
Nom | Disponibilité | Mise en page du MarkDown | Rendering des formules LaTeX
---|---|---|---
https://www.markdowntopdf.com/ | Online | Oui | Non
pandoc | local | Oui | Oui

Pandoc permet aussi de visionner ces notes dans un navigateur internet à l'aide
de la commande suivante.
```bash
pandoc --toc -s -f gfm+tex_math_dollars --mathjax fichier.md --output=fichier.html
```

## Contribuer
Tout fichier est le bienvenue : vidéos représentatives, ressources pdf, images,
modélisations (notamment Géogebra). Il faut néanmoins tous les intégrer au cours
principal, c'est à dire en mettant des liens dans un des cours en MarkDown vers
votre fichier.

Pour contribuer, il suffit de fork ce dépôt et de soumettre une Pull Request.
Vous pouvez ajouter de nouveaux fichiers texte, des ressources graphiques ou
autres, puis les commit et les envoyer après vérification. Certaines personnes
seront ajoutées en collaborateurs pour faciliter le fonctionnement du dépôt.

Tous les noms de fichiers de ce dépôt doivent être dans le style des
identificateurs de C : caractères ASCII seulement (pas d'accents), pas d'espaces
(remplacez-les par des "-" de préférence) ni de points (à part avant leur
extension), d'apostrophes ou de
guillemets, ou de marques de ponctuation en général.

Les cours peuvent se retrouver sous la forme d'un fichier texte `.md`, avec pour
nom le titre raccourci du chapitre commençant par une majuscule.\
Les documents additionnels doivent être rassemblés dans un dossier au même
niveau que le fichier texte correspondant, qui porte le même nom que le fichier
texte remplaçant `.md` par `-assets`.\
Veuillez ensuite mettre des liens vers ces fichiers dans le document texte comme
si vous étiez dans le dossier du document (donc des liens de la forme
`./Nom-du-cours-assets/nom-de-l'asset.png`). Si votre fichier est une image,
utilisez la syntaxe d'image du MarkDown (`![Nom de l'image](chemin-vers-le-fichier)`),
et pour tout autre fichier utilisez la syntaxe d'hyperlien
(`[Nom du fichier](chemin-vers-le-fichier)`).

## Mon setup
Mon workflow repose principalement sur l'utilisation de vim avec de nombreux
plugins :
- Vimtex (pour rendre le LaTeX)
- UltiSnips (pour une utilisation extensive de macros)
- Vim-markdown qui me permet de rendre le LaTeX inline

L'utilisation de ces outils permet de justifier la plupart des choix pris dans
ces notes, n'hésitez néanmoins pas à ouvrir une issue si des détails posent
problème dans votre utilisation de ces notes.
Si vous souhaitez utiliser cette configuration, n'hésitez pas à ouvrir une
issue.
