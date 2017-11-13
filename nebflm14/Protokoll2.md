# Protokoll der 2.Einheit (7.11.2017)

## Thema: Einführung zu Atmel Studio

Name:     Florian Nebel  
Klasse:   4AHME  
Gruppe:   2  

Anwesend: Köhler Marcel, Mandl Gerhard, Martinak Moritz, Mörth Michael, Muri Lorenz, Nabernik Mario, Nebel Florian, Platzer Andreas  
Abwesend: ---

## Was versteht man unter [Atmel Studio](http://www.atmel.com/microsite/atmel-studio/)?
Atmel Studio ist eine kostenlose Entwicklungsumgebung, welche von Atmel Corporation zur Verfügung gestellt wird. Grundsätzlich wurde Atmel Studio entwickelt um Software für Chips, hergestellt von Atmel Corporation, zu programmieren bzw. simmulieren. Dieses Programm kann auch für die Simulation von Chips anderer Hersteller verwendet werden. Da Atmel Studio auf der Visual Studio Shell, hergestellt von Microsoft basiert, kann es aber nur unter Windows eingesetzt werden.

## Hardware
Im Unterricht wird von uns der [ATmega328p](http://www.atmel.com/Images/Atmel-42735-8-bit-AVR-Microcontroller-ATmega328-328P_Datasheet.pdf) verwendet. Da dieser Mikrocontroller in Atmel Studio nicht zur Verfügung steht, weichen wir bei unseren Übungen auf den sehr ähnlichen **ATmega328** aus.

Produktinformationen:
* 16MHz Mikroprozessor
* 32kB Flash-Speicher
* 32 Register
* 2kB SRAM
* 1kB EEPROM

## X-, Y- und Z-Register
Diese drei Register erlauben es Werte größer als 255 zu speichern. Grundsetzlich besteht ein Register aus 8 Bits. Da für Werte >255 8 Bits nicht ausreichen werden jeweils zwei Register zu den X-, Y- und Z-Registern kombiniert. Das erlaubt es Werte bis zu einer Größe von 65535 (16 Bits) zu speichern. Es werden die Register 26-31 zu den X-, Y- und Z-Registern zusammengefast.

## Stack
Der Stack ist wichtiger Bestandteil des Speichers und wird im Deutschen als Stapelspeicher bezeichnet. In diesem Speicher werden Daten nach dem last-in, first-out Prinzip abgelegt bzw. aufgerufen. Dieses Prinzip ist vergleichbar mit einem Bücherstapel. Das zuletzt hinzugefügte Buch wird als erstes heruntergenommen.

### Stackpointer
Der Stackpointer entspricht einem Zeiger, welcher auf den *nächsten freien Platz* im Stack zeigt. Zeigt der Zeiger auf den untersten bzw. letzten Platz im Speicher, ist dieser leer. In unserem Fall entsprach dies dem Wert '08FF'. Sollte der Stackpointer auf einen Bereich zeigen, der nicht für den Stack reserviert war spricht man von einem **Stackoverflow**. Dieser löst Probleme aus welche nicht unmittelbar zum Vorschein kommen müssen.

### Aufbau des SRAM's im Atmel ATmega16

> Quelle: [FIVU Skript](https://lms.at/dotlrn/classes/informatik/610437.4AHME_FIVU.17_18/xolrn/EC743ABCF7AB5.symlink?resource_id=0-237409759&m=view#189503049)

## Übung
Folgender Quelltext wurde erstellt, simuliert und analysiert:
```c
int main ()
{
  return 0;
}
```
Die Simulation lieferte uns daraufhin die kompilierten Maschinenbefehle. Um die Funktion der einzelnen Befehle zu Verstehen verwendeten wir das [Atmel Instruction Set Manual](http://www.atmel.com/images/Atmel-0856-AVR-Instruction-Set-Manual.pdf). Es muss Sichergestellt werden, dass es sich um das Benutzerhandbuch für genau diesen Mikroprozessor handelt, da einzelne Befehle abweichen können.

### Hier eine Zusammenfassung der häufigsten Maschienenbefehle:
Maschinenbefehl | Ergebnis
--------------- | --------
JMP | Sprung zu einer bestimmten Adresse (benötigt 8 Bytes)
RJMP | Sprung zu einer Adresse (Offset muss eingehalten werden, benötigt 4 Bytes)
OUT | schreibt Daten von einem in ein anderes Register
CLR | Register wird mit Nullen überschrieben (Realisierung durch XOR-Verknüpfung mit sich selbst)
SER | Register wird mit Einsen überschrieben bzw. auf den höchstmöglichen Wert gesetzt
LDI | Konstante wird in Register geschrieben (nur bei Registern 16-31 möglich)

