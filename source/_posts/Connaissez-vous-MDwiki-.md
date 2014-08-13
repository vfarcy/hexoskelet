title: Connaissez-vous MDwiki ?
date: 2014-08-13 08:05:16
tags:
---

# MDwiki : Un wiki statique en markdown

[MDwiki](http://dynalon.github.io/mdwiki/) est un CMS / wiki qui s'exécute intégralement dans le navigateur (HTML5/Javascript) et qui utilise [Markdown](http://en.wikipedia.org/wiki/Markdown) comme syntaxe de description du texte.

Comme il s'exécute intégralement du côté client, il est possible de réaliser des choses assez sympathiques, comme par exemple suivre les changements sur git(hub) et héberger gratuitement le contenu sur les [pages Gitub](https://pages.github.com/).

# Mise en place sur Github

Il existe un [guide officiel](http://dynalon.github.io/mdwiki/#!tutorials/github.md) mais voici une procédure détaillée et complémentaire pour héberger MDwiki sur Github. Nous partons du principe que vous disposez déjà d'un compte Github.

* sur Github
  * [Créer un répo](https://github.com/new) et lui donner un nom adéquat(par exemple `my-mdwiki`)
* Installer MDwiki
  * [Télécharger la dernière version](https://github.com/Dynalon/mdwiki/releases)
  * L'extraire dans le répertoire du répo (par exemple `my-mdwiki`)
  * Choisir l'un des deux fichiers suivants :
    * `mdwiki.html` contient l'ensemble des librairies
    * `mdwiki-slim.html` contient le noyau de MDwiki et charge les librairies complémentaires depuis internet
  * En fonction de votre choix, renommer `mdwiki.html` ou `mdwiki-slim.html` en  `index.html`
  * Créer ensuite un fichier `config.json`. Pour cela, se référer à [ce document](http://dynalon.github.io/mdwiki/#!customizing.md) (en anglais)ou utiliser celui-ci :

```json
{
    "useSideMenu": true,
    "lineBreaks": "gfm",
    "additionalFooterText": "",
    "anchorCharacter": "&para;",
    "title": "My Shiny New MDwiki"
}
```

  * Créer un fichier `navigation.md` ([docs en aglais](http://dynalon.github.io/mdwiki/#!quickstart.md)) qui contient (essentiellement) les menus :

```markdown
# Le nom du wiki

[Home](index.md)
[About](about.md)
[Download](download.md)
```

  * Créer une première page (le principe est identique pour les autres pages) en créant un fichier `index.md` (même nom que le fichier déclaré dans `navigation.md`.

```markdown
# Hello World!

Voilà une première page!
```

  * Voilà, c'est terminé.
  * En bonus, de manière à tester le contenu en local, il est possible de lacer un serveur web, par exemple en utilisant le serveur intégré à python. Pour cela, il suffit de créer un script `run-pyserver.sh` (ne pas oublier de la rendre exécutable : `chmod +x run-pyserver.sh` !) : 

```bash
#!/bin/bash

open http://localhost:8000
python -m SimpleHTTPServer 8000
```

* Maintenant, il faut initialiser le repo Git:
  * Se rendre dans le répertoire ad-hoc (par exemple `cd ~/my-mdwiki`)
  * Initialiser le repo : `git init`
  * Créer une branche initiale *gh-pages* (et non *master*): `git symbolic-ref HEAD refs/heads/gh-pages`
  * Ajouter tous les fichiers créés jusqu'à maintenant : `git add .`
  * Les commiter :  `git commit -m "Initial Commit"`
  * Ajouter le repo Gihub en tant que distant (replacer `YOURUSERNAME` avec le login Github réel, et `my-mdwiki` avec le nom du repo créé initialement) : `git remote add origin git@github.com:YOURUSERNAME/my-mdwiki.git`
  * Puis pousser le tout sur github: `git push -u origin gh-pages`
* C'est terminé, très rapidement, le wiki est en ligne à l'adresse http://YOURUSERNAME.github.io/my-mdwiki

# Exemples 

Voici une liste de sites réalisés avec MDwiki avec le code associé :

* [Sample coffee place](http://dynalon.github.io/mdwiki-examples/cafe/) [[source markdown]](https://github.com/Dynalon/mdwiki-examples/tree/gh-pages/cafe)
* [Simple travel blog website](http://dynalon.github.io/mdwiki-examples/travel_blog/) [[source markdown]](https://github.com/Dynalon/mdwiki-examples/tree/gh-pages/travel_blog)
* [Single-page fansite about Muscle Cars](http://dynalon.github.io/mdwiki-examples/muscle_cars/) [[source markdown]](https://github.com/Dynalon/mdwiki-examples/tree/gh-pages/muscle_cars)

[source](http://blog.devalias.net/post/92579952637/mdwiki-and-how-to-get-started)