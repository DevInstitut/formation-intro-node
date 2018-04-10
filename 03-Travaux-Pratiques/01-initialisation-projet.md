# Initialisation Projet

* Créer un répertoire **breizhcamp-2018-console**.

* Génerer le fichier _package.json_.

```
npm init -y
```

* Créer un fichier _index.js_

```
/breizhcamp-2018-console
    index.js
    package.json
```

* Compléter le fichier _index.js_ comme suit :

```
console.log('** Application BreizhCamp 2018 **');
```

* Compléter le fichier _package.json_

```json
{
    "scripts" : {
      "start" : "node index.js"
    }
}
```
* Tester la configuration via la commande :

```bash
npm start
```

Vérifier l'affichage :

```
** Application BreizhCamp 2018 **
```