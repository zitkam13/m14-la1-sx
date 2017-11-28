# _Protokoll Erste Einheit_  

**Name: Daniel Sammer**  
**Gruppe: 3**  
**Datum: 21.11.2017**  
**Uhrzeit: 9:40-12:25**  
  
**Anwesenheit: _Es waren alle Schüler anwesend_**  
  
-----------------------------------------------------------  
### Git-Hub  
#### Issues  
* Kommentieren eines Repositories  
  * Teammitglieder können mittels _issues_ den Benutzer, der ein Projekt bearbeitet, auf Fehler aufmerksam werden und/oder ihm Tipps geben. Der Benutzer kann _issues_ wieder schließen (_close_).  
  * Übersicht mit _open_ und _closed_ _issues_.  
  * Kommunikationsplattform  
  
mehr dazu: [MasteringIssues](https://guides.github.com/features/issues/)  
##### Fork  
Mit _fork_ kann man eine exakte Kopie eines fremden Projekts in seinem eigenen Repository erstellen. Diese Funktion kann genutzt werden, wenn sich der eigentlicher Ersteller eines Projekts nicht auf einen _issue_ meldet und man die Lösung des Problems finden möchte. Der Ersteller sieht dann, dass es einen _fork_ gibt, den er dann suchen kan, um mögliche Änderungen zu übernehmen.  
_Fork_ kann auch auch genutzt werden, wenn sich der eigentlicher Ersteller eines Projekts nicht mehr meldet und man das Projekt weiterleben lassen möchte.  
##### Pull Request  
Mittels *pull request* kann ein Benutzer die Kopie des Repositories, die mittels *fork* erstellt wurde, dem eigentlichen Ersteller anbieten, die Änderungen zu übernehmen.  

Vereinfachte Erklärung:   
Benutzer A bearbeitet sein Repository  
Benutzer B erstellt mittels _fork_ eine Kopie und bearbeitet dieses dann in seinem Repository  
Benutzer B möchte seine Änderungen preisgeben und stellt einen _pull request_  
Benutzer A wird benachrichtigt und kann diesen _pull request_ _commiten_, um Änderungen zu übernehmen  
[PullRequest](https://help.github.com/articles/about-pull-requests/)   

---------------------  
### Atmel Studio  
* Entwicklungsumgebung für die Programmierung von AVR- und ARM-Mikrokontrollor  
* Kostenlos von Atmel zu Verfügung gestellt  
* Basiert auf Virtual Studio Shell von Microsoft (ab Verion 5)  
  * funktioniert daher nur auf PC's mit Windows-Betriebssystem  
  * Alternativen zur Programmierung: NetBeans  
* Programmiersprachen: Assembler, C, C++  
#### Bestandteile von Atmel Studio  
* Projektverwaltung  
* Editor  
* Debugger  
* Werkzeuge zur Beschreibung von µC  
[Atmel Studio](http://www.atmel.com/)   
[Mikrocontroller.net/Atmel Studio](https://www.mikrocontroller.net/articles/Atmel_Studio)  

--------------------------------------------  
##### Projekt anlegen  
* new  
  * project  //Projekt anlegen  
* Atmel Boards  
  * STK600ATmega328   //Board auswählen  
* Kompellieren  
* Debugg  
  * simulate    //Debugger auswählen  
  * speichern  
##### Prozessorfenster  
**Programm Counter**  
* Gibt Adresse des nächsten Maschinenbefehls  
**Cycle Counter**  
* Gibt an, wie viele Zyklen seit dem letzten Reset durchgelaufen sind  

In disassembly (debug-> windows-> diassembly)   
	Debug -> reset   
