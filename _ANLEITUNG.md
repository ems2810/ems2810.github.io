# Website auf GitHub Pages veröffentlichen
## Schritt-für-Schritt mit VS Code

---

## Vorbereitung (einmalig)

- [ ] **Git installieren:** https://git-scm.com/download — einfach durchklicken
- [ ] **VS Code installieren** (falls noch nicht): https://code.visualstudio.com
- [ ] **GitHub Account erstellen** (falls noch nicht): https://github.com → Sign up

---

## 1. GitHub Repository anlegen

1. Gehe zu https://github.com/new
2. **Repository name:** `ems2810.github.io` ← exakt so, mit deinem Username
3. **Visibility:** Public ← muss Public sein für kostenloses GitHub Pages
4. **"Add a README file"** — Haken **nicht** setzen
5. Klick **"Create repository"**

---

## 2. ZIP entpacken und in VS Code öffnen

1. ZIP-Datei entpacken → du bekommst einen Ordner namens `site`
2. VS Code öffnen
3. **File → Open Folder** → den `site`-Ordner auswählen
4. VS Code zeigt jetzt alle Dateien in der linken Leiste

---

## 3. Git in VS Code einrichten (einmalig)

1. In VS Code: **Terminal → New Terminal** (oben in der Menüleiste)
2. Diese drei Befehle nacheinander eingeben und mit Enter bestätigen:

```
git config --global user.name "Achim Braml"
git config --global user.email "gourd_pulp.9b@icloud.com"
```

---

## 4. Repository verbinden und hochladen

Im selben Terminal:

```
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/ems2810/ems2810.github.io.git
git push -u origin main
```

Beim `git push` öffnet sich ein Browser-Fenster → bei GitHub einloggen → Zugriff erlauben.

---

## 5. GitHub Pages aktivieren

1. Gehe zu https://github.com/ems2810/ems2810.github.io
2. Oben auf **Settings** klicken
3. Links im Menü: **Pages**
4. Unter "Branch": **main** auswählen, Ordner **/ (root)** lassen
5. **Save** klicken

⏳ Nach 1–2 Minuten ist die Seite live unter:
**https://ems2810.github.io**

---

## 6. Spätere Änderungen hochladen

Wenn du später Dateien bearbeitest (z.B. Notion-URLs eintragen):

1. In VS Code links auf das **Verzweigungssymbol** klicken (sieht aus wie drei Punkte mit Linien — "Source Control")
2. Geänderte Dateien erscheinen dort
3. Oben ins Textfeld eine kurze Beschreibung tippen, z.B. `Update links`
4. Klick auf **"Commit & Push"** (oder den ✓ Haken)

Fertig — Änderungen sind nach ~30 Sekunden live.

---

## Noch offene To Dos in den Dateien

Diese Werte musst du noch eintragen — danach wie oben beschrieben pushen:

### index.html
- [ ] `YOUR_APP_STORE_LINK` → ist bereits eingetragen ✓
- [ ] Notion Privacy URL → ist bereits eingetragen ✓
- [ ] Notion Copyright URL → ist bereits eingetragen ✓

### apps/playlistgenerator-support.html
- [ ] Support-E-Mail ist bereits eingetragen ✓

### Wenn Folio Home bereit für Beta ist:
- [ ] `beta/foliohome.html` → `YOUR_TESTFLIGHT_LINK_HERE` ersetzen
- [ ] In `index.html` den Folio Home Badge von "In Development" auf "Beta" ändern und Beta-Link ergänzen

### Wenn Notion-Seiten auf diese Website umgezogen werden sollen:
- [ ] In `index.html` die zwei Notion-URLs durch lokale Pfade ersetzen:
  - Privacy: `legal/playlistgenerator-privacy.html`
  - Copyright: `legal/playlistgenerator-copyright.html`

---

## App Store Connect — URLs eintragen

Sobald die Seite live ist, diese URLs in App Store Connect hinterlegen:

| Feld | URL |
|------|-----|
| Support URL | `https://ems2810.github.io/apps/playlistgenerator-support.html` |
| Privacy Policy URL | Notion-URL (bleibt vorerst) |
| Marketing URL | `https://ems2810.github.io` |

---

## Eigene Domain (optional, später)

Falls du irgendwann eine eigene Domain möchtest (z.B. `achimbraml.dev`):
1. Domain kaufen (z.B. bei Namecheap oder Cloudflare Registrar, ~10€/Jahr)
2. Eine Datei namens `CNAME` im `site`-Ordner anlegen mit dem Inhalt: `deinedomain.com`
3. Beim Domain-Anbieter DNS-Einträge setzen (A-Records auf GitHub Pages IPs)
4. In GitHub Repository Settings → Pages → Custom domain eintragen

GitHub Pages ist dann kostenlos weiter nutzbar, nur die Domain kostet etwas.
