# Entscheidungen

## 1. Single-File-HTML ohne Build-Step
Die gesamte App liegt in einer einzigen `index.html`. Kein Bundler, kein Framework, kein `npm install`. Die Datei lässt sich direkt öffnen, offline weitergeben und als statische Seite überall hosten.

## 2. Vanilla JavaScript
Kein React/Vue o. Ä. Der Umfang (wenige Screens, einfacher Zustand) rechtfertigt keine Abhängigkeiten; Rendering erfolgt über Template-Strings und `innerHTML`.

## 3. Schrift „Baloo 2“ über Google Fonts
Runde, kindgerechte Schrift mit guter Unterstützung türkischer Sonderzeichen (ğ, ş, ı, İ, â, î, û). Fallbacks: Nunito, Trebuchet MS, system-ui.

## 4. Inhalte paraphrasiert statt Buchtext kopiert
Die App folgt der Themenreihenfolge von „Etkinliklerle Dinimi Öğreniyorum“ (© Diyanet İşleri Başkanlığı), die Texte sind aber eigene Kurz-Zusammenfassungen und eigene Quizfragen. So bleiben die Urheberrechte des Buchs gewahrt.

## 5. Fortschritt nur lokal (`localStorage`, Key `gdo-v1`)
Keine Konten, kein Backend, keine Datenerhebung bei Kindern. Nachteil: Fortschritt ist an Gerät/Browser gebunden.

## 6. Inhaltlicher Ausbau: 6 Lernkarten + 6 Fragen pro Ünite
Statt 3 Karten und 3 Fragen hat jede Ünite jetzt 6 Lernkarten und 6 Quizfragen (174 + 174 insgesamt). Die Sternewertung richtet sich nach dem Anteil richtiger Antworten (alle = 3, ≥ ⅔ = 2, sonst 1). So bleibt sie unabhängig von der Fragenzahl, und gespeicherte Fortschritte unter `gdo-v1` bleiben gültig.

## 7. Hauptzielgruppe: Lehrkräfte im Unterricht (Sınıf Modu)
Die App wird vor allem per Beamer oder Smartboard im Unterricht eingesetzt. Deshalb gibt es einen Klassenmodus statt einer eigenen Lehrer-App:
- **Automatik:** Ab 1000 px Breite ist er automatisch aktiv und lässt sich umschalten (gespeichert als `cls` in `gdo-v1`). Auf dem Handy bleibt alles wie bisher.
- **Steuerung:** Die Lehrkraft steuert per Tastatur oder Presenter (→/←/Bild↑↓, A/B/C, F, Esc) und muss dafür nicht zum Laptop gehen.
- **Gesprächsfrage:** Pro Ünite gibt es eine Frage (`d`) für die Klasse, damit nicht nur abgefragt, sondern auch gesprochen wird.
- **Team-Punkte:** werden bewusst von Hand geführt (+/−) und nur im Speicher gehalten. So bleibt die Lehrkraft flexibel (Melden, Gruppenarbeit), und es werden keine Schülerdaten gespeichert.
- **Layout:** Es passt ab 1280×720 ohne Scrollen. In Lektionen wird die untere Navigation ausgeblendet.
