# Module Core

Les modules **Core** sont accessibles par défaut :

```js
// http est un module Core
var http = require('http');

// La méthode createServer permet de créer un serveur HTTP
http.createServer(function (req, res) {
    res.writeHead(200, {'Content-Type': 'text/plain'});
    res.end('Hello World!');
}).listen(8080);
```


# Liste des modules Core

||||||
|:-:|:-:|:-|:-|:-|
|assert|buffer|child_process|cluster|crypto
|dgram|dns|domain|events|fs
|http|https|net|os|path
|punycode|querystring|readline|stream|string_decoder
|timers|tls|tty|url|util|
|v8|vm
