# Protokoll 1 31.10.2017

## Thema: Einführung in Github

Name: Michael Mörth  
Klasse: 4AHME  
Gruppe: 2  

Anwesend: Nebel Florian, Mandl Gerhard, Michael Mörth, Moritz Martinak, Mario Nabernik, Muri Lorenz, Platzer Andreas, Marcel Köhler    
Abwesend: -

## Was ist Git?
**Git ist eine freie Software, welche zur Verwaltung von Dateien genützt wird.**

Unterschiede zu anderen Versionsverwaltungen:
* Das Erstellen von den Programmen ist meist nicht linear. 
* Große Bestandteile von Git sind das Erstellen und Verschmelzen von Entwicklungszweigen.
* Kein Zentraler Server
  * Jeder benutzer hat eine lokale Kopie des gesamten Repositories (local repository)
  * Es wird kein Internetzugriff erfordert (man kann also überall darauf zugreifen und damit arbeiten)
  * Synchronisation über das Internet möglich
  * Sollten zwei Personen gleichzeitig eine Änderung an der selben Datei durchführen und synchronisieren, werden beide Dateien hochgeladen und es entsteht ein Konflikt der gelöst werden muss

## Was ist Github
Github basiert auf der freien Software Git. Dadurch ist es möglich, dass alle Nutzer von Github einen Lesezugriff, jedoch keinen Schreibzugriff auf alle Repositorys haben, solange diese nicht privat sind. Private Repositorys können mit Geld erworben werden.

**Der Sinn von Github ist es, Daten versionsverwaltet zu speichern. Github und andere Versionsverwaltungen eignen sich besonders bei Projekten an denen mehrere Personen arbeiten, da die Verwaltung immer protokolliert, wer wann und was geändert hat. Außerdem ist das Wiederherstellen von alten Version auch jederzeit möglich.**

Andere Versionsverwaltungen: SVM, CVS, Mercury und Clearcase

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

Mithilfe von Befehlen wird zwischen den Ebenen kommuniziert.

**Befehle in Git:**
* git checkout
	* Dateien werden vom lokalen Repository in den Workspace befördert
* git add
	* Dateien werden vom Workspace in den Index befördert
* git commit
	* Dateien werden vom Index in das lokales repository befördert
* git push
	* Änderungen im lokalen Repository werden auf den Git-Server geladen
* git clone
	* Ein gesamtes Repository wird geklont
* git pull
	* Änderungen werden vom Server geladen
* git status
	* zeigt alle Änderungen im repository

## Branches

Branches werden auch Verzweigungen genannt. Sinn und Zweck eines Branches ist es, Funktionen getrennt voneinander zu entwickeln. Bei dem Erstellen eines neues Repositorys wird der sogenannte **Master Branch** erstellt. Im Master Branch sollten immer nur funktionsfähige Programme gespeichert werden, da es ansonsten zu Problemen bei der Zusammenarbeit kommen könnte.  
Um trotzdem eine Zusammenarbeit ermöglichen zu können, git es sogenannte Nebenzweige, welche dazu verwendet werden, unfertige und nicht funktionierende Funktionen zu verwalten. Nach der Fertigstellung eines Programmes kann dieses in den Master-Branch geschoben werden.

## Issues

**Issues sind Feedbacks von anderen Git-Nutzern. Dadurch können Erweiterungen sowie Fehler für ein Projekt leichter vefolgt werden.**
Issues können mit dem gesamten Team geteilt werden. Natürlich können diese Issues auch diskutiert werden. Desweiteren ist es möglich, dass wenn ein Issue verfasst wurde, der Ersteller des Projektes über eine E-Mail informiert wird.

Den Umgang mit Issues kann man [hier](https://guides.github.com/features/issues/) genauer nachlesen.

## Markdown

**Markdown ist eine Möglichkeit, eine Text-Datei in eine HTML-Datei umzuwandeln. Markdown wird z.B. von GitHub verwendet.**

Den Umgang mit Markdown kann man [hier](https://guides.github.com/features/mastering-markdown/) nachlesen.

## SSH Git-Repository

### Konfigurieren von Github 
1. SSH-Schlüsselpaar erzeugen und public-key unter settings - SSH and GPG Keys einfügen  
das erzeugen des SSH-Schlüsselpaars kann [hier](https://help.github.com/articles/connecting-to-github-with-ssh/) genauer nachgelesen werden.

2. SSH-Config konfigurieren zur Verbindung mit Github

	1. Config-Datei öffnen: nano ~/.ssh/config
	2. Hinzufügen des Hosts github:
		
		Host github  
			Hostname github.com  
			User git  
