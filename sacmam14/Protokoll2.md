# 1. Protokoll
## Thema: Atmel Studio  
**Name:** Sackl Martin   
**Klasse** 4ahme    
**Gruppe:** 3

Anwesend: Reinbacher, Ruffenacht, Sackl M., Sackl R., Sammer, Schmuck, Schuster   
Abwesend: -  

### Issues  
Issues sind Kommunikationsmöglichkeiten auf GitHub. Man kann auf einen beliebigen Repository eine Nachricht hinterlassen. Dadurch können Fehler und Erweiterungen in einem Projekt leichter verfolgt werden.  
Mehr dazu finden Sie [hier](https://guides.github.com/features/issues/).  

### Forks  
Ein Fork ist eine Kopie eines beliebigen Repositorys in das eigene Repository. Diese Funktion kann genutzt werden, wenn man einen Bug findet und man ihn selbst beheben möchte. Wenn man den Fehler behoben hat kann man ein **pull request** durchführen. Das bedeutet, dass das fehlerfreie Programm wieder ins original Repository übernommen werden soll. Der Entwickler kann diesen Vorgang ablehnen.  

## Atmel Studio  
Atmel Studio ist eine Entwicklungsumgebung, welche von der Firma Atmel zur Verfügung gestellt wird. Atmel Studio wird dazu verwendet um Programme für die Chips der Firma Atmel zu programmieren und kann außerdem für die Simulation von Mikrocontrollern verwendet werden.  

Wenn man mit Atmel Studios die Ausführung eines Programmes auf einem Mikrocontroller simuliert, erhält man detailierte Informationen über die Maschinenbefehle, welche aus dem Quellcode des Programmes kompiliert wurden. Desweiteren können die Register des Controllers eingesehen werden.  

### CPU-Aufbau  
![CPU](https://github.com/HTLMechatronics/m14-la1-sx/blob/sacmam14/sacmam14/CPU.PNG)  

* **Befehlsregister**  hier werden die vom Speicher kommenden Maschinenbefehle zwischengespeichert  
* **Program Counter** hier wird die Speicheradresse des nächsten Maschinbefehles angegeben    
* **Stack Pointer** zeigt nächsten freien Platz im Stack-Speicher  

### Atmega 328p  
In der Schule arbeiten wir mit dem Atmega 328p. In Atmel Studios gibt es diese Ausführung des µ-Cs allerdings nicht, daher verwendeten wir bei der Übung den Atmega328.  

Einige Daten zum Atmega 328p:  

* 16MHz Mikroprozessor  
* 32kB Flash-Speicher  
* 32 Register  
* 2kB SRAM  
* 1kB EEPROM  

### XYZ-Register  
Beim Atmega328p gibt es die sogenannten XYZ Register. Diese werden dazu verwendet, um Werte > 255 zu speichern. Dies Register Setzen sich wie folgt zusammen:  

* X = Register 26+27  
* Y = Register 28+29  
* Z = Register 30+31  

Weitere wichtige Register sind:  

* Register 3F = SREG = Statusflagregister  
* Register 3E = SPH = Stackpointer initialisieren (Register 7-15)  
* Register 3D = SPL = Stackpointer initialisieren (Register 0-7)  

### Stack  
Im Stack werden Daten nach dem Last-in-first-out (LIFO) Verfahren gespeichert. Sprich, die Daten werden von unten nach oben abgelegt, gelesen werden kann aber immer nur von oben nach unten. Um in den Stack zu speichern, bzw. daraus zu lesen gibt es folgende Operationen:  

* push: Legt die Daten auf den Stapel  
* pop: Liest das oberste Objekt aus und entfernt es aus dem Stack  
* peek: Liest das oberste Objekt aus, aber belässt es auf dem Stapel  

#### Stack-Pointer  
Der Stackpointer zeigt immer auf den nächsten freien Platz im Stack-Speicher. Wenn der Stack also leer ist, zeigt der Stackpointer auf den unteresten Platz im Speicher. Bei unserer Simulation war das der Wert 08FF. Wenn der Stackpointer allerdings über den reservierten Speicherplatz hinaus geht, spricht man von einem Stackoverflow.  

### Aufbau SRAM  
![SRAM](https://github.com/HTLMechatronics/m14-la1-sx/blob/sacmam14/sacmam14/SRAM_Aufbau.PNG)  

### Übung  
In Atmel Studio wurde folgender Code erstellt:  
```c  
int main ()  
{  
return 0;  
}  
```  
Atmel Studio lieferte uns einige Maschinenbefehle, welche aus dem Quellcode kompiliert wurden. Mit Hilfe des [Atmel Instruction Set Manual](http://www.atmel.com/images/Atmel-0856-AVR-Instruction-Set-Manual.pdf) konnten wir dann die Funktion der Maschinenbefehle bestimmen. Die Maschinenbefehle müssen unter der mega-AVR-Familie nachgeschlagen werden, da die Maschinenbefehle bei anderen µ-Cs anders arbeiten könnten und z.B. andere Register beschreiben werden könnten.  

### Maschinenbefehle  
Maschinenbefehl | Funktion  
--------------- | --------  
JMP | Sprung zu einer bestimmten Adresse (benötigt 8 Bytes)  
RJMP | Sprung zu einer Adresse (kann nur einen bestimmten Offset überspringen, benötigt 4 Bytes)  
OUT | Überträgt die Daten von Register 1 in ein I/O Register  (0x3F -> 3F = Statusregister)   
CLR | Setzt Register 1 auf 0 (Entspricht XOR)  
SER |  Register wird mit Einsen überschrieben bzw. auf den höchstmöglichen Wert gesetzt 
LDI | Konstante wird in Register geschrieben (nur bei Registern 16-31 möglich)  




