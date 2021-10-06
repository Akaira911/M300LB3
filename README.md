# M300LB3

## Inhaltsverzeichnis
1. [Beschreibung](Beschreibung)
2. [DockerBefehle](DockerBefehle)
3. [Reflexion](Reflexion)
4. [Projekt](Projekt)
5. [Apache](Apache)
6. [MySQL](MySQL)
7. [PHP](PHP)
8. [Containerstarten](Containerstarten)
9. [ReflexionEllavan](ReflexionEllavan)
10.[ReflexionMicael](ReflexionMicael)

## Beschreibung
-------------------
### Vagrant
Vagrant ist eine freie Ruby-Anwendung zum Erstellen und Verwalten virtueller Maschinen. Vagrant ermöglicht einfache Softwareverteilung (englisch Deployment) insbesondere in der Software- und Webentwicklung und dient als Wrapper zwischen Virtualisierungssoftware wie VirtualBox, KVM/QEMU, VMware und Hyper-V und Software-Configuration-Management-Anwendungen beziehungsweise Systemkonfigurationswerkzeugen wie Chef, Saltstack und Puppet.
### Visual Studio Code
Visual Studio Code (kurz VS Code) ist ein kostenloser Quelltext-Editor von Microsoft. Visual Studio Code ist plattformübergreifend für die Betriebssysteme Windows, macOS und Linux verfügbar. Visual Studio Code basiert auf dem Framework Electron und ermöglicht u. a. Syntaxhervorhebung, Code-Faltung, Debugging, Autovervollständigung und Versionsverwaltung.
### Virtualbox
VirtualBox ist eine Virtualisierungssoftware des US-amerikanischen Unternehmens Oracle, die ursprünglich von der InnoTek Systemberatung GmbH aus Baden-Württemberg entwickelt wurde. Nach der Übernahme durch Sun Microsystems im Februar 2008 wurde es Sun xVM VirtualBox bezeichnet, da Sun es in sein xVM-Portfolio eingliederte. Sun Microsystems wurde 2010 von Oracle übernommen, das Oracle VM VirtualBox nunmehr ebenfalls in sein VM-Portfolio eingliederte. Die freie Variante behielt jedoch den ursprünglichen Namen.
### VirtualBox 
VirtualBox kann auf den Betriebssystemen FreeBSD, Linux, macOS, OS/2 bzw. eComStation, Solaris, Windows und Genode als Wirtssystem auf x86- (32 Bit) und x86-64-Systemen (64 Bit) eingesetzt werden.
Als Gastsystem können wiederum x86- bzw. x64-Betriebssysteme eingesetzt werden. Für eine Vielzahl an Betriebssystemen werden Treiber, Kernel-Module bzw. -Erweiterungen mitgeliefert; diese stehen bei der Einrichtung einer neuen virtuellen Maschine zur Auswahl.
### Git-Client (Bash)
Bash (auch BASH oder bash), die Bourne-again shell, ist eine freie Unix-Shell unter GPL. Als Shell ist Bash eine Mensch-Maschine-Schnittstelle, die eine Umgebung (englisch environment) bereitstellt, in den zeilenweisen Texteingaben und -ausgaben möglich sind. Letzteres erfolgt über die Befehlszeile, in die Befehle eingetippt und durch Betätigen der Eingabetaste eingegeben werden. 
Bash ist elementarer Bestandteil des unixähnlichen Betriebssystems GNU und gehört zum GNU-Projekt. Auch bei den meisten auf GNU/Linux aufbauenden Betriebssystemen ist Bash die voreingestellte Shell. Darüber hinaus war Bash 3.x von 2003 bis 2019 die voreingestellte Shell in macOS von Apple (10.3–10.14) – wurde allerdings aus lizenzrechtlichen Gründen nie auf Version 4.0 oder höher aktualisiert. 
Der Name Bash ist im Englischen mehrdeutig ([to] bash, [the] bash) und erfuhr im Laufe der Zeit weitere, meist humoristische Bedeutungen.
### Docker
Docker ist eine Freie Software zur Isolierung von Anwendungen mit Hilfe von Containervirtualisierung.
Docker vereinfacht die Bereitstellung von Anwendungen, weil sich Container, die alle nötigen Pakete enthalten, leicht als Dateien transportieren und installieren lassen. Container gewährleisten die Trennung und Verwaltung der auf einem Rechner genutzten Ressourcen. Das beinhaltet laut Aussage der Entwickler: Code, Laufzeitmodul, Systemwerkzeuge, Systembibliotheken – alles was auf einem Rechner installiert werden kann.

### Docker Befehle
-------------------
```
attach Attach local standard input, output, and error streams to a running container
build Build an image from a Dockerfile
commit Create a new image from a container's changes
create Create a new container
diff Inspect changes to files or directories on a container's filesystem
events Get real time events from the server
exec Run a command in a running container
export	Export a container's filesystem as a tar archive
history	Show the history of an image
import	Import the contents from a tarball to create a filesystem image
info	Display system-wide informatio
load	Load an image from a tar archive or STDIN
login	Log in to a Docker registry
logout	Log out from a Docker registry
logs	Fetch the logs of a container 
pause	Pause all processes within one or more containers
ps	List containers
pull	Pull an image or a repository from a registry
push	Push an image or a repository to a registry
rename	Rename a container
rm	Remove one or more containers
rmi	Remove one or more images
run	Run a command in a new container
save	Save one or more images to a tar archive (streamed to STDOUT by default)
start	Start one or more stopped containers
stop	Stop one or more running containers
tag	Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE
unpause	Unpause all processes within one or more containers
update	Update configuration of one or more containers
version	Show the Docker version information
wait	Block until one or more containers stop, then print their exit codes
```
### Erste Erfahrungen
--------------------------
Wir haben damit angefangen via Vagrantfile eine Linux VM aufzusetzen. Nach der Installation haben wir Linux geupdatet:
```
apt-get update
```
Wir haben dann nach Angaben docker.io installiert, um die Dockerbefehle auszuführen.
Dies geht mit folgendem befehl: 
```
sudo apt-get install -y docker.io
```
Später haben wir uns von Herrn Berrnet inspirieren lassen und versucht eine Einfache Website zu kreieren. Dies half uns erste erfahrungen mit Docker zu machen. 
```
From Ubuntu
MAINTAINER Micael Insua <micael.insua@edu.tbz.ch>
Run apt-get update
CMD ["echo", "Hello World"]
```
Die erste Zeile des Codes hollt sich ein Ubuntu Image von docker.com. 

Nachdem das Dockerfile geschrieben war haben wir den Docker aufgebaut und gestartet. 
Dies geht mit folgdenem Code: 
```
sudo docker build -t myimage
sudo docker run myimage
```
### Projekt
------------------
Wir haben versucht eine Web Application Stack mit Docker Container zu erstellen, dieser besteht aus Apache, MySQL, PHP und PhpMyAdmin. Wir haben uns entschieden die Services auf einen eigenen Container laufen zu lassen, da es in der Wirklichkeit von grösserem Nutzen ist. So ist der Stack einfach mit weiteren Diensten erweiterbar. So kann MySQL mit einer anderen SQL Anwendung ausgetauscht werden.
Ich habe mich im Verlauf vom Projekt dazu entschieden das image aus bitnami zu nehemen, da mein Geschäft damit arbeitet und mir bei diesem Projekt als hilfestellung diente.

Für Unser Projekt haben wir eine grosse und spezifische Verzeichnisstruktur erstellt: 
```
dstack
  docker
    apache
      certs
      my_vhost.conf
    mysql
      data
    php
    www
    docker-compose.yml
```
Die gleiche Ordnerstruktur ist oben zu finden. 

Alle Contaienr werden mit Docker Compose gestartet, deshalb haben wir zuerst damit angefangen. Die Datei docker-compose.yml ist unter dstack > docker zu finden. 
```
version: "3"

### MYSQL
services:
  mysql:
    container_name: "dstack-mysql"
    image: bitnami/mysql:5.7
    environment:
      - MYSQL_ROOT_PASSWORD=Dasistkeinpassw0rt
      - MYSQL_USER=admin
      - MYSQL_PASSWORD=Dasistkeinpassw0rt
    ports:
      - '3306:3306'
    volumes:
      - ./docker/mysql/data:/bitnami/mysql/data

  # --- PHP 7.4
  #
  php:
    container_name: "dstack-php"
    image: bitnami/php-fpm:7.4
    depends_on:
      - redis
    volumes:
      - ./docker/www:/app:delegated
      - ./docker/php/php.ini:/opt/bitnami/php/etc/conf.d/php.ini:ro

  # --- Apache 2.4
  #
  apache:
    container_name: "dstack-apache"
    image: bitnami/apache:2.4
    ports:
      - '80:8080'
      - '443:8443'
    depends_on:
      - php
    volumes:
      - ./docker/www:/app:delegated
      - ./docker/apache/my_vhost.conf:/vhosts/myapp.conf:ro
      - ./docker/apache/certs:/certs

  redis:
    container_name: "dstack-redis"
    image: bitnami/redis:6.0
    environment:
      - REDIS_PASSWORD=Dasistkeinpassw0rt

  # --- PhpMyAdmin
  # http://127.0.0.1:81 oder https://127.0.0.1:8143
  # Login mit user root und gesetztes MYSQL_PASSWORD.
  phpmyadmin:
    container_name: "dstack-phpmyadmin"
    image: bitnami/phpmyadmin:latest
    depends_on:
      - mysql
    ports:
      - '81:8080'
      - '8143:8443'
    environment:
      - DATABASE_HOST=host.docker.internal

volumes:
  dstack-mysql:
    driver: local
```
Ausser PhpMyAdmin benutzen alle Dienste ihre Standard-Ports. Alle wichtigen Daten werden in Volumes ausserhalb der Container gespeichert.

### Apache
------------------
Bevor wir mit der Configfile von Apache anfangen konnten mussten wir mit folgendem Code zuerst ein selbst signiertes SSL-Zertifikat generieren und im Ordner ./docker/apache/certs abspeichern: 
```
openssl req -x509 -newkey rsa:4096 -sha256 -nodes -keyout server.key -out server.crt -subj "/CN=dstack.local" -days 3650
```
Im vorhinein wird die Apache-Konfiguration im Ordner apache abgelegt. 
Die Datei sieht nun folgendermassen aus:
```
<VirtualHost *:8080>
  DocumentRoot "/app"
  ProxyPassMatch ^/(.*\.php(/.*)?)$ fcgi://php:9000/app/$1
  <Directory "/app">
    Options Indexes FollowSymLinks
    AllowOverride All
    Require all granted
    DirectoryIndex index.html index.php
  </Directory>
</VirtualHost>

<VirtualHost *:8443>
  SSLEngine on  
  SSLCipherSuite ALL:!ADH:!EXPORT56:RC4+RSA:+HIGH:+MEDIUM:+LOW:+SSLv2:+EXP:+eNULL  
  SSLCertificateFile "/certs/server.crt"  
  SSLCertificateKeyFile "/certs/server.key"  
  DocumentRoot "/app"
  ProxyPassMatch ^/(.*\.php(/.*)?)$ fcgi://php:9000/app/$1
  <Directory "/app">
    Options Indexes FollowSymLinks
    AllowOverride All
    Require all granted
    DirectoryIndex index.html index.php
  </Directory>
</VirtualHost>
```
Um die DAten der Website abzuspeichern erstellen wir noch den Ordner www, welcher in der oberen Hirarchie ersichtlich ist. Für unseren Zweck, reicht die Datei info.php mit folgendem Inhalt:
```
<?php
phpinfo();
?>
```
### MySQL
------------------
Für MySQL haben wir im vorhinein den Ordner data erstellt, welcher nach dem Start des Containers alle von MySQL erzeugten Daten erhaltet.

### PHP
---------
Für die PHP Konfiguration, haben wir folgende Datei erstellt. 
```
display_errors = On
expose_php = off
max_execution_time = 360
max_input_time = 360
memory_limit = 256M
upload_max_filesize = 1G
post_max_size = 1G
opcache.enable = 1
opcache.revalidate_freq = 2
opcache.validate_timestamps = 1
opcache.interned_strings_buffer = 32
opcache.memory_consumption = 256
extension=imagick.so
zend_extension = "/opt/bitnami/php/lib/php/extensions/xdebug.so"
[Xdebug]
xdebug.=1
xdebug.remote_enable=1
xdebug.default_enable=0
xdebug.remote_host=host.docker.internal
xdebug.remote_port=9000
xdebug.remote_connect_back=0
xdebug.profiler_enable=0
xdebug.remote_log="/tmp/xdebug.log"
```
Hier wird die ImageMagick extension aktiviert und zusätzlich noch XDebug konfiguriert.

### Container starten
----------------------
Um alle Container zu starten, muss man in den Ordner, wo sich die docker-compose.yml Datei befindet. In Unserem Falle ist das unter dstack > docker zu finden. Nachdem man mit cd auf das Verzeichnis gewechselt hat muss man folgenden befehl eingeben:
```
docker-compose up -d
```
Wenn man alles richtig konfiguriert hat, kann man im Webbrowser seine Arbeit testen. Dies tut man indem man auf die localhost Adresse zugreift (http://127.0.0.1/) und dann sollte folgendes erscheinen.
![Unbenannt](https://user-images.githubusercontent.com/74959608/136148973-c617cc05-7cae-4021-bdee-66aadae87a91.PNG)

### Frontend / Backend
----------------------
![image](https://user-images.githubusercontent.com/74959608/136082247-cb280c90-4259-43cc-849e-17003bd9d175.png)

### Reflexion Ellavan
----------------------
Der Anfang war schwer für uns. Wir wussten zwar was unser Auftrag war, jedoch nciht wie man dies umsetzen muss. Deshalb entschieden wir uns, dies mit Frau Schmid zu besprechen. Frau Schmid erweis sich als Hilfreich und erklärte uns wie wir vorgehen mussten. Nach einigen Disukusionen mit ihr, begriffen wir endlich was wir machen müssen und konnten so weiter arbeiten. Hin und wieder Halfen wir auch Frau Schmid, da wir ohne ihre Hilfe nich weit gekommen wären. Wir kammen dannach schnell vorwärts, da wir auch die Hilfe des Internets hatten. 
Ich selbst konnte die Dokumentation erstellen. Es war keine grosse Arbeit doch verbrachte ich viel Zeit mit dem, da ich noch nie mit Github eine Dokumentation erstellen musste. Die war für mich eine Herausforderung, da ich vieles nach Googeln musste. Aber hingekrigt haben wir es dennoch. 

### Reflexion Micael
---------------------
Das Projekt empfand ich als schwerer als das Vagrant Projekt. Auch hier hatten wir einen schweren Start, da ich auch nach 3 stündiger Grübelei immer noch nicht verstand wie ich mit so einem dockerfile umgehen muss und wo ich die Dateein ausführen muss. Erst nachdem wir uns mit Frau Schmid zusammensetzten, konnten wir richtig anfangen. Dank ihr verstanden wir auch erst, dass alles auf einer Linux VM gemacht werden muss und nicht auf Bash, dies könnte aber auch uns zu verschulden sein. Bis auf diesen schlechten Start, konnten wir uns dennoch aufrapeln und das Projekt Zeitgemäss beenden. Dies konnten wir nur durch gute Zusammenarbeit erreichen, ich und Herr Pakeerathan haben uns jeweils alles aufgeteilt, so kümmerte ich mich um die Dockerfiles und Herr Pakeerathan um die Dokumentation. 
Es war für mich auch etwas furchteregend als ich sah, dass wir unsere Dokumentation auf Github machen müssen, da ich bis jetzt noch keine Erfahrung mit dieser Platform hatte. Trotzdessen konnte ich mich gut einarbeiten aber dies war auch nicht all zu schwer. 

Es war meine erste Erfahrung mit Docker, weshalb ich mich anfangs an das Internet wandte aber wie erwähnt führte dies nicht direkt zu Resultaten. Ich bekamm meine meiste Hilfe von meinem Betrieb, da die schon bereits damit zu tun hatten, der einzige Unterschied war die verwendete Datenbank, dies sah ich aber nicht als zu gravierend und lies mich drauf ein.
Insgesamt war das Projekt eine gute Erfahrung für mich, dass einzige was anzumerken ist, ist dass wir für mein gefühl zu wenig Zeit für dieses Projekt hatten. Für das Thema Vagrantfile hatten wir einen gesamten Tag mehr, obwohl ich dieses Thema als wengier schwer empfand. Ich hätte mich darüber gefreut, wenn die Abgabetermine umgekehrt währen, also dass wir für Vagrant eine und für Docker zwei Wochen haben. 
