helloworld-singleton: Helloworld Using a Singleton EJB
======================================================
Author: Serge Pagop  
Level: Beginner  
Technologies: EJB, Singleton  
Summary: Demonstrates the use of an EJB 3.1 Singleton Session Bean, instantiated once, maintaining state for the life of the session  
Target Product: EAP  
Product Versions: EAP 6.1, EAP 6.2  
Source: <https://github.com/jboss-developer/jboss-eap-quickstarts/>  

What is it?
-----------

This quickstart demonstrates the use of an *EJB 3.1 Singleton Bean* in Red Hat JBoss Enterprise Application Platform.

System requirements
-------------------

The application this project produces is designed to be run on Red Hat JBoss Enterprise Application Platform 6.1.

All you need to build this project is Java 6.0 (Java SDK 1.6) or later, Maven 3.0 or later.

 
Configure Maven
---------------

If you have not yet done so, you must [Configure Maven](https://github.com/jboss-developer/jboss-developer-shared-resources/blob/master/guides/CONFIGURE_MAVEN.md#configure-maven-to-build-and-deploy-the-quickstarts) before testing the quickstarts.


Start the JBoss EAP Server
-------------------------

1. Open a command prompt and navigate to the root of the JBoss EAP directory.
2. The following shows the command line to start the server:

        For Linux:   EAP_HOME/bin/standalone.sh
        For Windows: EAP_HOME\bin\standalone.bat

 
Build and Deploy the Quickstart
-------------------------

_NOTE: The following build command assumes you have configured your Maven user settings. If you have not, you must include Maven setting arguments on the command line. See [Build and Deploy the Quickstarts](../README.md#build-and-deploy-the-quickstarts) for complete instructions and additional options._

1. Make sure you have started the JBoss EAP server as described above.
2. Open a command prompt and navigate to the root directory of this quickstart.
3. Type this command to build and deploy the archive:

        mvn clean install jboss-as:deploy

4. This will deploy `target/jboss-helloworld-singleton.war` to the running instance of the server.

 
Access the application 
---------------------

The application will be running at the following URL: <http://localhost:8080/jboss-helloworld-singleton>.

This example demonstrates a singleton session bean that maintains state information for 2 variables: "Increment A" and "Increment B". 

A counter is incremented when you click on the link to the variable name. If you close and restart your browser, or if you have multiple browsers, you can see that the counter always increments the last value. These values are maintained until you restart the server. 

To test the singleton bean, click on either "Increment A" or "Increment B". The result page will give you the current value of the variable.


Undeploy the Archive
--------------------

1. Make sure you have started the JBoss EAP server as described above.
2. Open a command prompt and navigate to the root directory of this quickstart.
3. When you are finished testing, type this command to undeploy the archive:

        mvn jboss-as:undeploy


Run the Quickstart in JBoss Developer Studio or Eclipse
-------------------------------------
You can also start the server and deploy the quickstarts from Eclipse using JBoss tools. For more information, see [Use JBoss Developer Studio or Eclipse to Run the Quickstarts](https://github.com/jboss-developer/jboss-developer-shared-resources/blob/master/guides/USE_JDBS.md#use-jboss-developer-studio-or-eclipse-to-run-the-quickstarts) 


Debug the Application
------------------------------------

If you want to debug the source code or look at the Javadocs of any library in the project, run either of the following commands to pull them into your local repository. The IDE should then detect them.

        mvn dependency:sources
        mvn dependency:resolve -Dclassifier=javadoc
