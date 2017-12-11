
# *Protokoll Labor KW40*
## *Themen: AVR-Studio, Simulation*

Name: Raphael Tuttner    
Klasse: 4AHME    
Gruppe: 4  
Datum: 03.10.2017

### *Mikroprozessor (µC)*  
Als erstes haben wir den Aufbau einer CPU (Central Processing Unit) besprochen:  
![CPU Blockdiagramm](https://github.com/HTLMechatronics/m14-la1-sx/blob/tutram12/tutram12/Download.svg)  
BeFehlsablauf (Von-Neumann-Architektur):  
* Reset:                       - bringt die System-CPU in einen Ausgangszustand  
                               - setzt den Befehlscounter auf 0  
                               - die Bits im Status-Flag werden zurückgesetzt  
* Clock (Takt):                bestimmt den zeitlichen Ablauf  
* Steuerwerk:                  ladet den nächsten Befehl aus dem Speicher  
* Befehls-Decoder:             dekodiert den Befehl und erzeugt Maschinencodes und Signale für die internen Steuerleitungen  
* ALU (Arithmetic Logic Unit): führt die Rechenoperationen aus  
* Programcounter:              wird mit jedem Durchlauf aktualisiert

### *Atmel Studio*  
Atmel Studio, früher auch als AVR-Studio bekannt, ist eine Open-Source-Software mit der man Atmel-µC's programmieren und simulieren kann.  
Es basiert auf der Visual Studio Shell von Microsoft und besteht aus:
* einer Projektverwaltung  
* einem Editor  
* einem Debugger  
  
und Werkzeugen zum Beschreiben eines Mikroprozessors.  
  
Mit dem Atmel Studio kann in Assembler sowie in C/C++ programmiert werden.  
Beim simulieren erhält man detaillierte Informationen über die Maschinenbefehle, die aus dem Quellcode kompiliert wurden.  
Zudem hat man Einblick in die Register des Controllers.  
  
### *ATmega328p*  
Wir verwenden in der Schule den Mikrocontroller ATmega328p von Atmel.  
Weil dieser aber im Atmel Studio nicht verfügbar ist, verwenden wir den Mikrocontroller ATmega328.  
[Datenblatt-ATmega238p](http://www.atmel.com/Images/Atmel-42735-8-bit-AVR-Microcontroller-ATmega328-328P_Datasheet.pdf)  
#### *Produktdaten*  
* CPU-Register: 32 (jedes Register bestaht aus 8 bit)  
* Frequenz: 16MHz   
* Flash Speicher: 32kB 
* SRAM: 2kB   
* EEPROM: 1kB  

#### **XYZ-Register** 
Wird benötigt um Werte zu speichern, die größer als 255 sind.  
Dieses Register setzt sich zusammen aus:  
* X= 26 & 27  
* Y= 27 & 28  
* Z= 30 & 31  
  
### *Stack*  
Im Stack-Speicher, auch Stapelspeicher, werden Daten nach dem LIFO Verfahren(last-in-first-out) gespeichert.  
Das heißt das die Daten von unten nach oben abgelegt werden aber nur von oben nach unten gelesen werden können.  
Um mit dem Speicher zu kommunizieren, benötigt man folgende Operanden:  
* push: Speichert die Daten an die oberste stelle im Stapel  
* pop:  Liest das oberste Objekt aus, und entfernt es vom Stack  
* peek: Liest das oberste Objekt aus, und behält es am Stack  
  
#### *Stackpointer*  
Der Stackpointer zeigt immer auf den nächsten freien Platz im Stack-Speicher.  
Das gefährliche an einem Stack ist der sogennante **Stackoverflow**.  
**Stackoverflow** bedeutet, dass der Stack-Speicher voll ist,  
und wenn das passiert, ist es möglich bzw. sehr wahrscheinlich dass das System abstürtzt.  
  
### *Debugger*  
Wenn man ein programm fertig übersetzt hat, kann man in den Debug-Modus wechseln. Dort kann man dann bestimmte Werte der CPU sehen.  
Jetzt kann man den Wert des **Program Counter** (Speicheradresse des derzeitigen Befehls), dem **Stack Pointer**,  
den **XYZ Registern** und dem **Status Register** (beinhaltet die Status-Flags) sehen.  
Weiters sieht man den **Cycle Counter**, dieser zeigt, wieviele Zyklen durchgelaufen wurden, um das Prgoramm auszuführen.  
Man kann auch sehen welche Register und Bits gesetzt wurden. Aus dieser Hilfe (und dem [Instruction Set Maanual](http://www.atmel.com/images/Atmel-0856-AVR-Instruction-Set-Manual.pdf)) kann man ermitteln, welche Befehle ausgeführt werden.  

Befehle über die wir uns informiert haben:
* *RJUMP* -> führt einen Sprung zu einer Adresse durch.  
* *CLR*   -> "Clear Register" Exklusive Oder Verknüpfung mit sich selbst.  
* *OUT*   -> Ein bestimmtes Register wird einem Register der CPU zugewiesen.    
* *SER*   -> Setzt alle Bits im Register.  
* *LDI*   -> Lädt eine 8-Bit Konstante in ein Register.  
* *RCALL* -> Stack Pointer wir um 2 reduziert; Adresse wird im Stack gespeichert.   
* *RET*   -> Stack pointer wird um 2 erhöhrt; Adresse wird vom Stack geladen.  
* *PUSH*  -> Speichert Register auf Stack.  
* *POP*   -> Ladet Register vom Stack.  
* *IN*    -> Ladet Daten vom I/O Register.  
* *STD*   -> Speichert einzelne Bytes vom Register in ein Datenraum(z.B. Stack).  
* *SUBI*  -> Subtrahiert ein Register mit einer Konstanten.  
