title: 'Mise en place du nouveau lien RSS'
date: 2014-07-13 10:44:49
tags:
---

Cette année, Feedburner n'est pas passé à la trappe lors du grand nettoyage de printemps de Google (vous souvenez-vous de Google reader ?). Je profite donc que le service de redirection des flux est toujours diponible pour noter ici la manip à effectuer. 

Donc, avec Hexo.io, la déclaration de l'adresse du flux RSS s'effectue directement dans le fichier de configuration du thème `_config.yml`.

```   
# Header
menu:
  Home: /
  Archives: /archives
rss: http://feeds.feedburner.com/vfarcy?format=xml

# Content
excerpt_link: Read More
fancybox: true

# Miscellaneous
google_analytics:
favicon: favicon.png
```

Voilà, hope this helps !
