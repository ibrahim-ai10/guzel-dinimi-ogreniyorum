# Güzel Dinimi Öğreniyorum

Ein Unterrichts-Werkzeug für Lehrkräfte (auf Türkisch), aufgebaut nach dem Diyanet-Buch **„Etkinliklerle Dinimi Öğreniyorum“**. Die App wird per Beamer oder Smartboard gezeigt, und die Lehrkraft unterrichtet mit ihr. Kinder können sie auch allein am Tablet oder Handy nutzen.

## Inhalt

- **4 Bereiche:** İnanç · İbadet · Siyer · Ahlâk
- **29 Üniten**, jede mit 6 Lernkarten und einem Quiz mit 6 Fragen (insgesamt 174 Lernkarten und 174 Fragen)
- **Sterne-Fortschritt** (1–3 Sterne pro Ünite: alle richtig = 3, mindestens zwei Drittel = 2, sonst 1), lokal im Browser per `localStorage` gespeichert – keine Anmeldung, kein Server

## Im Unterricht: Sınıf Modu (Klassenmodus)

Auf großen Bildschirmen (ab 1000 px Breite) ist der Klassenmodus automatisch an. Ein- und ausschalten lässt er sich mit dem 📽️-Knopf oben rechts oder im Profil.

- **Große Darstellung** für Beamer und Smartboard, getestet bei 1280×720, 1366×768 und 1920×1080
- **Ablauf pro Ünite:** 6 Lernkarten, dann eine Gesprächsfrage „💬 Sınıfça konuşalım“ für die Klasse, dann 6 Quizfragen mit den Antworten A, B und C
- **Team-Punkte:** Punktestand für zwei Teams (A und B), den die Lehrkraft mit + und − führt
- **Steuerung mit Tastatur oder Presenter:** →, Leertaste oder Bild↓ für weiter, ← oder Bild↑ für zurück, A/B/C oder 1/2/3 zum Antworten, F für Vollbild, Esc zurück zur Üniten-Liste
- **Fortschritt:** wird pro Gerät gespeichert. Am Lehrer-Laptop zeigt er also, was die Klasse schon durchgenommen hat.

## Nutzung

Die komplette App steckt in einer einzigen Datei: `index.html`. Einfach im Browser öffnen oder als statische Seite hosten (z. B. GitHub Pages oder Vercel).

## Hinweis zu den Inhalten

Die Texte in der App sind **eigene, kurze Zusammenfassungen** und folgen lediglich der Themenreihenfolge des Buchs. Es wird kein Buchtext übernommen.

Das Buch „Etkinliklerle Dinimi Öğreniyorum“ ist © Diyanet İşleri Başkanlığı.
