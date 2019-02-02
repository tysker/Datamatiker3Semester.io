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

**2. Setting up profiles**

First, you should add a new section to your pom-file, just below your build-section as sketched below:

\<profiles\>
  ...
\</profiles\>

* A profile for integration-tests (emeded server)

Add a new profile to your pom file:

* <a href="https://docs.google.com/document/d/12D4fs3q6UOfZK1G4ytP6xeKelMpN_pl5STLsOdUYfHg/edit?usp=sharing" target="_blank">**Plugin**</a>


