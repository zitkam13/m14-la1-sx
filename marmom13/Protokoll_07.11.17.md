# Protokoll 07.11.2017  

## 2. Einheit  

## Thema: Atmel Studio

Name: Moritz Martinak  
Lehrer: sx  
Gruppe: 2  
Übungsdatum: 31.10.2017  
Abwesend: -  

## Atmel Studio

Atmel Studio ist eine Entwicklungsumgebung der Firma Atmel die für die Mikrocontroller Programmierung und Simulation von Chips der 
Firma Atmel.

Durch die Simulation einer Ausführung eines Mikrocontrollerprogrammes kann man detailierte Informationen über Maschienenbefehle bekommen welche aus dem Quellcode des Programmes kompiliert werden. Ausserdem kann man in die Register des Controllers einsehen.

Weitere Informationen erhält man auf der Offiziellen Seite des Entwicklers:  
[Atmel](http://www.atmel.com)  
[Atmel Studio](http://www.atmel.com/microsite/atmel-studio/)  

## CPU-Aufbau

![CPU](https://github.com/HTLMechatronics/m14-la1-sx/blob/marmom13/marmom13/CPU.PNG)  

Quelle: [Skriptum](https://lms.at/dotlrn/classes/informatik/610437.4AHME_FIVU.17_18/xolrn/EC743ABCF7AB5.symlink?resource_id=0-237409759&m=view#188315330)

## Atmega 328p  
Bei dem Mikrocontroller den wir verwenden handelt es sich um den **Atmega 328p** der Firma Atmel. Da es dieses Modell in Atmel Studios nicht gibt verwenden wir die, sehr ähnliche, Variante **Atmega 328**.

### Spezifikationen:  
* 16MHz
* 32kB Flash
* 32 Register
* 2kB SRAM
* 1kB EEPROM  

### XYZ Register  
XYZ Register werden dazu verwendet, um Werte > 255 zu speichern, sie zeten sich aus folgenden Bestandteilen zusammen:  
* X = Register 26+27
* Y = Register 28+29
* Z = Register 30+31

## Stack

Der Stack, zu deutsch **Stapelspeicher**. Nach dem sogenannten Last-in-first-out Verfahren werden Dateien im Speicher von unten nach oben abgelegt. Der Stack weitert sich auf den freien Speicher aus.

### Stack-pointer  
Der Stackpointer zeigt auf den nächsten freien Platz im Stack. Bei z.B. einem leeren Speicher zeigt er auf den untersten Platz im Stack (in unserem Fall auf 08FF). Geht der Stackpointer über den reservieten Speicherplatz hinaus spricht man von einem **Stackoverflow**.

## Wichtige Maschinenbefehle:  
* RJMP: Sprung zu einer Adresse (Kann nur einen bestimmten Offset überspringen, Benötigt 4 Byte)
* JMP: Sprung zu einer Adresse (Benötigt 8 Byte)
* CLR R1: Setzt Register 1 auf 0 (Entspricht XOR)
* OUT 0x3F, R1: Überträgt die Daten von Register 1 in ein I/O Register (3F -> Statusflagregister)
* SER R28: Das Register R28 bekommt den Wert 0xFF
* LDI R29, 0x08: Läd einen konstanten Wert in ein Register von 16-31 (R29 = 0x08)
* OUT 0x3E, R29 & OUT 0x3D, R28: setzen den Stackpointer auf 08FF (08FF ist die erste Adresse des Stackspeichers -> Der Stack ist leer)



