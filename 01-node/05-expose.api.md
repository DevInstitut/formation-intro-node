# Exposer une API

Exposer une API à l'extérieur d'un module via la variables ==exports==.

```js
// moduleA.js
var libelleCourant = 'valeur secrète';

function lireLibelle() { return libelleCourant; }

// les fonctions lire est accessible en dehors du module
exports.lire = lireLibelle;
```
La fonction ==require== permet de récupérer et utiliser un module.
```js
var moduleA = require('./moduleA.js');
var libelleCourantModuleA = moduleA.lire();
```