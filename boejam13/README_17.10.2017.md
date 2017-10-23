# Protokoll
## 2. Einheit
  Name: Jakob Boecksteiner  
  Klasse: 4AHME, Gruppe 1  
  Datum: 17.10.2017  
  Anwesend: Berger, Böcksteiner, Bullner, Enzi, Ehmann, Kobor, Knappitsch  
  Abwesend: niemand  
  
  ## Atmel Studio  
  Ist ein Entwicklungsprogramm für Mikrokontroller, es werden die Programmiersprachen C, C++ und Assambler verwendet. Dieses Programm ist leider nur unter Windows verfügbar deshalb verwenden wir es nur um den Prozess der Programmierung zu verstehen.  
  
  ### Erstes Programm  
  Als erstes muss man um ein Projekt zu starten eine Programmiersprache auswählen und danach den gewünschten Prozessor in unserem Fall ist das der ATmega328P, da wir auch in FIVU mit diesem Prozessor arbeiten.
  
  ### Daten ATmega328P
  [Datenblatt ATmega328P](http://www.atmel.com/Images/Atmel-42735-8-bit-AVR-Microcontroller-ATmega328-328P_Datasheet.pdf)
  * Frequenz: 16MHz  
  * Flash-Speicher: 32kb  
  * RAM: 2kb (Static RAM)  
  * CPU-Register: 32 (zu je 8 Bit)  
  * 1 kb EEPROM (Electrically Erasable Programmable Read-Only Memory)
  
  ### CPU-Register
  Der ATmega328P verfügt über einen XYZ-Register:   
  * X = 26&27   
  * Y = 28&29   
  * Z = 30&31  
  
  Diese Register haben den zweck um werte die größer als 255 sind zu speichern.
  
  ### CPU Aufbau
 ![CPU-Aufbau](https://github.com/HTLMechatronics/m14-la1-sx/blob/boejam13/boejam13/CPU-Mikroprozessor.png)  
   Für genauere Information siehe FIVU-Biblithek: [FIVU-µC, CPU](https://lms.at/dotlrn/classes/informatik/610437.4AHME_FIVU.17_18/xolrn/EC743ABCF7AB5.symlink?resource_id=0-237409759&m=view#188315330)  
   
  ## Stack
  Stackdaten werden mit dem LIFO Verfahrenen gespeichert (Last in first Out), das heist die Daten werden zwar von unten nach oben angelegt jedoch werden sie von oben nach unten ausgelesen. Funktionen für den Stack:  
- push: Legt die Datei in den Stack
- pop: Oberstes Objekt wird ausgelesen und aus dem Stack entfernt  
- peek: Oberstes Objekt wird ausgelesen wird aber nicht entfernt
   
   ### Stackpointer
   
   Der Stackpionter zeigt immer auf den nächsten freien platz im Stack, zeigt dieser auf den ersten Wert, ist der Stack leer in unserem Fall wäre das der Wert *08FF*. Zeigt der Stackpointer auf einen Wert der nicht mehr im Rahmen für den Stack liegt so spricht man von einem Stackoverflow.
   
   ![Aufbau Stack ATmega328P](https://github.com/HTLMechatronics/m14-la1-sx/blob/boejam13/boejam13/StackSpeicher.png)  
   
   ## Übung
   
   Wir haben eine einfache main funktion erstellt die nur einen **return 0;** enthalten hat wir haben die wichtigsten Codes aus dem [Instruction Set Manual](http://www.atmel.com/images/Atmel-0856-AVR-Instruction-Set-Manual.pdf) herausgesucht. Die Wichtigsten Maschinenbefehle folgen.  
   
   Maschinenbefehl | Ausführung
   --------------- | ----------
   RJMP | springt zu einem anders gelistetem Maschinenbefehl
   CLR R1 | Das Register R1 wird mit sich selbst XOR verknüpft --> es wird mit Nullen überschrieben
   OUT 0x3F, R1 | 0x3F --> Statusregister wird auf '0' gesetzt
   SER R28 | setzt R28 auf 0xFF
   CDI R29, 0x08 | *CDI --> lädt Konstante in Register 16-31* 0x08 wird in Register 29 geladen. Dadurch, dass R28 auf 0xFF und R29 auf    0x08 gesetzt wird, wird das Y-Register '0x08FF'
   OUT 0x3E, R29 | 0x3E & 0x3D --> Stackpointer
   OUT 0x3D, R29 | Stackpointer auf '08FF' gesetzt, das heist er ist leer (08FF ist der erste Stackspeicher). 
