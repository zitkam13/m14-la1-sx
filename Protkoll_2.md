

# **2.Laborprotokoll** 

*von Florian Ruffenacht*

Datum: 28.11.2017 (Gruppe 3)

Ort: AUT-Labor

Lehrkraft: SX

Abwesend: -


## **Issues auf GitHub**

Issues sind eine Kommunkationsmöglichkeiit auf GitHub. Es lassen sich **Nachrichten** an andere
Benutzer schicken, die auch formatiert werden können. Des Weiteren lassen sich Bilder hinzufügen.
An einem Issue können sich mehrere Benutzer beteiligen in dem sie einen Beitrag schreiben und außerdem 
besteht auch die Möglichkeit nur passiv über neue Beiträge in einem Issue benachrichtigt zu werden.
Issues können dazu verwendet werden Entwickler von **Open-Source Programmen** zu kontaktieren bzw. sie 
über Fehler zu informieren. Sie können auch wieder geschlossen werden.

[Weiteres zu Issues](https://guides.github.com/features/issues/) 


## **Forks auf GitHub**

Ein Fork ist eine Kopie eines beliebigen Repositorys in das eigene Repository. Dafür sind keine besonderen Rechte
erforderlich, aber es ist ersichtlich wer einen Fork gemacht hat. Das ist besonders nützlich, wenn ein **Bug** vom 
Entwickler nicht behoben wird und man es selber machen möchte. Ist der Fehler behoben oder das Programm verbessert, 
kann ein *__Pull request__* durchgeführt werden. Das bedeutet, dass dem ursprünglichen Entwickler angeboten wird, die 
verbesserte Version zu übernehmen, was er aber nicht muss.

[Weiteres zu Forks](https://guides.github.com/activities/forking/)

[Weiteres zu Pull requests](https://help.github.com/articles/about-pull-requests/)


##  **Welche Programmiersprache soll ich lernen?**

Die Frage, welche Programmiersprachen am Wichtigsten sind, ist nicht leicht zu beantworten, da sich das laufend ändert.

Der **TIOBE Index** versucht die Sprachen nach ihrer Wichitgkeit zu platzieren, indem die Anzahl der Enwickler einer 
Programmiersprache durch deren Aktivität auf Websites wie Wikepedia, YouTube, Amazon, usw. ermittelt wird. Ein Ranking
erscheint jedes Monat. Doch der TIOBE Index ist umstritten, denn der nicht wissenschaftliche Logarythmus lässt sich  teilweise durch geringfügig andere Suchbegriffe in den Suchmaschinen verschieben.

Der aktuelle TIOBE Index (Stand 11/2017):
![Tiobe Index](https://github.com/HTLMechatronics/m14-la1-sx/blob/rufflm14/BildTiobeE2.svg)

[TIOBE Index](https://www.tiobe.com/tiobe-index/)


Der **RedMonk Index** hingegen bezieht seine Daten aus zwei anderen Quellen und stellt diese auch in einem Koordinationsystem dar. Einerseits
wird bemessen, wie häufig eine Programmiersprache in Projekten auf **GitHub** vorkommt und andererseits wie viele Aktivitäten es zu 
dieser Sprache auf dem Forum **StackOverflow** gibt.

Der aktuelle RedMonk Index (Stand 3.Quartal 2017)
![RedMonk Index](https://github.com/HTLMechatronics/m14-la1-sx/blob/rufflm14/BildRedMonkE2.png)


[RedMonk Index](https://redmonk.com/sogrady/2017/06/08/language-rankings-6-17/)


Die Unterschiede der beiden Indizes sind teilweise sehr groß, was sich auf die **unterschiedlichen Berechnungsmethoden** zurückführen
lässt. Außerdem hat der TIOBE Index deutlich mehr Schwankungen, was damit zu tuen haben könnte, dass diese Berechnungsmethode anfälliger
auf kurzzeitge Hypes von Videos, Büchern und Ähnlichem einer Programmiersprache ist.


## **Analysieren von Assembler Befehlen**

Zum Analysieren von Assembler Befehlen verwenden wir die Entwicklungsumgebung AtmelStudio der Firma Atmel, mit der neben dem Programmieren von Atmel-Chips auch die Simulation von Mikroprozessoren durchgeführt werden kann. 

[Website von Atmel](http://www.atmel.com/)

[Website von Atmel Studio 7](http://www.atmel.com/microsite/atmel-studio/)


Da im AtmelStudio der von uns verwendete Prozessor **Atmega 328p** nicht vefügbar ist, verwendeten wir bei der Übung den **Atmega 328**.

Um die einfachsten Maschinenbefehle zu analysieren verwendeten wir folgendendes einfaches Programm:

![Programm](https://github.com/HTLMechatronics/m14-la1-sx/blob/rufflm14/BildProgrammE2.JPG)

In AtmelStudio besteht die Möglichkeit das Programm **Schritt für Schritt** durchzugehen und sich jeweils den aktuellen Status des Mikroprozessors anzeigen zu lassen. 
Das sind folgende Informationen:

* Programm - Counter (gibt Adresse des nächsten Maschinenbefehls an)
* Stack Pointer (zeigt den Beginn des Stacks an)
* Befehlsregister (X,Y,Z -> laden die nächsten Maschinenbefehle)
* Status der Statusflagregister

* Cycle - Counter
* Frequenz
 * Stop watch
 
Die letzten drei Anzeigen sind nur Infos für den Benutzer und sind am echten Prozessor nicht zu finden.

![AtmelStudio](https://github.com/HTLMechatronics/m14-la1-sx/blob/rufflm14/BildAtmelStudioE2.JPG)

Außerdem lassen sich die 32 CPU - Register (welche durch jeweils 8 FlipFlops realisiert sind -> Werte 0...255) anzeigen.


### XYZ - Register

Weil aber Adressen, zum Beispiel für das SRAM, größere Werte als 255 annehmen können, werden jeweils zwei CPU - Register zusammengelegt.
Die Register setzen sich folgendermaßen zusammen:


* X = Register 26 + 27
* Y = Register 28 + 29
* Z = Register 30 + 31

Weitere Informationen zur Pin- und Registerbelegung können [hier](http://www.atmel.com/Images/Atmel-42735-8-bit-AVR-Microcontroller-ATmega328-328P_Datasheet.pdf) im Datenblatt des Atmega 328/P nachgelesen werden.


### Aufbau der CPU

 Hier wird mithilfe eines Blockschaltbilds der Aufbau einer CPU anschaulich dargestellt
 
 ![CPU](https://github.com/HTLMechatronics/m14-la1-sx/blob/rufflm14/BildCpuE2.png)
 
 
### Stack

Im Stack (auch **Stapelspeicher** genannt) werden Datenn von untern noch oben abelegt. Allerdings werden die Daten von oben nach unten eingelesen. Dieses Verfahren wird als **Last-in-First-out** bezeichnet.

**Stackpointer**

Der Stackpointer zeigt immer auf den nächsten freien Platz im Stack-Speicher. Wenn der Stack also leer ist, zeigt der Stackpointer auf den unteresten Platz im Speicher. Bei unserer Simulation war das der Wert 08FF. Wenn der Stackpointer allerdings über den reservierten Speicherplatz hinaus geht, spricht man von einem Stackoverflow.

**Aufbau des SRAM**

![Stack](https://github.com/HTLMechatronics/m14-la1-sx/blob/rufflm14/BildStackE2.png)


### Besprochene Maschinenbefehle

Die von AtmelStudio ausgegebenen Maschinenbefehle, welche aus dem Quellcode kompiliert wurden, schlugen wir im [Atmel Instruction Manual](http://www.atmel.com/images/Atmel-0856-AVR-Instruction-Set-Manual.pdf) nach. Die im AtmelStudio in Hexadezimaler Darstellung angezeigten Maschinenbefehle, die aus zwei Bytes bestehen, sind vertauscht und müssen zuerst umgedreht werden.
Beispiel: Befehl *33.c0* wird zu *c0.33*

**Besprochene Maschinenbefehle:**

#### RJUMP
* **RJUMP** springt zu einer Adresse innerhalb des Programm Counters 
* Muster: 11kk kkkk kkkk kkkk
* Beispiel: c0.33 = 1100 0000 0011 0011 |-> RJUMP 51
#### CLR
* **Clear** setzt ein Register auf 0. Clear ist eigentlich eine EXOR-Verknüpfung eines Regsiters mit sich selbst.
* Muster: 0010 01rd. dddd rrrr (d = EXOR-Register, r=Register)
* Besipiel: 24.11 = 0010 0100. 0001 0001 |-> Zero Flag wird auf 0 gesetzt
#### OUT
* **OUT** überträgt Daten vom CPU-Register ins I/O-Register(SREG)
* Muster: 1011 1AAr. rrrr AAA (r = CPU-Register, A = I/O Register)
* Beispiel: be.17 = 1011 1110 0001 1111 |-> Status Flags werden auf 0 gesetzt
#### SER
* Einem der Register 16-31 wird der Wert FF zugwiesen
* Muster: 1110 1111. dddd 1111 ( 16 + d = Register)
* Beispiel: ef.cf = 1110 111. 1100 1111  |-> Dem Register 28 wird der Wert FF zugewiesen
#### LDI
* **Load Immediate** ladet einen Konstanten Wert in eines der Register 16-31
* Muster: 1110 KKKK. dddd KKKK (K = der konstante Wert, 16 + d = Register)
* Bespiel: e0.d8 = 1110 0000 1101 1000 |-> R29 wird auf 8 gesetzt
#### RCALL
* **RCALL** setzt den Programm Counter (PC) auf PC+1+k
* Muster: 1101 kkkk. kkkkk kkkk ( k = Wert um den der PC erhöht werden soll)
* Besipiel: d0.02 = 1101 0000, 0000 0010 |-> Der PC wird um 3 erhöht
#### RET
* Mit **RET** wird von einer Subroutine zurückgekehrt
* Muster: 1001 1010. 0000 1000




