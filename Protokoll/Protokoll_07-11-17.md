# Protokoll der 2.Einheit
* Name: Mario Nabernik
* Klasse: 4AHME
* Datum: 07.11.2017
* Gruppe: 2
* Anwesend: Marcel Köhler, Michael Mörth, Florian Nebel, Lorenz Muri, Moritz Martinak, Andreas Platzer, Mario Nabernik, Gerhard Mandl  
* Abwesend: -
* Thema: Atmel Studio


## Was ist Atmel Studio?
[Atmel Studio](http://www.atmel.com/microsite/atmel-studio/) ist eine von Atmel zur Verfügung gestellte __kostenlose__ Entwicklungsumgebung für Mikrocontroller.
Diese Entwicklungsumgebung besteht aus einer Projektverwaltung, einem Editor, einem Debugger und Werkzeugen zum Beschreiben der Mikrocontroller. 


_Download:_ 
[Atmel Studio](http://www.atmel.com/Microsite/atmel-studio/default.aspx)

## Mikrocontroller
In der Schule arbeiten wir mit dem __Atmega 328p__ und simulieren den sehr ähnlichen __Atmega 328__.

### Produktdaten  
* CPU-Register: 32 (jedes Register hat 8 Bit)  
* Frequenz: 16MHz   
* Flash Speicher: 32kB 
* SRAM: 2kB   
* EEPROM: 1kB 

### Register
#### XYZ-Register
XYZ-Register sind Register, welche vom Atmel328p dazu verwendet werden, um Werte >255 zu speichern. 
Aufbau dieser Register:
* X = Register 26+27
* Y = Register 28+29
* Z = Register 30+31
  
  
#### Weitere Register
* Register 3F = SREG / Statusflagregister
* Register 3E = SPH / Stackpointer initialisieren (Register __07-15__)
* Register 3D = SPL / Stackpointer initialisieren  (Register __00-07__)


_Datenblatt:_ [Atmega 328p](http://www.atmel.com/Images/Atmel-42735-8-bit-AVR-Microcontroller-ATmega328-328P_Datasheet.pdf)


## Stack und Heap
### Stack
Der Stack (Stapelspeicher) ist eine dynamische Datenstruktur, welche von den meisten Mikroprozessoren in der Hardware unterstützt wird.
Er funktioniert so, dass der Stapel eine begrenzte Menga an Objekten __aufeinanderstapeln__ kann. Diese Elemente können aber nur wieder in umgekehrter Reihenfolge vom Stapel heruntergenommen werden ([Last-In-First-Out-Prinzip](https://de.wikipedia.org/wiki/Last_In_%E2%80%93_First_Out)).

![Stack](https://upload.wikimedia.org/wikipedia/de/thumb/b/b5/Lifo.svg/602px-Lifo.svg.png)

#### Stackpointer
Ein Stackpointer ist ein Zeiger, welcher immer auf den __nächsten freien Speicherplatz__ im Stack zeigt.
Ist der Stapelspeicher leer, so zeigt dieser auf den untersten Speicherplatz. Bei unserer Simulation war dieser der Wert __08FF__.
Zeigt der Stackpointer über den reservierten, verfügbaren Speicher hinaus, so spricht man von einem __Stack Overflow__.

### Heap
Der Heap ([dynamischer Speicher](https://de.wikipedia.org/wiki/Dynamischer_Speicher)) ist ein ist ein Speicherbereich, aus dem zur Laufzeit eines Programms zusammenhängende Speicherabschnitte angefordert und in __beliebiger Reihenfolge__ wieder freigegeben werden können.


#### Unterschiede zum Stack:
* im Stack angeforderte Speicherabschnitte müssen in der __umgekehrten Reihenfolge__ wieder freigegeben werden
* der Zeitaufwand bei einer automatischen Speicheranforderung (Stack) zur Laufzeit ist in der Regel deutlich geringer als bei der dynamischen Speicheranforderung

![Speichereinheit](https://github.com/HTLMechatronics/m14-la1-sx/blob/nabmam14/Protokoll/Speichereinheit.png)

## Übung

Unsere Übung bestand darin folgendes C-Programm zu analysieren.

```c 
int main ()
{
  return 0;
}
```

Mit dem [AVR Instruction Ser Manual](http://www.atmel.com/images/Atmel-0856-AVR-Instruction-Set-Manual.pdf) wurden die Befehle von uns analysiert und bestimmt.
Daraufhin mussten wir im Instruction Set Manual der mega-AVR-Familie nachsehen, da bei anderen µ-Prozessoren die Maschinenbefehle anders arbeiten können und somit auch andere Register beschrieben werden könnten.

### Maschinenbefehle

* _CLR R1_ - Setzt Register 1 auf 0 
* _JMP_ - Sprung zu einer Adresse
* _LDI R29, 0x08_ - Läd einen konstanten Wert in Register 29
* _OUT 0x3F, R1_ - Überträgt die Daten von Register 1 in ein I/O Register
* _OUT 0x3E, R29 & OUT 0x3D, R28_ - setzen den Stackpointer auf 08FF
* _RJMP_ - Sprung zu einer Adresse 
* _SER R28_ - Das Register R28 bekommt den Wert 0xFF
