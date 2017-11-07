# Protokoll der 1.Einheit (31.10.2017)

## Thema Einführung zur Verwendung von GitHub

Name:     Florian Nebel  
Klasse:   4AHME  
Gruppe:   2  

Anwesend: Köhler Marcel, Mandl Gerhard, Martinak Moritz, Mörth Michael, Muri Lorenz, Nabernik Mario, Nebel Florian, Platzer Andreas  
Abwesend: ---

## Was versteht man unter Git bzw. GitHub?
**Git ist eine Software zur versionsverwaltenden Dateiablage, welche kostenlos zur Verfügung gestellt wird.**

**Entscheidende Merkmale dieses Systems sind:**
* Es kann an verschiedenen Zweigen (Branches) des Dateisystem zur selben Zeit gearbeitet werden, dass ermöglicht Veränderungen an einem bereits von Nutzern verwendeten Programms, da nur auf einem parallel verlaufendem Zweig gearbeitet wird, wärend der vom Endnutzer verwendete Zweig unberührt bleibt. Sobald die einwandfreie Funktion des veränderten Programms sichergestellt wird, können die Zweige wieder verschmolzen werden.
* Da kein zentraler Server verwendet wird, sondern jeder eine lokale Kopie des gesamten Repositorys besitzt, ist keine dauerhafte Internetverbindung erforderlich. Nach Änderungen kann man sein Repository mit der Onlinversion abgleichen. Solten mehrere Personen zur selben Zeit die selbe Datei verändert haben, kommt es zu einem Konflikt, welcher gelöst werden muss.

**GitHub bezeichnet eine auf Git basierende Software, welches als OpenSource-Projekt gehandhabt wird und dadurch jedem ermöglicht jedes Ropository einzusehen.**
* Man kann dem Verfasser eines Repositorys Vorschläge (Issues) zu seinem Projekt machen, oder dessen Arbeit übernehmen und selbst weiterführen.
* Um Repositorys nur für sich selbst zu nutzen, kann man eine kostenpflichtige Version erwerben.
**GitHub ermöglicht Projekte im Team einfach abzuwickeln, da jederzeit von jedem nachvollzogen werden kann, wer, was, wann verändert hat und das Wiederherstellen von alten Versionen jederzeit möglich ist.**

## Verwaltungsebenen:
**Die Unterteilung des Git-Systems erfolgt in fünf Ebenen.**
* Stash
* Workspace
* index
* lokal repository
* remote repository

## Befehle:
* **git checkout:** *Dateien werden vom lokal repository in den Workspace bewegt.*
* **git add:** *Dateien werden vom Workspace nach Index bewegt.*
* **git commit:** *Dateien werden vom Index ins lokal repository bewegt.*
* **git push:** *Dateien vom lokal repository auf Git-Server geladen.*
* **git clone:** *Das gesamte Repository wird geklont.*
* **git pull:** *Dateien werden vom Git-Server heruntergeladen.*
* **git status:** *Alle Änderungen anzeigen.*

## Branch:
Ein Branch bezeichnet einen Zweig innerhalb eines Repositoritys. Die Idee hinter Verzweigungen ist die, eine funktionsfähige, stabile Version welche bereits von einem Kunden genutzt wird nicht zu gefährden und trotzdem weiterarbeiten zu können. Beim erstellen eines neuen Repositorys wird standartmäsig ein *Master Branch* erstellt. In diesem Zweig sollte sich immer eine funktionsfähige Version befinden. Die Nebenzweige werden genutzt um weiterzuarbeiten bzw. neue Dinge auszuprobieren. Wenn der Nebenzweig stabil läuft und man diese Version in den Hauptzweig integrieren will, kann man beide verschmelzen.

## Issue:
Issues (übersetzt: "Vorschläge") werden verwendet um den Entwicklern eines Repositorys über Fehler oder Verbesserungsvorschläge zu informieren. Der Adressat eines Issues wird kann über ein e-Mail informiert werden.

## Markdown:
Damit kann man Text-Dateien mit einfachen Mitteln in eine formatierte HTML-Datei zu verwandeln. Markdown wird unter anderem von GitHub verwendet.
**Beispiele für Regeln zur Formatierung:**
* "#", "##", und "###" für Überschriften
* "* ... *": italic
* "** ... **": fett
* "[Name]("Link")": erstellt einen Link
