# **Laborprotokoll**

Datum: 21.11.2017 (Gruppe 3)

Ort: AUT-Labor

Lehrkraft: SX
Übung Nr: 
Abwesend: -


## **Versionsverwaltung mit Git**

**Git**

Git ist ein System mit zur Versonsverwaltung, welches sehr häufig verwendet wird. Damit können mehrere Personen,
die an einem Projekt arbeiten, auf die gemeinsamen Datein zugreifen. Es ist aber auch sinnvoll mit Git zu arbeiten
wenn man alleine arbeitet. Git wurde von Linus Torvald entwickelt, der mit den anderen Versionsverwaltungen nicht 
zufrieden war (z.B: SVN,CVS,ClearCase)

**Vorteile von Git:**

* Git unterstützt verschmelzen von Entwicklungszweigen
* Jeder Projektteilhaber hat eine lokale Kopie des gesamten Repositories (local repository)
* Somit ist zum Arbeiten keine Internetverbindung nötig
* local repositorys können über das Internet synchronisiert werden

**Aufbau von Git:**

Git ist auf 5 Ebenen aufbgebaut:
![Aufbau GIT](C:\Users\Florian\Documents\SCHULE1718\LABOR\Steiner\Bild1.png)
Bild vom [Skript](https://www.htl-mechatronik.at/e-books/sx/html/git/git.html#(4))

* __*workspace:*__ Arbeitsbereich
* __*stash:*__ Rücksicherung der Daten aus dem Workspace
* __*index:*__ Zwischenspeicher wenn Daten noch nicht für alle freigegeben werden sollen
* __*local repository:*__ Lokale Datenverwaltung am eigenen PC
* __*remote repository:*__ Gemeinsame Datenverwaltung, die sich mit den loaklen Datenverwaltungen abgeleicht

**Branches**

Branches werden auch Verzweigungen genannt. Sinn und Zweck eines Branches ist es, Funktionen getrennt voneinander zu entwickeln. Bei dem Erstellen eines neues Repositorys wird der sogenannte **Master Branch** erstellt. Im Master Branch sollten immer nur funktionsfähige Programme gespeichert werden, da es ansonsten zu Problemen bei der Zusammenarbeit kommen könnte.  
Um trotzdem eine Zusammenarbeit ermöglichen zu können, git es sogenannte Nebenzweige, welche dazu verwendet werden, unfertige und nicht funktionierende Funktionen zu verwalten. Nach der Fertigstellung eines Programmes kann dieses in den Master-Branch geschoben werden.


## **GitHub**

Mit GitHub können kostenlose Git-Systeme erstellt werden, bei denen jeder über Leserechte verfügt (öffentliche repositorys).
Schreibrechte hat nur der Benutzer. Private repositorys können mit Geld erworben werden. Beim erstellen einer repository 
ist auf folgendes zu achten:
* Es ist empfelenswert eine der vorgefertigten open source Lizenzen auszuwählen
* Es sollte die Programmiersprache ausgewählt werden, das so gewisse Datein ignoriert werden

Mit *readme´s* können Informationen an den Nutzer weitergegeben werden (z.B. Installationsinformation)

Link zur Website: [GitHub](https://github.com/)


## **Markdown**

Markdown ist ein Format, mit dem man ein Textfile in eine HTML-Datei (oder PDF´s, usw...)  umwandeln kann. Markdown wird zum Beispiel 
von GitHub verwendet. 

[Syntax Guide](https://guides.github.com/features/mastering-markdown/)

##


