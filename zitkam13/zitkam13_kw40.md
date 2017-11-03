# Protokoll  

## Mikroprozessor  
Am Beginn der Stunde wiederholten wir den prinzipiellen Aufbau der CPU.  
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
