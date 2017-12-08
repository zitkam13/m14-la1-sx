# # **2.Laborprotokoll** 

*von Florian Ruffenacht*

Datum: 05.12.2017 (Gruppe 3)

Ort: AUT-Labor

Lehrkraft: SX

Abwesend: -

## CPU-Register
Die folgende Register werden für spezielle Zwecke verwendet:

Register | Verwendung 
|---|---|
'R1'| ist immer mit 0x00 beschrieben
'R8-R25'| für Pararmeter und Rückgabewerte
'R26 + R27'| X- Register für Adressen
'R28 + R29'| Y- Register für Adressen
'R30 + R31 | Z- Register für Adressen

## Unterschied zwischen deklarieren, definieren und initialisieren

**Deklaration:** Dabei wird dem Compiler eine Variable bekannt gegeben

**Definition:** Dabei wird einer Variable ein Speicherbereich zugeteilt

**Initialisierung:** Dabei wird der Variable ein Wert zugewiesen

[Weitere Informationen](http://www.c-howto.de/tutorial/variablen/deklaration/)

## Analysieren von Assembler-Befehlen
  Wie bereits in der [letzten Einheit]() analysierten wir einfache C-Programme mit AtmelStudio.
  
### Informationen zum Syntax:

  **volotaile**
  
  Mit dem Schlüsselwort 'volotaile' wir dem Compiler bei der Varaiblendeklaration bekannt gegeben, dass die Variable
  auch durch analoge Signale von außen verändert werden kann. Das Schlüsselwort wurde verwendet um den Compiler davon abzuhalten,
  die einfachen Gleichungen unserer Programme selber zu lösen und im Programm nur mehr zurückzugeben.
  
  **unsignede char**
  
  Den Datentyp 'unsigned char' verwenden wir um mit 1 Byte vorzeichenunbehaftete Zahlen zwischen 0 und 255 darstellen zu können. 
  Die Datentypen 'char' und 'signed char' sinf vorzeichenbehaftet.
   
### Zuweisen eines Konstanten Wertes
  Es wurde folgendes Programm analysiert.
  ![Bild C- Code Programm1]()
  
  Dabei ergab sich nach dem Debuggen und Kompilieren folgender Maschinencode:
  
  ![Bild Assembler-Code Programm1]()
  
  Maschinenbefehl | in Worten | Kommentar
--- | --- | ---
`cf.93` | PUSH R28 | Register R28 wird auf den Stack gelegt, weil sich die Register R26-R31 während einer Funktion nicht verändern dürfen
`df.93` | PUSH R29 | Register R29 wird auf den Stack gelegt.
`1f.92` | PUSH R1 | Register R1 wird auf den Stack gelegt. *Register R1 ist immer "0", es wird auf dem Stack der Speicher für die lokale Variable reserviert.*
`cd.b7` | IN R28,0x3D | 0x3D wird aus dem I/O-Register in R28 geladen.
`de.b7` | IN R29,0x3E | 0x3E wird aus dem I/O-Register in R29 geladen.
`8c.e0` | LDI R24,0x0C | Konstante (0C = 12) wird im Register R24 abgelegt.
`89.83` | STD Y+1,R24 | Konstante aus R24 wird am Speicherplatz des Stacks der lokalen Variable abgelegt. *R28 & R29 beschreiben das Y-Register. Da die Variable genau nach dem Y-Register auf den Stack gelegt wurde, ist die Adresse im Stack "Y+1"* Die Variable wird gespeichert.
`89.81` | LDD R24,Y+1 | Die Variable wird in Register R24 geladen.
`90.e0` | LDI R25,0x00 | Rückgabewert
`0f.90` | POP R0 | Variable wird freigegeben.
`df.91` | POP R29 | Register R29 wird vom Stack entfernt.
`cf.91` | POP R28 | Register R28 wird vom Stack entfernt. *(R29 muss zuerst enfernt werden, da im Stack nur von oben nach unten gelesen werden kann. Gespeichert kann hingegen nur von unten nach oben werden. Weiteres ist ebenfalls im [Protokoll der zweiten Einheit](/beremm14/README_2017-10-17.md) zu finden.)*



