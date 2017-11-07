# Protokoll der 1.Einheit
* Name: Mario Nabernik
* Klasse: 4AHME
* Datum: 31.10.2017
* Gruppe: 2
* Anwesend: Marcel Köhler, Michael Mörth, Florian Nebel, Lorenz Muri, Moritz Martinak, Andreas Platzer, Mario Nabernik, Gerhard Mandl  
* Abwesend: -
* Thema: Git (Versionsverwaltung), Markdown

## Git
[Git](https://git-scm.com/) ist eine einfache Versionsverwaltung, welche sich von ihren "Mitbewerbern", wie SVN, CVS, Clearcase etc. durch folgende Dinge unterscheidet: 
Unterschiede zu SVN:
In Git ist es möglich lokal zu arbeiten, sprich Versionen downzuloaden und an dieser Version offline weiter zu arbeiten. Das bedeutet u. a. das Git User nicht von einem funktionstüchtigen und immer erreichbaren zentralen Server abhängig sind. Daraufhin ist ein Abgleich mit dem zentralen Repository möglich.
Versionsnummern werden nicht mehr verwendet, sondern werden durch SHA-1 Hashes ersetzt und es werden nicht einzelne Dateien versioniert sondern Dateien bzw Verzeichnis-Snapshots.
Git wurde von Linus Torvalds entwickelt. Sein Ziel war es verteilte Arbeitsabläufe, hohe Sicherheit und hohe Effizienz möglich zu machen.

### Worklflowebenen
Das lokale Repository besteht aus drei Ebenen:

* __workspace__ – Hier befinden sich die Dateien
* __index__ – alles was für den nächsten Commit ansteht
* __local__ repository – Hier speichert Git die Blobs (was die versionisierten Dateien sind) und die Trees (Die Zuordnung zwischen Datei/Pfad und einem Blob)

weiters gibt es noch 2 Ebenen:

* __stash__ (Zwischenspeicher)
* __remote__ repository (hier spricht man vom "onlinen", "zentralen" repository, auf welches alle Mitarbeiter zugreifen können)

### Git Befehle

#### Terminal History der letzten Einheit + Erklärung:

  122  cd la1  
  123  git clone https://github.com/****/labor.git        __auschecken/kopiren des zentralen Repositories/es besteht nun aus workspace, index und local repository__  
  124  ll  
  125  cd labor/  
  126  ll  
  127  git status                                             __Änderungen im Repository__  
  128  git checkout stunde4                                   __wir wechseln in den genannten Branch__    
  129  git status  
  130  ll  
  131  nano main.c  
  132  gir status  
  133  git status                                               
  134  git add main.c                                         __auf commit vorbereiten__  
  135  git status  
  136  git commit -m "Testcommit"                             __wir führen den commit aus, verschieben es damit vom index in das local repository und schreiben ein Bermerkung bei__  
  137  git config --global  user.email ""  
  138  git config --global  user.name ""  
  139  git commit -m "Testcommit"  
  140  nano ~/.gitconfig   
  141  git push                                               __wir bringen unsere Änderung in das entfernte Repository/nun können andere Mitarbeiter auch auf diese zugreifen__  
  142  cd ~/.ssh  
  143  ssh -keygen  
  144  ssh keygen  
  145  ssh-keygen                                             __wir generieren ein Schlüsselpaar__  
  146  cd ~/.ssh  
  147  ll  
  148  cat id_rsa.pub                                         __wir sehen nun unseren öffentlichen Schlüssel, den wir für die Konfiguration der Verschlüsselung unseres Gits benötigen__  
  149  exit  
  150  cd la1  
  151  sudo rm -r labor  
  152  ll  
  153  git clone git@github.com:****/labor.git  
  154  git checkout stunde4  
  155  cd labor  
  156  git checkout stunde4  
  157  nano main.c  
  158  git commit -m "Erste Aenderung mit SSH"  
  159  git add main.c  
  160  git commit -m "Erste Aenderung mit SSH"  
  161  git push  
  162  git status  
  163  git checkout master  
  164  git status   
  165  git merge stunde4                                    __Änderung des aktuellen Branch werden mit dem master branch zusammengeführt__  
  166  git push  
  167  exit  
  
### Versionsverwaltung [siehe auch](https://de.wikipedia.org/wiki/Versionsverwaltung)
Sie ist dazu da, um ältere Versionen einer Software aufrufen zu können, falls eine fehlerhafte Datei hochgeladen, gespeichert oder auch weiterverarbeitet wurde.
Ein Beispiel hierführ ist auch Wikipedia. Da zu jedem Versionswechsel die grundlegenden Angaben wie Verfasser und Uhrzeit festgehalten werden, kann genau nachvollzogen werden, wer wann was geändert hat.

## Github

[Github](https://github.com/) ist eine Plattform, auf der man mit der freien Software Git arbeiten kann. Sie ist benutzerfreundlich aufgebaut und man kann sie kostenfrei verwenden, solang man seine Repositories öffentlich hält.
D. h., dass das Repository von allen Personen eingesehen werden kann, jedoch nicht bearbeitet.
Im Gegenteil dazu kann man auch private Repositories für Geld erwerben. Diese sind dann nur für berechtigte Personen einsichtig.
Benötigt werden Plattformen wie diese, um das Arbeiten eines größeren Teams an einem Projekt zu ermöglichen und zu dokumentieren, während man durch die Dokumentationen tritzdem noch den Überblick behalten kann, da eine Versionsverwaltung (siehe Versionsverwaltung) zu Verfügung steht.

## Markdown
Ein einfacher Weg eine Textdatei in eine HTML Datei umzuwandeln.

### Formatierungszeichen
Eine kleine Zusammenfassung der Möglichkeiten, die Markdown bitet (ausführliche Anleitung zu finden unter [Mastering Markdown](https://guides.github.com/features/mastering-markdown/): 

Ein "# " vor einer Zeile erzeugt eine Überschrift. Je mehr "# " man am Stück verwndet (Bsp.: "## ") desto untergeordneter wird die Überschrift.
Ein "*" am Anfang und am Ende eines Wortes oder einer Phrase macht dieses kursiv. Dies ist auch mit einem "_" möglich.
Ein "**" am Anfang und am Ende eines Wortes oder einer Phrase macht dieses fett. Dies ist auch mit einem "__" möglich.
Falls man Listen erstellen möchte, so macht man dies mit einem "* " am Anfang einer jeden gewünschten Zeile. Falls man diese auch noch numerisch ordnen möchte, verwendet man statt des Sternchens ein"1. "
