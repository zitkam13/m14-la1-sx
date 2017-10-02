# KW39  

## Git Repository mit einem Linux System  

Bevor man  mit Repository am Linux System arbeiten kann muss man sie vom GitHub-Server klonen.  
Dies funktioniert mit der Konsole mit dem Befehl "git clone und der Link der Repository".  
![git clone](/zitkam13/clone.png)    
Den Link findet man bei GitHub in der Repository unter dem Button **clone or downlad.**  
![clone-link](/zitkam13/clone-link.png)  
Danach kann man mit der Konsole oder mit dem Dateimanger Dateien einfügen oder bearbeiten.  
Damit man die Dateien wieder mit dem Github-Server synchronisiert benötigt man folgende Befehele.  
* git add -A (-A = Damit alle Dateien kopiert werden)  
![git add](/zitkam13/add.png)  
* git commit -m "Kurzbefehl" (-m = Für ein Kommentar)  
![git commit](/zitkam13/commit.png)  
* git push  
![git push](/zitkam13/push.png)  
Wenn man mit einem gemeinsamen Repository arbeitet kann man auch am Linux-System mit der Konsole Branches erstellen, damit man seine eigenen Dateien in einm eigenen Branch speichern kann.  
Dies funktoniert mit dem folgenden Befehl:  
* git checkout -b "zitkam13"  


## SSH Schlüssel bei GitHub  
Bevor man mit einem SSH-Schlüssel klonen kann muss man zuerst am Linux System ein RSA-Schlüsselpaar erstellen. Das funktioniert mit der Konsole mit dem Befehl "ssh-keygen". 
![ssh-keygen](/zitkam13/ssh-keygen.png)  
Danchach muss man den öffentlichen Schlüssel (id_rsa.pub) bei GitHub in de Einstellungen einfügen.  
![schlüsselpaar](/zitkam13/schlüsselpaar.png)
* **Settings** bei GitHub  
* **SSH and GPG keys**  
* **New SSH key**   
![ssh-settings](/zitkam13/ssh-settings.png)

## Atmel AVR Studio  
Atmel AVR Studio ist ein Program mit dem man einen Mirkrocontroller programmieren kann. Am folgenden Bild sieh man die Benutzeroberfläche des Programms.  
![AVR-Studio](/zitkam13/avr-studio.png)  
AVR-Studio gibt es nur für Windows-Systeme.
