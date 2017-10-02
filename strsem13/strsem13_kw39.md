# *Protokoll*
## *Thema: Git - Linux*
 Name:   Sebastian Strutz  
 Klasse: 4AHME  
 Datum: 26.09.2017  
 Anwesend: Strutz, Strauß, Tuttner, Uhl, Waltl, Wieser, Zitz  
### *Repoitory klonen*  
Um an einem Repository am Linux System arbeiten zu können, muss man es sich zuerst vom Github-Server kopieren.  
Dies funktioniert auf 2 Verschieden Arten:
* Mit einem Link   
* Über SSH  
Beide Links findet man bei GitHub in dem Repository, unter dem Buuten clone or download, auf den rechten-oberen Eck kann man zwischen dem SSH-, und dem HTTPS- Link auswählen.  
### *Datein beareiten*  
Da sich jetzt das gewünschte Repository auf dem Rechner befindet kannman mittels der Konsole, oder dem Dateimanager die Daten ändern. Um das geänderte wieder mit dem GitHub-Server zu synchronisieren benötigt man folgende Befehle:  

*git add -A (-A Damit alle Dateien kopiert werden, und nicht nur einzelne)  
Mit dem Befehl **git add** werden die Dateien zum Index transferiert.  

*git commit -m "Kommentar" (-m damit man ein Kommentar einfügen kann)  
Mit dem Befehl **git commit** werden die Daten vom Index zum lokalen Repository tranferiert  

*git push  
Mit dem Befehl **git push** werden die Daten vom lokalen Repository zum Server transferiert.  

