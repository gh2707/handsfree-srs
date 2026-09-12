# Hands-free SRS – Prototyp

Dieser Prototyp setzt den gewünschten Ablauf um:

- Vokabeln zufällig
- Deutsch → Spanisch und Spanisch → Deutsch gemischt
- TTS liest Frage und Antwort vor
- Bewertung per Sprache:
  - 1 = Einfach
  - 2 = Gut
  - 3 = Schwer
  - 4 = Nochmal
- eigener SRS-Termin für jede Vokabelrichtung
- zugehörige Beispielsätze folgen unmittelbar nach der Vokabel
- Beispielsätze sind eigene Karten und werden ebenfalls mit 1–4 bewertet
- danach geht es wieder mit einer zufälligen fälligen Vokabel weiter
- Lernstand wird lokal im Browser gespeichert
- CSV/TSV-Import ist eingebaut

## Schnelltest

1. `index.html` in Chrome öffnen.
2. Auf `Start / Fortsetzen` drücken.
3. Mikrofonzugriff erlauben, falls Chrome danach fragt.
4. Nach der Antwort einfach `eins`, `zwei`, `drei` oder `vier` sagen.

Hinweis: TTS funktioniert normalerweise auch bei lokal geöffneter Datei.
Die Browser-Spracherkennung kann je nach Android/Chrome-Version für lokale `file://`-Dateien eingeschränkt sein.
Wenn die Sprachbewertung lokal nicht startet, die Dateien über HTTPS bereitstellen (z. B. GitHub Pages).
Die vier Bildschirmtasten funktionieren unabhängig davon immer.

## Importformat

Mindestens:

Deutsch;Spanisch
erfordern;requerir

Mit Beispielsatz:

Deutsch;Spanisch;Beispielsatz Deutsch;Beispielsatz Spanisch
erfordern;requerir;Diese Aufgabe erfordert viel Geduld.;Esta tarea requiere mucha paciencia.

Weitere Sätze:

Beispielsatz Deutsch 2
Beispielsatz Spanisch 2
Beispielsatz Deutsch 3
Beispielsatz Spanisch 3

Tab-getrennte Anki-Exporte (`.tsv`/`.txt`) funktionieren ebenfalls.

## SRS-Logik im Prototyp

- 1 / Einfach: 4 Tage bzw. bisheriges Intervall × 3,5
- 2 / Gut: 1 Tag bzw. bisheriges Intervall × 2,5
- 3 / Schwer: 1 Tag bzw. bisheriges Intervall × 1,2
- 4 / Nochmal: in 10 Minuten

Das ist bewusst eine einfache, nachvollziehbare SRS-Version für den ersten Funktionstest.
Später kann die Terminberechnung durch FSRS ersetzt werden, ohne den restlichen Hands-free-Ablauf umzubauen.


V6 – spanische Sprachbefehle
- Spracherkennung für die Bewertung auf es-ES.
- Gesprochen: uno = Einfach, dos = Gut, tres = Schwer, seis = Nochmal.
- Intern bleiben die Bewertungen 1/2/3/4.
- Sonst basiert diese Version auf dem Basis-Test.
