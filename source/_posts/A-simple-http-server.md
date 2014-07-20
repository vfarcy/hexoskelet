title: 'A simple http server'
date: 2014-07-20 17:59:18
tags:
---

``` js A simple http server
var http = require("http");

http.createServer(function(request, response) {
  response.writeHead(200, {"Content-Type": "text/plain"});
  response.write("Hello World");
  response.end();
}).listen(8888);
}

exports.start = start;
```