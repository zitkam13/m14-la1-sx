# 1.Einheit: 10.10.2017

Gegenstand: LA1  
Name: Gert Enzi  
KN: 5  
Klasse: 4AHME  
Gruppe: 1  

# Einführung Git - Github

## 1: Was ist Git?
Git ist eine sogenannte Versionsverwaltung. Sie dient der Verwaltung von Dateien und hat den Vorteil, dass mehrere Benutzer darauf zugreifen können. Der Vorteil von Repositorys ist, sie werden lokal gespeichert und Änderungen können recht simpel abgerufen beziehungsweise hochgeladen werden.

## 2: Verwendung von Git

Um nun ein solches Repository lokal am Gerät zu speichern benutzt man zunächst den Befehl(Befehle in der Konsole - Git muss installiert sein):  
  
**git clone** *(URL des Repositorys)*   
  
Nun sollte man einen Ordner mit dem Namen des Repositorys im Verzeichnis vorfinden, indem man sich befindet.
Man kann jetzt in diesem Ordner bzw. Verzeichnis arbeiten. Je nach Anwendung Quelltexte oder andere Dateien hinzufügen bzw. bearbeiten.  
  
Will man die Änderungen wieder in das Repository hochladen, verwendet man den Befehl:  
  
**git add -A**(-A bedeutet dass alle Änderungen übernommen werden, man kann anstelle von -A auch die Datei einsetzen wenn man nicht den ganzen Inhalt hochladen möchte)  
  
Nun hat man die Änderung vom **Workspace** (Die Ebene, auf der man am PC arbeitet) in die **Staged Area** verschoben. Mit dem Befehl **git status** kann man sehen welche Elemente sich in der Staged Area befinden, weiters kann man auch den **Branch**, auf dem man sich befindet sehen.  
  
Der nächste Schritt ist:  
  
**git commit -m"Kommentar"**
  
Die nächste Ebene wird **local Repository** genannt. Und mit dem Befehl:  
  
**git push**  
  
werden die Änderungen ins **remote Repository** hochgeladen.  
Wenn man Änderungen vom **remote Repository** beziehen, so ist es nicht notwendig, das gesamte Repository erneut zu klonen.  
Mit dem Befehl:  
  
**git pull**  
  
werden nur die Änderungen vom **remote Repository** in den **Workspace** übernommen.  
Weitere Infos: [Git-Book](https://git-scm.com/book/en/v2)  
  
## 3: Github

Github ist ein kostenloser Online-Dienst, der einem das erstellen und verwalten von Repositorys vereinfachen soll. Ein Nachteil ist, dass solange man nicht gewillt ist zu zahlen jeder darauf zugreifen kann. In unseren Laboreinheiten verwalten wir alles mittels Github.

## 4: Branches

Branches erleichtern das Arbeiten auf einem Repository, vor allem in Sachen Ordnung. Hat man beispielsweise eine Arbeitsgruppe, kann man dem jeweiligen Mitglied einen eigenen Branch zuweisen. Der wichtigste Branch, der in jedem Repository vorhanden sein sollte, ist der Branch **Master**. Auf diesem Branch sollten sich nur Dateien befinden, die nicht fehlerbehaftet sind. So kann man die Dateien auf dem eigenen Branch umändern und sollte etwas schiefgehen, kann man sich die funktionierende Datei vom Master-Branch holen.

## 5: Sonstiges über Git und Github

**gitignore**: Ein Dokument, dass Informationen beinhaltet, welche Dateien beim klonen bzw "pullen" übernommen werden sollen und welche nicht.

**markdown-File**: Wird für die Dokumentation von Projekten benutzt (siehe auch: [Mastering Markdown](https://guides.github.com/features/mastering-markdown/))

