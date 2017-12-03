# Laborprotokoll  
Zweite Einheit am 28. Nov. 2017  
Martin Schmuck  
4AHME  
Gruppe 3

Automatisierungslabor HTL Kaindorf  
Anwesend: Reinbacher, Ruffenacht, Sackl M., Sackl R., Sammer, Schmuck, Schuster  
Abwesend: niemand  

## Thema der Einheit: Issues in GIT + Beginn µC
__________

#### Was ist ein Issue? 
Man kann über Git auch kommunizieren! Dazu geht man in ein beliebiges Repository, wählt den Reiter Issues und klick dann auf New Issue. Dann kann man eine Meldung eingeben welche öffentlich zugänglich ist. Der Eigentümer bekommt automatisch eine E-Mail zugeschickt. Andere Personen, welche interessiert sind, können das Issue abonieren, und werden dann bei neuen Meldungen auch informiert. Jeder kann mitdiskutieren. Dies wird häufig verwendet, um die Entwickler auf Bugs hinzuweisen. Wenn das Problem gelöst wurde, kann der Issue auch geschlossen werden. 

#### Wie funktioniert das Fork/Pull-Konzept?
Wenn jemand auf ein Issue nicht reagiert, kann man mit `fork` ein bestimmte Repository für sich selbst kopieren, die Änderungen vornehmen und dann mit einem Pull-Request den eigentlichen Eigentümer bitten, die Änderungen zu übernehmen. Wenn dieser jemand dazu nicht bereit ist, kann man ja auch selbst die Änderungen veröffentlichen. So kann man auch, wenn man an einem fremden Repository keine Schreibrechte hat, an Projekten mitarbeiten.

#### Kleines Zwischenthema: welche ist die häufigste Programmiersprache?
Es gibt mehrere Webseiten, auf denen man die aktuellen Marktanteile der verschiedenen Plattformen einsehen kann. Eine davon ist [TIOBE](https://www.tiobe.com/tiobe-index/). Da der TIOBE-Index sich allerdings auf umstrittene Quellen verlässt (z.B. Google-Suchanfragen), wird er heftig kritisiert. Eine Alternative wäre [RedMonk](http://redmonk.com/sogrady/2017/06/08/language-rankings-6-17/). Diese Seite richtet sich nach der Anzahl der Sprachen, in den Projekte auf [GitHub](github.com) gehalten sind, und der Anzahl der Theards über diese Sprach auf [Stackoverflow](stackoverflow.com), einem Forum für Programmierer.


### Einführung µC
___________________

#### Atmel Studio  
Atmel Studio ist eine Entwicklungsumgebung, welche durch die Firma __Atmel__ zur Verfügung gestellt wird. Diese IDE ist optimiert für die eigenen Atmega-Chips. Man kann damit auch einen Mikrokontroller simulieren. Diese Software baut auf das Microsoft Visual Studio auf, daher ist sie leider nur für Windows-Systeme verfügbar.  
Man kann damit einen µC komplett simulieren, inklusive Einblick in den Speicher, die Register, usw. 
Außerdem lässt sich der Maschinencode Zeile für Zeile abarbeiten und auswerten. Beim Maschinencode muss man aufpassen, da Atmel Studio immer zwei Bytes bei der Ausgabe des Maschinencodes am Bildschirm vertauscht. 

#### Aufbau einer CPU

![CPU](https://github.com/smumam14/labor1/blob/master/cpu.svg)
>abgerufen aus dem [FIV-Skript](https://lms.at/dotlrn/classes/informatik/610437.4AHME_FIVU.17_18/xolrn/EC743ABCF7AB5.symlink?resource_id=0-237409759&m=view#189503049) der HTL Arnfels, DI Steiner M., 2017  

#### ATmega328P
[Datenblatt des ATmega328P](http://www.atmel.com/images/Atmel-8271-8-bit-AVR-Microcontroller-ATmega48A-48PA-88A-88PA-168A-168PA-328-328P_datasheet_Complete.pdf)
Am Ende des vorangegangenen Schuljahres bestellten wir Mikrokontroller der Firma Atmel des Typs ATmega328P, welche wir zu Beginn des aktuellen Schuljahres erhielten. Die Kollegen auf den Stand-PC's, wo ein ältere Version des Atmel Studios installiert ist, hatten diesen nicht zur Verfügung und verwendeten deswegen die Version 328. Die Laptop-Schüler mit Atmel Studio 7 konnten jedoch auch den 328P auswählen.   
  
  
Spezifikationen |  -
---------------- | ---
Frequenz | 16 MHz  
Register | 32
EEPROM | 1KB
SRAM | 2KB
Flash | 32KB  

__Wofür gibt es XYZ-Register?__  
Da es sich um einen 8-Bit-Prozessor handelt, können in einem Register nur Werte 0 bis 255 (2^8 - 1) gespeichert werden. Damit man größere Werte speichern kann, werden immer zwei Register zu einem zusammengefasst. Darin können dann Werte von 0 bis 65.535 (2^16 - 1) gespeichert werden.  
__X = 26 & 27__  
__Y = 28 & 29__  
__Z = 30 & 31__  

#### Wichtige Maschinenbefehle
Wir schreiben folgendes Programm in C:
```c
int main()
{
return 0;
} 
``` 
Mithilfe des Atmel Studios lassen wir uns den Maschinencode anzeigen. Obwohl es sich hierbei zweifelsfrei um eines der kürzesten Programme handelt, kann man daraus Informationen über eine breite Anzahl an Maschinenbefehlen gewinnen.  

Maschinenbefehl | Bedeutung, Ausführung
--------------- | ---------------------
`RJMP` | Relativer Sprung (Relative Jump) zu einem anderen Maschinenbefehl. Die allgemeinere Version wäre `JMP`, womit man zu einer absoluten Stelle im Maschienencode springen kann.
`RCALL` | Im Grunde w.o., jedoch wird hier die Rücksprungadresse am Stack abgelegt, so dass man wieder zurück springen kann, ähnlich einem "Funktionsaufruf" in C. `CALL` wäre hier auch wie oben die allgemeine Form.
`CLR R1` | Damit wir das Register R1 Exklusiv Oder mit sich selbst verknüpft, also komplett mit 0 überschrieben.
`OUT 0x3F, R1` | Damit wird der Inhalt des Registers R1 in das Stausregister geschrieben (3F = Statusregister)
`SER R28` | Register R28 wird komplett auf 1 gesetzt

