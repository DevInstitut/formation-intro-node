# Catégories de dépendances

* Les dépendances de **développement** (propriété **devDependencies**);

```json
  "devDependencies": {
    "gulp": "^3.9.1"
  }
```

* Les dépendances de **production** (propriété **dependencies**).

```json
  "dependencies": {
    "underscore": "^1.8.3"
  }
```

# Récupérer les dépendances

La commande **npm install** (ou **npm i**) récupère toutes les dépendances définies dans le fichier **package.json** et les *installe* dans un répertoire **node_modules** courant.

```bash
/super-projet
  package.json
  /node_modules
    /gulp
    /angular
    /underscore
    ...
```
---
# Ajouter une nouvelle dépendances

Pour ajouter une nouvelle dépendance de production :

```bash
npm install angular --save
```

Pour ajouter une nouvelle dépendance de développement :

```bash
npm install gulp --save-dev
```