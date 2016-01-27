
1. Steps to set up swagger-ui server:
-------------------------------------

* git clone https://github.com/swagger-api/swagger-ui.git
* docker build -t swagger-ui-builder .
* docker run -p host_vm_ip:80:8080 swagger-ui-builder /bin/sh
* edit url in dist/index.html

          $(function () {
              var url = window.location.search.match(/url=([^&]+)/);
              if (url && url.length > 1) {
                  url = decodeURIComponent(url[1]);
              } else {
                  url = "http://x.x.x.x/nimbula.json";  # this is where need edit.
          }

* create dist/nimibula.json
* start up web server

          ./node_modules/gulp/bin/gulp.js serve

the swagger-ui(index.html) url will be : http://x.x.x.x/ and the json url will be: http://x.x.x.x/nimbula.json.
Refer to [Setting_up_Swagger_UI_for_a_development_environment](https://www.ibm.com/developerworks/community/blogs/5e15a5a7-d4d6-4880-bd9c-e6819061a832/resource/Setting_up_Swagger_UI_for_a_development_environment.pdf?lang=en)

2. How to fix cors issue
------------------------

refer to [Run Swagger Editor in a browser that ignores HTTP access control](https://github.com/swagger-api/swagger-editor/blob/master/docs/cors.md)

