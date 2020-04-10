# Chapitre 3. CSS

(*Cascading Style Sheet*)

Ce langage permet de gérer l'apparence (=le style) des balises d'un document HTML à l'aide de couples `propriété: valeur` définis dans une *feuille de styles*.

> Attention: des différences d'affichage d'une même page peuvent survenir d'un navigateur à l'autre. Pour tenter d'y remédier, il est possible de spécifier une normalisation CSS dans l'en-tête du document HTML ex: http://necolas.github.io/normalize.css/):
> 
> ```html
> <link rel="stylesheet" src="//normalize-css.googlecode.com/svn/trunk/normalize.css">
> ```
> 
> (ou équivalent)

## 3.1. Règles cascadées

Une feuille CSS est constituée de règles dont le format est le suivant:

```css
selecteur {
  propriete1: valeur1;
  propriete2: valeur2;
}
```

La liste des propriétés supportées et les valeurs possibles dépendent de la cible (Cf [documentation](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference))

Les balises HTML neutres (`<div>` et `<span>`) sont souvent ajoutées au code-source de la page HTML pour faciliter la définition de son style.

Les règles CSS peuvent être déclarées à divers emplacements de priorité croissante:

1. Règles par défaut du navigateur:
   
   - [WebKit (Chrome ou Safari)](http://trac.webkit.org/browser/trunk/Source/WebCore/css/html.css)
   - [Firefox](http://hg.mozilla.org/mozilla-central/file/tip/layout/style/html.css)
   - [Internet Explorer](http://www.iecss.com/)

2. Feuille de style externe. À l'aide de la balise `link` dans l'en-tête HTML:      
   
   ```html
     <link rel="stylesheet" href="feuille.css" />
   ```

3. Balise HTML `<style>`:

```html
<style> ... </style>
```

4. Attribut de balise (ouvrante) `style`:

```html
<div style="font-size: 185%;">
```

> Pour insérer des commentaires dans une feuille de style:
> 
> ```css
> body {
>   height: 100%;
>   background-color: white;
> /* background-image:url(loading.gif);
>   background-position:center center;
>   background-repeat:no-repeat;*/
> }
> ```

## 3.2. Sélecteur

Il spécifie la cible (élément(s) HTML) sur laquelle s'applique la règle. Les plus courants sont:

- un nom de balise : `h1`, `p`...

```css
p {
  color: red;
}
```

> Les modifications s'appliquent à tous les balises de type `p`.

- un nom de classe: le sélecteur s'écrit `.maclasse`.

```css
.ma-classe {
  text-align: center;
}
```

>  Les modifications s'appliquent à la ou les balises avec l'attribut `class=ma-classe`.

- un nom d'identifiant: le sélecteur s'écrit `#mon-identifiant` 

```css
#mon-identifant {
  text-align: center;
}
```

> Les modifications s'appliquent à la balise avec l'attribut `id=mon-identifiant`.

- combinaison *descendante*:

```css
li a {
  ...
}
```

> Les modifications s'appliquent aux balises `<a>` dans une liste.

Pour définir une règle s'appliquant à toutes les balises:

```css
* {
  ...
}
```
