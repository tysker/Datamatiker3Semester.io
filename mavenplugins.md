[**HOME**](index.md)    [**INFO**](gruppe.md)   [**PLUGINS**](mavenplugins.md)    [**TEK**](tek.md) 


## Get Started


* <a href="https://maven.apache.org/download.cgi" target="_blank">**Maven download**</a>

**Creating a project:**

_mvn archetype:generate -DgroupId=com.mycompany.app -DartifactId=my-app -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.4 -DinteractiveMode=false_


**Build project:**

_mvn package_

**Test project**

_java -cp target/my-app-1.0-SNAPSHOT.jar com.mycompany.app.App_

___

## Plugins Maven

**Creating Documentation for the Project:**

a) Add this section to your pom-file, just above the properties section.

* <a href="https://docs.google.com/document/d/1C7_n6UIj_yp6HwWsPGRsn08sP0-iuXQR8fbazT2DZ68/edit" target="_blank">**Plugin**</a>

b) Generate the site info using Maven like this: mvn site
c) Navigate into target→ site→ and double-click the project-info.html file to see the generated information. Make sure that you can find the Javadoc API documentation.

d) Use this <a href="https://maven.apache.org/ref/3.6.0/maven-model/maven.html" target="_blank">**link**</a> and add the necessary  fields to your pom-file to include, as a minimum, the following in the report: name, description, list of developers (name+email), the ciManagement system used (Travis)

___

**Running integration tests with Maven**

* maven-surefire-plugin

* <a href="https://docs.google.com/document/d/13o2L2d8pNr58tfD1meQYaGVHxD8ESdjsQUrud-hEQiI/edit" target="_blank">**Plugin**</a>

___

* maven-failsafe-plugin

* <a href="https://docs.google.com/document/d/13o2L2d8pNr58tfD1meQYaGVHxD8ESdjsQUrud-hEQiI/edit" target="_blank">**Plugin**</a>

___


* Embeded Maven test Plugin

* <a href="https://docs.google.com/document/d/12D4fs3q6UOfZK1G4ytP6xeKelMpN_pl5STLsOdUYfHg/edit" target="_blank">**Plugin**</a>

___

* Plugin for Netbeans or Remote Tomcat Server

* <a href="https://docs.google.com/document/d/1T4P2xCNQD544kS2F_o5zuxr2s9UlJa2r3T4RjIjTxWE/edit" target="_blank">**Plugin**</a>














