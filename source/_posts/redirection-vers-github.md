title: 'Comment rediriger un nom de domaine vers un blog statique hébergé sur Github ?'
date: 2014-07-13 10:44:49
tags:
---

Github autorise l'hébergement de page web statiques et offre la possibilté d'y accéder à partir d'un nom de domaine du type sousdomaine.domaine.tld. C'est gratuit (hors le coût du nom de domaine !) et gratuit.

Il existe de nombreux tutoriaux qui indiquent la marche à suivre, mais ils sont souvent anciens, ou bien compliqués. Je vous résume la méthode que j'ai utilisée avec succès.

Depuis le panneau de contrôle de votre registar, il sufit de créer un enregistement CNAME qui pointe vers votre adresse github (du type votrenom.github.io) et de créer un fichier CNAME dans votre repository qui contient l'adresse du type sousdomaine.domaine.tld.

Concrêtement, je recommande de commencer, dans l'ordre, par créer l'enregistrement CNAME (attention, certains registar réclament une adresse du type sousdomaine.domaine.tld. - noter le point final)chez votre registar et de laisser suffisamment de temps pour que le DNS se propage. Vous pouvez vérifier la progression de la propagation en utilisant un service comme whatosmydns.com. Chez moi, une une 20aine de minutes ont suffis avant d'avoir une couverture quasi totale.

Quand cette première étape est passée, il vous reste à créer chez Github un fichier CNAME comportant le même sous domaine (sousdomaine.domaine.tld - sans le point final !) et de patienter une 15aine de minutes. 















