# WEBSERVER/LINUX
 



### **D I G I T A L O C E A N**
1. Klik på **_CREATE_**
2. Klik på **_DROPLETS - Create Cloud Servers_**
3. Klik på **_CentOS_ - version 6.9x32**
4. Klik på **_$5/mo_**
5. Klik på **_Amsterdam_** (2 eller 3 er ligegyldigt)
6. Kald din Droplet noget kort og præcist nederst på siden under **_Choose a hostname_**


### **P U T T Y**
1. Åben **_PUTTY_**
2. Indsæt IP-adresse (findes på mail/under Droplets på DigitalOcean) 
3. Giv den et navn
4. Klik "ja" til "Putty Security Alert"
5. Brugernavn (findes på mail) er: **_"ROOT"_**
6. Password (findes på mail) kopieres og sættes ind med højreklik.
7. Sæt password ind igen.
8. Lav nyt password.

--- 

### 1. I N S T A L L E R **_NANO_**

> yum install nano

---

### 2. I N S T A L L E R MySQL

> yum install mysql-server

**Start/stop/restart**

> service mysqld start/stop/restart

**Konfigurer MySQL**

> sudo /usr/bin/mysql_secure_installation

---

### 3. I N S T A L L E R Node.js

> yum install epel-release

> yum install nodejs

> yum install npm

> npm install -g n

--- 

**Opdater nodejs**

> n lts
> n

**(Genstart linux)**

---

### 4. I N S T A L L E R PM2
_PM2 er en process manager til Node.js applikationer_

> npm install -g pm2

**Kør PM2 ved startup**

> pm2 startup

---

### 5. I N S T A L L E R Git

> yum install git

---

**Konfiguration**

> git config --global user.name "Dit navn"
> git config --global user.email "din@email.dk"

**Tjek konfigurationen**

> nano ~/.gitconfig

---

### 6. O P R E T  E T  N Ø G L E S Æ T  T I L  A T  L O G G E  I N D  P Å  G I T H U B
_Opret nøglesæt_

> ssh-keygen -t rsa


**Åbn den offentlige nøgle**

> nano ~/.ssh/id_rsa.pub

Kopier indholdet af den offentlige nøgle til GitHub -> **Settings** -> **SSH** and **GPG keys** -> **New SSH key**

---

### 7. Opret en mappe til applikation

> mkdir ~/www

**Naviger ind i mappen**

> cd ~/www

---

### 8. Klon repository fra GitHub

> git clone git@github.com:brugernavn/repository

**Når jeg har en opdatering, skal jeg lave et pull**

> git pull git@github.com:brugernavn/repository

---

---

### **YES or NO**
Disallow root login remotely - NO!

Remove test database - YES!

Skriv "cat ~/.ssh/id_rsa.pub" i stedet for "nano ~/.ssh/id_rsa.pub"








