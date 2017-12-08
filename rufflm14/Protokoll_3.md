.# # **2.Laborprotokoll** 

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
  Es wurde folgendes Programm analysiert:
  ![Bild C- Code Programm1]()
  
  Dabei ergab sich nach dem Debuggen und Kompilieren folgender Maschinencode:
  
  ![Bild Assembler-Code Programm1]()
  
  Maschinenbefehl | in Worten | Kommentar
--- | --- | ---
`cf.93` | PUSH R28 | Register R28 wird auf den Stack gelegt, weil sich die Register R26-R31 während einer Funktion nicht verändern dürfen.
`df.93` | PUSH R29 | Register R29 wird auf den Stack gelegt, weil sich die Register R26-R31 während einer Funktion nicht verändern dürfen.
`1f.92` | PUSH R1 | Register R1 wird auf den Stack gelegt. Somit wird auf dem Stack der Speicher für die lokale Variable reserviert.
`cd.b7` | IN R28,0x3D | Der Stackpointer (0x3D) wird aus dem I/O-Register in R28 (Y-Register) geladen.
`de.b7` | IN R29,0x3E | Der Stackpointer (0x3E) wird aus dem I/O-Register in R29 (Y-Register) geladen.
`81.e2` | LDI R24,0x21 | Konstante (0x21 = 12) wird im Register R24 abgelegt.
`89.83` | STD Y+1,R24 | Konstante aus R24 wird am vorhin reservierten Speicherplatz des Stacks abgelegt. Das ist aufgrund des Schlüsselweortes 'volotaile' nötig, weil die Variable ja von außen verändert werden kann.
`89.81` | LDD R24,Y+1 | Die Variable wird ins Register R24 geladen. Das ist aufgrund des Schlüsselwortes 'volotaile' nötig, weil die Variable ja von außen verändert werden kann.
`90.e0` | LDI R25,0x00 | Rückgabewert
`0f.90` | POP R0 | Variable wird freigegeben.
`df.91` | POP R29 | Register R29 wird vom Stack wieder zurückgeholt.
`cf.91` | POP R28 | Register R28 wird vom Stack wieder zurückgeholt. 

### Addition zweier Variablen
Es wurde folgendes Programm analysiert:

![Bild C-Code Programm 2]()

Dabei ergab sich nach dem Debuggen und Kompilieren folgender Maschinencode:

![Bild Assembler-Code Programm 2]()

Maschinenbefehl | in Worten | Kommentar
--------------- | --------- | ---------
`cf.93` | PUSH R28 | Register R28 wird auf den Stack gelegt.
`df.93` | PUSH R29 | Register R29 wird auf den Stack gelegt.
`00.d0` | RCALL PC+0x0001 | Springt zum nächsten Befehl. *Durch den RCALL werden 2 Bytes auf dem Stack reserviert, die für die Variablen a & b verwendet werden.*
`cd.b7` | IN R28,0x3D | 0x3D wird aus dem I/O-Register in R28 geladen.
`de.b7` | IN R29,0x3E | 0x3E wird aus dem I/O-Register in R29 geladen.
`8c.c0` | LDI R24,0x0C | Konstante (0C = 12) wird im Register R24 abgelegt.
`89.83` | STD Y+1,R24 | Konstante aus R24 wird am Speicherplatz des Stacks der ersten lokalen Variable (a) abgelegt.
`88.e0` | LDI R24,0x08 | Konstante (08 = 8) wird im Register R24 abgelegt.
`89.83` | STD Y+2,R24 | Konstante aus R24 wird am Speicherplatz des Stacks der zweiten lokalen Variable (b) abgelegt.
`89.81` | LDD R24,Y+1 | Variable a wird in Register R24 geladen.
`2a.81` | LDD R18,Y+2 | Variable b wird in Register R18 geladen.
`30.e0` | LDI R19, 0x00 | Konstante 0x00 wird am Register R19 abgelegt.
`28.0f` | ADD R18,R24 | Die beiden Register werden addiert, ohne Berücksichtigung des Carry-Flags. Das Endergebnis wird in R18 gespeichert.
`31.1d` | ADC R19,R1 | Addition mit Berücksichtigung des Carry-Flags. *Das Carry-Flag enthält den Übertrag einer Addition. [Weitere Informationen](https://de.wikipedia.org/wiki/Übertragsbit)
`0f.90` | POP R0 | Variable b wird freigegeben.
`0f.90` | POP R0 | Variable a wird freigegeben.
`df.91` | POP R29 | Register R29 wird vom Stack entfernt.
`cf.91` | POP R28 | Register R28 wird vom Stack entfernt.




