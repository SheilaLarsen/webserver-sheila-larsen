# WEBSERVER/LINUX
 



## **D I G I T A L O C E A N**
1. Klik på **_CREATE_**
2. Klik på **_DROPLETS - Create Cloud Servers_**
3. Klik på **_CentOS_ - version 6.9x32**
4. Klik på **_$5/mo_**
5. Klik på **_Amsterdam_** (2 eller 3 er ligegyldigt)
6. Kald din Droplet noget kort og præcist nederst på siden under **_Choose a hostname_**


## **P U T T Y**
1. Åben **_PUTTY_**
2. Indsæt IP-adresse (findes på mail/under Droplets på DigitalOcean) 
3. Giv den et navn
4. Klik "ja" til "Putty Security Alert"
5. Brugernavn (findes på mail) er: **_"ROOT"_**
6. Password (findes på mail) kopieres og sættes ind med højreklik.
7. Sæt password ind igen.
8. Lav nyt password.

(Hvis jeg skal ind på en allerede eksisterende droplet - skal jeg huske at tænde den)
---

--- 

### 1. Installer **_NANO_**
```
 yum install nano
```
---

### 2. Installer **_MySQL_**
```
yum install mysql-server
```
**Start/stop/restart**
```
service mysqld start/stop/restart
```
**Konfigurer MySQL**
```
sudo /usr/bin/mysql_secure_installation
```
---

### 3. Installer **_Node.js_**
```
yum install epel-release
```
```
yum install nodejs
```
```
yum install npm
```
```
npm install -g n
```

**Opdater nodejs**
```
n lts
```
```
n
```
**(Genstart linux)**

---

### 4. Installer **_PM2_**
_PM2 er en process manager til Node.js applikationer_
```
npm install -g pm2
```
**Kør PM2 ved startup**
```
pm2 startup
```
---

### 5. Installer **_Git_**
```
yum install git
```

**Konfiguration**

```
git config --global user.name "Dit navn"
```
```
git config --global user.email "din@email.dk"
```
**Tjek konfigurationen**

```
nano ~/.gitconfig
```
---

### 6. Oret et nøglesæt til at logge ind på Github
_Opret nøglesæt_

```
ssh-keygen -t rsa
```

**Åbn den offentlige nøgle**

```
nano ~/.ssh/id_rsa.pub
```
Kopier indholdet af den offentlige nøgle til GitHub -> **Settings** -> **SSH** and **GPG keys** -> **New SSH key**

---

### 7. Opret en mappe til applikation

```
mkdir ~/www
```
**Naviger ind i mappen**

```
cd ~/www
```
---

### 8. Klon repository fra GitHub

```
git clone git@github.com:brugernavn/repository
```
**Når jeg har en opdatering, skal jeg lave et pull**

```
git pull git@github.com:brugernavn/repository
```

### 10. Installer node modules i rod-mappen

```
npm install
```
### 11. Opstart node

```
node app/app.js*
```
---

### YES or NO
Disallow root login remotely - NO!

Remove test database - YES!

Skriv "cat ~/.ssh/id_rsa.pub" i stedet for "nano ~/.ssh/id_rsa.pub"

---

---

## **Log på MySQL fra Linux-serveren** (Gøres for hver nye droplet)

```
service mysqld start
``` 
_Tryk ENTER_

_Skriv password til root-brugeren_

### 1. Giv rootbrugeren lov til at logge ind fra andre adresser end localhost

```
GRANT ALL ON *.* 

(betyder alle databaser/tabeller - dvs., brugeren jeg navngiver 

får alle privilegier på alle databaser/tabeller på MySQL serveren) 

TO 'root'@'%';
```
_Tryk ENTER_

### 2. Sæt et password for "root-brugeren" når der logges på fra andre adresser end localhost
```
SET PASSWORD FOR 'root'@'%' = PASSWORD ('Aliehs1011');
```
_Tryk ENTER_

---

## **W O R K B E N C H** (eksporter/importer database)

1. Åben MySQL Workbench/Start Xamp
2. Klik på localhost-boksen ("continue anyway")
3. Klik på **_server_** -> **_Data Export_** -> Vælg database -> Marker **_Export to Dump Project Folder_** -> Klik på **_Start Export_** ("continue anyway" - skriv evt. password)

4. Luk vindue
(5. Åben stifinder -> Find mappen med database-navn \Documents\dumps\Dump...)
6. Gå tilbage til Workbench
**For at importere det over på Linux bruges MySql Workbench til at forbinde til MySql serveren på Linux maskinen**
7. Tryk på plus
8. Sæt IP fra server ind under **_Hostname:_**
9. Giv den et navn - Klik OK
10. Åben forbindelsen (skriv password)
11. Opret den database der skal importeres data til 
12. Klik på **_Create a new schema in the connected server_**
13. Skriv navnet på databasen -> Klik på **_Apply_** og **_Finish_**
14. Gå op i **__Server__**
15. Find mappen i **_dumps_** - OK
16. **_Start import_** - Opdater.




