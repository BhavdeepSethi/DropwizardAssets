DropwizardAssets
================

You might want to serve some static content with Dropwizard. You may want to keep this content separate from the jar so that you don't have to build the entire project everytime you makes changes to these static files.

One use case might be having a rest api being served by Dropwizard. Now, you develop a console over it and want it to be served by the same jetty container. 

You can do this by using this plugin:
https://github.com/bazaarvoice/dropwizard-configurable-assets-bundle

A lot of people had difficulty using this plugin so on request, here is a sample project that serves static content outside the jar with Dropwizard.

To see this in action: 

1) Run "mvn package"

2) Run "java -jar target/DropwizardAssets-1.0-SNAPSHOT.jar server config/assets-example.yml"

3) Open your browser, go to "http://localhost:8080/v1/hello-world" 
    This is the resource file being served from the jar by Dropwizard. 
    
4) Create a file in /var/www/ called index.html You can change the "/var/www/" to any absolute file path. Just make the changes in config/assets-example.yml file. 

5) Open your browser, go to "http://localhost:8080/sample/index.html".
    This static file is being served outside the jar by Dropwizard.

