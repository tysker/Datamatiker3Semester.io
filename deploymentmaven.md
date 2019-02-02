[**HOME**](index.md)



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

* <a href="https://docs.google.com/document/d/1T4P2xCNQD544kS2F_o5zuxr2s9UlJa2r3T4RjIjTxWE/edit?usp=sharing" target="_blank">**Plugin**</a>

* Verify that you can deploy like this: _mvn tomcat7:deploy -Pdeployremote_

* This does unfortunately not execute our integration test since they are “controlled” by the test-profile. Run both like this: 

_mvn verify -Ptest tomcat7:deploy -Pdeployremote_
