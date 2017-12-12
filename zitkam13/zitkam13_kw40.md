# Protokoll  

## Mikroprozessor  
Am Beginn der Stunde wiederholten wir den prinzipiellen Aufbau der CPU.  
![CPU](/zitkam13/CPU.PNG)  
Quelle: [FIVU Skript](https://lms.at/dotlrn/classes/informatik/610437.4AHME_FIVU.17_18/xolrn/EC743ABCF7AB5.symlink?resource_id=0-237409759&m=view#188315330)  

**Befehlsaufbau** (Von-Neumann-Architekur)  
* Reset :arrow_right: bringt das System in den Ausgangszustand, der Befehlszähler wird auf den Wert 0 gesetzt und die Bits im Status-Flag werden auch zurükgesetzt  
* Takt  :arrow_right: bestimmt den zetilichen Ablauf (auch Clock genannt)  
* Steruerwerk :arrow_right: lädt den nächsten Befehl aus dem Speicher  
* Befehls-Decoder :arrow_right: dekodiert den Befehl und erzeugt Signale und einen Maschinencode für interne Steuerleitungen  
* ALU :arrow_right: "Arithmetic Logic Unit" :arrow_right: führt Rechenoptionen durch  
* Programcounter :arrow_right: wird aktualisiert  

## ATmega328p  
In der Schule verwenden wir den Mirkrocontroler ATmega328p. Da es diesen bei Atmel Studio aber nicht gibt verwendeten wir den ATmega328.  
[Datenblatt ATmega328/p](http://www.atmel.com/Images/Atmel-42735-8-bit-AVR-Microcontroller-ATmega328-328P_Datasheet.pdf)    


**Produktdaten**  
* Frequenz: 16MHz  
* CPU-Register: 32 (jedes Register besteht aus 8 Bit)  
* Flash Speicher: 32kB  
* EEPROM: 1kB  
* SRAM: 2kB  

**XYZ-Register**  
Für die Speicherung eines Wertes über 255, git es beim ATmega328p die **XYZ-Register**. Diese setzten sich zusammen aus:  
* X :arrow_right: 26 und 27  
* Y :arrow_right: 28 und 29  
* Z :arrow_right: 30 und 31  

## Atmel Studio  

Atmel Studio (zuerst AVR-Studio) ist eine Open-Source Software und dient zur Programmierung von AVR-Mikroprozessoren. Das Programm basiert auf der Visual Studio Shell von Microsoft und besteht aus einem Editor, einem Debugger und Werkzeugen für das Beschreiben eines Mikroprozessors.   

Mit Atmel Studio kann man in Assembler, C und C++ programmieren. Atmel Studio ermäglicht eine Simulation auf einem Atmel-Mikrokontroller. Man erhält auch eine detallierte Information über die Maschinenbefehle, die aus dem programmierten Quellcode kompiliert wurden. Man hat auch einen Einblick in die Register des Controllers.  

## Debugger  
Nach dem Übersetzen des Programms kann man in den Debug-Modus wechsekn und in bestimmte Werte der CPU einsehen.(zum Beispiel: **Program Counter**, **Stack Pointer**, **Status Register**, **XYZ Register** und **Cycle Counter**) Der **Cycle Counter** zeigt die gebrauchten Zyklen zur Durchführung des Programs an.   

**Einige Maschinenbefehle**    

Maschinenbefehl | Ergebnis
--------------- | --------
JMP | Sprung zu einer bestimmten Adresse (benötigt 8 Bytes)
RJMP | Sprung zu einer Adresse (Offset muss eingehalten werden, benötigt 4 Bytes)
OUT | schreibt Daten von einem in ein anderes Register
CLR | Register wird mit Nullen überschrieben (Realisierung durch XOR-Verknüpfung mit sich selbst)
SER | Register wird mit Einsen überschrieben bzw. auf den höchstmöglichen Wert gesetzt
LDI | Konstante wird in Register geschrieben (nur bei Registern 16-31 möglich)  

## Stack  
Im Stack werden Daten nach dem **Last in frist out(LIFO)** Verfahren gespeichert. Das heißt die Daten welche als letztes in den Stack kommen, kommen als erstes heraus. 

Um in den Stack Daten zu speichern, bzw daraus zu lesen gibt es folgende Operationen:  

- push: "Legt die Daten auf den Stapel"
- pop: Liest das oberste Objekt aus und entfernt es aus dem Stack
- peek: Liest das oberste Objekt aus, aber belässt es auf dem Stapel

### Stackpointer  
Der **Stackpointer** zeigt immer auf den nächsten freien Platz im Stack-Speicher. Wenn der Stack leer ist zeigt der Stackpointer also auf den untersten Platz im Speicher. Wenn der Satckpointer allerdings über den reservierten Speicherplatz hinaus geht, spricht man von einem Stackoverflow.
