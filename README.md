# BFI-Teamprojekt

## Übersicht

In diesem Projekt haben wir die Zusammenarbeit mit Git und GitHub als Team geübt.

Dabei haben wir mit zwei Partnern gearbeitet:

- **Partner A:** Admin / erstellt den ersten Stand
- **Partner B:** Developer / arbeitet mit einem eigenen Feature-Branch

## Aufgabe 1 – Repository erstellen und klonen

Partner A hat auf GitHub das private Repository **BFI-Teamprojekt** erstellt und Partner B eingeladen.

Partner B hat die Einladung angenommen.

Anschließend haben beide das Repository mit `git clone` auf ihren Computer heruntergeladen.

```bash
git clone <URL>
```

Danach haben beide im Projektordner gearbeitet.

---

## Aufgabe 2 – Erste Änderung durch Partner A

Partner A hat die Datei `index.html` erstellt.

Die Datei enthält:

- ein HTML-Grundgerüst
- eine Überschrift

Danach wurden die Änderungen mit Git gespeichert und auf GitHub hochgeladen:

```bash
git add index.html
git commit -m "Create index.html"
git push origin main
```

Damit war die erste Version im `main`-Branch auf GitHub.

---

## Aufgabe 3 – Partner B holt die Änderungen

Partner B musste zuerst den aktuellen Stand von GitHub herunterladen:

```bash
git pull
```

Dadurch hatte Partner B die Änderungen von Partner A lokal.

Danach wurde ein eigener Branch erstellt:

```bash
git checkout -b feature-content
```

In diesem Branch wurde die `index.html` bearbeitet und ein Textabsatz hinzugefügt.

Anschließend wurde die Änderung gespeichert:

```bash
git add index.html
git commit -m "Add project content"
```

---

## Aufgabe 4 – Feature-Branch in main mergen

Nach dem Commit wechselte Partner B zurück zu `main`:

```bash
git checkout main
```

Danach wurde der Feature-Branch in `main` zusammengeführt:

```bash
git merge feature-content
```

Der Merge wurde erfolgreich als **Fast-forward** durchgeführt.

Anschließend wurde der aktualisierte `main`-Branch zu GitHub gepusht:

```bash
git push origin main
```

---

## Warum muss man zuerst `git pull` machen?

Partner B muss `git pull` ausführen, weil Partner A bereits Änderungen auf GitHub hochgeladen hat.

Ohne `git pull` hätte Partner B lokal einen älteren Stand.

Wenn Partner B dann direkt versucht hätte zu pushen, könnte Git den Push ablehnen:

```text
Updates were rejected because the remote contains work
that you do not have locally.
```

Mit `git pull` wird der aktuelle Stand vom Remote-Repository heruntergeladen. Dadurch können beide auf dem aktuellen Projektstand arbeiten.

---

## Verwendete Git-Befehle

Die wichtigsten Befehle aus dem Projekt waren:

```bash
git clone <URL>
git status
git add index.html
git commit -m "Create index.html"
git push origin main
git pull
git checkout -b feature-content
git checkout main
git merge feature-content
```

### Bedeutung der wichtigsten Befehle

| Befehl | Bedeutung |
|---|---|
| `git clone` | Repository herunterladen |
| `git status` | Aktuellen Git-Status anzeigen |
| `git add` | Änderungen für einen Commit vorbereiten |
| `git commit` | Änderungen lokal speichern |
| `git push` | Änderungen zu GitHub hochladen |
| `git pull` | Änderungen von GitHub herunterladen |
| `git checkout -b` | Neuen Branch erstellen und wechseln |
| `git checkout` | Zu einem anderen Branch wechseln |
| `git merge` | Änderungen eines Branches zusammenführen |

---

## Ergebnis

Am Ende enthält der `main`-Branch:

```text
index.html
├── HTML-Grundgerüst
├── Überschrift
└── Textabsatz
```

Der Branch `feature-content` wurde erfolgreich in `main` gemergt.

Beide Partner haben an dem Projekt mit Git und GitHub zusammengearbeitet.

## Lernziel

Durch die Aufgabe haben wir gelernt:

- wie man mit GitHub im Team arbeitet
- wie man ein Repository klont
- wie man Änderungen committed und pusht
- warum `git pull` wichtig ist
- wie man mit Branches arbeitet
- wie man einen Branch in `main` merged
- wie mehrere Personen gemeinsam an einem Projekt arbeiten können