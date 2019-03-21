[**HOME**](/index.md)


## Get Started


* <a href="https://maven.apache.org/download.cgi" target="_blank">**Maven download**</a>

**Creating a project:**

You will need somewhere for your project to reside, create a directory somewhere and start a shell in that directory. On your command line, execute the following Maven goal:

_mvn archetype:generate -DgroupId=**com.default** -DartifactId=**NameOfProject** -DarchetypeArtifactId=**maven-archetype-quickstart** -DarchetypeVersion=**1.4** -DinteractiveMode=**false**_

* <a href="https://maven.apache.org/archetypes/index.html" target="_blank">**Maven Archtypes**</a>

**HINT!** : If you leave out -DarchetypeVersion=1.4, Maven automatically creates the newest version in the POM file.

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




