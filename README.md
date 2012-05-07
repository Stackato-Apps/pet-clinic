Pet clinic Sample
=============

This is a Java sample using the Spring framework and a MySQL service. 

[http://static.springsource.org/docs/petclinic.html](http://static.springsource.org/docs/petclinic.html)

This application uses a [java buildpack](https://github.com/heroku/heroku-buildpack-java).

The java buildpack allows to download dependencies, build and run the application directly on the server. You do not need to 
build the application before pushing it on Stackato.
It uses [Jetty](http://jetty.codehaus.org/jetty/). Jetty is a lightweight Java application server which includes a Jetty Runner jar. 
Therefore, the Java Application can be run directly from the java command and can be passed a war file to load right 
on the command line. An example of this would be:

	java -jar jetty-runner.jar application.war

As it is a Heroku java buildpack, the execution is declared in the Procfile file:

	web:	 java $JAVA_OPTS -jar target/dependency/jetty-runner.jar --port $PORT target/*.war

Deploying the Application to Stackato
-------------------------

To deploy to stackato:

    stackato push -n

The application will download dependencies. Then it will be built and run.
You can view the application at the 'Application Deployed URL'.


Running the Application locally
------------------------

This application uses the DATABASE_USE variable to get the database informations.
To run the application locally, set the DATABASE_URL variable in your local environment to point to your local mysql database:

	export DATABASE_URL=mysql://user:password@localhost/myapp

To build the application, make sure you have [Maven](http://maven.apache.org/ "Maven") installed.
Then, *cd* into the root directory and execute:

	mvn clean package

If you do not want to set up a local database, you can skip the test and buid the application with:

	mvn clean package -Dmaven.test.skip=true

That will create the *petclinic.war* file in the 'target' directory.
