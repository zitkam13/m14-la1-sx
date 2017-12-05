# _Protokoll Dritte Einheit_  

**Name: Daniel Sammer**  
**Gruppe: 3**  
**Datum: 05.12.2017**  
**Uhrzeit: 9:40-12:25**  
  
**Anwesenheit: _Es waren alle Schüler anwesend_**  
  
-----------------------------------------------------------  
#### Wiederholung Einheit 2  
*Was findet man im Prozessorfenster? Aufgaben der Bestamdteile?*  
* program counter  
* cyclic counter  
* X-/Y-/Z-Register  
* stackpointer  
* frequenzy  
* stop watch  

Die Aufgaben der einzelnen Bestandteile sind dem Protokoll 2 zu entnehmen.  
zum Protokoll: [Protokoll Einheit 2](https://github.com/HTLMechatronics/m14-la1-sx/blob/samdam14/samdam14/Protokoll2.md)  
  
*Was findet man im disassembly?*  
* Adressen der Befehle im Speicher  
* Maschinenbefehl in hexadezimaler Darstellung  
* Abgekürzte Maschinenbefehl-Namen und Parameter  

*Für was werden die Register R25 bis R8 benötigt?*  
* R25 bis R8 wird vom C-Compiler für Parameter und Rückgaben verwendet  
--------------------------------------------  
#### Datentypen unsigned und volatile  
Datentyp | Auswirkung
-------- | ----------
unsigned | Modifiziert den eigentlichen Datentyp. Der Datentyp _int_ (_signed int_) umfasst einen Zahlenbereich von  2³² = 4294967296 Zahlen, die den Bereich von -2147483648 bis +2147483647 abdecken. Steht _unsigned_ vor dem _int_, dann deckt man einen Bereich von 2³² Zahlen größer gleich 0 ab.
volatile | Steht im Datentyp einer Variable _volatile_, dann darf diese Variable vom Compiler nicht mehr wegoptimiert werden.
Quelle:[C++ Forum](https://www.c-plusplus.net/forum/154918-full)  

--------------------------------------  
#### Übungsbeispiel 1  
```c
int main(void)  
{  
  volatile unsigned char x;  
  x=10+23;  
  return x;  
}  
```  

-------------------------------
Die genauen Erklärungen folgender Maschinenbefehle können im Protokoll 2 oder im instruction set manual entnommen werden. Die in der Tabelle folgende Erklärungen beziehen sich teilweise auf die Verwendung in diesem Beispiel!  
[Protokoll Einheit 2](https://github.com/HTLMechatronics/m14-la1-sx/blob/samdam14/samdam14/Protokoll2.md)  
[instruction set manual](http://www.atmel.com/images/Atmel-0856-AVR-Instruction-Set-Manual.pdf)  

Maschinenbefehl | Erklärung
--------------- | --------------
PUSH R28 & PUSH R29 | Sichern des Y-Registers, der Inhalt des Registers befindet sich nun im Stack
PUSH R1 | Stackpointer wird auf 1 gesetzt
IN R28, 0x3D & IN R29, 0x3E | Y-Register wird zum Stackpointer
LDI R24, 0x21 | Ins Register 24 wird der Zahlenwert 33(=10+23=2x16+1x1) geschrieben
STD Y+1, R24 | Register 24 wird im Stack gespeichert an der Stelle, auf der der Stackpointer (=Y-Register) zeigt, +1
LDD R24, Y+1 | Inhalt im Stack an der Stelle Stackpointer +1 wird ins Register R24 geladen. Dies entspricht dem _return x;_ aus dem Quelltext
POP R0 & POP R28 & POP R29 | Register werden wieder freigegeben (Gegensatz zu PUSH)
RET | Return to subroutine

--------------------------------------
#### Übungsbeispiel 2  
```c
int main(void)  
volatile unsigned char a = 10;  
volatile unsigned char b= 20;
volatile unsigned char e=a+b;  
return a+b;
```

--------------------------------
Maschinenbefehl | Erklärung
--------------- | ---------------
PUSH R28 & PUSH R29 | Der Inhalt des Y-Registers wird nun gesichert, indem er auf den Stack gelegt wird.
RCALL PC0x0001 (2 Mal) | Im Stack werden Plätze reserviert.
IN R28, 0x3D & IN R29, 0x3E | Y-Register wird zum Stackpointer.
LDI R24, 0x0A | Ins Register wird der Wert 10=0x0A geschrieben.
STD Y+1, R24 | Der Inhalt des Registers 24 wird in den Stack an der Stelle Y+1(SP+1) gespeichert.
LDI R24, 0x14 | Ins Register wird der Wert 20=0x14 geschrieben.
STD Y+2, R24 | Der Inhalt des Registers 24 wird in den Stack an der Stelle Y+2(SP+2) gespeichert.
LDD R18, Y+1 & LDD R24, Y+2 | Der Inhalt an der jeweiligen Stelle im Stack wird ins jeweilige Register geladen.
LDD R25, 0x00 | Ins Register 25 wird der Wert 0 geschrieben.
ADD R24, R14 | Die Inhalte beider Register werden addiert. Das Ergebnis ist im Inhalt von R24.
ADC R25, R1 | Addition unter Berücksichtigung des Carry-Bits. Ein Carry-Bit wird gesetzt, wenn das Ergebnis der Addition mehr als eine Stelle (Stellenwertsystem: Einer, Zehner, Hunderter ,...) hat. Dann wird das Carry-Bit auf die nächsthöhere Stelle gesetzt, um das richtige Ergebnis zu erhalten. Quelle:[wiki/Übertragungsbit](https://de.wikipedia.org/wiki/%C3%9Cbertragsbit)
STD Y+4, R18 & STD Y+3, R24 | Der Inhalt der jeweiligen Register wird in den Stack an die jeweilige Stelle geschrieben.
LDD R18, Y+3 & LDD, Y+4 | Dies entspricht dem _return e;_ aus dem Quellcode.
POP R0 (3 Mal) | Variablen e,b und a (in dieser Reihenfolge) werden freigegeben.
POP R28 & POP R29 | Register 28 und 29 werden freigegeben.
RET | Return from subroutine

-----------------------------------------------


