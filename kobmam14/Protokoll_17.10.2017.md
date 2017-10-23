# Protokoll 17.10.2017

## 2. Einheit
## Thema: Atmel Studio

Name: Markus Kobor  <br>
Klasse: 4AHME  <br>
Datum 17.10.2017  <br>
Gruppe: 1  <br>
Anwesend: Berger Emil, Böcksteiner Jakob, Bullner Jeremy, Ehmann Julian, Enzi Gert, Knappitsch Robert, Kobor Markus  <br>
Abwesend: -  <br>

### Was ist Atmel Studio?

**Das Atmel Studio ist eine kostenlose Entwicklungsumgebung zum entwickeln und debuggen von Atmel Mikrocontrolleranwendungen.** <br> <br>
Ab der fünften Version basiert Atmel Studio auf der Visual Studio Shell von Microsoft, weshalb man es nur auf Windowsbetriebssystemen verwenden kann, und besteht aus einer Projektverwaltung, einem editor, einem Debugger und Werkzeugen zum beschreiben von Mikrocontrollern. Die Anwendungen müssen in C, C++ oder Assemblierungscode geschrieben sein.

### ATmega 328 P

Im Atmel Studio haben wir den ATmega 328 P als Mikrocontroller ausgewählt, da wir diesen auch im Gegenstand FIVU verwenden.
Dieser verfügt über: <br>
* **einen Program Counter** (enthält die Speicheradresse des derzeitigen oder des nächsten auszuführenden Befehls)
* **einem Stack Pointer** (zeigt immer auf die nächste freie Speicherstelle im Stack)
* **x, y, z Register** (die letzten drei Registerpaare, die man als Pointer auf SRAM,
FLASH und den Rest des Adressbereiches (Register, I/O) verwenden KANN,
aber nicht muss)
* **einem Status Register** (enthält eine Reihe von Flags, die von der arithmetisch-logischen Einheit (ALU) in Abhängigkeit von der zuletzt durchgeführten Rechenoperation gesetzt werden)
* und arbeitet mit einer **Frequenz von 16 MHz** <br> <br>
Er verfügt aber nicht über einen **Cycle Counter**
