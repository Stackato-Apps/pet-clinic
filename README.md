Spring Sample
=============

This is a Java sample using the Spring framework and a MySQL service. This application uses a java
buildpack.


Database configuration
----------------------

As this example uses a java heroku buildpack, the database configuration requires the environment variable [DATABASE_URL].
To run the application locally, set the DATABASE_URL variable in your local environment to point to your local mysql database.

For example : export DATABASE_URL=mysql://user:password@localhost/myapp


Building the Application
------------------------

First, set the DATABASE_URL (required for test):

	export DATABASE_URL=mysql://user:password@localhost/myapp

To build the application, make sure you have [Maven](http://maven.apache.org/ "Maven") installed.
Then, *cd* into the root directory and execute:

	mvn clean package

If you do not want to set up a local database, you can skip the test with:

	mvn clean package -Dmaven.test.skip=true

That will create the *petclinic.war* file in the 'target' directory.

Deploying the Application
-------------------------

To deploy to stackato:

    stackato push -n

You can view the application at the 'Application Deployed URL'.
