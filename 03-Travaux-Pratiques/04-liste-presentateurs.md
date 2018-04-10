# Liste des présentateurs

Voici la page des présentateurs du BreizhCamp : http://www.breizhcamp.org/conference/speakers/.


Il n'y a visiblement pas d'API permettant de récupérer les présentateurs au format JSON.

Cette particularité est une opportunité supplémentaire pour continuer à progresser en Node et JavaScript.

Nous allons donc récupérer la page au format HTML et y extraire les informations.

## Exemple de récupération de code HTML

* Créer un fichier `prototype/proto-request-html.js`.


```js
var request = require('request');

request('http://www.breizhcamp.org/conference/speakers/', {}, function(err, res, body) {
    if (err) { return console.log('Erreur', err); }

    console.log(body);
});
```

* Exécuter le script `node prototype/proto-request-html.js` et vérifier que le code HTML est bien récupéré.

## Extraction d'informations d'une page HTML

Nous allons ici utiliser la librairie `jsdom` (https://github.com/jsdom/jsdom).

Cette librairie permet de récupérer du code HTML au format chaîne de caractères et de construire un DOM.
L'intérêt recherché est la possibilité de naviguer à travers la structure avec des méthodes JavaScript connues.


* Installer `jsdom`

```
npm i -S jsdom
```

* Créer un fichier exemple `prototype/unePage.html`.

```html
<!doctype html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Démo jsdom</title>
</head>
<body>

<ul>
    <li>JavaScript</li>
    <li>Java</li>
    <li>Rust</li>
</ul>

</body>
</html>
```

* Créer un fichier `prototype/proto-jsdom.js`.

```js
var jsdom = require('jsdom');

// récupération de la page HTML exemple
var fs = require('fs');
var pageHTML = fs.readFileSync('./prototype/unePage.html').toString();

var dom = new jsdom.JSDOM(pageHTML);
var langs = dom.window.document.querySelectorAll("li");
langs.forEach(function(lg) {
    console.log(lg.innerHTML);
});

```

* Exécuter le script `node prototype/proto-jsdom.js` et vérifier l'affichage.

```
JavaScript
Java
Rust
```

## Menus supplémentaires

* Implémenter le menu suivant :

```
1. Rafraichir les données
2. Lister les sessions
3. Lister les présentateurs
99. Quitter

```

L'option 3 permet d'afficher les noms et prénoms des présentateurs de l'événement.