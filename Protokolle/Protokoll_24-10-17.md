# Protokoll: Knappitsch Robert

## 3. Einheit: Atmel Studio
* Klasse: 4AHME (Gruppe 1)
* Datum: 24.10.2017
* Anwesend: Berger Emil, Bullner Jeremy, Böcksteiner Jakob, Ehmann Julian, Enzi Gert, Kobor Markus, Knappitsch Robert
* Abwesend: -
### Wiederholung
Nachdem die Protokolle kontrolliert wurden, hat Herr Prof. Steiner jedem Schüler der Teilgruppe einige Fragen zum Stoff der vergangenen Stunden (siehe Protokoll [1](https://github.com/HTLMechatronics/m14-la1-sx/blob/knarom14/Protokolle/Protokoll_10-10-17.md)&[2](https://github.com/HTLMechatronics/m14-la1-sx/blob/knarom14/Protokolle/Protokoll_17-10-17.md)) gestellt. Die Note setzte sich dann aus Protokoll und Stundenwiederholung zusammen.

### Heartbleed-Bug
Der Heartbleed-Bug ist ein schwerwiegender Programmfehler in OpenSSL. Gelöschte Daten (private Schlüssel) werden nicht direkt vom Speicher entfernt. Sie bleiben solange erhalten, bis sie von neuen Daten überschrieben werden. Hacker konnten diesen Bug ausnutzen, indem sie Anfragen an den Server schickten, bei denen sie sich mit zusätzlichen Befehlen deutlich mehr Daten schicken ließen. So wurden auch die "gelöschten" privaten Schlüssel freigegeben. Der Bug wurde allerdings behoben bevor Hacker großen Schaden anrichten konnten.

### Praktische Übung
<pre><code>int main (void)
{
unsigned char x;
x = 12;
return 0;
} </code></pre>

#### Disassembly
<pre><code>PUSH R28     --> legt R28 auf dem Stack ab
PUSH R29   --> legt R29 auf dem Stack ab 
PUSH R1   --> legt R1 am Stack ab
IN R28, 0x3D  --> lädt SPL in R28
IN R29, 0x3E  --> lädt SPH in R29
LDI R24, 0x0C   --> speichert eine 8 Bit Konstante R24
STD Y+1, R24
LDD R24, Y+1
LDI R25, 0x00   --> setzt R25 auf 0
POP R0  --> entfernt R0 vom Stack, um um an R29/R28 heranzukommen
POP R29
POP R28   --> stellt R28 und R29 wieder her, da er diese Register nicht verändern darf
