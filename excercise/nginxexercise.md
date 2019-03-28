[HOME](../index.md)


## Nginx excercise


* **What is the purpose on Nginx (a reverse proxy) as used in this week?**

_The purpose of an reversed proxy is that all requests coming in on port 80 will face requirements for communication through https before being forwarded to the tomcat server on port 8080._


* **What is the purpose of a ssl-certificate, and for your certificate answer the following questions?**

_The primary reason why we use an ssl-certificate is to keep sensitive information sent across the network encrypted, so only the intended receiver can access and read the information._

  * **Who is your certificate issued to?**
  
  _The ssl-certificate is issued to my domain  joergoertel.com www.joergoertel.com_
  
  * **What is the expiry date for your certificate?**
  
  _Expiry Date: 2019-05-08 17:13:17+00:00 (VALID: 89 days)_
  
  * **Who/what guarantees that your certificate is valid and not a certificate from a “man in the middle”?**
  
  _**????????????????????????**_
  
  * **What is the value of the public key, contained in your certificate?**
  
  _It is to be found in the folder: Certificate Path: /etc/letsencrypt/live/joergoertel.com/fullchain.pem_
