# ems2810.github.io — Homepage Specification
**Version 1.6 — May 31, 2026**

---

## 1. Site Identity

| | |
|---|---|
| **URL** | https://ems2810.github.io |
| **GitHub Repo** | https://github.com/ems2810 |
| **Purpose** | Developer homepage for Achim's iOS apps — showcases apps, hosts legal documents, and links to TestFlight betas |
| **Hosting** | GitHub Pages (free, static) |
| **Contact email** | gourd_pulp.9b@icloud.com |

---

## 2. Site Structure

```
ems2810.github.io/
├── index.html                          — Homepage (app overview)
├── shared.css                          — Global stylesheet
├── app-ads.txt                         — AdMob verification
├── icons/                              — App icon PNGs (not inline SVGs)
│   ├── tracktailor.png
│   ├── sketchline.png
│   └── foliohome.png
├── legal/                              — Legal documents, flat structure, appname-doctype.html
│   ├── playlistgenerator-privacy.html  — Track Tailor Privacy Policy
│   ├── playlistgenerator-copyright.html— Track Tailor Copyright
│   ├── playlistgenerator-terms.html    — Track Tailor Terms of Use
│   ├── sketchline-privacy.html         — Sketchline Privacy Policy
│   ├── sketchline-terms.html           — Sketchline Terms of Use
│   ├── foliohome-privacy.html          — Folio Home Privacy Policy
│   └── foliohome-terms.html            — Folio Home Terms of Use
├── beta/                               — TestFlight landing pages
│   ├── tracktailor.html                — Track Tailor beta page
│   ├── sketchline.html                 — Sketchline beta page
│   └── foliohome.html                  — Folio Home beta page (future)
└── apps/                               — App support pages
    ├── playlistgenerator-support.html  — Track Tailor Support
    ├── sketchline-support.html         — Sketchline Support
    └── foliohome-support.html          — Folio Home Support
```

**Naming convention:** `appname-doctype.html` — flat under `legal/`, no subdirectories.

**Internal files (hidden from GitHub Pages rendering):**
- `_ANLEITUNG.md`, `_README.md`, `_config.yml` — prefixed with underscore per convention

**File status:** Alle Legal- und Support-Dateien für die drei Apps existieren (Stand 2026-05-09).

---

## 3. Apps

### 3.1 Track Tailor
| | |
|---|---|
| **Status** | ✅ Live on App Store · 🧪 New build in TestFlight |
| **Internal name** | `playlistgenerator` (used in all filenames) |
| **App Store** | https://apps.apple.com/us/app/track-tailor/id6761209212 |
| **TestFlight** | https://testflight.apple.com/join/EYUFyc9k (100 slots) |
| **Description** | Dynamic Apple Music playlist generator |
| **Legal hosting** | Privacy Policy + Copyright → `legal/playlistgenerator-privacy.html` / `playlistgenerator-copyright.html`; Terms → `playlistgenerator-terms.html`; Support → `apps/playlistgenerator-support.html` |
| **Beta page** | `beta/tracktailor.html` |
| **CTA on homepage** | "Download on the App Store" badge + black TestFlight pill ("Join the Beta on TestFlight") + "About the beta" link |

**App icon:** `icons/tracktailor.png`

### 3.2 Sketchline
| | |
|---|---|
| **Status** | ✅ Live on App Store |
| **App Store** | https://apps.apple.com/us/app/sketchline/id6762081024 |
| **TestFlight** | https://testflight.apple.com/join/WyqxGCUU (100 slots) — no longer linked from homepage |
| **Platform** | iPad only (iPadOS 17.0+) |
| **Description** | Natural drawing app for iPad with full Apple Pencil support |
| **Legal hosting** | `legal/sketchline-privacy.html`, `sketchline-terms.html`; copyright + support pages missing (to be created) |
| **Beta page** | `beta/sketchline.html` — exists but unlinked (reachable only by direct URL) |
| **CTA on homepage** | "Download on the App Store" badge + Support link; `Live` badge; no TestFlight/"About the beta" link |

**App icon:** `icons/sketchline.png`

### 3.3 Folio Home
| | |
|---|---|
| **Status** | 🚧 In Development (Coming Soon) |
| **App Store** | Not yet available |
| **Platform** | iOS 26.0+ (iPhone & iPad) |
| **Description** | Household budget & finance app |
| **Legal hosting** | `legal/foliohome-privacy.html`, `foliohome-terms.html`; copyright + support pages missing (to be created) |
| **Beta page** | `beta/foliohome.html` (exists, future use) |
| **CTA on homepage** | "Coming Soon" — no link |

**App icon:** `icons/foliohome.png`
- Background: linear gradient `#534AB7` → `#7A72D6`, top-left to bottom-right
- House: white roof (polyline, rounded linecap/linejoin) + white rect body (`rgba(255,255,255,0.95)`)
- Chart bars inside house (left to right, rising): `#9B6FE8` / `#7A72D6` / `#534AB7` / `#1DA882` (green, tallest)
- Style: flat, no shadow, no border

---

## 4. Legal Documents per App

### Track Tailor (`playlistgenerator`)
| Document | File | Note |
|---|---|---|
| Privacy Policy | `legal/playlistgenerator-privacy.html` | ✅ Exists |
| Copyright | `legal/playlistgenerator-copyright.html` | ✅ Exists |
| Terms of Use | `legal/playlistgenerator-terms.html` | ✅ Exists → redirect to Apple EULA |
| Support | `apps/playlistgenerator-support.html` | ✅ Exists |

### Sketchline
| Document | File | Note |
|---|---|---|
| Privacy Policy | `legal/sketchline-privacy.html` | ✅ Exists |
| Terms of Use | `legal/sketchline-terms.html` | ✅ Exists → redirect to Apple EULA |
| Copyright | `legal/sketchline-copyright.html` | ✅ Exists |
| Support | `apps/sketchline-support.html` | ✅ Exists |

### Folio Home
| Document | File | Note |
|---|---|---|
| Privacy Policy | `legal/foliohome-privacy.html` | ✅ Exists |
| Terms of Use | `legal/foliohome-terms.html` | ✅ Exists → redirect to Apple EULA |
| Copyright | `legal/foliohome-copyright.html` | ✅ Exists |
| Support | `apps/foliohome-support.html` | ✅ Exists |

**Terms of Use for all apps:** Use the Apple Standard EULA —
`https://www.apple.com/legal/internet-services/itunes/dev/stdeula/`
All `*-terms.html` files should redirect to or prominently link this URL. No custom EULA needed.

---

## 5. Design System

`shared.css` ist die **Single Source of Truth**. Der `<style>`-Block in `index.html` enthält nur seitenspezifische Regeln; alles Geteilte gehört in `shared.css`.

**Design-Prinzip (ab v1.4):** Ruhig, neutral, Apple-Stil. Schwarz/Weiß/Grau + **ein** Akzent. Keine externen Webfonts.

### 5.1 Color Tokens

| Token | Value | Role | WCAG-Notiz |
|---|---|---|---|
| `--ink` | `#111111` | Primary text | passt überall |
| `--ink-muted` | `#555555` | Secondary text (descriptions) | ~7,4:1 auf weiß, AA ✓ |
| `--ink-faint` | `#767676` | Tertiärer Text, Meta-Labels | ~4,5:1 auf weiß, AA ✓ |
| `--paper` | `#ffffff` | Page background | — |
| `--paper-warm` | `#fafafa` | Sehr leichte Flächen, Hover-States | — |
| `--rule` | `rgba(0,0,0,0.08)` | Hairlines, dividers | nur für Linien, nicht für Text |
| `--accent` | `#534AB7` | Primary CTA, Beta-Badge, Links | ~7,4:1 auf weiß, AA ✓ |
| `--accent-dark` | `#443BA8` | Hover-State Button | — |

**Regel:** Genau ein Akzent. Keine zusätzlichen Farbfamilien (Grün, Light-Variants etc.) — Status wird durch Graustufen + Text vermittelt, nicht durch Farbe.

### 5.2 Typography

- **Eine** Schriftfamilie: System-Stack — `-apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif`. Keine externe Google-Font, kein Display/Body-Split.
- Hierarchie ausschließlich über Größe und Gewicht (`400` / `500` / `600`).
- **Skala (max. 6 Stufen):**

| Use | Size | Weight |
|---|---|---|
| Mikro (Badges, Eyebrows) | `0.6875–0.75rem` | 500 |
| Klein (Sekundär-Links, Meta) | `0.875rem` | 400/500 |
| Body | `1rem` | 400 |
| App-Name / H2 | `1.125rem` | 600 |
| Page-H1 (Subseiten) | `2.25rem` | 600 |
| Hero-H1 | `clamp(2.25rem, 5vw, 3.25rem)` | 600 |

Zwischenwerte (`0.8125`, `0.9375`, `1.0625`, `1.1`, `1.3`) vermeiden — Drift ohne wahrnehmbaren Nutzen.

### 5.3 Spacing & Radius

- **Eckenradien:** `8px` Container/Button, `14px` App-Icon, `20px+` Pill (Badges, Language-Pills). Keine weiteren Werte.
- **Layout-Breite:** `max-width: 680px` Homepage, `640px` Subseiten. Padding `2rem` Desktop / `1.25rem` ab 540 px abwärts.

### 5.4 Components

- **App Card:** Grid `64px` Icon + `minmax(0, 1fr)` Content, `1.25rem` Gap. Border-Top als Trenner (`--rule`). Erste Card ohne Border.
- **Badge:** Pill, `0.6875rem`, uppercase, `padding: 2px 8px`. Default = grau (`rgba(0,0,0,0.05)` + `--ink-muted`). Nur `.badge-beta` trägt den Akzent (Purple-Tint).
- **Primär-CTA:** Solider Button — `--accent` Hintergrund, weißer Text, `8px` Radius, `0.5rem 1.1rem` Padding. Eine visuelle Form pro Aktion.
- **Sekundär-Link:** Inline, Underline (`border-bottom`), `--ink-muted`.
- **Coming-Soon-Card:** Icon `opacity: 0.55` + `grayscale(0.4)`, App-Name in `--ink-muted`. Kein Link-Bereich → `mailto:`-Notify.
- **Nav:** Sticky, weißer Backdrop-Blur, keine Brand-Mark im Header (nur Footer trägt Namen/Copyright).
- **Language-Switch:** Vier Pill-Buttons (`EN · DE · ES · FR`) rechts in der Nav. Aktiver Status: schwarzer Border + `--ink` Text. Werte werden in `localStorage` unter `lang` gespeichert; Initialwert via `navigator.language` (Fallback `en`).

---

## 6. App Status Indicators

| Status | Badge | Icon-Treatment | CTA |
|---|---|---|---|
| Live on App Store | Default grau (`Live`) | normal | Primär-Button „App Store →" |
| TestFlight Beta | `.badge-beta` (purple-tint) | normal | Primär-Button „Join Beta →" |
| In Development | Default grau (`Coming Soon`) | desaturiert + opacity 0.55 | Kein primärer Link; `mailto:` „Email me when it ships" |

---

## 7. Versioning

| Version | Date | Change |
|---|---|---|
| 1.0 | 2026 (initial) | Site built, Track Tailor + Sketchline live, Folio Home placeholder |
| 1.1 | 2026-05-09 | Spec created; real file structure documented; Terms of Use → Apple EULA; missing pages identified |
| 1.2 | 2026-05-09 | Design-System konkretisiert (Token-Rollen, Typo-Skala, Radius-Set); Accessibility-Anforderungen (§8); Known-Issues-Backlog aus Design-Review (§9); Spec aus Downloads in Repo verschoben |
| 1.3 | 2026-05-09 | Backlog §9 umgesetzt: Kontrast-Fix (`--ink-faint` → `#6c6c6c`), Cards entrümpelt (Privacy/Terms/Copyright als kleine Legal-Zeile), `.btn-primary` für alle primären CTAs, Folio-Home Notify-Affordance, Early-Access-Sektion entfernt + Nav-Beta auf `beta/sketchline.html`, CSS-Duplikation aufgelöst (shared.css verlinkt), `:focus-visible` + `prefers-reduced-motion`, Hero-Em auf `--purple`, App-Sub ohne Italic, Brand-Mark ausgeschrieben |
| 1.4 | 2026-05-13 | Design-Refresh: System-Font-Stack statt DM Serif/DM Sans (keine externen Webfonts mehr), weißer Hintergrund statt warmes Beige, **ein** Akzent (Purple) — Green-Tokens und Purple-Light entfernt. „Achim Braml" Nav-Brand auf allen Seiten entfernt; Name nur noch im Footer. Sketchline `privacy` + `terms`: 4-Sprachen-Switcher (EN/DE/ES/FR) mit Auto-Erkennung via `navigator.language`, `localStorage`-Persistenz und Disclaimer für nicht-englische Versionen. |
| 1.5 | 2026-05-23 | Track Tailor bekommt parallel zum App Store einen TestFlight-CTA: schwarzer TestFlight-Pill-Button in der Card (gleiche `.btn-testflight`-Form wie Sketchline), zusätzliches `.badge-beta` neben dem `Live`-Badge, `app-tech`-Zeile „iOS · A new build is in TestFlight · 100 tester slots", neuer `beta/tracktailor.html` nach Sketchline-Muster. Alle vier Track-Tailor-Seiten (`legal/playlistgenerator-privacy.html`, `playlistgenerator-terms.html`, `playlistgenerator-copyright.html`, `apps/playlistgenerator-support.html`) auf 4-Sprachen-Switcher (EN/DE/ES/FR) umgestellt — DE/ES/FR voll übersetzt, EN bleibt authoritativ. |
| 1.6 | 2026-05-31 | Sketchline live auf dem App Store (id6762081024): TestFlight-Pill in der Card durch „Download on the App Store"-Badge ersetzt, Badge von `.badge-beta` auf `Live` (grau), „100 tester slots" aus `app-tech` entfernt, „About the beta"-Link sowie der „Beta"-Nav-Eintrag (→ `beta/sketchline.html`) entfernt. Beta-Seite bleibt bestehen, ist aber nicht mehr verlinkt. |

---

## 8. Accessibility — Pflicht

- **Kontrast:** WCAG AA — ≥ 4,5:1 für Normaltext (< 18 px), ≥ 3:1 für Großtext und UI-Elemente. Vor Merge prüfen.
- **Focus-Visible:** Globale Regel im `shared.css`:
  ```css
  :focus-visible { outline: 2px solid var(--purple); outline-offset: 2px; }
  ```
- **Reduced Motion:** `scroll-behavior` und Transitions hinter `@media (prefers-reduced-motion: no-preference)` gateen.
- **Alt-Texte:** Jedes inhaltliche `<img>` (App-Icons) braucht aussagekräftiges `alt`. Dekorative Bilder: `alt=""`.
- **Keyboard-Navigation:** Alle Links/Buttons müssen per Tab erreichbar und sichtbar fokussiert sein.
- **Mobile-Test:** Layout auf 375 px (iPhone SE) und 320 px prüfen, bevor „fertig".

---

## 9. Known Issues / Backlog (aus Design-Review 2026-05-09)

### High
1. **Kontrast-Failure `--ink-faint`** — aktuell `#9a9a9a` (~3,0:1) wird für App-Taglines, Section-Labels, Footer genutzt. → Auf `#767676` heben (≥ 4,5:1).
2. **App-Cards inkonsistent in Dichte** — Track Tailor: 5 Links, Sketchline: 6 Links, Folio Home: 0 Links. Privacy/Terms/Copyright drücken die primäre CTA in den Hintergrund. → Legal-Links hinter einen einzigen „Legal"-Link bündeln oder auf Subseiten verlagern; Folio Home eine Notify-Affordance geben.
3. **CTA-Inkonsistenz** — „Join Beta" einmal als Underline-Link auf der Sketchline-Card, einmal als solider Button in der Early-Access-Sektion. → Ein Pattern wählen: Primär-CTA überall als Button.
4. **Coming-Soon ohne Affordance** — Folio-Home-Card hat keinen Link, wirkt visuell unfertig. → `mailto:`-Notify oder konkreter ETA-Hinweis.

### Medium
5. **Early-Access-Sektion dupliziert die Sketchline-Card** — gleiche Inhalte in anderer Optik. → In die Card mergen oder zu echtem Beta-Programm-Bereich ausbauen (Screenshots, Testlauf, Feedback-Kanal).
6. **Inline-Styles + Inline-`onmouseover` in der Beta-Sektion** — neue Eckenradien (6, 8, 12 px) zusätzlich zu den bestehenden (14, 20 px). → In Klassen verschieben, Radius-Set auf 2–3 Werte fixieren.
7. **App-Sub italic + low-contrast + small** — drei Lesbarkeits-Hits gestapelt. → Italic raus, `--ink-muted`, leicht größer (`0.9375rem` → `1rem`).
8. **Hero-Em zu blass** — `--purple-light` auf cream ist 4,0:1; das Eyebrow darüber nutzt das stärkere `--purple` → Hierarchie kippt. → Hero-Em auf `--purple` setzen.
9. **Typo-Skala mit ~11 Stufen** — auf 6 reduzieren (siehe §5.2).
10. **`--green` wird nur einmal genutzt** (Live-Badge). → Entweder konsequent für Live-CTAs verwenden oder Token entfernen.

### Low
11. **Kein `:focus-visible`** — Fix: globale Regel (siehe §8).
12. **Mobile 375 px:** Badge „Coming Soon" + App-Name + Gap könnten umbrechen. → `flex-wrap` auf `.app-name-row` oder Badge-Text kürzen.
13. **Brand-Mark „AB" zu leise** in der Nav. → Voll-Name oder Signatur in den Hero.
14. **Kontakt-Mail wirkt wie Hide-My-Email-Alias.** → Custom-Domain-Alias oder persönlich wirkende iCloud-Adresse.
15. **CSS-Duplikation** zwischen `<style>` in `index.html` und `shared.css`. → Gemeinsame Regeln nur in `shared.css`.
16. **Section-Eyebrow „Apps"** redundant. → Streichen oder durch sinnstiftenden Satz ersetzen.
17. **`prefers-reduced-motion` nicht behandelt.** → Fix: §8.

---

## 10. Localization (Legal Pages)

Mehrsprachige Seiten (Stand v1.5):
- `legal/sketchline-privacy.html`, `legal/sketchline-terms.html`
- `legal/playlistgenerator-privacy.html`, `legal/playlistgenerator-terms.html`, `legal/playlistgenerator-copyright.html`
- `apps/playlistgenerator-support.html`

- **Unterstützte Sprachen:** EN (authoritative), DE, ES, FR.
- **Mechanismus:** Pure client-side. Inline-Script im `<head>` setzt `<html lang>` vor dem ersten Paint anhand `localStorage('lang')` oder `navigator.language` (Prefix-Match). Inhalte tragen `data-i18n="key"`, ein zweites Script tauscht `innerHTML` aus dem `translations`-Objekt.
- **Switcher:** Vier Pill-Buttons in der Nav (`.lang-switch`). Klick aktualisiert UI und `localStorage`.
- **Disclaimer:** Bei jeder nicht-englischen Sprache erscheint zwischen Meta und erstem Abschnitt ein kursiver Hinweis: *„Translation provided for convenience — the English version is authoritative."* (sprachspezifisch). Englisch zeigt keinen Disclaimer.
- **Authoritative Version:** EN. ES/FR sind „best effort"-Übersetzungen ohne juristisches Lektorat.
- **Erweiterung auf andere Legal-Seiten** (Track Tailor, Folio Home, Copyright-Seiten): bei Bedarf nach demselben Muster — Translation-Objekt + `data-i18n` Attribute.

---

*Homepage Spec — ems2810.github.io*
*Last updated: May 23, 2026*
