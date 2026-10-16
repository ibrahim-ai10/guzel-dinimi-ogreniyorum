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
