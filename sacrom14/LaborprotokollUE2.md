
# 2. Protokoll  28.11.2017

## Thema: Atmel Studio

**Name:** Sackl Roland   
**Klasse:** 4AHME  
**Gruppe:** 3  

**Anwesend:** Sackl Martin, Sammer Daniel, Schmuck Martin, Ruffennacht Florian,Schuster Patrick,Sackl Roland,Reinbacher Bernhard  
**Abwesend:** -  

--------------------

## Git-Hub  
### Issues

Issues sind Feedbacks von anderen Git-Nutzern. Dadurch können Erweiterungen sowie Fehler für ein Projekt leichter vefolgt werden.  
Issues können mit dem gesamten Team geteilt werden. Eine weitere Möglichkeit is es wenn ein Issue verfasst wurde, der Ersteller des Projektes über eine E-Mail informiert wird.

* ein neues Issue erstellen mit*new Issue*       
* nur der Benutzer kann Issues schließen mittels close 

Mehr Information [hier](https://guides.github.com/features/issues/)


### Fork  
Als **Fork** bezeichnet man eine exakte Kopie des gesamten Repositorys.Wird gemacht wenn sich plötzlich der Innhaber nichts mehr ändern kann(z.B. Autounfall).Auf der Startseite des Repository wird angezeigt wenn es Forks gibt,den er dann suchen kann, um mögliche Änderungen zu übernehmen.  Fork kann auch auch genutzt werden, wenn sich der eigentlicher Ersteller eines Projekts nicht mehr meldet und man das Projekt weiterleben lassen möchte.    



### Tiobe Index und Red Monk 
Im *Tiobe Index* werden die wichtigsten Programmiersprachen aufgelistet.Ein weiteres Möglichkeit dafür ist *Red Monk*.   
Weitere Informationen:  
* [Red Monk](http://redmonk.com/sogrady/2017/06/08/language-rankings-6-17/)  
* [Tiobe Index](https://www.tiobe.com/tiobe-index/)   


## Atmel Studio
Atmel Studio ist eine Entwicklungsumgebung, die die Firma **Atmel** zur Verfügung stellt.
Die IDE ist optimiert für die Entwicklung von Programmen für die hauseigenen Chips, aber auch für die Simulation der Mikrocontroller.

Mit Atmel Studio kann man die Ausführung eines Programms auf einem Atmel-Mikrokontroller simulieren. Man erhält detaillierte Informationen über die Maschinenbefehle, die aus dem Quellcode kompiliert wurden. Außerdem hat man Einblick in die Register des Controllers.

Atmel Studio wurde in *Microsoft Visual Studio* programmiert, daher ist die Software nur für Microsoft **Windows**-betriebene Systeme verfügbar.
Allein für die Prgrammierung gibt es aber Alternativen, wie das uns bekannte *NetBeans*, oder die *Arduino IDE*. Beide sind für **Linux** und Apples **OS X** ebenfalls verfügbar.

  [Website Netbeans](https://netbeans.org)    
  [Website Arduino IDE](https://www.arduino.cc/en/main/software#)   
  [Website Atmel](http://www.atmel.com)    
  [Website Atmel Studio 7](http://www.atmel.com/microsite/atmel-studio/)    
 

### Hardware
Im Unterricht wird von uns der [ATmega328p](http://www.atmel.com/Images/Atmel-42735-8-bit-AVR-Microcontroller-ATmega328-328P_Datasheet.pdf) verwendet. Auf Grund das dieser Mikrocontroller in Atmel Studio nicht zur Verfügung steht,wählen wir den sehr ähnlichen **ATmega328** aus.  

Produktinformationen:
* 16MHz Mikroprozessor
* 32kB Flash-Speicher
* 32 Register
* 2kB SRAM
* 1kB EEPROM



### X-, Y-, und Z-Register  
Mithilfe dieser 3 Register kann man werte größer als 255 speichern. Im Normalfall besteht ein Register aus 8 Bit, damit kann man Werte bis 255 darstellen. Um diesen Bereich zu vergrößern werden, die Register 26-31 zu je 2 zusammengefasst und man kann somit 16 Bit also 65535 Werte darstellen.   

### Stack
Der Stack ist wichtiger Bestandteil des Speichers und wird im Deutschen als Stapelspeicher bezeichnet. In diesem Speicher werden Daten nach dem last-in, first-out Prinzip abgelegt bzw. aufgerufen. Dieses Prinzip ist vergleichbar mit einem Bücherstapel. Das zuletzt hinzugefügte Buch wird als erstes heruntergenommen.

 
 ### CPU-Aufbau
  ![CPU](https://github.com/HTLMechatronics/m14-la1-sx/blob/moemim14/moemim14/CPU.PNG)
  > Quelle: [FIVU Skript](https://lms.at/dotlrn/classes/informatik/610437.4AHME_FIVU.17_18/xolrn/EC743ABCF7AB5.symlink?resource_id=0-237409759&m=view#188315330)
  
* **Befehlsregister** werden die vom Speicher kommenden Maschinenbefehle zwischengespeichert 
* **Program Counter** gibt die Speicheradresse des nächsten Maschinenbefehls  
* **Stack Pointer**  für den nächsten freien Platz im Stack-Speicher


### Aufbau SRAM
![SRAM](https://github.com/HTLMechatronics/m14-la1-sx/blob/moemim14/moemim14/SRAM_Aufbau.PNG)
> Quelle: [FIVU Skript](https://lms.at/dotlrn/classes/informatik/610437.4AHME_FIVU.17_18/xolrn/EC743ABCF7AB5.symlink?resource_id=0-237409759&m=view#189503049)



### Übung
In Atmel Studio wurde folgender Code erstellt:
```c
int main ()
{
return 0;
}
```



### Zusammenfassung der häufigsten Maschienenbefehle:
Maschinenbefehl | Ergebnis
--------------- | --------
JMP | Sprung zu einer bestimmten Adresse (benötigt 8 Bytes)
RJMP | Sprung zu einer Adresse (Offset muss eingehalten werden, benötigt 4 Bytes)
OUT | schreibt Daten von einem in ein anderes Register
CLR | Register wird mit Nullen überschrieben (Realisierung durch XOR-Verknüpfung mit sich selbst)
SER | Register wird mit Einsen überschrieben bzw. auf den höchstmöglichen Wert gesetzt
LDI | Konstante wird in Register geschrieben (nur bei Registern 16-31 möglich)



