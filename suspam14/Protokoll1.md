# Protokoll
## Thema: Einführung in Git

Name: Patrick Schuster  
Klasse: 4AHME  
Gruppe: 3  

Anwesend: Reinbacher, Ruffenacht, Sackl, Sackl, Sammer, Schmuck, Schuster  
Abwesend: keiner  

## Git
Git ist eine kostenlose Software, die zur Versionsverwaltung von Dateien genützt werden kann. 
### Versionsverwaltung
Eine Versionsverwaltung ist ein System für die Erfassung von Änderungen an Dateien. Mit einer Versionsverwaltung können mehrere Person gleichzeitig an einem Projekt arbeiten und auf die gemeinsamen Daten zugreifen. Jede Datei hat eine History in der man nachschauen kann, wer die Datei wann verändert hat und was er verändert hat. Es ist auch sinnvoll mit einer Versionsverwaltung zu arbeiten wenn man  alleine arbeitet. 
### Unterschiede zu anderen Versionsverwaltungen  
Die Repositorys werden lokal auf dem Rechner gespeichert (local Repository), somit wird zum arbeiten keine Verbindung mit dem Sever benötigt.

### Ebenen
Git wird in 5 Ebenen unterteilt
* Stash (Zwischenspeicher)
* Workspace (Arbeitskopie)
* Index (Staging Area)
* local Repository (Repository am Rechner)
* remote Repository (Repository am Git-Server)

### Befehle
* `git clone `  
klont das Repository ins aktuelle Verzeichnis

* `git status `  
zeigt die Änderungen im Repository an   

* `git add `  
transferiert die Dateien vom Workspace in den Index

* `git commit `  
transferiert die Dateien vom Index in das lokale Repository

* `git push `  
transferiert die Dateien vom lokalen Repository ins remote Repository

* `git checkout `  
wechselt in den gewünschten Branch  

* `git checkout -b`  
erstellt neuen Branch  

* `git pull`  
lädt die Änderungen vom Server

* `git fetch`  
lädt das remote Repository ins lokale Repository 


## Github
Github ist ein Online-Dienst basierend auf Git. Man kann online Repositorys anlegen auf die jeder Zugriff hat. Deswegen wird Github vorwiegend für Open Source Projekte verwendet. Es ist auch möglich ein privates Repository zu erstellen, das ist aber mit Kosten verbunden.  

## Markdown  
Markdown ist ein Dateiformat für Text-Dateien. Man benötigt um einen Text in Markdown zu schreiben nur einen Editor. Im Vergleich zu `.txt` Dateien ist es möglich diese übersichtlicher und strukturierter zu gestalten. Markdown wird z.B. in Github verwendet.  
**Syntax Guide für Markdown: [Mastering Markdown](https://guides.github.com/features/mastering-markdown/)**

## SSH
Es ist auch möglich die Übertragung mit dem remote Repository über das SSH Protokoll zu machen. Ohne SSH ist die übertragung unsicher. Ein weiterer Vorteil der verbindung mit SSH ist das kein Passwort mehr eingegeben werden muss.  
**SSH Übertragung für Github konfigurieren**
1. SSH-Schlüsselpaar erzeugen mit `ssh-keygen`
1. Die Schlüsseldatei `id_rsa.pub` öffnen und den gesamten Inhalt kopieren
1. In den Einstellungen von Github den neuen Schlüssel einfügen

