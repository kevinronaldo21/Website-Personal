###### Apache Friends XAMPP (Basispaket) version 1.7.2 ######

  + Apache 2.2.12 (IPV6 enabled)
  + MySQL 5.1.37 (Community Server) mit PBXT engine 1.0.08-rc
  + PHP 5.3.0 + PEAR (PEAR, Mail_Mime, MDB2, Zend)
  + Perl 5.10.0 (Bundle::Apache2, Bundle::Apache::ASP, Bundle::Email, Bundle::DBD::mysql, DBD::SQlite)
  + XAMPP Control Version 2.5.8 (ApacheFriends Edition)
  + XAMPP CLI Bundle 1.6
  + XAMPP Port Check 1.4
  + XAMPP Security 1.1
  + SQLite 2.8.17
  + SQLite 3.6.16
  + OpenSSL 0.9.8k
  + phpMyAdmin 3.2.0.1
  + ADOdb v5.09a
  + FPDF v1.6
  + Zend Framework 1.9 Minimal Package (via PEAR)
  + Mercury Mail Transport System v4.62
  + msmtp 1.4.17 (ein sendmail kompatibler SMTP client)
  + FileZilla FTP Server 0.9.32
  + Webalizer 2.21-02 (mit GeoIP lite)
  + Xdebug 2.0.5 für PHP
  + eAccelerator 0.9.6-rc1 für PHP
  + Ming 0.4.2 für PHP
  + PDF mit pdflib lite v7.0.4p4 für PHP

---------------------------------------------------------------

* System-Voraussetzungen:

  + 128 MB RAM
  + 255 MB freier Speicherplatz
  + Windows 2000, XP (Server 2003), Vista (Server 2008)
  + alle Systeme 32 bit (64 bit nicht getestet)

* SCHNELLINSTALLATION:

[HINWEIS: Auf die obersten Hirachie eines beliebigen Laufwerks bzw. auf dem Wechseldatenträger des USB-Sticks entpacken => E:\ oder W:\. Es entsteht E:\xampp oder W:\xampp.]

Schritt 1: Das Setup mit der Datei "setup_xampp.bat" im XAMPP-Verzeichnis starten. Bemerkung: XAMPP macht selbst keine Einträge in die Windows Registry und setzt auch keine Systemvariablen.

Schritt 2: Starten Sie den Apache mit dem Control Panel (xampp-control.exe) oder wahlweise mit => \xampp\apache_start.bat.
           Stoppen Sie den Apache mit dem Control Panel (xampp-control.exe) oder wahlweise mit => \xampp\apache_stop.bat.

Schritt 3: Starten Sie MySQL mit dem Control Panel (xampp-control.exe) oder wahlweise mit => \xampp\mysql_start.bat.
           Stoppen Sie MySQL mit dem Control Panel (xampp-control.exe) oder wahlweise mit => \xampp\mysql_stop.bat.

Schritt 4: Öffne deinen Browser und gebe http://127.0.0.1/ oder http://localhost/ ein. Danach gelangst du zu den zahlreichen ApacheFriends-Beispielen auf dem lokalen Server.

Schritt 5: Das Root-Verzeichnis (Hauptdokumente) für HTTP(S) ist => \xampp\htdocs. PHP hat die Endung *.php, SSI *.shtml , CGI *.cgi (z.B. auch für Perlskripte), Perl *.pl und ASP *.asp

Schritt 6: XAMPP DEINSTALLIEREN?
           Einfach das "XAMPP"-Verzeichnis löschen. Vorher aber alle Server stoppen bzw. als Dienste deinstallieren.
           Alternativ die Datei "uninstall_xampp.bat" ausführen.

---------------------------------------------------------------

* PASSWÖRTER:

1) MySQL:

   Benutzer: root
   Passwort:
   (also kein Passwort!)

2) FileZilla FTP:

   Benutzer: newuser
   Passwort: wampp

   Benutzer: anonymous
   Passwort: some@mail.net

3) Mercury:

   Postmaster: Postmaster (postmaster@localhost)
   Administrator: Admin (admin@localhost)

   TestUser: newuser
   Passwort: wampp

4) WEBDAV:

   Benutzer: wampp
   Password: xampp

---------------------------------------------------------------

* WINDOWS DIENSTE:

- \xampp\apache\apache_installservice.bat
  ===> Installiert den Apache als Dienst

- \xampp\apache\apache_uninstallservice.bat
  ===> Deinstalliert den Apache als Dienst

- \xampp\mysql\mysql_installservice.bat
  ===> Installiert MySQL als Dienst

- \xampp\mysql\mysql_uninstallservice.bat
  ===> Deinstalliert MySQL als Dienst

- \xampp\filezilla\filezilla_installservice.bat
  ===> Installiert FileZilla als Dienst

- \xampp\filezilla\filezilla_uninstallservice.bat
  ===> Deinstalliert FileZilla als Dienst

- \xampp\mercury\mercury_installservice.bat
  ===> Installiert Mercury als Dienst

- \xampp\mercury\mercury_uninstallservice.bat
  ===> Deinstalliert Mercury als Dienst

Oder benutze einfach im Control Panel die Klickbox "Svc" dazu.

---------------------------------------------------------------

* DAS THEMA SICHERHEIT:

Wie schon an anderer Stelle erwähnt ist XAMPP nicht für den Produktionseinsatz gedacht, sondern nur für Entwickler in Entwicklungsumgebungen. Das hat zur Folge, dass XAMPP absichtlich nicht restriktiv, sondern im Gegenteil sehr offen vorkonfiguriert ist. Für einen Entwickler ist das ideal, da er so keine Grenzen vom System vorgeschrieben bekommt.
Für einen Produktionseinsatz ist das allerdings überhaupt nicht geeignet!
Hier eine Liste, der Dinge, die an XAMPP absichtlich (!) unsicher sind:

- Der MySQL-Administrator (root) hat kein Passwort.
- Der MySQL-Daemon ist übers Netzwerk erreichbar.
- phpMyAdmin ist über das Netzwerk erreichbar.
- In dem XAMPP-Demo-Seiten (die man unter http://localhost/ findet) gibt es den Punkt "Sicherheitscheck".
  Dort kann man sich den aktuellen Sicherheitszustand seiner XAMPP-Installation anzeigen lassen.

Will man XAMPP in einem Netzwerk betreiben, so dass der XAMPP-Server auch von anderen erreichbar ist, dann sollte man unbedingt die folgende URI aufrufen, mit dem man diese Unsicherheiten einschränken kann:

    http://localhost/security/

Hier kann das Root-Passwort für MySQL und phpMyAdmin und auch ein Verzeichnisschutz für die
XAMPP-Seiten eingerichtet werden.

---------------------------------------------------------------

* MYSQL-Hinweise:

Der MySQL-Server startet ohne Passwort für MySQl-Administrator "root".
Für eine Zugriff in PHP sähe das also aus:

    mysql_connect("localhost", "root", "");

Ein Passwort für "root" könnt ihr über den MySQL-Admin in der Eingabeaufforderung setzen. Z.B.:

    \xampp\mysql\bin\mysqladmin.exe -u root -pgeheim

Wichtig: Nach dem Einsetzen eines neuen Passwortes für Root muss auch phpMyAdmin informiert werden! Das geschieht über die Datei "config.inc.php"; zu finden als C:\xampp\phpmyadmin\config.inc.php. Dort also folgenden Zeilen editieren:

    $cfg['Servers'][$i]['user']            = 'root';   // MySQL User
    $cfg['Servers'][$i]['auth_type']       = 'cookie';   // HTTP-Authentifzierung

So wird zuerst das "root"-Passwort vom MySQL-Server abgefragt, bevor man auf phpMyAdmin zugreifen darf.

---------------------------------------------------------------

* CPAN/PEAR:

CPAN und PEAR wird nur mit einer Basisinstallation ausgeliefert. Wenn du weitere Pakete benötigst,
kannst du diese in der XAMPP Shell (xampp_shell.bat) mit den Kommandozeilentools installieren:
- cpanp i Foo
- pear install Foo

Solltest du keinen VC6 Kompiler installiert haben, kannst du anstatt "cpanp" auch "ppm" zum Installieren von Binärpaketen benutzen.

---------------------------------------------------------------

        Have a lot of fun! | Viel Spaß! | Bonne Chance!
