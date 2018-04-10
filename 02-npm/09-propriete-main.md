# Propriété main

La propriété **main** définit le point d'entrée d'un module.

```bash
app.js
/monmodule
  package.json
  superscript.js
```

```js
// package.json
"main" : "superscript.js"
```

```js
// app.js
// Récupération du module (superscript.js)
var mod = require("./monmodule");
```