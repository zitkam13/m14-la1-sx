# Protokoll: Knappitsch Robert

## 2. Einheit: Atmel Studio
* Klasse: 4AHME (Gruppe 1)
* Datum: 17.10.2017
* Anwesend: Berger Emil, Bullner Jeremy, Böcksteiner Jakob, Ehmann Julian, Enzi Gert, Kobor Markus, Knappitsch Robert
* Abwesend: -

### Atmel Studio
Das Atmel Studio ist eine kostenlose Entwicklungsumgebung für die die Programmierung der AVR-Mikrocontroller von Atmel.
Sie basiert auf der Visual Studio Shell von Microsoft und ist deshalb nur auf Windows verfügbar. Sie besteht aus einer
Projektverwaltung, einem Editor, einem Debugger und Werkzeugen zum Beschreiben der Mikrocontroller .Mit dem Atmel Studio
kann in Assembler sowie C/C++ programmiert werden.

### ATmega328P
Da unser Arduino Nano, mit dem wir im FIVU Unterricht arbeiten, den MicroProzessor ATmega328P verbaut hat, haben wir diesen 
auch im Atmel Studio gewählt. Das Programm zeigt folgendes im Prozessormenü an:
* Program Counter
* Stack Pointer (begrenzt den Stack-Speicher indem er auf den letzen Speicherplatz des Stack-Speichers zeigt)
* XYZ-Register
* Status Register
* Cycle Counter (zeigt die Takt-Durchläufe an)
* Frequency (Frequenz)
* Stop Watch (zeigt die Betriebszeit an)

#### Technische Daten
* 32kB Flash-Speicher
* 2kB Static RAM
* 32 (0-31) interne Register(FF's)
* 1kB EEPROM (Electrically Erasable Programmable Read-Only Memory)

#### XYZ-Register
Mithilfe dieser Register kann man auch Werte, die größer als 255 Bit sind, speichern.
X Register: R26 + R27
Y Register: R28 + R29
Z Register: R30 + R31

### Stackspeicher
Der Stapelspeicher wird vom Stackpointer nach unten hin begrenzt. Er arbeitet nach dem Speicherprinzip *First-in-First-out*. Daten
werden immmer in die oberste Adresse geschrieben (PUSH) und schieben die bereits gespeicherten Daten nach unten. Entfernen von Daten (POP) ist auch nur von oben nach unten möglich.

### Praktische Übung
* Wir haben ein einfaches Programm geschrieben: 
 *int main()
{
  return 0;
}*

* Dieses haben im Debugger gestartet und den Disassembler aktiviert (Debug/Windows/Disassembly).
 Falls der Cycle Counter nicht auf null war, musste mit Shift+F5 zurückgesetzt (Reset) werden.

* Jeder Speicherplatz ist 2 Byte groß (in Hex)

* Mit F10/F11 sind wir Befehl für Befehl durchgegangen [InstuctionSetManual.pdf](http://www.atmel.com/images/Atmel-0856-AVR-Instruction-Set-Manual.pdf):
  * RJMP PC+0x0034 (relativer Jump nach Speicherplatz 34)
  * CLR R1 (cleared Register R1: wendet EXOR zwischen R1 und R1 an (ergibt also 0, da die 2 Werte immer gleich sind --> ZeroFlag 1))
  * OUT 0x3F, R1 (Daten aus R1 werden ins I/O-Register 3F (SREG = Status Register) geschreiben --> ZeroFlag 0)
  * SER28 (R28 bekommt Wert 0xFF)
  * LDI R29, 08 (lädt eine 8 Bit Konstante in ein Register von 16-31 --> Y 0x08FF)
  * OUT 0x3E, R29 --> 3E = SPH (Stack Pointer High)
  * OUT 0x0D, R28 --> 3D = SPL (Stack Pointer Low)
  * RCALL PC 0x0003 --> 2 Byte im Stack abgelegt --> SP zeigt wieder auf letzen freien Platz --> springt auf die Position
  * LDI R24 0x00
  * LDI R25 0x00 (*return 0;* in C)
  * RET (springt zurück, SP wieder auf Wert 08FF)
  * RJMP
  * CLI
  * RJMP PC 0x000 ("Springt am Stand" --> Programm bleibt stehen)
