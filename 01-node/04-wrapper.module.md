# Wrapper de module

Afin d'isoler le code exécuté dans un module NodeJS, le code est embarqué dans une fonction.

```js
(
function(exports, require, module, __filename, __dirname) {
// code du module
});
/*
* exports : api exposé en dehors du module
* require : utiliser un autre module
* module : objet représentant le module
* __filename : le fichier en cours d'exécution
* __dirname : le répertoire où se trouve le fichier
*/
```