[**HOME**](index.md)


**Maven Plugins**

* A Maven plugin is a group of goals. However, these goals aren’t necessarily all bound to the same phase.
* A goal is a "unit of work" in Maven (You find the goals for each plugin in the link "Complete List of Plugins on Apache Maven Site")

For example, here’s a simple configuration of the Maven Failsafe plugin which is responsible for running integration tests:
![alt text](plugins.jpg "Plugins")

As we can see, the Failsafe plugin has two main goals configured here:

* integration-test: run integration tests
* verify: verify all integration tests passed

 **To list all goals in a specific plugin:**
 
 _mvn <PLUGIN>:help_
  
**To run a specific goal, without executing its entire phase (and the preceding phases)**

_mvn <PLUGIN>:<GOAL>_

**HINT!**

* To get goal and information about a plugin, write in GitBash follwing command:

_mvn help:describe -Dplugin=pluginName_

_**example:** mvn help:describe -Dplugin=archetype_


![alt text](goal.jpg "Plugins Goals")

## Maven consist of several core plugins:
* JAR plugin (which creates the JAR, or Java Archive files.)
* Compiler Plugin (which contains goals for compiling source code and unit tests.)
* Surefire plugin ( which is used for executing unit tests and generating reports.)
* Create custom plugins (A custom plugin can be written in Java, or a plugin can be written in any number of languages, including Ant, Groovy, Bean, Ciao or Ruby.)
* <a href="https://maven.apache.org/plugins/index.html" target="_blank">**Complete List of Plugins on Apache Maven Site**</a>


___

* **documentation-plugin**

* <a href="https://docs.google.com/document/d/1C7_n6UIj_yp6HwWsPGRsn08sP0-iuXQR8fbazT2DZ68/edit?usp=sharing" target="_blank">**Plugin**</a>

* **maven-surefire-plugin**

* <a href="https://docs.google.com/document/d/13o2L2d8pNr58tfD1meQYaGVHxD8ESdjsQUrud-hEQiI/edit?usp=sharing" target="_blank">**Plugin**</a>

___

* **maven-failsafe-plugin**

* <a href="https://docs.google.com/document/d/13o2L2d8pNr58tfD1meQYaGVHxD8ESdjsQUrud-hEQiI/edit?usp=sharing" target="_blank">**Plugin**</a>

___


* **Embeded Maven test Plugin**

* <a href="https://docs.google.com/document/d/12D4fs3q6UOfZK1G4ytP6xeKelMpN_pl5STLsOdUYfHg/edit?usp=sharing" target="_blank">**Plugin**</a>

___

* **Plugin for Netbeans or Remote Tomcat Server**

* <a href="https://docs.google.com/document/d/1T4P2xCNQD544kS2F_o5zuxr2s9UlJa2r3T4RjIjTxWE/edit?usp=sharing" target="_blank">**Plugin**</a>














