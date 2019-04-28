[**HOME**](../index.md)



# Deployment with Maven on a remote Tomcat Server


## 1. Create an admin user for Tomcat, and assign the necessary roles

* Open **/etc/tomcat8/tomcat-users.xml** with nano as given below:

         sudo nano /etc/tomcat8/tomcat-users.xml

* Insert the following after line 21 in the file – please use your own password!
* The manager-gui role will allow you to add war-files using Tomcat’s  “Web Application Manager”. The manager-script role will allow you to upload war-files using Maven

        <role rolename="manager-gui"/>
        <role rolename="manager-script"/>
        <user name="admin" password="XXX" roles="manager-gui,manager-script"/>

* Save the file
* Restart the Tomcat Server:   

        service tomcat8 restart
   
___


## 2. Deploy to a remote Tomcat Server in a Secure way.

                <plugin>
                <groupId>org.apache.tomcat.maven</groupId>
                <artifactId>tomcat7-maven-plugin</artifactId>
                <version>2.2</version>
                <configuration>
                    <server>TomcatServer</server>
                    <url>${remote.server}</url>
                    <username>${remote.user}</username>
                    <password>${remote.password}</password>
                    <!-- <username>${env.TOMCAT_USER} </username>-->
                    <!--  <password>${env.TOMCAT_PASSWORD}</password>-->
                    <update>true</update>    
                </configuration>


___


## 3. Deploy to a remote Tomcat Server if you include password and username in the pom file.

Insert the profile given below to your pom file and give it an id (can also be different then the one below), and fill in the details for your remote server.

     <profile>
       <id>deployremote</id>
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



* Deploy like this: 

         mvn tomcat7:deploy -Pdeployremote


