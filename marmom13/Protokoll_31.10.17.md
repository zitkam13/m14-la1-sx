# Protokoll 31.10.2017  

## 1. Einheit  

## Thema: Git und Github

Name: Moritz Martinak  
Lehrer: sx  
Gruppe: 2  
Übungsdatum: 31.10.2017  
Abwesend: -  

## Git und GitHub  

**Git** ist eine freie Software zur verteilten Versionsverwaltung von Dateien.
Einer der Hintergrundgedanken von Git ist das Arbeiten ohne an ein Netzwerk gebunden zu sein. Das wird durch ein Lokales
Repository am Rechner selbst erzielt.

**GitHub** ist ein Open-Source Onlinedienst der auf Git basiert und kostenlos verwendbar ist (es sei denn man will ein privates Repository erstellen, dann zahlt man eine monatliche Gebühr). Es kann jeder nutzer auf öffentliche Repositorys zugreifen, diese aber nur mit Berechtigung des Besitzers bearbeiten. Man kann ein Repository aber klonen und dann unabhängig selbst weiter arbeiten.

**Ebenen**

* Stash (Zwischenspeicher)
* Workspace (Arbeitsdatei)
* index 
* local repository (Repository am Computer)
* remote repository (Repository am Server)

**Befehle**

* git add (Hinzufügen einer Datei)
* git commit [-a] (Veränderte datei wird dem local repository hinzugefügt (-a fügt alle Dateien hinzu)
* git push (Der Inhalt des local repository wird auf den Server geladen)
* git clone (das gesamte Repository wird copiert)
* git pull (Veränderungen werden vom Server geladen)
* git checkout (Dateien werden vom local repository zum Workspace befördert)
* git merge (Vereinigt zwei branches)

## Branches

Branches sind Verzweigungen eines Repository damit mehrere Menschen gemeinsam an einem Projekt arbeiten können. Wird ein Repository erstellt gibt es zuerst nur den sog. "master"-Branch. Dieser sollte immer eine funktionsfähige Version des Projekts enthallten um Probleme bei der Zusammenarbeit zu vermeiden. Noch nicht funktionierente versionen sollten in neben Branches abgelegt werden und erst bei voller Funktionalität mit dem Masterbranch gemerged werden.

## Markdown

**Git hub nutzt eine Formationsmöglichkeit namens Markdown**
Dabei verwendet man folgende Formatierungszeichen:

* "#" 1.Überschrift ## 2. Überschrift...
* "*" Aufzählungszeichen
* "1." Geordnete Aufzählung
* ein * am Anfang und am Ende des Texts formatiert ihn *Kursiv*
* zwei * am Anfang und am Ende des Texts formatieren ihn **fett**
* "[name](link)" wird verwendet um eine Link zu erstellen
