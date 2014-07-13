title: 'Mise en place du nouveau lien RSS'
date: 2014-07-13 10:44:49
tags:
---

Cette année, Feedburner n'est pas passé à la trappe du grand nettoyage de printemps habituel de Google. J'en profite pour noter ici la manip à effectuer pour proposer dans le menu le lien RSS qui pointe vers les articles du blog. J'ignore s'il existe beaucoup d'utilisateurs de hexo.io francophones, mais au moins, si je le note ici, il est possible que je ne l'oublie pas !

Donc, avec Hexo.io, la déclaration des menus (et donc l'entrée RSS) s'effectue directement dans le fichier de configuration du thème : _config.yml.

``` 
# Header
menu:
  Home: /hexoskelet
  Archives: /hexoskelet/archives
rss: http://feeds.feedburner.com/vfarcy?format=xml

# Content
excerpt_link: Read More
fancybox: true

# Miscellaneous
google_analytics:
favicon: favicon.png
```

Hope this helps !
