# _Protokoll Erste Einheit_  

**Name: Daniel Sammer**  
**Gruppe: 3**  
**Datum: 21.11.2017**  
**Uhrzeit: 9:40-12:25**  
  
**Anwesenheit: _Es waren alle Schüler anwesend_**  
  
  
  
### GIT  
GIT ist ein System zur Versionsverwaltung von Dateien. Versionsverwaltungssysteme, wie zum Beispiel GIT, sehen die Daten als eine Menge an Dateien und Änderungen (_Snapshots_). Andere Systeme sehen die Daten hingegen als eine fortlaufende Liste an Änderungen der Dateien.  
Versionsverwaltungssysteme sind wichtig für Firmen, bei denen mehrere Teammitglieder an einem Projekt gleichzeitig arbeiten. Die beiden Versionen werden hochgeladen und synchronisiert.  
  
* Entwickler: Linus Torvalds  
* freie Software zur Versionsverwaltung  
* kein Internetzugriff notwendig  
  * Komponenten _workspace und local repository_ reichen als lokale Verwaltung am eigenen Rechner  
* 2 oder mehr Personen können gleichzeitig an einer Datei Änderungen vornehmen (Verwaltung über Server)  
* Synchronisation kann über Internet stattfinden  
  
#### GIT-Ebenen und Kommandos  
* Stash  
  * _Zwischenspeicher_ für Änderungen, während andere Daten bearbeitet werden  
* Workspace  
  * _Arbeitsspeicher_  
  * Änderungen an Dateien finden hier statt  
* Index  
  * _staging area_  
  * Änderungen und Dateien warten, bis sie einen _commit_ erhalten  
* Local repository  
  * lokaler Speicher im Verzeichnis _.git_  
* Remote repository  
  * externer Speicher auf einem Git-Server  
  
---------------------------------------------------  

Git add -> workspace in index
Git commit -> index in local repository
Git push -> local rep. in remote repository
Git pull -> remote rep. in workspace
Git fetch -> remote rep. in local repository

  
![GIT-Ebenen und Kommandos](https://github.com/HTLMechatronics/m14-la1-sx/blob/samdam14/samdam14/System.PNG)
  
