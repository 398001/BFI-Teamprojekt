# BFI-Teamprojekt

## Übersicht

In diesem Projekt haben wir die Zusammenarbeit mit **Git und GitHub** als Team geübt.

Dabei haben wir mit zwei Partnern gearbeitet:

- **Partner A:** Admin – erstellt das Repository und den ersten Stand
- **Partner B:** Developer – arbeitet mit einem eigenen Feature-Branch

Das Ziel des Projekts war es, den grundlegenden Ablauf einer Zusammenarbeit mit Git und GitHub kennenzulernen.

---

# 1. Repository auf GitHub erstellen

Zuerst erstellt **Partner A** auf GitHub ein neues privates Repository.

Das Repository heißt:

```text
BFI-Teamprojekt
```

Anschließend wird **Partner B** als Mitarbeiter zum Repository eingeladen.

Partner B nimmt die Einladung an und kann danach am Projekt mitarbeiten.

---

# 2. Repository klonen

Nachdem das Repository erstellt wurde, müssen beide Partner das Repository auf ihren eigenen Computer herunterladen.

Dafür wird `git clone` verwendet:

```bash
git clone <URL>
```

Beispiel:

```bash
git clone https://github.com/Benutzername/BFI-Teamprojekt.git
```

Danach wechselt man in den Projektordner:

```bash
cd BFI-Teamprojekt
```

Mit folgendem Befehl kann man überprüfen, ob das Repository korrekt funktioniert:

```bash
git status
```

---

# 3. Erste Änderung durch Partner A

Partner A erstellt zunächst die Datei:

```text
index.html
```

Die Datei enthält zum Beispiel:

- ein HTML-Grundgerüst
- eine Überschrift

Bevor die Änderungen gespeichert werden, kann man mit folgendem Befehl überprüfen, was geändert wurde:

```bash
git status
```

Danach wird die Datei für den nächsten Commit vorbereitet:

```bash
git add index.html
```

Anschließend wird die Änderung lokal gespeichert:

```bash
git commit -m "Create index.html"
```

Danach wird der Commit zu GitHub hochgeladen:

```bash
git push origin main
```

Damit befindet sich die erste Version des Projekts im `main`-Branch auf GitHub.

---

# 4. Partner B holt den aktuellen Stand

Da Partner A bereits Änderungen zu GitHub hochgeladen hat, muss Partner B zuerst den aktuellen Stand herunterladen.

Dafür wird verwendet:

```bash
git pull
```

Damit wird der aktuelle Stand von GitHub auf den Computer von Partner B übertragen.

Das ist wichtig, damit Partner B nicht mit einer veralteten Version des Projekts arbeitet.

---

# 5. Eigenen Feature-Branch erstellen

Partner B arbeitet nicht direkt im `main`-Branch.

Stattdessen wird ein eigener Branch für die neue Funktion erstellt:

```bash
git checkout -b feature-content
```

Dieser Befehl macht zwei Dinge gleichzeitig:

1. Der neue Branch `feature-content` wird erstellt.
2. Git wechselt direkt auf diesen Branch.

Mit:

```bash
git branch
```

kann man überprüfen, auf welchem Branch man sich befindet.

Der aktuelle Branch wird mit `*` angezeigt.

Beispiel:

```text
  main
* feature-content
```

---

# 6. Änderungen im Feature-Branch durchführen

Jetzt kann Partner B die Datei `index.html` bearbeiten.

Zum Beispiel wird ein zusätzlicher Textabsatz eingefügt.

Nach der Änderung kann man den aktuellen Zustand überprüfen:

```bash
git status
```

Danach wird die geänderte Datei für den Commit vorbereitet:

```bash
git add index.html
```

Anschließend wird die Änderung gespeichert:

```bash
git commit -m "Add project content"
```

Die Änderung befindet sich jetzt zunächst nur lokal im Feature-Branch.

---

# 7. Zurück zu main wechseln

Nachdem die Arbeit am Feature abgeschlossen wurde, wechselt Partner B zurück zum `main`-Branch:

```bash
git checkout main
```

Mit:

```bash
git status
```

kann überprüft werden, dass man sich jetzt wieder auf `main` befindet.

---

# 8. Feature-Branch in main mergen

Jetzt wird der fertige Feature-Branch in `main` übernommen.

Dafür wird folgender Befehl verwendet:

```bash
git merge feature-content
```

Git übernimmt damit die Änderungen aus `feature-content` in den aktuellen `main`-Branch.

In unserem Projekt wurde der Merge erfolgreich als **Fast-forward** durchgeführt.

Das bedeutet, dass Git die Änderungen ohne einen zusätzlichen Merge-Commit übernehmen konnte.

---

# 9. Aktualisierten main-Branch zu GitHub pushen

Nachdem der Feature-Branch erfolgreich in `main` übernommen wurde, wird der aktualisierte `main`-Branch zu GitHub hochgeladen:

```bash
git push origin main
```

Damit ist die neue Version auch auf GitHub verfügbar.

---

# 10. Warum ist git pull wichtig?

`git pull` ist besonders wichtig, wenn mehrere Personen an einem Repository arbeiten.

Angenommen, Partner A hat eine Änderung gemacht und diese zu GitHub gepusht.

Partner B hat diese Änderung noch nicht auf seinem Computer.

Dann besitzt Partner B lokal einen älteren Stand.

Deshalb sollte Partner B vor dem Weiterarbeiten den aktuellen Stand holen:

```bash
git pull
```

Ohne `git pull` kann es beispielsweise beim Pushen zu Problemen kommen:

```text
Updates were rejected because the remote contains work
that you do not have locally.
```

Mit `git pull` werden die Änderungen vom Remote-Repository heruntergeladen und mit dem lokalen Stand zusammengeführt.

---

# 11. Aktuellen Stand überprüfen

Mit `git status` kann jederzeit überprüft werden, wie der aktuelle Zustand des Projekts ist:

```bash
git status
```

Wenn alles aktuell ist, kann beispielsweise folgende Meldung erscheinen:

```text
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```

Das bedeutet:

- Man befindet sich auf `main`.
- Der lokale `main` ist auf dem gleichen Stand wie GitHub.
- Es gibt keine nicht gespeicherten Änderungen.

---

# 12. Wichtige Git-Befehle

| Befehl | Bedeutung |
|---|---|
| `git clone <URL>` | Repository von GitHub herunterladen |
| `cd <Ordner>` | In einen Ordner wechseln |
| `git status` | Aktuellen Git-Status anzeigen |
| `git branch` | Vorhandene Branches anzeigen |
| `git checkout <branch>` | Zu einem vorhandenen Branch wechseln |
| `git checkout -b <branch>` | Neuen Branch erstellen und direkt wechseln |
| `git add <Datei>` | Änderung für einen Commit vorbereiten |
| `git add .` | Alle Änderungen vorbereiten |
| `git commit -m "Nachricht"` | Änderungen lokal speichern |
| `git push origin main` | `main` zu GitHub hochladen |
| `git pull` | Änderungen von GitHub herunterladen |
| `git merge <branch>` | Einen Branch in den aktuellen Branch integrieren |

---

# 13. Kurzanleitung – Typischer Ablauf

Wenn man in einem Team mit Git arbeitet, kann der normale Ablauf beispielsweise so aussehen:

## Schritt 1 – Aktuellen Stand holen

```bash
git checkout main
git pull
```

## Schritt 2 – Neuen Feature-Branch erstellen

```bash
git checkout -b feature-name
```

## Schritt 3 – Änderungen durchführen

Dateien bearbeiten und neue Funktionen hinzufügen.

Danach:

```bash
git status
```

## Schritt 4 – Änderungen vorbereiten

```bash
git add .
```

## Schritt 5 – Änderungen committen

```bash
git commit -m "Beschreibung der Änderung"
```

## Schritt 6 – Feature-Branch zu GitHub pushen

```bash
git push -u origin feature-name
```

## Schritt 7 – Zurück zu main wechseln

```bash
git checkout main
```

## Schritt 8 – Aktuellen main-Stand holen

```bash
git pull
```

## Schritt 9 – Feature-Branch mergen

```bash
git merge feature-name
```

## Schritt 10 – Aktualisierten main-Branch pushen

```bash
git push origin main
```

Damit befindet sich die neue Änderung sowohl lokal als auch auf GitHub im `main`-Branch.

---

# 14. Was passiert bei den einzelnen Befehlen?

Der grundlegende Ablauf kann man sich so merken:

```text
Änderung machen
      ↓
git status
      ↓
git add
      ↓
git commit
      ↓
git push
      ↓
GitHub
```

Wenn man Änderungen von GitHub benötigt:

```text
GitHub
   ↓
git pull
   ↓
Lokaler Computer
```

Bei der Arbeit mit einem Feature-Branch:

```text
main
 │
 └── feature-name
       │
       ├── Änderungen
       ├── git add
       └── git commit
              │
              ↓
           git merge
              │
              ↓
             main
              │
              ↓
        git push origin main
              │
              ↓
            GitHub
```

---

# 15. Ergebnis unseres Projekts

Am Ende enthält der `main`-Branch die gemeinsame Version des Projekts.

Die Datei `index.html` enthält:

```text
index.html
├── HTML-Grundgerüst
├── Überschrift
└── Textabsatz
```

Der Branch `feature-content` wurde erfolgreich in `main` gemergt.

Zusätzlich wurde eine `README.md` erstellt, die den Ablauf des Projekts und die wichtigsten Git-Befehle dokumentiert.

---

# 16. Was haben wir gelernt?

Durch das Projekt haben wir gelernt:

- wie man ein Repository auf GitHub erstellt
- wie man ein Repository mit `git clone` herunterlädt
- wie man den Git-Status überprüft
- wie man Änderungen mit `git add` vorbereitet
- wie man Änderungen mit `git commit` speichert
- wie man Änderungen mit `git push` zu GitHub hochlädt
- warum `git pull` bei Teamarbeit wichtig ist
- wie man eigene Branches erstellt
- wie man zwischen Branches wechselt
- wie man einen Feature-Branch in `main` merged
- wie mehrere Personen gemeinsam an einem Projekt arbeiten können
- wie man einen typischen Git-Workflow im Team verwendet

---

# 17. Kurz gesagt

Der wichtigste Ablauf bei der Zusammenarbeit mit Git ist:

```bash
git pull
git checkout -b feature-name

# Änderungen machen

git status
git add .
git commit -m "Beschreibung"
git push -u origin feature-name

git checkout main
git pull
git merge feature-name
git push origin main
```

Damit kann man Änderungen getrennt entwickeln, anschließend in `main` übernehmen und den gemeinsamen Projektstand auf GitHub aktualisieren.