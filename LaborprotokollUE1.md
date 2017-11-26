# Laborprotokoll  
Erste Einheit am 21. Nov. 2017  
Martin Schmuck  
4AHME  
Gruppe 3

Automatisierungslabor HTL Kaindorf  
Anwesend: Reinbacher, Ruffenacht, Sackl M., Sackl R., Sammer, Schmuck, Schuster  
Abwesend: niemand  

## Thema der Einheit: Einführung in GIT
___________________
  
#### Was ist eine Versionsverwaltung?  
Eine Versionsverwaltung wird immer dann verwendet, wenn mehrere Personen an einem Projekt arbeiten oder auch wenn man nur allein daran arbeitet, sich aber die Möglichkeit schaffen möchte, jederzeit zu einem früheren Zeitpunkt im Projekt zurückzukehren.

#### Was ist GIT?
Git ist ein eine freie Software, welche die Versionsverwaltung von Dateien möglich macht. Sie wurde vom Linux-Gründer Linus Torvalds ins Leben gerufen. Die Besonderheiten von GIT sind unter anderem:
* Repositories sind offline zugänglich
* sie werden lokal am Rechner als auch auf einem Server gespeichert
* man kann auch ohne Internetverbindung ganz normal mit seinen Dateien arbeiten  

#### Was ist GitHub?  
GitHub ist ein Onlinedienst zur Versionsverwaltung auf Basis von GIT. Hauptmerkmale sind unter anderem:
* Registrierung von Privatpersonen, Organisationen oder Unternehmen ist kostenlos
* Der Betrieb von beliebig vielen öffentlich zugänglichen Repositories ist kostenlos
* Der Betrieb von beliebig vielen privaten Repositories schlägt mit 8 USD pro Monat zu Buche.    

Eine Alternative zu GitHub wäre [BitBucket](https://bitbucket.org/).

#### Wie beginnt man mit GIT?  
Als erstes muss man sich das Git-Paket am Rechner installieren (z.B. mit apt-get install git). Danach legt man sich am besten einen Ornder an, der nur für GIT-Repositories gedacht ist. Ist dies geschehen, muss man noch mit   

git config --global user.name "Franz Meier"   
git config --global user.email meierfranzl@saustall.at

seine persönlichen Einstellungen hinterlegen. Nun kann man schon entweder mit git init ein neues Repository anlegen oder mit git clone ein entferntes Repository klonen. Am besten ist, man klont sich das Repository mit einem SSH-Schlüssel, da dies wesentlich sicherer ist, als die Kennwortauthentifizierung. 


