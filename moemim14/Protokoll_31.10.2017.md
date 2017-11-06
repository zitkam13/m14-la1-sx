# Protokoll 1 31.10.2017

## Thema: Einführung in Github

Name: Michael Mörth  
Klasse: 4AHME  
Gruppe: 2  

Anwesend: Nebel Florian, Mandl Gerhard, Michael Mörth, Moritz Martinak, Mario Nabernik, Muri Lorenz, Platzer Andreas, Marcel Köhler    
Abwesend: -

## Was ist Git? Was ist Github?
**Git ist eine freie Software, welche zur Verwaltung von Dateien genützt wird.
Der Sinn von Git ist es, eine Arbeit im Team zu ermöglichen.**

Unterschiede zu anderen Versionsverwaltungen:
* Das Erstellen von den Programmen ist meist nicht linear. 
* Große Bestandteile von Git sind das Erstellen und Verschmelzen von Entwicklungszweigen.
* Kein Zentraler Server
  * Jeder benutzer hat eine lokale Kopie des gesamten Repositories (local repository)
  * Es wird kein Internetzugriff erfordert (man kann also überall darauf zugreifen und damit arbeiten)
  * Synchronisation über das Internet möglich
  * Sollten zwei Personen gleichzeitig eine Änderung an der selben Datei durchführen und synchronisieren, werden beide Dateien hochgeladen und es entsteht ein Konflikt der gelöst werden muss


## 5.SSH Git-Repository

### Konfigurieren von Github 
1. SSH-Schlüsselpaar erzeugen und public-key unter settings - SSH and GPG Keys einfügen
*das erzeugen des SSH-Schlüsselpaars kann [hier](https://help.github.com/articles/connecting-to-github-with-ssh/) genauer nachgelesen werden.

2. SSH-Config konfigurieren zur Verbindung mit Github

	1. Config-Datei öffnen: nano ~/.ssh/config
	2. Hinzufügen des Hosts github:
		
		Host github  
			Hostname github.com  
			User git  
