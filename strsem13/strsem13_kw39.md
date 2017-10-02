# *Protokoll*
## *Thema: Git - Linux*
 Name:   Sebastian Strutz  
 Klasse: 4AHME  
 Datum: 26.09.2017  
 Anwesend: Strutz, Strauß, Tuttner, Uhl, Waltl, Wieser, Zitz  
### *Repository klonen*  
Um an einem Repository am Linux System arbeiten zu können, muss man es sich zuerst vom Github-Server kopieren.  
Dies funktioniert auf 2 Verschieden Arten:
* HTTPS  
![HTTPS](https://github.com/HTLMechatronics/m14-la1-sx/blob/strsem13/strsem13/Befehl%20clone.png) 
* SSH  

Beide Links findet man bei GitHub in dem Repository, unter dem Button clone or download, auf den rechten-oberen Eck kann man zwischen dem SSH-, und dem HTTPS- Link auswählen.  
![Link](https://github.com/HTLMechatronics/m14-la1-sx/blob/strsem13/strsem13/Links%20vom%20Repository.png)  

### *Datein bearbeiten*  
Da sich jetzt das gewünschte Repository auf dem Rechner befindet kannman mittels der Konsole, oder dem Dateimanager die Daten ändern. Um das geänderte wieder mit dem GitHub-Server zu synchronisieren benötigt man folgende Befehle:  

* git add -A (-A Damit alle Dateien kopiert werden, und nicht nur einzelne)  
Mit dem Befehl **git add** werden die Dateien zum Index transferiert.  
![add](https://github.com/HTLMechatronics/m14-la1-sx/blob/strsem13/strsem13/git%20add.png)  

* git commit -m "Kommentar" (-m damit man ein Kommentar einfügen kann)  
Mit dem Befehl **git commit** werden die Daten vom Index zum lokalen Repository tranferiert  
![commit](https://github.com/HTLMechatronics/m14-la1-sx/blob/strsem13/strsem13/git%20commit.png)

* git push  
Mit dem Befehl **git push** werden die Daten vom lokalen Repository zum Server transferiert.  
![push](https://github.com/HTLMechatronics/m14-la1-sx/blob/strsem13/strsem13/git%20push.png)  

* git checkout -b "Branch_Name"
Mit diesem Befehl erstellt man einen Branch, wenn man auf einem gemeinsamen Repository arbeitet, kann dass sehr nutzvoll sein, weil dadurch das ganze Repository viel übersichtlicher ist.  

### *SSH Schlüssel*  
Es ist sehr praktisch wennman sich über SSH mit dem GitHub-Server verbindet, weil man dann kein Passwort und Benutzernamen mehr braucht. Um sich mit dem GitHub-Server zu verbinden muss man zuerst ein RSA-Schlüsselpaar erstellen.  
Das fuktioniert mit dem Befehl **ssh-keygen**.    
![ssh-keygen](https://github.com/HTLMechatronics/m14-la1-sx/blob/strsem13/strsem13/ssh-keygen.png)  
Danach muss man den öffentlichen Schlüssel **id_rsa.pub** kopieren, dass geht am einfachensten wenn man ihn mit dem Befehl **less id_rsa.pub** öffnet und mit dem Mausrad kopiert.  
![ssh ordner](https://github.com/HTLMechatronics/m14-la1-sx/blob/strsem13/strsem13/ssh%20ordner.png)  
Als nächstes muss die Seite [GitHub-Keys](https://github.com/settings/keys) geöffnet werden. Wenn man dann auf den Button **New SSH key** drückt kannman den öffentlichen Schlüssel reinkopieren.  
![Github-Keys](https://github.com/HTLMechatronics/m14-la1-sx/blob/strsem13/strsem13/SSH.png)  

### *Atmel AVR Studio*  
Atmel AVR Studio ist ein Programm mit dem man Microcontroller programmieren uund auch simulieren kann.  
Dadurch das Programm noch nicht funktioniert hatt, haben wir noch nicht viel darüber gehört.  
AVR-Studio gibt es nur für Windows Betriebssysteme.  
Die Benutzeroberfläche sieht wie folgt aus:
![AVR-Studio](https://www.google.at/url?sa=i&rct=j&q=&esrc=s&source=images&cd=&cad=rja&uact=8&ved=0ahUKEwity4zr4NLWAhXDVxoKHfMsBrYQjRwIBw&url=http%3A%2F%2Fmaxembedded.com%2F2011%2F06%2Fusing-avr-studio-5%2F&psig=AOvVaw2zM2yG3RDnaQYPRAfPaEBx&ust=1507061701826297)  
Quelle: [Link](http://maxembedded.com/2011/06/using-avr-studio-5/)
