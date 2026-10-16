# CLAUDE.md

## Projektüberblick

„Güzel Dinimi Öğreniyorum“ ist eine türkischsprachige Lern-Web-App für Kinder auf Basis des Diyanet-Buchs „Etkinliklerle Dinimi Öğreniyorum“. 4 Bereiche (İnanç, İbadet, Siyer, Ahlâk), 29 Üniten mit Lernkarten + Quiz, Sterne-Fortschritt.

## Struktur

- **Alles steckt in `index.html`** – HTML, CSS und Vanilla-JS in einer Datei, kein Build-Step, keine Abhängigkeiten außer der Google-Font „Baloo 2“.
- **Inhalte:** im JS-Array `CATS`. Jeder Bereich hat `id`, `name`, `sub`, `c` (Farbe `"b"`/`"g"`) und `units`. Jede Ünite hat
  - `t` – Titel
  - `p` – Lernkarten als `[emoji, überschrift, text]`
  - `q` – Quizfragen als `[frage, [optionen…], indexDerRichtigenAntwort]` (Optionen werden zur Laufzeit gemischt)
- **Fortschritt:** `localStorage`-Key `"gdo-v1"`, Format `{name: string, stars: {"<bereichId>-<üniteIndex>": 1..3}}`. Bei inkompatiblen Formatänderungen den Key hochzählen.

## Konventionen

- Inhalte sind eigene, kindgerechte Kurz-Zusammenfassungen – keinen Buchtext kopieren.
- Light-/Dark-Mode über CSS-Variablen in `:root`.
- Entscheidungen werden in `ENTSCHEIDUNGEN.md` festgehalten.
