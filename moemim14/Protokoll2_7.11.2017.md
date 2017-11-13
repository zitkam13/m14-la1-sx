# Protokoll 1 31.10.2017

## Thema: Atmel Studio

Name: Michael Mörth  
Klasse: 4AHME  
Gruppe: 2  

Anwesend: Nebel Florian, Mandl Gerhard, Michael Mörth, Moritz Martinak, Mario Nabernik, Muri Lorenz, Platzer Andreas, Marcel Köhler    
Abwesend: -

## Atmel Studio
Atmel Studio ist eine Entwicklungsumgebung, welche von der Firma Atmel zur Verfügung gestellt wird. Atmel Studio wird dazu verwendet um Programme für die Chips der Firma Atmel zu programmieren und kann außerdem für die Simulation von Mikrocontrollern verwendet werden.

Wenn man mit Atmel Studios die Ausführung eines Programmes auf einem Mikrocontroller simuliert, erhält man detailierte Informationen über die Maschinenbefehle, welche aus dem Quellcode des Programmes kompiliert wurden. Desweiteren können die Register des Controllers eingesehen werden.

Genauere Informationen zu Atmel Studio können in den Links unterhalb gefunden werden:  
  [Website Atmel](http://www.atmel.com)  
  [Website Atmel Studio 7](http://www.atmel.com/microsite/atmel-studio/)  
  
  ## CPU-Aufbau
  ![CPU](https://github.com/HTLMechatronics/m14-la1-sx/blob/moemim14/moemim14/CPU.PNG)
  > Quelle: [FIVU Skript](https://lms.at/dotlrn/classes/informatik/610437.4AHME_FIVU.17_18/xolrn/EC743ABCF7AB5.symlink?resource_id=0-237409759&m=view#188315330)

### Atmega 328p
In der Schule arbeiten wir mit dem **Atmega 328p**. In Atmel Studios gibt es diese Ausführung des µ-Cs allerdings nicht, daher verwendeten wir bei der Übung den **Atmega328**.

Einige Daten zum Atmega 328p:
* 16MHz Mikroprozessor
* 32kB Flash-Speicher
* 32 Register
* 2kB SRAM
* 1kB EEPROM

### XYZ Register
Beim Atmega328p gibt es die sogenannten XYZ Register. Diese werden dazu verwendet, um Werte > 255 zu speichern. Dies Register Setzen sich wie folgt zusammen:
* X = Register 26+27
* Y = Register 28+29
* Z = Register 30+31

Weitere wichtige Register sind:
* Register 3F = SREG = Statusflagregister
* Register 3E = SPH = Stackpointer initialisieren (Register 7-15)
* Register 3D = SDL = Stackpointer initialisieren (Register 0-7)

Pinbelegung und weitere Informationen zum Atmega328p können [hier](http://www.atmel.com/Images/Atmel-42735-8-bit-AVR-Microcontroller-ATmega328-328P_Datasheet.pdf) nachgelesen werden.

## Stack
Der Stack wird auch als **Stapelspeicher** bezeichnet. Im Stack werden Daten im Speicher von unten nach oben abgelegt. Dieses Verfahren nennt man Last-in-first-out. Eingelesen werden die Daten dann allerdings von oben nach unten.

### Stack-pointer
Der Stackpointer zeigt immer auf den **nächsten freien Platz** im Stack-Speicher. Wenn der Stack also leer ist, zeigt der Stackpointer auf den unteresten Platz im Speicher. Bei unserer Simulation war das der Wert `08FF`. Wenn der Stackpointer allerdings über den reservierten Speicherplatz hinaus geht, spricht man von einem **Stackoverflow**.

### Aufbau SRAM
![SRAM](https://github.com/HTLMechatronics/m14-la1-sx/blob/moemim14/moemim14/SRAM_Aufbau.PNG)
> Quelle: [FIVU Skript](https://lms.at/dotlrn/classes/informatik/610437.4AHME_FIVU.17_18/xolrn/EC743ABCF7AB5.symlink?resource_id=0-237409759&m=view#189503049)

## Übung
Folgender Code wurde erstellt und simuliert:
```c
int main ()
{
  return 0;
}
```

