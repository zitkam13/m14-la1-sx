# Protokoll 2: Git und Microcontroller
Name: Patrick Schuster  
Klasse: 4AHME  
Gruppe: 3    
Anwesend: Reinbacher, Ruffenacht, Sackl, Sackl, Sammer, Schmuck, Schuster  
Abwesend: keiner

## Git
### Issues
Git dient nicht nur zur Versionsverwaltung sondern dient auch zur Kommunikation. Damit kann man bei Projekten mit anderen kommunizieren und den Eigentümer eines Repositorys auf einen Fehler hinweisen. Dieser bekommt dann automatisch eine E-Mail zugeschickt. Andere Personen können das Issue auch kommentieren und bei der Diskussion mitwirken. Personen die sich für das Issue interessieren, sich aber bei der Diskussion nicht beteiligen wollen, können das Issue auch abonnieren.  
### Fork und Pull
Mit einem fork kann man ein fremdes Projekt auf sein eigenes Repository klonen. Diese Funktion kann genutzt werden wenn der der ersteller des eigentlichen Projekts nicht auf ein Issue reagiert und man selber die Lösung für das Problem beheben möchte. Ein Fork kann auch dazu verwendet werden ein Projekt weiter zuführen wenn sich der eigentliche Ersteller des Projektes nicht mehr meldet und das Projekt nicht weiterführt.
Mit einer pull request kann ein Benutzer der mit einem fork das ursprüngliche Projekt geklont hat, dem eigentlichen Ersteller anbieten die Änderungen zu übernehmen. 

## Die am häufigsten verwendetsten Programmiersprachen
Es gibt mehrere Websiten auf denen man feststellen kann welche Programmiersprachen am häufigsten verwendet werden.
Eine sehr bekannte Website ist der [Tiobe Index](https://www.tiobe.com/tiobe-index/). Dieser ist aber nicht sehr präzise und hat einen großen Kritikpunkt und zwar, dass die Popularität über die Anzahl der Suchanfragen auf Google festgestellt wird.  

Eine Alternative ist [Redmonk](http://redmonk.com/sogrady/2017/06/08/language-rankings-6-17/). Redmonk ermittelt die Popularität über die Anzahl der Projekte auf [Github](https://github.com/) und der Anzahl der Beiträge auf [Stackoverflow](https://stackoverflow.com/).   

## Microcontroller

### Atmel Studio
Atmel Studio ist eine Entwicklungsumgebung für die Programmierung von Chips der Firma Atmel. Diese Software kann auch für die Siumlation eines Mikrocontrollers verwendet werden.  Man erhält beim simulieren detailierte Informationen über Maschinenbefehle und den Inhalt von Registern und dem Flash-Speicher. Bei Bedarf kann dieser auch während das Programm läuft manipuliert werden.
Weitere Informationen können auf der Website von Atmel Studio gefunden werden. [Atmel Studio](http://www.atmel.com/microsite/atmel-studio/)

## Aufbau einer CPU
![Bild CPU](https://github.com/suspam14/la1/blob/master/cpu.svg)

## ATmega 328p
### Produktdaten:
* 16MHz Mikroprozessor
* 32kB Flash-Speicher
* 32 Register
* 2kB SRAM
* 1kB EEPROM

### XYZ Register
Ein normales Register kann nur Werte von 0 bis 255 speichern. (8 bit) Um Werte größer als 255 zu speichern werden beim Atmge328p die XYZ-Register verwendet.  
* X = r26 & r27
* Y = r28 & r29  
* Z = r30 & r31  

### Stack
Der Stack ist ein wichtiger Bestandteil des Speichers und wird auch Stapelspeicher genannt. Die Datem werdem nach dem last-in first-out Prinzip gespeichert bzw. abgelegt. Die Daten werden von unten nach oben abgelegt und von oben nach unten wieder entnommen.
#### Stack-Pointer
Der Stackpointer entspricht einem Zeiger der, auf den nächsten freien Platz im Stack zeigt. Zeigt er auf den untersten Platz ist der Stack leer. Im unserem Fall (Atmega 328) wäre dies der Zeiger `08FF`. Falls der Stackpointer auf einen Bereich zeigt, der nicht für den Stack reserviert ist nennt man das *Stackoverflow*. Durch einen Stackoverflow treten Probleme auf die nicht unbedingt direkt zum Vorschein kommen.
#### Aufbau des SRAM im Atmega 328
![Bild SRAM](https://github.com/suspam14/la1/blob/master/stack.svg)
> Grafik aus dem FIVU-Skript - angepasst an den Atmega328p durch Patrick Schuster

### Programm Counter
Der Programm Counter zeigt auf die Adresse des nächsten Maschinenbefehls und zählt nicht die Maschinenbefehle, wie der Name es vermuten lassen würde.

## Übung
Folgender Quelltext wurde erstellt, simuliert und analysiert:
```c
int main ()
{
  return 0;
}
```
Die Simulation lieferte uns daraufhin die kompilierten Maschinenbefehle. Um die Funktion der einzelnen Befehle zu verstehen verwendeten wir die [Atmel Instruction Set Manual](http://www.atmel.com/images/Atmel-0856-AVR-Instruction-Set-Manual.pdf).
Bei verwendung eines Benutzerhandbuchs muss sichergestellt werden, dass es sich um das richtige für den Microprozessor handelt, es können nämlich einzelne Befehle abweichen. 

### Maschinenbefehle des Quelltestes
 Maschinenbefehl | Ergebnis  
---------------- | -----------------------------------------------------  
JMP 0x00000034   | Springt zur Adresse 0x34 des Programms  
CLR R1           | cleared das Register R1 (EXOR  mit sich selbst) -> setzt zero-flag 
OUT 0x3F,R1      | Schreibt die Daten vom R1 Register ins I/O Register (SREG)  (setzt zero-flag zurück)
SER R28          | setzt alle Bits des Registers auf 1 (0xFF)  
LDI R29,0x08     | lädt die Konstante 0x08 in das Register  
OUT 0x3E,R29     | Erstes Byte vom Stackpointer wird auf den Inhalt von R29 gesetzt  (Stackpointer = 0x0800)
OUT 0x3D,R28     | Zweites Byte vom Stackpointer wird auf den Inhalt von R28 gesetzt  (Stackpointer = 0x08FF)
CALL 0x00000040  | Springt auf Adresse und speichert den Programm Counter im Stack  
LDI R24,0x00     | R24 wird auf 0 gesetzt  
LDI R25,0x00     | R25 wird auf 0 gesetzt  
RJMP PC-0x0000   | Ende des Programms -> Endlosschleife 







