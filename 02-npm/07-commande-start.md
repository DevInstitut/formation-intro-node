# Commande npm start

Par défaut, la commande **npm start** lance le script : **node server.js** si un fichier **server.js** est présent.

Il est possible de redéfinir cette configuration.

```json
"scripts" : {
  "start" : "node autrescript.js"
}
```

```bash
npm start
```

Noter l'absence de *run* dans la commande.
