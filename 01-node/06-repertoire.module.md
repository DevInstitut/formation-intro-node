# Un répertoire comme module

Un module peut aussi être un répertoire contenant un script **index.js**.

```bash
/app
  moduleA.js
  /moduleB
    index.js # fichier représentant le moduleB
```

```js
// moduleA.js
var moduleB = require("./moduleB");
```
