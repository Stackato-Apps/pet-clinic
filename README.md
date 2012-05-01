Pet clinic Sample
=============

This is a Java sample using the Spring framework and a MySQL service. This application uses a java
buildpack.


Deploying the Application to Stackato
-------------------------

To deploy to stackato:

    stackato push -n

You can view the application at the 'Application Deployed URL'.


Running the Application locally
------------------------

To run the application locally, set the DATABASE_URL variable in your local environment to point to your local mysql database:

	export DATABASE_URL=mysql://user:password@localhost/myapp

To build the application, make sure you have [Maven](http://maven.apache.org/ "Maven") installed.
Then, *cd* into the root directory and execute:

	mvn clean package

If you do not want to set up a local database, you can skip the test and buid the application with:

	mvn clean package -Dmaven.test.skip=true

That will create the *petclinic.war* file in the 'target' directory.
