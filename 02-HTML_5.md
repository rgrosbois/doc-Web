# Chapitre 2. HTML 5

> Après s'être fortement rapproché de l'XML jusqu'aux version 4.x, le HTML s'en en ré-éloigné avec la version 5. 

Le HTML est un langage qui permet de décrire le contenu et la structure d'un document multimédia (texte, image, son, hyperliens...) à l'aide de containers sémantiques (les balises). Un fichier HTML (version 5) début par la ligne suivante:

```html
<!DOCTYPE html>
```

> Attention: bien que subsistent quelques balises ou attributs HTML capables d'influer sur la présentation du document, il est désormais préférable de gérer exclusivement l'apparence du document à l'aide de styles CSS.

## 2.1. Structure d'un document

La structure classique d'un document HTML est la suivante:

```html
<!DOCTYPE html>
<html lang="fr">
  <head> <!-- métadonnées -->
    <meta charset="utf-8" />
    <title>Titre du document</title>
    ...
  </head>

  <body> <!-- contenu du document -->

  </body>
</html>
```

## 2.2. Balises classiques

Les principales balises sont:

```html
<!-- Commentaire -->
```

- Titres (niveaux de 1 à 6):

```html
<h1>Titre de premier niveau</h1>
  <h1>Titre de second niveau</h2>
```

- Paragraphe:

```html
<p>Ceci est un premier paragraphe</p>

<p>Ceci est un second paragraphe</p>
```

- Lien hypertexte:

```html
<a href="http://un.autre.site">Mon lien vers un autre site ou page</a>

<a href="#ancre1">lien vers une ancre de page</a>
```

- Passage important:

```html
<p>Dans ce paragraphe, certains mots sont <strong>très importants</strong></p>
```

- Retour à la ligne:

```html
<p>1ère ligne du paragraphe<br />
2ème ligne du paragraphe</p>
```
