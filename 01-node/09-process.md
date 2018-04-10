# Objet global process

L'objet global **process** contient les informations du processus courant :

```js
/* arguments d'éxécution
  exemple : exécution node process.js ARG1 ARG2
 ['/usr/bin/nodejs', '/home/rossi/process.js', 'ARG1', 'ARG2']
*/
process.argv

// linux
process.platform;

// { http_parser: '2.7.0', node: '6.11.2', v8: '5.1.281.103'}
process.versions;

```