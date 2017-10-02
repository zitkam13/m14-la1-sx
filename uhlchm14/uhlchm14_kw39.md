
# KW39
 
Name: Christian Uhl

Klasse: 4AHME

Datum: 26.09.2017

Gruppe: 4


## Bearbeiten eines Git Repository mit einem Linux System

Um mit einem Repository in der Linux Konsole arbeiten zu können, muss man es zuerst vom Server klonen.

Das funktioniert in der Konsole mit dem Befehl **"git clone"** und danach der Link des Repository.

Den Link dazu findet man auf der Github [Webseite](github.com) unter **"clone or download"**

![cod](https://raw.githubusercontent.com/uhlchm14/rep1/master/4.PNG)

Danach kann man in der Konsole Daten verwalten, Branches erstellen und Dateien bearbeiten.

Hier sind die wichtigsten Befehle dazu:

* **git add -A** (-A um alles zu kopieren)

* **git commit -m "<Kommentar>"** (-m für einen Kommentar in den Anführungszeichen)

* **git push** (Repository auf den Server laden)

* **git checkout -b "uhlchm14"** (Dateien in einem bestimmten Branch speichern)


## SSH Schlüssel

Für einen SSH Schlüssel muss zuerst in der Konsole mit dem Befehl **"ssh-keygen"** ein RSA Schlüsselpaar (öffentlicher und privater Schlüssel) erzeugt werden.

Nach dem Erzeugen wird der öffentliche Schlüssel mit dem Namen *id_rsa.pub* auf der Github [Webseite](github.com) unter den Einstellungen eingefügt.

![SSH KEYS](https://raw.githubusercontent.com/uhlchm14/rep1/master/1.PNG)

Durch das Erstellen des SSH Schlüssels ist nun das klonen mittels SSH möglich.

![cod](https://raw.githubusercontent.com/uhlchm14/rep1/master/2.PNG)

## Atmel AVR Studio  
Atmel AVR Studio ist ein Program mit dem man einen Mirkrocontroller programmieren bzw. simulieren kann. Am folgendem Bild ist die Benutzeröberfläche grob erklärt. Microkontroller werden in **C** programmiert.
![AVR-Studio](https://maxembedded.files.wordpress.com/2011/06/avr-studio-new-project-start-screen.png)  
AVR-Studio gibt es nur für Windows-Systeme.

