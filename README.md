# Cours-MP2I
Cours en MP2I au lycée Janson de Sailly. Ces notes sont publiquement
disponibles, mais aussi participatives; n'hésitez pas à apporter des
corrections, des additions ou vos propres cours à ce dépôt.

WIP : Deck Anki, qui sera maintenu avec des cartes tirées de ces notes, et
éventuellement automatiquement (selon l'avancée d'un plugin python en parallèle)

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
lisibles à l'aide de divers outils.

### Lecteurs
Nom | Disponibilité | Mise en page du MarkDown | Rendering des formules LaTeX
---|---|---|---
Vim (voir plus bas) | Local | Partiellement (coloration) | Partiellement (caractères simples et inline)
GitHub (lire les fichiers ici) | Online | Oui | Oui

Pour lire ces notes avec une partie des symboles simplifiés, il suffit
d'installer neovim avec le plugin
[vim-markdown](https://github.com/preservim/vim-markdown) (voir guide
d'installation sur leur page), puis d'ajouter la ligne
```viml
let g:vim_markdown_math = 1
```
dans le fichier ~/.config/nvim/init.vim (ou tout autre fichier de configuration
selon votre environnement).

N'hésitez pas à me signaler d'autres modes de visionnage des notes, plus
accessibles, notamment des lecteurs web simples.

### Compilateurs
Nom | Disponibilité | Mise en page du MarkDown | Rendering des formules LaTeX
---|---|---|---
https://www.markdowntopdf.com/ | Online | Oui | Non

Cette partie de mon workflow est toujours en cours de préparation, n'hésitez
néanmoins pas à conseiller des outils permettant de convertir le MarkDown comme
le LaTeX vers des formats PDF.

## Mon setup
Mon workflow repose principalement sur l'utilisation de vim avec de nombreux
plugins :
- VimWiki / VimLink (liens permettant d'organiser les leçons, notamment dans les
  index)
- Vimtex (pour rendre le LaTeX)
- UltiSnips (pour une utilisation extensive de macros)
- Vim-markdown qui me permet de rendre le LaTeX inline

L'utilisation de ces outils permet de justifier la plupart des choix pris dans
ces notes, n'hésitez néanmoins pas à ouvrir une issue si des détails posent
problème dans votre utilisation de ces notes.
Si vous souhaitez utiliser cette configuration, n'hésitez pas à ouvrir une
issue.
