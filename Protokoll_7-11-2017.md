# Protokoll 07.11.2017
## 2. Einheit

Name: Muri Lorenz <br>
Klasse: 4AHME <br>
Gruppe: 2 <br>
Datum der Einheit: 07.11.2017 <br>
Anwesend: Nebel Florian, Mandl Gerhard, Michael Mörth, Moritz Martinak, Mario Nabernik, Muri Lorenz, Platzer Andreas, Marcel Köhler <br>
Abwesend: - <br>

## Thema: Atmel-Studio

### Atmel-Studio
Atmel Studio ist eine Entwicklungsumgebung zur Programmierung von [Atmel](http://www.atmel.com/) Mikrocontrollern. Sie besteht hauptsächlich aus drei Teilen: einem **Editor**, einem **Debugger** und verschieden **Werkzeugen**. Es können Programme in **C/C++ und Assembler** programmiert werden. <br>
Die Entwicklungsumgebung wird verwendet um Programme, simuliert auf Mikrocontrollern auszuführen. Außerdem werden alle Maschinenbefehle aufgelistet.

### CPU
Im folgenden Blockdiagramm ist der prinzipiellen Aufbau einer CPU dargestellt.
![CPU-Aufbau](https://github.com/HTLMechatronics/m14-la1-sx/blob/murlom14/cpu.svg)

Quelle: [Mirkroprozessor-FIVU](https://lms.at/dotlrn/classes/informatik/610437.4AHME_FIVU.17_18/xolrn/EC743ABCF7AB5.symlink?resource_id=0-237409759&m=view#188315330)

### Arbeitsspeicher bei Mirkroprozessoren


### Arbeiten mit Atmel Studio

Wir haben ein sehr einfaches C-Programm geschreiben, welches wir anschließend mit Atmel Studio, auf dem Mikroprozessor Atmega328 simuliert haben. 

**Daten von [Atmega328](http://www.microchip.com/wwwproducts/en/ATmega328):**
 * 20MHZ Mikroprozessor
 * 2kB SRAM
 * 1kB EEPROM
 * 32kB Flash-Speicher
 * 32 Register 
 <br>
 

**C-Programm**
```c
int main ()
{
  return 0;
}
```
