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
  
##### Git-Hub  
...ist ein kostenloser Online-Dienst, mit dem eine Versionskontrollsystem in einem Team verwirklicht werden kann!  
zum Online-Dienst: [GitHub](https://github.com/)  
  
#### Git-Ebenen und Kommandos  
##### Git-Ebenen  
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
##### Transport-Kommandos  
* Git add  
  * Transport der Datei vom _workspace_ in die _staging area/index_  
* Git commit  
  * Transport der Datei von der _staging area_ in das _local repository_  
* Git push  
  * Transport der Datei vom _local repsitory_ in das _remote repository_  
* Git pull  
  * Transport der Datei vom _remote repository_ in den _workspace_  
* Git fetch  
  * Transport der Datei vom _remote repository_ in das _local repository_  
 
![GIT-Ebenen und Kommandos](https://github.com/HTLMechatronics/m14-la1-sx/blob/samdam14/samdam14/System.PNG)  
Bildursprung: [E-Book SX](https://www.htl-mechatronik.at/e-books/sx/html/git/git.html#(4))    
  
#### Arbeitsprinzip  
Alles funktioniert auf dem Prinzip von Zweigen (_Branches_). Im Hauptzweig (_master branch_) soll sich die funktionsfähige Version befinden. Gearbeitet wird im Nebenzweig (_sub branch_). Den Hauptzweig kann man mit dem Befehl _git checkout_ verlassen.  
im Skript: [E-Book SX](https://www.htl-mechatronik.at/e-books/sx/html/git/git.html#(6))  
  
#### Markdown  
...ist eine Möglichkeit, mit der man Textdokumente mit _plain text_ durch einfache Codes zu formatieren.  
  
Codes zur Gestaltung/Formatierung findest du hier: [MasteringMarkdown](https://guides.github.com/features/mastering-markdown/)  
  
  
#### Befehle der Einheit    
[Befehle](https://github.com/HTLMechatronics/m14-la1-sx/blob/samdam14/samdam14/Befehle.md)  
