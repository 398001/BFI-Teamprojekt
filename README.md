# BFI-Teamprojekt

## Übersicht

In diesem Projekt haben wir die praxiserprobte Zusammenarbeit mit **Git und GitHub** im Team umgesetzt. 

Das Projekt basiert auf einer klaren Rollenverteilung zwischen zwei Teampartnern:

- **Partner A (Admin):** Erstellt das Repository, richtet das Grundgerüst ein und verwaltet den `main`-Branch.
- **Partner B (Developer):** Entwickelt neue Funktionen isoliert in einem eigenen Feature-Branch.

Ziel des Projekts war die strukturierte und fehlerfreie Umsetzung eines typischen Entwicklungs-Workflows in Git.

---

## 1. Repository-Setup auf GitHub

1. **Repository erstellen:** Partner A erstellt auf GitHub ein neues privates Repository namens `BFI-Teamprojekt`.
2. **Teammitglieder einladen:** Partner B erhält eine Einladung als Mitarbeiter und tritt dem Repository bei.
3. **Repository klonen:** Beide Partner laden das Repository lokal auf ihren Computer herunter:

```bash
git clone https://github.com/Benutzername/BFI-Teamprojekt.git
cd BFI-Teamprojekt
```

---

## 2. Basiseinrichtung durch Partner A

Partner A erstellt das Grundgerüst der Webseite in der Datei `index.html`:

1. **Datei erstellen & bearbeiten:** Erstellung von `index.html` mit einem HTML5-Grundgerüst und einer Hauptüberschrift.
2. **Änderungen stagen und committen:**
   ```bash
   git add index.html
   git commit -m "Create index.html with basic layout"
   ```
3. **Stand veröffentlichen:**
   ```bash
   git push origin main
   ```

---

## 3. Feature-Entwicklung durch Partner B

Partner B übernimmt die Erweiterung der Webseite. Um den `main`-Branch stabil zu halten, erfolgt die Entwicklung in einem separaten Feature-Branch.

1. **Aktuellen Stand holen:**
   ```bash
   git checkout main
   git pull origin main
   ```
2. **Feature-Branch erstellen & wechseln:**
   ```bash
   git checkout -b feature-content
   ```
3. **Inhalte hinzufügen:** Partner B ergänzt `index.html` um einen Textabsatz und weitere Inhalte.
4. **Commit & Push des Feature-Branches:**
   ```bash
   git add index.html
   git commit -m "Add project content and description"
   git push -u origin feature-content
   ```

---

## 4. Integration & Merge in den Main-Branch

Nach erfolgreicher Fertigstellung wird das Feature in den Haupt-Branch zusammengeführt:

1. **Zurück zum Main-Branch wechseln:**
   ```bash
   git checkout main
   git pull origin main
   ```
2. **Feature-Branch mergen:**
   ```bash
   git merge feature-content
   ```
3. **Aktualisierten Stand zu GitHub pushen:**
   ```bash
   git push origin main
   ```
4. **Aufräumen (Branch-Cleanup):**
   Nach dem erfolgreichen Merge wird der abgearbeitete Feature-Branch lokal und auf GitHub entfernt:
   ```bash
   git branch -d feature-content
   git push origin --delete feature-content
   ```

---

## 5. BFI Git-Workflow Spickzettel

### Standard Git-Befehle

| Befehl | Funktion |
| :--- | :--- |
| `git status` | Prüft den aktuellen Zustand des Arbeitsverzeichnisses |
| `git log --oneline --graph` | Zeigt den Commit-Verlauf übersichtlich an |
| `git pull` | Lädt aktuelle Änderungen vom GitHub-Server herunter |
| `git add .` | Bereitet alle geänderten Dateien für den Commit vor |
| `git commit -m "Nachricht"` | Speichert den Vorbereitungsstand lokal ab |
| `git push` | Lädt lokale Commits auf GitHub hoch |

### Typischer Feature-Workflow

```bash
# 1. Starten
git checkout main
git pull
git checkout -b feature-name

# 2. Arbeiten & Speichern
git add .
git commit -m "Feature umgesetzt"

# 3. Abschließen
git checkout main
git pull
git merge feature-name
git push origin main

# 4. Aufräumen
git branch -d feature-name
```

---

## 6. Lernergebnisse

Im Rahmen dieses Projekts wurden folgende Kernkompetenzen erfolgreich erarbeitet:

- Einrichten und Verwalten von Repositories auf GitHub.
- Arbeiten mit Feature-Branches zur Vermeidung von Konflikten im Hauptcode.
- Sicherer Umgang mit Merges, Commits und Remote-Synchronisation (`pull`/`push`).
- Sauberer Projektabschluss durch strukturiertes Löschen gemergter Branches.