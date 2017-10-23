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
- pop: Oberstes objekt wird ausgelesen und aus dem Stack eintfernt  
- peek: Oberstes Objekt wird ausgelesen wird aber nicht entfernt
   
   
