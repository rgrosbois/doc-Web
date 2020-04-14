# Chapitre 5. JavaScript

C'est un langage script orienté objet exécuté par le client Web (i.e. le navigateur). 

> Même si certaines instructions ressemblent au Java, ces deux langages n'ont aucune parenté. Le véritable est d'ailleurs **ECMA-xxx**. *JavaScript* a été utilisé ensuite, suite à un accord avec *Sun*, afin de profiter de la notoriété du langage Java.

> Le langage ayant fortement évolué depuis sa création en 1995, il existe de nombreuses manières de faire les mêmes choses. Comme de nombreuses bibliothèques existent pour faciliter le développement en JavaScript, l'écriture en JavaScript *nu* est qualifiée de *Vanilla JavaScript*.

## 5.1. Chargement et lancement

Les scripts sont fournis via des balises `<script>` :

- il peuvent être écrits directement dans la page HTML:

```html
 <script>
   <!-- Instruction JavaScript -->
 </script>
```

- il peuvent être importés depuis un fichier externe (`*.js`):

```html
 <script src="monscript.js"></script>
```

Comme le script est évalué par le client au moment où il le rencontre dans la page HTML, les balises `<script>` sont généralement placées à la fin de la section `<body>`.

Pour s'assurer que l'évaluation d'une fonction ne se fasse qu'une fois la page chargée, on peut l'appeler via l'attribut `onload` de la balise `<body>` du document HTML.

```html
<body onload='maFonction();'>

  <script>
  function maFonction() {

  }
  </script>
</body>
```

## 5.2. Déboggage

On peut utiliser une des deux méthodes suivante:

- la console du navigateur:

```javascript
console.log("Mon message");
console.error("Mon message");
console.warn("Mon message");
console.info("Mon message");
```

> Pour autoriser l'écriture dans la console de *Firefox*, il faut donner la valeur `true` à la clé `devtools.chrome.enabled`  (accessible via l'URL *about:config*).

- une fenêtre *popup*:

```javascript
alert("Afficher un message");
let nom = prompt("Quel est votre nom ?");
```

## 5.3. Langage

- le code est sensible à la casse,

- les instructions sont séparées par des points-virgules (même s'ils sont optionnels en fin de ligne),

- les commentaires sont similaires à ceux du *C* et de *Java*:

```javascript
// Commentaire sur une ligne
/*
 Commentaire sur
 plusieurs lignes
*/
```

### 5.3.1. Types de données

JavaScript est un langage à typage *implicite*.

Le type d'une variable peut s'obtenir à l'aide de l'instruction:

```javascript
typeof x
```

Les principaux types sont:

- numérique (pas de distinction entre *entiers* et *flottants*): `number`

- chaîne de caractères : `string`

- booléen (`true` ou `false`): `boolean`

- fonction: `function`

- objet: `object`

- tableau: `Array`

### 5.3.2. Variables

Il est possible d'utiliser une variable sans l'avoir préalablement déclarée:

```javascript
a = "Bonjour";
```

Mais il est préférable de les déclarer à l'aide des mots-clés `let`, `const` ou `var`: 

- Variable locale (valables qu'entre 2 accolades):

```javascript
{
  let a, x, y, x, t, jours;
  x = 1;
  y = 12.5;
  z = ’Bonjour’;
  t = true;
  jours = [’lundi’, ’mardi’, ’mercredi’];  
}
```

- constante:

```javascript
const PI = 3.14;
```

- variable globale:

```javascript
var maVariable = 10;
```

> Attention: il n'est pas possible de changer le type a-posteriori d'une variable déclarée avec `let`, `const` ou `var`.

### 5.3.3. Les opérateurs

- classiques (i.e. identiques à Python):

```javascript
(3 + 2) * (4 - 2.15) / 6
nom + ’,’ + prenom
x<=15
2**4 // puissance
```

- spécifiques:

```javascript
pseudo === "nsi" // égalité du contenu de 2 chaînes
5 !== 3 // inégalité
(x>0) && ( (x<=15) || (x>24) ) // pas de double inégalité comme en Python
```

### 5.3.4. Exécution conditionnelle

```javascript
let age = Number(prompt("Quel age ?"));
if (age<13) {
  categorie = "enfant";
} else if (age<18) {
  categorie = "adolescent";
} else {
  categorie = "adulte";
}
```

### 5.3.5. Boucles

- boucle `for`:

```javascript
let jours = [31, 28, 31, 30, 31];
let somme = 0
for (let i=0; i<jours.length; i++) {
  somme += jours[i];
}
```

- boucle *foreach*:

```javascript
var person = {
  "fname" : "John",
  "lname" : "Doe",
  "age": 25
};

for (x in person) { // attention x est l'index ou la propriété
  txt = txt + person[x];
}
```

- Il existe aussi les boucles `while` et `do/while`

Les mots-clés `break` et `continue` permettent respectivement passer à l'itération suivante ou de sortir de la boucle.

> Il est possible d'adjoindre un *label* et de réaliser l'équivalent d'un `goto`:
> 
> ```javascript
> monLabel: // instructions à exécuter
> ...
> break monLabel;
> ...
> continue monLabel; // uniquement à l'intérieur d'une boucle
> ```

### 5.3.6. Exception

Elle peut se gérer à l'aide de la structure `try/catch/throw`:

```javascript
if (typeof a !== 'number') {
  throw new Error("a devrait être un nombre");
}
```

### 5.3.7. Fonction

- Elle se déclare avec le mot-clé `function`

- les paramètres sont positionnels (les types sont *implicites*)

- elle peut retourner une valeur (type *implicit*) grâce au mot-clé `return`

```javascript
function maFonction(param1, param2) {
  ...
  return val;
}
```

Une fonction est du type *objet* et peut être sauvegardée (on parle alors de *fermeture* ou *Closure*):

```javascript
var maFonction = funtion(param1, param2) {
  ...
  return val;
}
```

> Les arguments non spécifiés lors de l'appel se voient attribués la valeur `undefined`.

### 5.3.8. Objet

> Il n'existe pas de classe en JavaScript
