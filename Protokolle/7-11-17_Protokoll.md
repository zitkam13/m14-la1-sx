# Protokoll: Marcel Köhler
## Zweite Einheit
## Thema: Atmel Studio
Klasse: 4AHME  
Anwesend: Köhler Marcel, Mandl Gerhard, Martinak Moritz, Mörth Michael, Muri Lorenz, Nabernik Mario, Nebel Florian, Platzer Andreas  
Abwesend: -  


## Atmel Studio
[Atmel Studio](http://www.atmel.com/microsite/atmel-studio/) ist eine Entwicklungsumgebenung, welche von der Firma und Microprozessor hersteller [Atmel](http://www.atmel.com/) zur vefügung gestellt wird.
In dieser Umgebung kann man Programme für die Mikroprozessoren der Firma erstellen und auch Simulieren.  
Wenn es zum simulieren des Programmes kommt sieht man in der Umgebung detailierte Informationen.
Darunter kann man auch in die Register einsehen.

### Atmega328p
Wir arbeiten in der schule mit dem µ-Prozessor Atmega328p, da es diesen aber nicht in der Entwicklungsumgebung gibt nehmen wir den sehr ähnlichen Prozessor Atmega328.

#### Wichtige Register
* XYZ-Register
  Diese Register werden benötigt um werte welche größer als 255 zu speicher.
  * X = Register 26+27
  * Y = Register 28+29
  * Z = Register 30+31
  
* Register 3F = SREG = Statusflagregister
* Register 3E = SPH = Stackpointer initialisieren 
* Register 3D = SPL = Stackpointer initialisieren

Weitere informationen zum Atmega328p können im diesem [Datenblatt](http://www.atmel.com/Images/Atmel-42735-8-bit-AVR-Microcontroller-ATmega328-328P_Datasheet.pdf) entnommen werden.


## Stack
Im Stack, auch Stapelspeicher genannt, werden Daten nach dem "Last-in-First-out" Prinzip gespeichert, dies bedeutet das die Daten von unten nach oben gespeichert werden. 

### SRAM Aufbau
![SRAM](https://github.com/HTLMechatronics/m14-la1-sx/blob/koemam13/Protokolle/SRAM.PNG)

### Stackpointer
Der Stackpointer zeigt immer auf den nächsten freien Speicher im Stack. Wenn der Stack leer ist zeigt der Stackpointer auf den untersten Platz im Speicher, welcher bei unserer Simulation den Wert '08ff' hatte.
Wenn man über den reservierten Speicher hinausgeht spricht man von einem Stackoverflow.


## Übung

Wir haben folgenden Code simuliert:

```c
int main ()
{
  return 0;
}
```

Nachdem wir diesen Code simuliert haben, haben wir die Maschinenbefehle mithilfe des [AVR Instruction Ser Manual](http://www.atmel.com/images/Atmel-0856-AVR-Instruction-Set-Manual.pdf) die befehle bestimmt und besprochen was diese machen.
Im Instruaction Set Manual muss man unter der mega-AVR-Familie nachsehen, da bei anderen µ-Prozessoren die Maschinenbefehle anders arbeiten können und somit auch andere Register beschrieben werden könnten.

### Wichtige Maschinenbefehle

* CLR R1: Setzt Register 1 auf 0 
* JMP: Sprung zu einer Adresse 
* LDI R29, 0x08: Läd einen konstanten Wert in Register 29
* OUT 0x3F, R1: Überträgt die Daten von Register 1 in ein I/O Register
* OUT 0x3E, R29 & OUT 0x3D, R28: setzen den Stackpointer auf 08FF
* RJMP: Sprung zu einer Adresse 
* SER R28: Das Register R28 bekommt den Wert 0xFF
