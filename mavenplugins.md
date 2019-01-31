
## Maven Plugins


* <a href="https://maven.apache.org/download.cgi" target="_blank">**Maven download**</a>

**Creating a project:**

_mvn archetype:generate -DgroupId=com.mycompany.app -DartifactId=my-app -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.4 -DinteractiveMode=false_


**Build project:**

_mvn package_

**Test project**

_java -cp target/my-app-1.0-SNAPSHOT.jar com.mycompany.app.App_

___

## Pom files Maven

**Creating Documentation for the Project:**

a) Add this section to your pom-file, just above the properties section.

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


b) Generate the site info using Maven like this: mvn site
c) Navigate into target→ site→ and double-click the project-info.html file to see the generated information. Make sure that you can find the Javadoc API documentation.

d) Use this <a href="https://maven.apache.org/ref/3.6.0/maven-model/maven.html" target="_blank">**link**</a> and add the necessary  fields to your pom-file to include, as a minimum, the following in the report: name, description, list of developers (name+email), the ciManagement system used (Travis)

___

**Running integration tests with Maven**

* maven-surefire-plugin

\*<plugin>\*
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

* maven-failsafe-plugin

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


* Embeded Maven test Plugin

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

* Plugin for Netbeans or Remote Tomcat Server

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














