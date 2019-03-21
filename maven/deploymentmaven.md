[**HOME**](/index.md)



## Deployment with Maven on a remote Tomcat Server


**1. Create an admin user for Tomcat, and assign the necessary roles**

* Open /etc/tomcat8/tomcat-users.xml with nano as given below:

_sudo nano /etc/tomcat8/tomcat-users.xml_

* Insert the following after line 21 in the file – please use your own password!
  * The manager-gui role will allow you to add war-files using Tomcat’s  “Web Application Manager”. The manager-script role will allow you to upload war-files using Maven

_\<role rolename="manager-gui"/\>_

_\<role rolename="manager-script"/\>_

_\<user name="admin" password="XXX" roles="manager-gui,manager-script"/\>_

* Save the file
* Restart the Tomcat Server:   

_service tomcat8 restart_

**2. Deploy to a remote Tomcat Server**

Insert the profile given below to your pom file and give it the id (can also be different)deployremote, and fill in the details for your remote server.

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


* Verify that you can deploy like this: 

**mvn tomcat7:deploy -Pdeployremote**

* This does unfortunately not execute our integration test since they are “controlled” by the test-profile. Run both like this: 

**mvn verify -Ptest tomcat7:deploy -Pdeployremote**
