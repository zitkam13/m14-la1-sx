# *Protokoll*  
## *Thema: AVR-Studio*
 Name:   Sebastian Strutz  
 Klasse: 4AHME  
 Datum: 26.09.2017  
 Anwesend: Strutz,Tuttner, Uhl, Waltl, Wieser, Zitz  
 
 ### *Mikroprozessor (µP)*
 Zuerst haben wir den prinzipiellen Aufbau einer CPU besprochen:  
 ![CPU Blockdiagramm](https://github.com/HTLMechatronics/m14-la1-sx/blob/strsem13/strsem13/cpu.svg)  
 Befehlsablauf (Von-Neumann-Architektur):  
 * Reset -> bringt das System CPU in einen Ausgangszustand, der Befehlszähler afu den Wert 0 gesetzt, und die bits im Status-Flag werden zurückgesetzt.
 * Takt -> auch Clock gennant, bestimmt den zeitlichen Ablauf.  
 * Steuerwerk -> lädt aus dem Speicher den nächsten Befehl.  
 * Befehls-Decoder -> dekodiert den Befehl, und erzeugt einen Maschinencode und Signale für die internen Steuerleitungen.  
 * ALU -> "Arithmetic Logic Unit" -> führt die Rechenoperationen durch.
 * Programcounter -> wird aktualisiert. 
 
 
 ### *Atmel Studio*  
Atmel Studio (früher AVR-Studio) ist eine Open-Source Software zur Programmierung der AVR-Mikroprozessoren. Es basiert auf der Visual Studio Shell von Microsoft und besteht aus einer Projektverwaltung, einem Editor, einem Debugger und Werkzeugen zum Beschreiben eines Mikroprozessors.  

Mit dem Atmel Studio kann in Assembler sowie in C/C++ programmiert werden.  
Mit Atmel Studio kann man die Ausführung eines Programms auf einem Atmel-Mikrokontroller simulieren. Man erhält detaillierte Informationen über die Maschinenbefehle, die aus dem Quellcode kompiliert wurden. Außerdem hat man Einblick in die Register des Controllers.  

### *ATmega328p*  
Wir verwenden in der Schule den Mikrocontroller ATmega328p von Atmel, dadurch dieser in Atmel Studio nicht verfügbar ist, verwendeten wir den Mikrocontroller ATmega328.  
[Datenblatt-ATmega238p](http://www.atmel.com/Images/Atmel-42735-8-bit-AVR-Microcontroller-ATmega328-328P_Datasheet.pdf)  
#### **Produktdaten**  
* CPU-Register: 32 (jedes Register bestaht aus 8 bit)  
* Frequenz: 16MHz   
* Flash Speicher: 32kB 
* SRAM: 2kB   
* EEPROM: 1kB  

#### **XYZ-Register**  
Wird benötigt um Werte zu speichern, die größer als 255 sind.  
Setzt sich zusammen aus:  
* X= 26 & 27  
* Y= 27 & 28  
* Z= 30 & 31  

### *Stack*  
Im Stack-Speicher, auch Stapelspeicher, werden Daten nach dem LIFO Verfahren(last-in-first-out) gespeichert. Das heißt, die Daten werden von unten nach oben abgelegt, gelesenn können die Daten aber nur von oben nach unten.  
um mit dem Speicher zu kommunizieren, benötigt man folgende Operanden:  
* push: "Legt" die Datei auf den Stapel  
* pop: Liest das oberste Objekt aus, und entfernt es vom Stack  
* peek: List das oberste Objekt aus, und behält es am Stack  

#### *Stackpointer*  
Der Stackpointer zeigt immer auf den nächsten freien Platz im Stack-Speicher. Das gefährliche an einem Stack ist der sogennante "**Stackoverflow**". **Stackoverflow** bedeutet, dass der Stack-Speicher voll ist, und wenn das passiert, ist es möglich bzw. sehr wahrscheinlich dass das System abstürtzt.  

### *Debugger*  
Wenn man ein programm fertig übersetzt hatt, kann man in den Debug-Modus wechseln. dort kann man dann, bestimmte Werte der CPU sehen. jetzt kann man den Wert des **Program Counter** (Speicheradresse des derzeitigen Befehls), dem **Stack Pointer**, den **XYZ Registern** und dem **Status Register** (beinhaltet die Status-Flags) sehen. Weiters sieht man den **Cycle Counter**, dieser zeigt, wieviele Zyklen durchgelaufen wurden, um das Prgoramm auszuführen.  
man kann uach sehen welche Register und Bits gesetzt wurden. Aus dieser Hilfe(und dem [Instruction Set Maanual](http://www.atmel.com/images/Atmel-0856-AVR-Instruction-Set-Manual.pdf)) kann man ermitteln welche Befehle ausgeführt werden.  

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


