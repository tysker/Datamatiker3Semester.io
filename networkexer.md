
**Understanding Basic Network Terms like: IP, TCP/IP, DNS, DHCP and more.**

**Most of these exercises are meant to be answered in text, so write down your replies so you will remember.**

**1.What is your public IP address right now, and how did you find it?**
 * google "what is my ip"
 

**2.What is your private IP address right now (do this both at home and in school), and who/what gave you that address?**
  * schoolIp = 5.179.80.204 = google.com
  * homeIP =
  * LAN (LocalArealNetwork) Ip = 10.50.130.166 = commandPrompt --> ipconfig /all

**3.What’s special about these address ranges?**
10.0.0.0 – 10.255.255.255
172.16.0.0 – 172.31.255.255
92.168.0.0 – 192.168.255.255

**4.What’s special about this ip-address: 127.0.0.1?**
  * Det er en localHostIp.

**5.What kind of service would you expect to find on a server using these ports: 22, 23, 25, 53, 80, 443?**
  * 22 = SSH
  * 23 = TELNET
  * 25 = SMTP
  * 53 = DNS
  * 80 = HTTP
  * 443 = HTTPS

**6.What is the IP address of studypoints.dk and how did you find it?**
  * GitBash or cmp command = nslookup studypoints.dk = 165.227.137.75

**7.If you write https://studypoints.dk in your browser, how did “it” figure out that it should go to the IP address you discovered above?**
  * Browseren spørger DNS-serveren om IP-adressen på https://studypoints.dk, hvis den er kendt på første DNS-server sender den IP-adressen tilbage ellers forespørges på yderligere DNS-serverer indtil IP-adressen er fundet.

**8.Explain shortly the purpose of an ip-address and a port-number and why we need both**
  * Et godt eksempel er, når man taster DNS-adressen da.wikipedia.org ind i browserens adressefelt. Så vil browseren som standard slå DNS-adressen op og få en IP-adresse tilbage. Browseren vil nu forsøge at lave en TCP-forbindelse med IP-adressen og port nr 80 på da.wikipedia.org WWW-server. Svarer serveren, fås en WWW-side i filformatet HTML eller XML. Navnet for internetadresser er URL og den fuldstændige adresse er: http://da.wikipedia.org:80/.

**9.What is your (nearest) DNS server?**
  * Comandprompt command ipconfig /all = 10.3.1.2

**10.What is (conceptually) the DNS system and the purpose with a DNS Server?**
  * DNS er en forkortelse for Domain Name System (Domain Name Server, Domain Name Service). En DNS-server eller navneserver er en server placeret på et IP-baseret datanet, der tager sig af oversættelsen af de navne man normalt arbejder med på Internettet.
  * DNS-servere løser to opgaver. En DNS-server kan oversætte mellem IP-adresser og domænenavne for et begrænset antal domæner eller den kan kontakte andre servere for at få oversat en vilkårlig adresse.

**11.What is your current Gateway, and how did you find it?**
  * Comandprompt command ipconfig /all = 10.50.128.1

**12.What is the address of your current DHCP-Server, and how did you find it?**
  * Comandprompt command ipconfig /all = 10.255.1.9

**13.Explain (conceptually) about the TCP/IP-protocol stack**
  * http://www.technologyuk.net/telecommunications/internet/tcp-ip-stack.shtml

**14.Explain about the HTTP Protocol (the following exercises will go much deeper into this protocol)**
  * HTTP er en protokol der beder en server på TCP-port 80 (med mindre andet er angivet) om specifikke ressourcer. Serveren svarer med HTTP-protokolkode for at angive det overordnede resultat af anmodningen, og derefter typisk selve ressourcen (fx et HTML-dokument eller et billede) eller en fejlbesked.. 

**15.Explain (conceptually) how HTTP and TCP/IP are connected (what can HTTP do, and where does it fit into TCP/IP)**
  * What can HTTP do?
    * HTTP can send request or respond to the client and back
    * HTTP can send data back and forward
  * How HTTP and TCP/IP are connected?
    * HTTP er et protokol som er sendt til webserveren via TCP med en given IP adresse.
