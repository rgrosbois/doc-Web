# Chapitre 3. CSS

*Cascading Style Sheet*

Ce langage permet de gérer l'apparence (=le style) des balises d'un document HTML à l'aide de couples `propriété: valeur` définis dans une *feuille de styles*.

> Attention: des différences d'affichage d'une même page peuvent survenir d'un navigateur à l'autre. Pour tenter d'y remédier, il est possible de spécifier une normalisation CSS dans l'en-tête du document HTML ex: http://necolas.github.io/normalize.css/):
> 
> ```html
> <link rel="stylesheet" src="//normalize-css.googlecode.com/svn/trunk/normalize.css">
> ```
> 
> (ou équivalent)

## 3.2. Règles cascadées

Une feuille CSS est constituée de règles dont le format est le suivant:

```css
selecteur {
  attribut: valeur;
}
```

Les règles CSS peuvent être déclarées à divers emplacements de priorité croissante:

1. Règles par défaut du navigateur:
   
   - [WebKit (Chrome ou Safari)](http://trac.webkit.org/browser/trunk/Source/WebCore/css/html.css)
   - [Firefox](http://hg.mozilla.org/mozilla-central/file/tip/layout/style/html.css)
   - [Internet Explorer](http://www.iecss.com/)

2. Feuille de style externe. À l'aide de la balise `link` dans l'en-tête HTML:      
   
   ```html
     <link rel="stylesheet" href="feuille.css" />
   ```


