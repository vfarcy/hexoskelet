title: 'A simple http server'
date: 2014-07-20 17:59:18
tags:
---



``` js A simple http server https://github.com/vfarcy/nodebeginner/blob/master/server.js Server
var http = require("http");
var url = require("url");

function start(route, handle) {
  function onRequest(request, response) {
    var pathname = url.parse(request.url).pathname;
    console.log("Requête reçue pour le chemin " + pathname + ".");
    route(handle, pathname, response, request);
  }

  http.createServer(onRequest).listen(8888);
  console.log("Démarrage du serveur.");
}

exports.start = start;
```