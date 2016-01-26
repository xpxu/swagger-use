1. Steps to set up swagger-ui server:
-------------------------------------

1. git clone https://github.com/swagger-api/swagger-ui.git
2. docker build -t swagger-ui-builder .
3. docker run -p host_vm_ip:80:8080 swagger-ui-builder /bin/sh
4. edit url in dist/index.html
5. create dist/nimibula.json
6. ./node_modules/gulp/bin/gulp.js serve
7. the swagger-ui(index.html) url will be : http://x.x.x.x/ and 
the json url will be: http://x.x.x.x/nimbula.json

2. How to fix cors issue
------------------------

refer to "Run Swagger Editor in a browser that ignores HTTP access control" in 
https://github.com/swagger-api/swagger-editor/blob/master/docs/cors.md


3. details about edit url in dist/index.html in 5 of #1
-----------------------------------------------

    $(function () {
    var url = window.location.search.match(/url=([^&]+)/);
    if (url && url.length > 1) {
      url = decodeURIComponent(url[1]);
    } else {
      url = "http://x.x.x.x/nimbula.json";  # this is where need edit.
    }
