# _Protokoll Zweite Einheit_  

**Name: Daniel Sammer**  
**Gruppe: 3**  
**Datum: 28.11.2017**  
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
### Aufbau der CPU eines ATmega328P  
Bevor wir mit Atmel Studio begonnen haben, haben wir die einzelnen Bausteine einer CPU eines µC's besprochen, da sich diese in kurzer Zeit in Atmel Studio wiederfinden werden lassen.  
* Program Counter  
  * liefert die Adresse des nächsten Maschinenbefehls  
* Stack Pointer  
  * zeigt auf den nächsten freien Platz im Stack  
* Befehls Register  
  * empfängt Maschinenbefehle und speichert sie zwischen, während sie ausgeführt werden  
* Statusregister  
  * Flagregister, gewisse Zustände werden hier, während Befehle ausgeführt werden, gespeichert  
![CPU-Aufbau](https://github.com/HTLMechatronics/m14-la1-sx/blob/samdam14/samdam14/CPU_Aufbau.svg)  
### Atmel Studio  
![AtmelLogo](https://github.com/HTLMechatronics/m14-la1-sx/blob/samdam14/samdam14/atmel.jpg)  
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
* X -> R27&R26  
* Y -> R29&R28  
* Z -> R31&R30  
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
  
Info's zum µC: [ATmega328 Wiki](https://en.wikipedia.org/wiki/ATmega328)  

----------------------------------------------  
##### Instruction Set Manual  
Im _instruction set manual_ kann man die wichtigsten Maschinenbefehle und deren Beschreibungen nachschauen.  
[Instruction Set Manual](http://www.atmel.com/images/Atmel-0856-AVR-Instruction-Set-Manual.pdf)  

----------------------------------------
##### Beispiel  
int main (void)  
{  
  return 0;  
}  
Die folgenden Maschinenbefehle können im _instruction set manual_ genauer durchgelesen werden.  

-----------------------------------  
###### RJMP 33.c0  
* RJMP springt zu einer Adresse innerhalb des Program Counters PC (von -2k bis +2k)  
* Wenn der Programmspeicher kleiner als 4k ist, dann kann an jede beliebige Stelle gesprungen werden  
  
33.c0 => 0011 0011[Byte 2] 1100 0000[Byte 1]    //Byte 1 und 2 sind hingegen zum _instruction set manual_ vertauscht  
1100 0000 0011 0011 Maschinenbefehl  -> 11=JMP, k=51  
Muster für JMP: **11**kk kkkk kkkk kkkk  

----------------------------------------------   
###### CLR  
* Clear ist eigentlich eine Exklusiv-Oder-Verknüpfung (ein Register wird mit sich selbst verknüpft = Output ist immer 0  
  * EXOR Register(d), Register(r)
* Zero-Flag wird gesetzt  
* Muster: **0010 01**rd dddd rrrr -> EXOR Register(d), Register(r)  

---------------------------------------------  
###### OUT 0x3F, R1  
* OUT speichert Daten vom Rr Register ins I/O-Register(SREG)  
* Ins Statuslag-Register (SREG) wird R1 reingeschrieben  
* Zero-Flag wird deaktiviert  
* Muster: **1011 1**AAr rrrr AAAA
* be.1f = 1011 1110 0001 1111 A=3f; r=1-> Register 1  

------------------------------------------------  
###### SER R28  
* Set Register  
* R28 wird auf 0xFF gesetzt  

----------------------------------------  
###### LDI R29(d), 0x08(k)  
*	Load Immediate  
* Ladet 8 Bit direkt ins Register 16-31  
* Muster: **1110** kkkk dddd kkkk  
*	e0d8 = 1110 0000 1101 1000 k=8, d=13
*	R29 wird auf 8 gesetzt  

-------------------------------------------  
###### OUT 0x3E R29  
*	3E= SPH (Stackpointer auf 0x0800 gesetzt)  

------------------------------------------
###### OUT 0x3D R28  
*	3D= SPL (Stackpointer auf 0x08FF gesetzt)  

----------------------------------------
###### RCALL PC+3  
*	Do02 =1101 0000 0000 0010 k=2  
*	Muster: **1101** kkkk kkkk kkkk  
* Stack -> PC +1  
* SP=SP-2   //SP=Stackpointer  

--------------------------------------  
###### LDI R24, 0x00  
*	R24 wird auf 0 gesetzt  

-------------------------------  
###### LDI R25, 0x00  
*	R25 wird auf 0 gesetzt  

--------------------------------  
###### RET  
*	Subroutine return  

-----------------------------------  
#### Aufbau einer SRAM  
![Aufbau SRAM ATmega328P](https://github.com/HTLMechatronics/m14-la1-sx/blob/samdam14/samdam14//sram.jpg)  
**SRAM bestehen aus:**  
*	Globale Variablen  
*	Heap  
  * dynamische Speicherverwaltung  
*	Freier Speicher  
*	Stack  
  * Daten werden unten im Stack eingefügt  
  * Obersten Daten sind somit die ältesten Daten und müssen als nächstes verarbeitet werden (last in, first out)  
  * [wiki/Stack](https://de.wikipedia.org/wiki/Stapelspeicher)  
* SRAM Adresse beginnt nicht bei 0, sondern bei 0x100  
##### Stackpointer  
* Stackpointer zeigt auf den nächsten freien Platz im Speicher  
* In unserem Fall setzen wir ihn nach dem Reset auf 0x08FF (erster freier Platz)  
* Zeigt der Stackpointer auf einen besetzten Platz, dann ergibt sich ein Systemabsturz (_**Stackoverflow**_)  

