# Güzel Dinimi Öğreniyorum

Ein Unterrichts-Werkzeug für Lehrkräfte (auf Türkisch), aufgebaut nach dem Diyanet-Buch **„Etkinliklerle Dinimi Öğreniyorum“**. Die App wird per Beamer oder Smartboard gezeigt, und die Lehrkraft unterrichtet mit ihr. Kinder können sie auch allein am Tablet oder Handy nutzen.

## Inhalt

- **4 Bereiche:** İnanç · İbadet · Siyer · Ahlâk
- **29 Üniten** in der Reihenfolge des Buchs, jeweils mit Seitenangabe („📖 Kitap s. 8–13“), 6–8 Lernkarten, einer Gesprächsfrage für die Klasse und 6 Quizfragen (insgesamt 198 Lernkarten und 174 Fragen)
- **Sterne-Fortschritt** (1–3 Sterne pro Ünite: alle richtig = 3, mindestens zwei Drittel = 2, sonst 1), lokal im Browser per `localStorage` gespeichert – keine Anmeldung, kein Server

## Im Unterricht: Sınıf Modu (Klassenmodus)

Auf großen Bildschirmen (ab 1000 px Breite) ist der Klassenmodus automatisch an. Ein- und ausschalten lässt er sich mit dem 📽️-Knopf oben rechts oder im Profil.

- **Große Darstellung** für Beamer und Smartboard, getestet bei 1280×720, 1366×768 und 1920×1080
- **Ablauf pro Ünite:** 6 Lernkarten, dann eine Gesprächsfrage „💬 Sınıfça konuşalım“ für die Klasse, dann 6 Quizfragen mit den Antworten A, B und C
- **Team-Punkte:** Punktestand für zwei Teams (A und B), den die Lehrkraft mit + und − führt
- **Steuerung mit Tastatur oder Presenter:** →, Leertaste oder Bild↓ für weiter, ← oder Bild↑ für zurück, A/B/C oder 1/2/3 zum Antworten, F für Vollbild, Esc zurück zur Üniten-Liste
- **Fortschritt:** wird pro Gerät gespeichert. Am Lehrer-Laptop zeigt er also, was die Klasse schon durchgenommen hat.

## 📖 Buch-Leser und ✏️ Arbeitsheft

- **Buch-Leser (Tab „Kitap“ oder „📖 Kitap s. …“ an jeder Ünite):** Die Lehrkraft öffnet ihr eigenes PDF des Buchs. Mehrere Teildateien wie `001-100`, `101-200` und `201-224` können zusammen ausgewählt werden. Die Seiten werden mit Blätter-Animation angezeigt, am Beamer als Doppelseite. Mit Stift, Marker, Textfeld und Radierer lässt sich direkt auf die Seiten schreiben. **PDF und Notizen bleiben nur im Browser dieses Geräts (IndexedDB)**; nichts wird hochgeladen, und das Buch liegt nicht im Repo.
- **Arbeitsheft (pro Ünite „✏️ Etkinlik“):** 99 eigene, an die Aktivitäten des Buchs angelehnte Aufgaben auf Papier-Seiten mit Blätter-Animation: Lückentext, Zuordnen, Reihenfolge, Sortieren, Richtig/Falsch, Wortsuche und Schreibaufgaben. Die Aufgaben werden automatisch geprüft; der Fortschritt wird gespeichert.

## Nutzung

Die komplette App steckt in einer einzigen Datei: `index.html`. Einfach im Browser öffnen oder als statische Seite hosten (z. B. GitHub Pages oder Vercel).

## Hinweis zu den Inhalten

Die Inhalte folgen der 5. Auflage (Ankara 2019) des Buchs: gleiche Üniten, gleiche Reihenfolge, Seitenangaben. Inhaltlich übernehmen sie die Schwerpunkte, Verse, Hadithe und Geschichten des Buchs, und aus den Aktivitäten des Buchs werden Gesprächsfragen. Die Texte sind **eigene, kurze Zusammenfassungen**; Buchtext wird nicht übernommen, das Buch selbst liegt nicht im Repo.

Das Buch „Etkinliklerle Dinimi Öğreniyorum“ ist © Diyanet İşleri Başkanlığı.
