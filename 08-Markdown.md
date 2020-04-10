# Chapitre 8. Markdown

Il s'agit d'un langage à balisage léger créé par John Gruber. 

Exemples d'utilisation:

- documentation des projets sur [GitHub](https://github.com),

- cellule de texte dans un Jupyter Notebook,

- cette documentation,

- ...

Il existe plusieurs versions de Markdown avec des spécifications de syntaxe plus ou moins développées:

- **CommonMark**: version la plus basique

- **GFM** (*Github Flavored Markdown*): version plus sophistiquée, utilisée sur Github.

## 8.1. Éditeurs Linux

2 éditeurs avec prévisualisation en temps réel (CommonMark, GFM, plugins d'affichage de diagramme...) semblent sortir du lot:

- [Typora 0.9.86(beta)](https://typora.io/): probablement le plus abouti, projet **non open-source**, gratuit dans sa version beta (le restera-t-il?).
  
  - beaucoup de formats d'exportation
  
  - génération automatique de table des matières
  
  - fonctionnalités de zoom sur le document
  
  > Pas de rpm mais des binaires `*.deb` ou dans une archive `tar.gz`.

- [Mark Text 0.16.1](https://github.com/marktext/marktext/releases): projet open-source sur [Github](https://github.com).

## 8.2. Syntaxe

## 8.3. Convertisseurs

- **Pandoc**: bibliothèque *Haskell*, conversion vers la plupart des langages à balises.

- **ShowdownJS**: bibliothèque *JavaScript*, conversion vers HTML.

## 8.4. Diagrammes

Avec [mermaid](https://mermaid-js.github.io) (bibliothèque JavaScript) 
