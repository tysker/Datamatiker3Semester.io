[**HOME**](index.md)



## Deployment with Maven on a remote Tomcat Server
hallo

1. Create an admin user for Tomcat, and assign the necessary roles

* Open /etc/tomcat8/tomcat-users.xml with nano as given below:

_sudo nano /etc/tomcat8/tomcat-users.xml_

Insert the following after line 21 in the file – please use your own password!

_\<role rolename="manager-gui"/\>_

_\<role rolename="manager-script"/\>_

_\<user name="admin" password="XXX" roles="manager-gui,manager-script"/\>_

* Save the file
* Restart the Tomcat Server:   

_service tomcat8 restart_
