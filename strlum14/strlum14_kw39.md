# Laborprotokoll KW39
## Git repository mit Linux!

Um mit der Repository an einem Linux System arbeiten zu können, muss man sie als estes vom Github-Server klonen !
(Klonen=verdoppeln)

In der Konsole schafft man das Mit dem Befehl git Clone !

     --> git clone + Link der Repositiry
     
Den Link der Repository kann man ganz einfach unter der Repository finden ! Man kann dann
entweder über die **SSH** Verschlüsselung klonen oder über **HTTPS** ! 

     --> Clone with SSH
     --> Clone with HTTPS

Mithilfe der Konsole können Dateien dann eingefügt oder berbeitet werden. 
Dies kann man auch mit dem Dateimanager machen, jedoch ist es mit der Konsole weitaus praktischer.
Wenn man etwas verändert muss man muss man es allerdings manuell mit dem Github-Server synchronisieren.
Dies gelingt mit folgenden Befehlen:

     --> git add -A   (-A um alle Dateien zu kopieren, add um Dateien zum Index zu transferieren)
     -->git commit -m   (-m Kurzbefehl für Kommentar, commit um Dateien vom Index zum Server zu transferieren)
     -->git push      (um Daten vom lokalem Repository zum Server zu transferieren)
     
     
Wird mit einem gemeinsamen Repository gearbeitet, kann man auch am Linux System
mithilfe der Konsole Branches erstellen um eigene Dateien in einem eigenen Branch zu speichern.
Dies funktioniert so:

     -->  git checkout -b + "Name vom Branch"
 
## SSH Schlüssel
Man muss als erstes am Linux-System ein RSA-Schlüsselpaar erzeugen!

     --> ssh keygen
Dannach kann man auswählen wo man den Schlüssel hinspeichern will.
Als nächstes muss der öffententliche Schlüssel (id_rsa.pub) bei Github in den Einstellungen eingefügt werden.
Das funktioniert so:

     --> id_rsa
     --> id_rsa.pub
     --> known_hosts
     --> less id_rsa.pub
     
Als nächstes öffnet man https://github.com/settings/keys !
Dannach klickt man auf "new SSH Key" und dannach kann der öffentliche Schlüssel problemlos reinkopiert werden.


## Atmel AVR Studio

Atmel AVR Studio ist ein Programm mit dem man Microcontroller programmieren kann und auch simulieren kann !
Sprich: kostenlose Entwicklungsumbegung:
Sie basiert ab Version 5 auf der Visual Studio Shell von Microsoft und besteht aus einer Projektverwaltung, einem Editor,
einem Debugger und Werkzeugen zum Beschreiben der Mikrocontroller. 

