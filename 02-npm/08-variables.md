# Variables
Les propriétés du fichier **package.json** sont transformées en variables accessibles via **process.env.npm_package_****** dans des scripts.

```json
"name": "super-nom",
"config" : {
  "port" : 5000,
  "api" : "http://api.com"
}
```
```js
var port = process.env.npm_package_config_port;
var nom = process.env.npm_package_name;
```