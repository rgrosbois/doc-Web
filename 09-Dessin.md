# Chapitre 9. Dessin vectoriel

## 9.1. Canvas (HTML)

C'est un élément dans lequel il est possible de dessiner avec le langage JavaScript.

```html
<canvas width="400" height="300" id="moncanvas">
  Canvas non supporté!
</canvas>
```

### 9.1.1. Contexte 2d

Pour récupérer ce contexte:

```javascript
let canvas = document.querySelector("#moncanvas");
let pinceau = canvas.getContext("2d");
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

- Un rectangle:

```javascript
pinceau.fillRect(25, 25, 100, 100);
pinceau.clearRect(45, 45, 60, 60);
pinceau.strokeRect(50, 50, 50, 50);
```

- Un arc

```javascript
// cercle centré en (75,75) et de rayon 50
pinceau.arc(75,75,50,0,Math.PI*2,true); 
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

### 9.1.2. Contexte webgl

## 9.2. SVG

Langage à balise XML.
