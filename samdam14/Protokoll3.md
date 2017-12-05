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
Die Erklärung folgender Maschinenbefehle können im Protokoll 2 oder im instruction set manual entnommen werden.  
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









