#Laborprotokoll KW38
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
 

 
