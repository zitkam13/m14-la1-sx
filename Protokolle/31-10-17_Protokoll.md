# Protokoll: Marcel Köhler
## Erste Einheit
## Thema: Git u. Markdown
Klasse: 4AHME  
Anwesend: Köhler Marcel, Mandl Gerhard, Martinak Moritz, Mörth Michael, Muri Lorenz, Nabernik Mario, Nebel Florian, Platzer Andreas  
Abwesend: -  

### GitHub
[GitHub](https://github.com) ist ein Webdienst der es Benutzern ermöglicht , mittels Git, öffentliche Repositorys zu erstellen.
Öffentliche Repositorys können von jedem eingesehen werden aber nicht bearbeitet werden. Private Repositorys sind kostenpflichtig und sind nicht
für die Öffentlichkeit zugängig bzw. man kann in diese nicht einsehen wenn man keine Rechte dazu hat.

### Git
[Git](https://de.wikipedia.org/wiki/Git) ist eine kostenlose Software zur Versionsverwaltung von Dateien und wurde von Linus Torvalds initiiert.
Anders als SVN kan Git auch offline benutzt werden da Git nicht nur ein Remote Repository hat sondern am Rechner auch noch ein Lokales Repository
erstellt, was bedeutet das man auch wenn man keine Internetverbndung hat an dem Projekt arbeiten kann.

#### Workflow Ebenen
* stash                 (Zwischenspeicher)
* workspace             (Arbeitsdatei/Kopie)
* index                 (Dateien die bei einem Push ins remote Rep. gesendet werden)
* local repository      (Repository am Rechner)
* remote repository     (Repository auf eiem Server)

#### Git Befehle
* git add               (Datei wird zum Index hinzugefügt)
* git commit [-a]       (Dateie vom Index werden dem Local Repository hinzugefügt (-a lädt alle Dateien ins local Repository))
* git push              (Local Repository wird auf das Remote Repository geladen)
* git clone             (Remote Repository wird ins Local repository gespeichert)
* git checkout <branch> (zum wechseln zwischen der verscheidenenn Branches)
* git merge             (zum zusammenfügen von zwei Branches)

### Versionsverwaltung
Die Versionsverwaltung ist ein System das verwendet wird um Dateien welche gespeichert oder verändert wurden mit einem Zeitstempel zu versehen. Dies ist sehr nützlich da man dadurch, falls eine Datei fehlerhaft ist, eine ältere Version wiederherstellen kann.

* **Branches**  
Branches (Zweige) dienen dazu um an verschiedenen Versionen gleichzeitig arbeiten zu können ohne das man sich untereinander stört.

* **Merge**  
Bei eine merge führt man zwei Arbeitzweige zusammen. Meist passiert dies mit dem Master-branch und dem Work-branch, wenn der Work-branch ausgibig getestet wurde und das Programm/die Datei freigegeben wurde.

### Markdown
[Markdown](https://de.wikipedia.org/wiki/Markdown) ist eine vereinfachte Auszeichnungssprache.
#### Formatierungszeichen
* '# ' 1. Überschrift, '## ' 2. Überschrift ....
* '* ' erstellt eine Liste
* '1. ' erstell eine geornete Liste
* einen Stern for und nach einem Text formatiert den Text in *italic*
* zwei Sterne for und nach einem Text formatiert den Text in **fett**
* '[name] (link)' erstellt einen Link (ohne Leerzeichen zwischen den Klammern)
* '>text' erstellt ein Zitat
