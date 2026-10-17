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

## 8. Inhalte am Buch ausgerichtet (5. Auflage, Ankara 2019)
Alle 29 Üniten wurden mit dem Buch abgeglichen und neu geschrieben. Inhalte, die nicht im Buch stehen, sind entfernt (z. B. Hilfu’l-Fudûl, Habeşistan, Suffe, Misvak). Dazugekommen sind die Schwerpunkte des Buchs: Besmele/Elhamdülillâh/Allâhü Ekber, 16 Esmâ, Farz/Sünnet/Helâl/Haram, Cuma (4+2+4), Teravih, Bayram namazı, was die Abdest und was das Gebet bricht, İftar duası, Alltags-Dua-Formeln, Hacerü’l-Esved, Safâ, Ebû Eyyûb, Veda Haccı, Sofra adabı, Özür/Teşekkür, „Yalancının mumu…“ usw.
- Pro Ünite gibt es 6–8 Karten statt fest 6, damit umfangreiche Üniten (z. B. Namaz Kılıyorum, Örnek Kişiliği) nicht gekürzt werden müssen. Die Fragen bleiben bei 6, damit die Sternewertung vergleichbar bleibt.
- Die Gesprächsfragen (`d`) greifen die Aktivitäten des Buchs auf (Düşünelim/Paylaşalım, Geschichten zum Weiterdenken).
- Die Seitenangaben (`s`) sind für Lehrkräfte gedacht, um parallel im Buch zu arbeiten.
- Das Buch selbst wird bewusst nicht ins öffentliche Repo gelegt (Urheberrecht © DİB).

## 9. „Interaktives Buch“: eigener PDF-Leser + eigenes Arbeitsheft
Das Buch ist © DİB, und Repo und Website sind öffentlich. Deshalb werden die Buchseiten **nicht** in die App eingebaut. Stattdessen gibt es zwei Teile:
- **Buch-Leser:** Die Lehrkraft lädt ihr eigenes PDF; es bleibt lokal in IndexedDB. Die Darstellung übernimmt pdf.js 3.11.174 von jsDelivr. Das ist die erste Skript-Abhängigkeit, sie wird nur beim Öffnen des Lesers geladen; der Rest der App bleibt ohne Internet nutzbar. Das Blättern ist eine CSS-3D-Animation (Doppelseite: das Blatt dreht sich um den Buchrücken). Notizen werden als Vektoren in Seitenkoordinaten gespeichert, damit sie bei jeder Bildschirmgröße passen.
- **Arbeitsheft:** Die Aufgaben des Buchs sind als eigene, automatisch prüfbare Aufgabentypen neu gestaltet (keine Kopie der Buchseiten). Bedient wird alles per Antippen statt Ziehen, das ist zuverlässiger auf Smartboard und Tablet. Lange Reihenfolge-Aufgaben stehen zweispaltig, damit sie ab 1280×720 ohne Scrollen passen.
