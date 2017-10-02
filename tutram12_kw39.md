# Protokoll Labor KW39  

Name: Raphael Tuttner    
Klasse: 4AHME    
Gruppe: 4  
Datum: 27.09.2017

## Git Repository mit Linux-Terminal bearbeiten  

Um mit dem Linux-Terminal ein Git-Repository zu bearbeiten, muss man es vom Server klonen.  
Dies funktioniert mit dem Befehl "git clone (gefolgt vom Link des Repositorys)".  
Den Link findet man bei GitHub in der Repository unter dem Button clone or downlad.  
  
Erst dann kann man mit der Konsole oder mit dem Dateimanger Dateien einfügen und/oder bearbeiten.  
Damit man die Dateien wieder mit dem Github-Server synchronisiert benötigt man folgende Befehele.  
* **git add -A** (-A = Damit alle Dateien in den Index kopiert werden)  
* **git commit -m ".........."** (-m = Für ein Kommentar, verschiebt die Dateien ins Local Repository)  
* **git push** (übermittelt die Daten auf den Server)  
  
Wenn man mit einem gemeinsamen Repository arbeitet kann man auch mit dem Linux-Terminal Branches erstellen um die Dateien zu Organisieren.  
Dies funktoniert mit dem folgenden Befehl:  
* **git checkout -b "tutram12"**  

### SSH Schlüssel bei GitHub  
Bevor man mit einem SSH-SChlüssel klonen kann muss man zuerst am Linux System ein RSA-Schlüsselpaar erstellen. Das funktioniert mit der Konsole mit dem Befehl "ssh-keygen". 
  
Danchach muss man den öffentlichen Schlüssel (id_rsa.pub) bei GitHub in die entsprechenden Einstellungen einfügen.  
* **Settings** in GitHub  
* **SSH and GPG keys**  
* **New SSH key**   



## Atmel AVR Studio  
Atmel AVR Studio ist ein Program mit dem man Mirkrocontroller programmieren und die Programme simulieren kann.  
Auf diesem Bild sieht man die Benutzeroberfläche mit ein paar Erklärungen:  
![avr-studio](https://github.com/HTLMechatronics/m14-la1-sx/blob/tutram12/tutram12/avr-studio.png)  
(Copyright zitkam13, bei mir hat AVR-Studio nicht richtig funktioniert)  

AVR-Studio gibt es nur für Windows-Systeme. Keine weiteren Alternativen sind bekannt.  
