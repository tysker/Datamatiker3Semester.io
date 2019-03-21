[**HOME**](/index.md)

**Maven Plugins**

## Maven consist of several core plugins:
* JAR plugin (which creates the JAR, or Java Archive files.)
* Compiler Plugin (which contains goals for compiling source code and unit tests.)
* Surefire plugin ( which is used for executing unit tests and generating reports.)
* Create custom plugins (A custom plugin can be written in Java, or a plugin can be written in any number of languages, including Ant, Groovy, Bean, Ciao or Ruby.)
* <a href="https://maven.apache.org/plugins/index.html" target="_blank">**Complete List of Plugins on Apache Maven Site**</a>

**HINT!**

* To get goal and information about a plugin, write in GitBash follwing command:

_mvn help:describe -Dplugin=pluginName_

_**example:** mvn help:describe -Dplugin=archetype_

___


* **documentation-plugin**

      <reporting>
          <plugins>
            <plugin>
              <groupId>org.apache.maven.plugins</groupId>
              <artifactId>maven-javadoc-plugin</artifactId>
              <version>3.0.1</version>
              <configuration>
                <show>public</show>
              </configuration>
            </plugin>
          </plugins>
      </reporting>


* **maven-surefire-plugin**
 
       <plugin>
           <groupId>org.apache.maven.plugins</groupId>
           <artifactId>maven-surefire-plugin</artifactId>
           <version>2.12.1</version>
           <configuration>
              <excludes>
                 <exclude>**/integrationtests/*</exclude>
              </excludes>
           </configuration>
       </plugin>


___

* **maven-failsafe-plugin**

       <plugin>
          <groupId>org.apache.maven.plugins</groupId>
          <artifactId>maven-failsafe-plugin</artifactId>
          <version>2.12.4</version>
          <configuration>
            <includes>
              <include>**/integrationtests/*</include>
            </includes>
          </configuration>
          <executions>
            <execution>
              <goals>
                <goal>integration-test</goal>
                <goal>verify</goal>
              </goals>
            </execution>
          </executions>
       </plugin>


___


* **Embeded Maven test Plugin**

      <plugin>  
         <groupId>org.apache.tomcat.maven</groupId>

         <artifactId>tomcat7-maven-plugin</artifactId>

         <version>2.2</version>

         <configuration>  
           <path>/</path>
           <port>7777</port>
         </configuration>
         <executions>
           <execution>
             <id>start-tomcat</id>
             <phase>pre-integration-test</phase>
             <goals>
               <goal>run</goal>
             </goals>
             <configuration>
               <fork>true</fork>
             </configuration>
           </execution>
           <execution>
             <id>stop-tomcat</id>
             <phase>post-integration-test</phase>
             <goals>
               <goal>shutdown</goal>
             </goals>
           </execution>
         </executions>
      </plugin>


___

* **Plugin for Netbeans or Remote Tomcat Server**

      <profile>
        <id>deploylocal</id>
        <build>
          <plugins>
            <plugin>  
              <groupId>org.apache.tomcat.maven</groupId>
              <artifactId>tomcat7-maven-plugin</artifactId>
              <version>2.2</version>
               <configuration>
               <url>http://localhost:8084/manager/text</url>
               <server>TomcatServer</server>
               <path>/NameToDeployUnder</path>
               <username>XXX_USER</username>
               <password>XXX_PASSWORD</password>
               <update>true</update>
              </configuration>
            </plugin>
          </plugins>
        </build>
      </profile>

____


**Maven Plugins**

* A Maven plugin is a group of goals. However, these goals aren’t necessarily all bound to the same phase.
* A goal is a "unit of work" in Maven.

For example, here’s a simple configuration of the Maven Failsafe plugin which is responsible for running integration tests:

      <plugin>
          <artifactId>maven-failsafe-plugin</artifactId>
          <version>2.21.0</version>
          <executions>
              <execution>
                  <goals>
                      <goal>integration-test</goal>
                      <goal>verify</goal>
                  </goals>
                  <configuration>
                      ...
                  </configuration>
              </execution>
          </executions>
      </plugin>

As we can see, the Failsafe plugin has two main goals configured here:

* integration-test: run integration tests
* verify: verify all integration tests passed

 **To list all goals in a specific plugin:**
 
 _mvn \<PLUGIN\>:help_
  
**To run a specific goal, without executing its entire phase (and the preceding phases)**

_mvn \<PLUGIN\>:\<GOAL\>_
















