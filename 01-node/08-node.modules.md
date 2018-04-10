# Répertoire node_modules

Lorsque la fonction **require** est appelée avec un module **qui n'est pas un module Core** et qui ne commence pas par **/", "../" ou "./"** alors la recherche s'effectuera dans le répertoire **node_modules**.

```bash
/home/rossi/application
              app.js
              /node_modules
                /gulp
                  index.js
```

```js
// app.js
var gulp = require("gulp");
```

# Recherche dans les répertoires parents

```js
// app.js
var gulp = require("gulp");
```

```bash
/home/rossi/application
              app.js
```
Dans le cas où le module n'est pas trouvé dans le répertoire *./node-modules*, la recherche du module se poursuit dans les répertoires parents.

```bash
/home/rossi/node_modules
/home/node_modules
/node_modules
```


# NODE_PATH

Si une variable d'environnement **NODE_PATH** est définie, la recherche se poursuit dans les répertoires définies dans cette variable.

```bash
# Si NODE_PATH=/home/apps:/usr/local/share

# La recherche du module aura lieu dans les répertoires suivants :

/home/apps
/usr/local/share
```


# NPM_CONFIG_PREFIX

NodeJS va également inclure dans sa recherche de modules les répertoires suivants :

* `$HOME/.node_modules`
* `$HOME/.node_librairies`
* `$PREFIX/lib/node`

`$HOME` représente le répertoire utilisateur et `$PREFIX` est défini par la variable d'environnement **NPM_CONFIG_PREFIX**.

---