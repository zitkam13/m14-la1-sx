# 2.Einheit: 17.10.2017

Gegenstand: LA1  
Name: Gert Enzi  
KN: 5  
Klasse: 4AHME  
Gruppe: 1  
  
# Einführung Atmel-Studio

## Was ist Atmel-Studio?

**Atmel-Studio ist eine Entwicklungsumgebung zur Programmierung von Microcontrollern**.  

Die verwendete Programmiersprachen sind C, C++ und Assembler. Da Atmel-Studio nur für Windows verfügbar ist und kein besonders gutes
Programm ist, verwenden wir es nur um die Hintergründe der Programmierung zu verstehen.  

## Erstes Programm auf Atmel

Um nun auf Atmel ein Programm für einen Microprozessor zu schreiben, muss man zuerst ein entsprechendes Board auswählen, um Kompatibilität
zu gewährleisten. In unserem Fall wählen wir den ATMEGA 328p.  
  
### Einige Daten zum ATMEGA 328p

* Frequenz: 16 MHz
* Flash-Speicher: 32 kb
* RAM: 2kb static RAM
* CPU-Register: 32 Register (wobei jedes Register aus 8 Bit besteht)
* EEPROM(Electrically Erasasable Programmable Read Only Memory): 1 kb
  
Aufbau der CPU:  
  
![CPU-Aufbau](https://github.com/HTLMechatronics/m14-la1-sx/blob/enzgem13/enzgem13/cpu_svg.svg)  
  
Nun kann man beginnen, ein Programm zu schreiben. Wir haben es fürs erste nur bei der main.c mit einem *return* befehl belassen.  
  
## Debugger

Wenn man das Programm fertig übersetzt hat, hat man die Möglichkeit in den Debug-modus zu wechseln. Dort kann man nun in einem Fenster sehen, welche Werte bestimmte Teile der CPU (siehe Grafik) haben. So kann man nun den Wert des **Program Counter** (Speicheradresse des derzeitigen Befehls), dem **Stack Pointer** (zeigt auf die nächste Freie Adresse im Stack), den **X, Y, Z Registern** (Register R26, R27->x; R28, R29->y; R30, R31->z) und dem **Status Register**(beinhaltet die Status-Flags: Z, V, C...) sehen. Weiters enthält es auch Informationen über einen sogenannten **Cycle Counter**, dieser ist lediglich in der Entwicklungsumgebung gespeichert und zeigt, wieviele Zyklen durchlaufen wurden, um das Programm vollständig auszuführen. Die CPU selbst hat kein Wissen über einen **Cycle Counter**.  
  
Weiters kann man im Debugger sehen, welche Register und Bits gesetzt werden. Aus dieser Information(und mithilfe der [Instruction Set Manual](http://www.atmel.com/images/Atmel-0856-AVR-Instruction-Set-Manual.pdf)) kann man ermitteln, welche Befehle zu welchem Zeitpunkt ausgeführt werden.  
So haben wir z.B. einen Befehl der aus 2 Bytes besteht(hexadezimal angeschrieben):  
```
33.c0->  
-> 0011 0011 1100 0000 - zunächst müssen die beiden Bytes vertauscht werden...  
-> 1100 0000 0011 0011 - nun im Instruction Set Manual den entsprechenden Befehl suchen...  
-> 1100 kkkk kkkk kkkk - RJMP Befehl
```  
Es handelt sich hierbei um einen *RJMP* Befehl -> führt einen Sprung zu einer Addresse durch (weitere Infos: [Instruction Set Manual](http://www.atmel.com/images/Atmel-0856-AVR-Instruction-Set-Manual.pdf))  
Weitere Befehle:
* *CLR* -> Exklusive Oder Verknüpfung mit sich selbst (führt immer zum Wert 0 bzw. löschen der Werte in einem Register)
* *OUT* -> Ein bestimmtes Register wird einem Register in der CPU zugewiesen (z.B.: *SREG* - Status Register - I/O Register wird R1 zugewiesen)  
* *SER* -> Set all Bits in Register ladet lediglich den Wert 0xFF in ein Register (Alle Bits werden gesetzt)  
* *LDI* -> Load immediately lädt eine 8-Bit Konstante in ein Register (nur für R16 bis R31)  
  
Ein weiteres Register ist der *SP* Stackpointer - dieser zeigt auf ein Byte im Arbeitsstpeicher.  
  
## Stack

Im Mikroprozessor befindet sich ein sogenannter Stack-Speicher, auch Stapelspeicher. Die Speicherung erfolgt in exakter Reihenfolge und wird in umgekehrter Reihenfolge wieder ausgegeben.  
  
Um mit dem Speicher zu kommunizieren werden folgende Operanden benötigt:
* push (ein Objekt wird hinzugefügt)
* pop (ein Objekt wird geliefert und entfernt)
* peek (ein Objekt wird nur geliefert)  


