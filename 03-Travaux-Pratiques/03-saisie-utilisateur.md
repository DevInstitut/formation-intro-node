# Saisie Utilisateur

Pour récupérer la saisie utilisateur, nous allons utiliser un module core de Node `readline`.


## Exemple avec readline

* Créer un fichier `prototype/proto-readline.js`.

```js
var readline = require('readline');

var rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
});

rl.question('Vous allez bien ? : ', function(saisie) {
    console.log(`Vous avez saisi : ${saisie}`);


    rl.close();// attention, une fois l'interface fermée, la saisie n'est plus possible
});

```

* Tester le code `node prototype/proto-readline.js`.

```
Vous allez bien ? : oui très bien
Vous avez saisi : oui très bien
```

## Menu

* Implémenter le menu suivant :

```
*************************
1. Rafraichir les données
2. Lister les sessions
99. Quitter
```

Quelques indications :
* Après l'exécution d'une action le menu est réaffiché sauf dans le cas de l'option 99
* L'option 99 permet de quitter le programme
* L'option 1 invoque la méthode `service.init(callback)` et affiche le message suivant après le raffraîchissement `... Données mises à jour`.
* L'option 2 invoque une méthode `service.listerSessions(callback)` (à créer) et affiche la liste des sessions sous la forme `TITRE (PRESENTATEURS)`.
* Le service `service.listerSessions(callback)` permet de retourner le tableau de sessions (données complètes).