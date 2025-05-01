# graphite.dev-cheat-sheet


# Docs
- https://graphite.dev/docs/get-started
















<br><br>
<br><br>
___
<br><br>
<br><br>


# Getting started

<details><summary>Click to expand..</summary>

1. Organisation erstellen und Repo dort integrieren
   - https://github.com/CyberT33N/github-cheat-sheet/blob/master/README.md#%C3%BCbertragung-eines-privaten-repositories-an-eine-organisation
  
2. Install the CLI by pasting this in your terminal:
```
npm install -g @withgraphite/graphite-cli@stable

```

Finally, authenticate the CLI by pasting this in your command line:
```
gt auth --token \
  xxxxxxxxxxxxxxxx
```


</details>
















<br><br>
<br><br>
___
<br><br>
<br><br>






# CLI

<details><summary>Click to expand..</summary>




# Quick start
- https://graphite.dev/docs/cli-quick-start

<details><summary>Click to expand..</summary>


# Quick Start: GitHub PR Stacking mit Graphite CLI

Lerne, wie man **Stacked Pull Requests** effizient mit dem `gt` CLI Tool erstellt und verwaltet.

---

## 🚀 Introduction

Das `gt` CLI-Tool verfolgt zwei Hauptziele:

1. Git-Befehle vereinfachen – vor allem komplexe Vorgänge wie das Rebasen.
2. PR-Stacking ermöglichen – für schnelleres Arbeiten ohne Blockaden.

Mehr zu den Vorteilen: [stacking.dev](https://stacking.dev)

---

## 🔄 Workflow-Überblick

Der Graphite-Workflow umfasst:

1. Stack erstellen  
2. Stack einreichen  
3. Feedback umsetzen  
4. Stack mergen  
5. Von `main` synchronisieren & lokale Branches aufräumen  

---

## 📦 Erste Pull Request erstellen

```bash
# Auf main wechseln
gt checkout main

# Änderungen machen
echo "new code changes" >> file.js

# Branch mit Commit erstellen
gt create --all \
  --message "feat(api): Add new API method for fetching users"

# Push + Pull Request erstellen
gt submit

# Weitere Änderungen? Bestehenden Commit anpassen
echo "some more changes" >> file.js
gt modify --all

# Änderungen erneut submitten
gt submit
```

---

## 🧱 Zweite Pull Request stacken

```bash
# Interaktiven Branch Picker öffnen
gt checkout

# Änderungen vornehmen
echo "update frontend to use the API from PR 1" > frontend/admin/UsersPage.tsx

# Zweite PR stacken
gt create --all \
  --message "feat(frontend): Load and show a list of users"

# Stack pushen + PR erstellen
gt submit --stack
```

### Stack visualisieren

```bash
gt log short   # oder gt ls
```

### PR im UI öffnen

```bash
gt pr
```

### Reviewer direkt beim Submit zuweisen

```bash
gt submit --stack --reviewers alice
```

---

## ✏️ Reviewer-Feedback umsetzen

Änderungen im unteren PR der Stack-Kette:

```bash
gt checkout first_pr_in_the_stack
echo "making some edits" > a_file_my_coworker_wants_changed.js

# Änderungen anwenden + Restack
gt modify -a
```

### Alternativ: Manuell

```bash
git add a_file_my_coworker_wants_changed.js
git commit --amend --no-edit
gt restack
```

### Feedback als neuen Commit speichern

```bash
gt modify --commit --all \
  --message "Responded to reviewer feedback"

# Oder kürzer:
gt modify -cam "Responded to reviewer feedback"
```

---

## 🔃 Main-Änderungen in Stack übernehmen

```bash
gt sync
```

Dieser Befehl:

- holt `main` auf den neuesten Stand
- rebaset alle offenen PRs auf `main`
- bietet an, gemergte Branches lokal zu löschen

---

## ✅ Stack mergen

```bash
# Top-PR auschecken
gt top

# PR im Graphite-UI öffnen
gt pr
```

Dort kannst du den Stack (oder nur Teile davon) mergen.

---

## 🧹 Nach Merge: Aufräumen & Sync

```bash
gt sync
```

`gt sync` wird:

- gemergte Branches erkennen & zum Löschen anbieten
- offene Branches auf neuesten `main`-Stand bringen

---

## 💡 Tipp

Nutze `gt sync` regelmäßig, um stets auf dem aktuellsten Stand deines Trunks zu bleiben.

---

**🔗 Weitere Infos**: [stacking.dev](https://stacking.dev)
t du das als `.md`-Datei exportiert haben oder direkt in ein bestehendes GitHub-Wiki pushen?



</details>



<br>
<br>

# Create PR


```shell
gt track main
gt track refactor/PRIV-10/mvp-roo-code-v2/main

gt submit
```












</details>
