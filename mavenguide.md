[**HOME**](index.md)


## Get Started


* <a href="https://maven.apache.org/download.cgi" target="_blank">**Maven download**</a>

**Creating a project:**

You will need somewhere for your project to reside, create a directory somewhere and start a shell in that directory. On your command line, execute the following Maven goal:

_mvn archetype:generate -DgroupId=com.mycompany.app -DartifactId=my-app -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.4 -DinteractiveMode=false_

**Build project:**

_mvn package_

**Test project**

You may test the newly compiled and packaged JAR with the following command:

_java -cp target/my-app-1.0-SNAPSHOT.jar com.mycompany.app.App_

**Clean Project**

This command will clean the project, copy dependencies, and package the project (executing all phases up to package, of course).

_mvn clean dependency:copy-dependencies package_

**Generating Site**

This phase generates a site based upon information on the project's pom. You can look at the documentation generated under target/site.

_mvn site_

**Maven Phases**
* **validate:** validate the project is correct and all necessary information is available
* **compile:** compile the source code of the project
* **test:** test the compiled source code using a suitable unit testing framework. These tests should not require the code be packaged or deployed
* **package:** take the compiled code and package it in its distributable format, such as a JAR.
* **integration-test:** process and deploy the package if necessary into an environment where integration tests can be run
* **verify:** run any checks to verify the package is valid and meets quality criteria
* **install:** install the package into the local repository, for use as a dependency in other projects locally
* **deploy:** done in an integration or release environment, copies the final package to the remote repository for sharing with other   developers and projects.

There are two other Maven lifecycles of note beyond the default list above. They are

* **clean:** cleans up artifacts created by prior builds
* **site:** generates site documentation for this project

Phases are actually mapped to underlying goals. The specific goals executed per phase is dependant upon the packaging type of the project. For example, package executes jar:jar if the project type is a JAR, and war:war if the project type is - you guessed it - a WAR.

An interesting thing to note is that phases and goals may be executed in sequence.
___

## Plugins Maven

**Creating Documentation for the Project:**

a) Add this section to your pom-file, just above the properties section.

* <a href="https://docs.google.com/document/d/1C7_n6UIj_yp6HwWsPGRsn08sP0-iuXQR8fbazT2DZ68/edit" target="_blank">**Plugin**</a>

b) Generate the site info using Maven like this: mvn site
c) Navigate into target→ site→ and double-click the project-info.html file to see the generated information. Make sure that you can find the Javadoc API documentation.

d) Use this <a href="https://maven.apache.org/ref/3.6.0/maven-model/maven.html" target="_blank">**link**</a> and add the necessary  fields to your pom-file to include, as a minimum, the following in the report: name, description, list of developers (name+email), the ciManagement system used (Travis)

