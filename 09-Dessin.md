# Chapitre 9. Dessin vectoriel

## 9.1. Canvas (HTML)

C'est un élément rectangulaire (300x150, par défaut) où il est possible de dessiner grâce au langage JavaScript.

```html
<canvas width="400" height="300" id="moncanvas">
  Canvas non supporté!
</canvas>
```

> Attention: les dimensions du Canvas spécifiées via CSS ne s'appliquent qu'une fois le dessin effectué et peuvent donner une image *étirée*.

La manipulation et la création de contenu requiert un *contexte de rendu*. Plusieurs peuvent être disponibles

- 2D

- WebGL

- 3D (inspiré de OpenGL ES)

- ...

### 9.1.1. Contexte 2d

On récupère ce contexte depuis l'élément *Canvas*:

```javascript
var canvas = document.querySelector("#moncanvas");
var pinceau = canvas.getContext("2d");
```

Pour modifier le pinceau:

- couleur de remplissage:

```javascript
pinceau.fillStyle = "red";
pinceau.fillStyle = "#FFA500";
pinceau.fillStyle = 'rgb(255, 165, 0)';
pinceau.fillStyle = 'rgba(255, 165, 0, 0.5)';
```

- couleur de contour:

```javascript
pinceau.strokeStyle = "green";
```

Dessiner des formes:

- Une ligne:

```javascript
pinceau.beginPath();
pinceau.moveTo(0,0);
pinceau.lineTo(100,100);
pinceau.stroke();
```

- Un rectangle:

```javascript
pinceau.fillRect(25, 25, 100, 100); // x,y, width, height
pinceau.strokeRect(50, 50, 50, 50);
```

- Un arc

```javascript
// cercle centré en (75,75) et de rayon 50
pinceau.beginPath();
pinceau.arc(75,75,50,0,Math.PI*2,true); 
pinceau.closePath();
pinceau.fill();
```

- Un chemin (`path`):

```javascript
pinceau.beginPath();
pinceau.moveTo(75,50);
pinceau.lineTo(100,75);
pinceau.lineTo(100,25);
pinceau.closePath();

pinceau.stroke(); // le contour
pinceau.fill(); // l'intérieur
```

- Du texte (`x` et `y` sont les coordonnées du coin **inférieur gauche**):

```javascript
pinceau.font = '20pt comicsans';
pinceau.fillStyle = 'black';
pinceau.fillText("Texte à afficher", 100, 100); // x,y
```

Effacer une zone rectangulaire:

```javascript
// Tout le contenu du canvas
pinceau.clearRect(0, 0, canvas.width, canvas.height);
```

### 9.1.2. Contexte webgl

### 9.1.3. Animation

Il suffit de prévoir une fonction principale de dessin:

```javascript
function draw() {
  // dessiner du contenu de l'interface
}
```

Puis utiliser une des 2 méthodes suivantes:

- appeler périodiquement cette fonction:

```javascript
setInterval(draw, 10); // toutes les 10ms
```

- laisser le navigateur gérer le rafraichissement:

```javascript
requestAnimationFrame(draw);
```

### 9.1.4. Gestion d'événements

Il faut demander à l'élément approprié (*Canvas*, `document`...) d'écouter l'événement en question et d'appeler une certaine fonction le cas échéant:

```javascript
canvas.addEventListener('mousedown', gestionAppuiSouris, false);
document.addEventListener('keydown', gestionAppuiTouche);
```

La fonction appelée reçoit automatiquement l'événement en paramètre:

```javascript
function gestionAppuiSouris(event) {
  // Coordonnées du clic
  let x = event.offsetX;
  let y = event.offsetY;
}

function gestionAppuiTouche(event) {
  if (event.key == "Right" || event.key == "ArrowRight") {
    // Touche droite
  }
}
```

## 9.2. SVG

Langage à balise XML.
