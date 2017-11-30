# WEBSERVER/LINUX
 



### **DIGITALOCEAN.COM**
1. Klik på **_CREATE_**
2. Klik på **_DROPLETS - Create Cloud Servers_**
3. Klik på **_CentOS_ - version 6.9x32**
4. Klik på **_$5/mo_**
5. Klik på **_Amsterdam_** (2 eller 3 er ligegyldigt)
6. Kald din Droplet noget kort og præcist nederst på siden under **_Choose a hostname_**


### **PUTTY**
1. Åben **_PUTTY_**
2. Indsæt IP-adresse (findes på mail/under Droplets på DigitalOcean) 
3. Giv den et navn
4. Klik "ja" til "Putty Security Alert"
5. Brugernavn (findes på mail) er: **_"ROOT"_**
6. Password (findes på mail) kopieres og sættes ind med højreklik.
7. Sæt password ind igen.
8. Lav nyt password.

--- 

#### Installer **_NANO_**

> yum install nano


#### Installer MySQL

> yum install mysql-server

#### Start/stop/restart

> service mysqld start/stop/restart


Disallow root login remotely - NO!
Remove test database - YES!
