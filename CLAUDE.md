# CLAUDE.md

## Projektüberblick

„Güzel Dinimi Öğreniyorum“ ist ein türkischsprachiges Unterrichts-Werkzeug für Lehrkräfte (Beamer/Smartboard), auch allein von Kindern nutzbar, auf Basis des Diyanet-Buchs „Etkinliklerle Dinimi Öğreniyorum“. 4 Bereiche (İnanç, İbadet, Siyer, Ahlâk), 29 Üniten mit Lernkarten + Quiz, Sterne-Fortschritt.

## Struktur

- **Alles steckt in `index.html`** – HTML, CSS und Vanilla-JS in einer Datei, kein Build-Step, keine Abhängigkeiten außer der Google-Font „Baloo 2“ und pdf.js (nur für den Buch-Leser, wird bei Bedarf nachgeladen).
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
- **Arbeitsheft:** Objekt `WB` mit Schlüssel `"<bereichId>-<üniteIndex>"` → Liste von Aufgaben. Typen: `fill` (`t`: Sätze mit `[Antwort]`, `x`: Ablenker), `match` (`p`: Paare), `order` (`i`: in richtiger Reihenfolge), `sort` (`c`: Kästen, `i`: `[Text, KastenNr]`), `tf` (`i`: `[Satz, true/false]`), `ws` (`w`: Wörter in Großbuchstaben, `n`: Rastergröße), `write` (`i`: offene Fragen, ohne Prüfung). Die Mischreihenfolge ist pro Aufgabe fest (seeded). Ansicht: `openWB`, Prüfung: `WB_CHECK`.
- **Buch-Leser:** `openBook(seite)`. Lädt pdf.js 3.11.174 bei Bedarf von jsDelivr (`PDFJS`). Das PDF wird in IndexedDB (`gdo`/`kv`, Schlüssel `pdf`) gespeichert, Notizen unter `ann:<seite>` (Koordinaten 0–1). PDF-Seite n = Buchseite n (5. Auflage, drei Teildateien in Namensreihenfolge). Doppelseite ab 900 px Breite im Querformat.
- **Overlays:** Leser und Arbeitsheft sind Vollbild-Ebenen (`openOv`/`closeOv`, Objekt `OV`); Pfeiltasten und Presenter blättern, Esc schließt.
- **Fortschritt:** `localStorage`-Key `"gdo-v1"`, Format `{name: string, stars: {"<bereichId>-<üniteIndex>": 1..3}, cls?: boolean, wb?: {"<uid>-<aufgabe>": 1}, wbt?: {"<uid>-<aufgabe>": [texte]}, bpos?: number}`. Bei inkompatiblen Formatänderungen den Key hochzählen.

## Konventionen

- Inhalte sind eigene, kindgerechte Kurz-Zusammenfassungen – keinen Buchtext kopieren.
- Light-/Dark-Mode über CSS-Variablen in `:root`.
- Entscheidungen werden in `ENTSCHEIDUNGEN.md` festgehalten.
