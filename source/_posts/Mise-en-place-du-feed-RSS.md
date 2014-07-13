title: 'Mise en place du nouveau lien RSS'
date: 2014-07-13 10:44:49
tags:
---

Cette année, Feedburner n'est pas passé à la trappe du grand nettoyage de printemps de Google (vous souvenez-vous de Google reader !). Je profite donc que le service de redirection des flux soit toujours en vie pour noter ici la manip à effectuer. J'ignore s'il existe beaucoup d'utilisateurs francophones de hexo.io, mais au moins, si je le note ici, il est possible que je ne l'oublie pas !

Donc, avec Hexo.io, la déclaration des menus (et donc l'entrée RSS) s'effectue directement dans le fichier de configuration du thème `_config.yml`.

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
