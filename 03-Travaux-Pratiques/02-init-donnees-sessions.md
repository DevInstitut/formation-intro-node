# Initialiser les données sessions

## Les sessions sur le site du BreizhCamp

Le programme du BreizhCamp est accessible à l'url : http://www.breizhcamp.org/conference/programme/.

* Grâce aux outils de développement du navigateur, déterminer les URLs permettant d'obtenir la liste des sessions au format JSON.

## Requête HTTP

Il y a plusieurs techniques permettant de récupérer des données via HTTP.

L'article suivant en donne un aperçu des techniques permettant d'effectuer une requête HTTP dans l'environnement Node : https://www.twilio.com/blog/2017/08/http-requests-in-node-js.html.

Nous allons utiliser la librairie _Request_ (https://github.com/request/request).

Expérimentons l'usage de cette librairie.

* Installer la librairie via NPM

```
npm install --save request
```

Visualiser l'impact dans le _package.json_.


* Créer un fichier : _prototype/proto-request-json.js_ avec le contenu suivant :

```js
// importation de la librairie request
// recherche par défaut dans le répertoire node_modules
var request = require('request')

// Envoie de la requête http
request('https://jsonplaceholder.typicode.com/posts', { json: true }, function(err, res, body) {
    if (err) { return console.log('Erreur', err); }

    // body contient les données récupérées
    console.log('Ok', body);
});
```
* Tester le script `node prototype/proto-request-json.js`.

## Architecture du projet

* Ajouter au projet 2 fichiers : _ihm.js_ et _service.js_.

```
/breizhcamp-2018-console
    index.js
    ihm.js
    service.js
```

`index.js` : le point d'entrée de l'application.
`ihm.js` : composant qui intéragit avec l'utilisateur
`service.js` : composant qui récupère les données

### `service.js` : service d'initialisation des données

* Compléter le fichier `servicejs` :

```js

// tableau qui contiendra toutes les sessions du BreizhCamp
var talks = [];

exports.init = function (callback) {

   callback(12);

};
```

* Créer un fichier `prototype/proto-service.js` avec le code suivant :

```js
var service = require('../service')

service.init(function(nb) {
    console.log('[init]', nb, 'sessions trouvées.')
});
```

* Exécuter le fichier `prototype/proto-service.js` :

```
node prototype/proto-service.js
```

Vérifier l'affichage :

```
[init] 12 sessions trouvées.
```

* Compléter le fichier `service.js` en suivant les instructions en commentaires.


```js

// tableau qui contiendra toutes les sessions du BreizhCamp
var talks = [];

exports.init = function (callback) {

    // TODO effectuer les requêtes HTTP permettant de récupérer les données du BreizhCamp

    // TODO     => une fois les données récupérées, alimenter la variable talks

    // TODO         => invoquer la callback avec le nombre de sessions récupérées

};
```

Vérifier la récupération des données.

### `ihm.js` : Démarrage de l'application.

```js
var service = require('./service');

exports.start = function() {
    service.init(function(nb) {
        console.log('[init]', nb, 'sessions trouvées.')
    });
};
```

### `index.js` : Lancement de l'IHM

```js
var ihm = require('./ihm');

console.log('** Application BreizhCamp 2018 **');

ihm.start();
```

Tester l'ensemble via `npm start` et vérifier que les sessions sont bien récupérées.


