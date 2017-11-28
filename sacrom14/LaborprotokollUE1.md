# 1.Protokoll  
  
  **Name**:  *Sackl Roland*  
  **Datum:** *21.11.2017*  
  **Uhrzeit:** *9:40-12:25*  
  **Gruppe:** *3*  
  
   
    
 **Abwesend:** -  
 **Anwesend:**  Bernhard Reinbacher, Ruffenacht Florian, Sackl Martin, Sackl Roland, Sammer Daniel, Schmuck Martin, Schuster Patrick  
-------------------------------------


### Git
Git ist eine Software für die Versionsverwaltung von Dateiein, das es einem Team aus Softwareentwicklern es einfacher macht miteinander zusammenzuarbeiten.
Das macht aus diesem Grund Sinn, da man so Fehler, die eventuell eingebaut wurden schneller behoben werden können, oder damit die Entwickler gleichzeitig arbeiten und ihre Werke zusammenführen können.

**Vorteile bei Git:**  
* Die lokale Versionsverwaltung ist auch offline verfügbar  
* Repositories werden lokal gespeichert  



## GitHub
**GitHub** ist ein **Online-Dienst** für Versionsverwaltung dieser auf Git basiert.  
Da GitHub eine Open-Source Software ist kann jeder auf öffentliche Repositories zugreifen. 
Es eignet sich vor allem für Open-Source-Projekte, da im Gratis-Paket nur öffentliche Repositories enthalten sind, sprich es können alle auf das Projekt zugreifen.Dieses kann man mit private Reposities vermieden werden. Dieses funktioniert aber nur wenn man 7$ im Monat bezahlt.



## Branches

Ein Branch bezeichnet einen Zweig innerhalb eines Repositoritys. Die Idee hinter Verzweigungen ist die, eine funktionsfähige, stabile Version welche bereits von einem Kunden genutzt wird nicht zu gefährden und trotzdem weiterarbeiten zu können. Es gibt einen **master**-Branch - die offizielle Version - und Branches in denen zum Beispiel neue Funktionen eingebaut werden, 
die aber noch nicht stabil laufen.Um trotzdem eine Zusammenarbeit ermöglichen zu können, git es sogenannte Nebenzweige, welche dazu verwendet werden, unfertige und nicht funktionierende Funktionen zu verwalten. Nach der Fertigstellung eines Programmes kann dieses in den Master-Branch geschoben werden.  


## Markdown

Damit kann man Text-Dateien mit einfachen Mitteln in eine formatierte HTML-Datei zu verwandeln. Markdown wird unter anderem von GitHub verwendet.
**Beispiele für Regeln zur Formatierung:**
* "#", "##", und "###" für Überschriften
* "* ... * ": *italic*
* "** ... ** ": **fett**
* "[Name]""(Link)": erstellt einen Link  
Weitere Informationen finden Sie [hier](https://guides.github.com/features/mastering-markdown/).  



## Ebenen und Befehle mit Git

**Git wird in fünf Ebenen unterteilt:**
* Stash (Zwischenspeicher)
* Workspace (Arbeitskopie) 
	* hier werden Änderungen vorgenommen 
* index (staging area)
	* hier sind Dateien welche im nächsten commit enthalten sind
* local repository
	* Lokales Repository im Verzeichnis .git
* remote repository
	* Repository auf einem Git-Server



**Befehle in Git:**
* git checkout
	* Dateien werden vom lokalen Repository in den Workspace befördert
* git add
	* Neue Version wird vom Workspace in den Index übertragen
* git commit
	* Dateien werden vom Index in das lokales repository befördert
* git push
	* Änderungen im lokalen Repository werden auf den Git-Server geladen
* git clone
	* Repository wird auf dem Computer erstellt und die Daten des Servers übertragen
* git pull
	* Änderungen werden vom Server geladen
* git status
	* Anzeige der Änderungen, die übernommen werden
  
  
