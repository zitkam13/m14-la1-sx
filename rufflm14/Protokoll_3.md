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
  Als erstes wurde mit
  

