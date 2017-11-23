# 1. Protokoll
## Thema: Einführung in GitHub  
**Name:** Sackl Martin   
**Klasse** 4ahme    
**Gruppe:** 3

Anwesend: Reinbacher, Ruffenacht, Sackl M., Sackl R., Sammer, Schmuck, Schuster   
Abwesend: -  

### Was ist GitHub?  
**GitHub** basiert auf der freien Software **Git**. Da GitHub eine Open-Source Software ist, hat jeder Lesezugriff auf öffentliche Repositories, aber keinen Schreibzugriff, solange sie nicht privat sind. Private Repositories können mit Geld erworben werden.  

### Was ist Git?  
**Git ist eine frei Software, welche zur Verwaltung von Dateien genutzt wird.**  

Unteschiede zu anderen Versionsverwaltungen:  
* Kein Zentraler Server  
* Große Bestandteile von Git sind das Erstellen und Verschmelzen von Entwicklungszweigen 
* Das Erstellen von Programmen ist meist nicht linear  

**Vorteile bei Git**  
* Repositories werden lokal gespeichert  
* Die lokale Versionsverwaltung ist auch offline verfügbar  

### Ebenen und Befehle in Git  
**Git wird in 5 Ebenen unterteilt:**    
* Stash (Zwischenspeicher)  
* Workspace  
  * Änderungen werden hier vorgenommen  
* Index (Staging area)  
  * hier sind Dateien vom nächsten commit  
* Local repository  
  * Lokales Repository im Verzeichnis .git  
* Remote repository  
  * Repository auf dem Git-Server  

**Befehle in Git**  
* git clone
	* Ein gesamtes Repository wird geklont
* git add
	* Dateien werden vom Workspace in den Index befördert
* git commit
	* Dateien werden vom Index in das lokale Repository befördert
* git push
	* Änderungen im lokalen Repository werden auf den Git-Server geladen  
* git checkout
	* Dateien werden vom lokalen Repository in den Workspace befördert
* git pull
	* Änderungen werden vom Server geladen
* git status
	* zeigt alle Änderungen vom Repository  

### Branches  
Branches werden auch Verzweigungen genannt. Repositories können in Branches unterteilt werden, damit eine stabile Version immer erhalten bleibt, wenn man daran arbeitet. Daher sollte sich die stabile Version immer im **Master branch** befinden.  
Mehr dazu finden Sie [hier](https://git-scm.com/book/en/v1/Git-Branching-What-a-Branch-Is).  

### Issues  
Issues sind Feedbacks von anderen Git-Nutzern. Dadurch können Fehler und Erweiterungen in einem Projekt leichter verfolgt werden.  
Mehr dazu finden Sie [hier](https://guides.github.com/features/issues/).  

### Markdown  
Markdown ist eine Möglichkeit, eine Textdatei in eine HTML-Datei umzuwandeln. Markdown wird z.B. von GitHub verwendet.
Den Umgang mit Markdown können Sie [hier](https://guides.github.com/features/mastering-markdown/) nachlesen.  

### SSH-Schlüssel bei GitHub  
Bevor man mit einem SSH-Schlüssel klonen kann muss man zuerst am Linux System ein RSA-Schlüsselpaar erstellen. Das funktioniert in der Konsole mit dem Befehl "ssh-keygen".  
Danchach muss man den öffentlichen Schlüssel (id_rsa.pub) bei GitHub in den Einstellungen einfügen.  
* Settings bei GitHub  
* SSH and GPG keys  
* New SSH key
