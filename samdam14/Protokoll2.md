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
#### Prozessorfenster  
**Programm Counter**  
* Gibt Adresse des nächsten Maschinenbefehls  
**Cycle Counter**  
* Gibt an, wie viele Zyklen seit dem letzten Reset durchgelaufen sind  
**X-/Y-/Z-Register**  
Um die 2048Byte nutzen zu können, bräuchte man theoretisch mehr als 32 Register (32 Register => 255 Werte). Im ATmega328 wurde die mit dem X-/Y-/ und Z-Register umgesetzt:  
Register | Zusammensetzung  
-------- | ---------------  
X | R27&R26  
Y | R29&R28  
Z | R31&R30  
##### Projekt anlegen  
* new  
  * project  //Projekt anlegen  
* Atmel Boards  
  * STK600ATmega328   //Board auswählen  
* Kompellieren  
* Debuggen  
  * simulate    //Debugger auswählen  
  * speichern  
* Reset  
  * debug -> windows -> disassembly   //nun befindet man sich im _disassembly_  
  * disassembly: debug -> reset   //Reset  
  * mit F11 kann man jeden Maschinenbefehl eines Programms extra Aufrufen lassen  
----------------------------------------------  
##### Instruction Set Manual  

##### Beispiel  
int main (void)  
{  
  return 0;  
}  

-----------------------------------  
###### RJMP 33.c0  
* RJMP springt zu einer Adresse innerhalb des Program Counters PC (von -2k bis +2k)  
* Wenn der Programmspeicher kleiner als 4k ist, dann kann an jede beliebige Stelle gesprungen werden  
  
33.c0 => 0011 0011[Byte 2] 1100 0000[Byte 1]  
1100 0000 0011 0011 Maschinenbefehl  
Muster für JMP: **11**kk kkkk kkkk kkkk  

----------------------------------------------   
###### 
