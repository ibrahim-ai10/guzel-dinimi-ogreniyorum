# CLAUDE.md

## Projektüberblick

„Güzel Dinimi Öğreniyorum“ ist ein türkischsprachiges Unterrichts-Werkzeug für Lehrkräfte (Beamer/Smartboard), auch allein von Kindern nutzbar, auf Basis des Diyanet-Buchs „Etkinliklerle Dinimi Öğreniyorum“. 4 Bereiche (İnanç, İbadet, Siyer, Ahlâk), 29 Üniten mit Lernkarten + Quiz, Sterne-Fortschritt.

## Struktur

- **Alles steckt in `index.html`** – HTML, CSS und Vanilla-JS in einer Datei, kein Build-Step, keine Abhängigkeiten außer der Google-Font „Baloo 2“.
- **Inhalte:** im JS-Array `CATS`. Jeder Bereich hat `id`, `name`, `sub`, `c` (Farbe `"b"`/`"g"`) und `units`. Jede Ünite hat
  - `t` – Titel (wie im Buch)
  - `s` – Seitenbereich im Buch (5. Auflage 2019), z. B. `"8–13"`, wird in der Üniten-Liste und im Klassenmodus angezeigt
  - `d` – Gesprächsfrage für die Klasse („Sınıfça konuşalım“), wird nach den Lernkarten gezeigt
  - `p` – Lernkarten als `[emoji, überschrift, text]`
  - `q` – Quizfragen als `[frage, [optionen…], indexDerRichtigenAntwort]` (Optionen werden zur Laufzeit gemischt)
  - Standard: 6–8 Lernkarten und genau 6 Fragen mit je 3 Antwortoptionen pro Ünite
- **Quelle der Inhalte:** jede Ünite basiert auf den Buchseiten in `s`. Bei Änderungen am Inhalt immer gegen das Buch prüfen; Verse/Hadithe mit Quellenangabe, sonst eigene Formulierungen.
- **Sterne:** alle Fragen richtig = 3, mindestens zwei Drittel richtig = 2, sonst 1 (Funktion `finish`).
- **Sınıf Modu:** CSS-Klasse `cls` auf `<html>`, alle Overrides unter `:root.cls`. Ist `S.cls` nicht gesetzt, gilt der Modus ab 1000 px Breite. Teams (`TEAMS`) nur im Speicher. Tastatur und Presenter im `keydown`-Handler am Ende des Skripts. Muss ab 1280×720 ohne Scrollen passen.
- **Fortschritt:** `localStorage`-Key `"gdo-v1"`, Format `{name: string, stars: {"<bereichId>-<üniteIndex>": 1..3}, cls?: boolean}`. Bei inkompatiblen Formatänderungen den Key hochzählen.

## Konventionen

- Inhalte sind eigene, kindgerechte Kurz-Zusammenfassungen – keinen Buchtext kopieren.
- Light-/Dark-Mode über CSS-Variablen in `:root`.
- Entscheidungen werden in `ENTSCHEIDUNGEN.md` festgehalten.
