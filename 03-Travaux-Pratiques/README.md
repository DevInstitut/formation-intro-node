# Travaux Pratiques

## Objectif

L'objectif est de réaliser une application console permettant d'explorer les données
de la conférence **BreizhCamp 2018** (http://www.breizhcamp.org/conference/programme/).

L'application console aura la forme suivante :

```
** Application BreizhCamp 2018 **

1. Lister les sessions
2. Lister les sessions par catégorie
3. ...

Choisir une action : ...

```

L'application va être réalisée à l'aide de NodeJS.




* Créer un répertoire *breizhcamp-2018-console*.


* Initialiser un projet via la commande _npm init_.

```
cd breizhcamp-2018-console
npm init
```


* Intégrer le module _devfest-2015.js_ dans le projet :

----
/formation-frontend
    /01-rappels-es5
    /02-nodejs
        package.json
        /data                   <1>
            devfest-2015.js

----
<1> : répertoire à créer.

* Créer un script _service.js_ :

----
/formation-frontend
    /01-rappels-es5
    /02-nodejs
        service.js <1>
        package.json
        /data
            devfest-2015.js
----
<1> : fichier à ajouter.

* Compléter le module _service.js_ pour qu'il expose les services suivants :
** _listerTousLesPresentateurs()_ : retourne le tableau de tous les présentateurs;
** _listerToutesLesSessions()_ : retourne le tableau de toutes les sessions;
** _trouverUneSession(idSession)_ : retourne la session dont l'identifiant est fourni;
** _listerTopPresentateurs()_ : retourne uniquement les présentateurs qui ont la propriété _topspeaker_ à _true_.


* Créer un script _console.js_ :

----
/formation-frontend
    /01-rappels-es5
    /02-nodejs
        console.js <1>
        package.json
        service.js
        /data
            devfest-2015.js
----
<1> : fichier à ajouter.

* A l'aide du module _readline_ (documentation officielle : https://nodejs.org/dist/latest-v6.x/docs/api/), créer le menu suivant :

----
*** Application Conférence ***
1. Liste de tous les présentateurs  <1>
2. Top présentateurs                <2>
3. Liste des sessions               <3>
4. Détail d'une session             <4>
----
<1> : affichage des prénoms et noms des présentateurs
<2> : affichage des prénoms et noms des présentateurs top
<3> : affichage des titres des sessions
<4> : demande à l'utilisateur de saisir un identifiant de session puis affiche la description et le(s) présentateur(s) de la session.

