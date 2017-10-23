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

Wenn man das Programm fertig übersetzt hat, hat man die Möglichkeit in den Debug-modus zu wechseln. Dort kann man nun in einem Fenster sehen, welche Werte bestimmte Teile der CPU (siehe Grafik) haben. So kann man nun den Wert des **Program Counter** (Speicheradresse des derzeitigen Befehls), dem **Stack Pointer** (zeigt auf die nächste Freie Adresse im Stack), den **X, Y, Z Registern** (Register R26, R27->x; R28, R29->y; R30, R31->z)
