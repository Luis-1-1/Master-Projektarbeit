# Projektarbeit (Master)

Layout wie in der Bachelorarbeit (Knechtel-Vorlage, Hochschule Schmalkalden).

## Struktur

```
main.tex             Hauptdatei: Angaben zur Arbeit + Reihenfolge aller Teile
praeambel.tex        Pakete und Seitenlayout
vorspann/            Deckblatt, Sperrvermerk, Erklärung, Verzeichnisse, Zusammenfassung
kapitel/             ein Kapitel pro Datei
anhang/anhang.tex    Anhang (Seitenzahlen A, B, C ...)
abbildungen/         alle Bilder (Logos/ aus der BA hierher kopieren)
literatur.bib        Literaturdatenbank
```

## TeXstudio

1. `main.tex` öffnen. Alle Kapiteldateien haben oben `% !TeX root = ../main.tex`,
   dadurch kompiliert F5 immer das ganze Dokument, egal welche Datei offen ist.
2. Biber wird über die Zeile `% !TeX TXS-program:bibliography = txs:///biber` in `main.tex`
   automatisch gewählt. Alternativ in den Einstellungen unter „Erzeugen“ das
   Standard-Bibliographieprogramm auf Biber stellen.
3. Reihenfolge beim ersten Mal: Kompilieren → Werkzeuge/Literaturverzeichnis (Biber) → 2× Kompilieren.

## Git

Einmalig:

```bash
git init
git add .
git commit -m "Grundgerüst Projektarbeit"
git remote add origin https://github.com/NAME/projektarbeit.git   # privates Repo
git branch -M main
git push -u origin main
```

Täglich:

```bash
git add .
git commit -m "Kapitel 2: Abschnitt XY ergänzt"
git push
```

Abgegebenen Stand markieren und Änderungen seitdem als PDF zeigen:

```bash
git tag -a v0.1-entwurf -m "Erster Entwurf an Betreuer"
git push --tags
latexdiff-vc --git -r v0.1-entwurf --flatten main.tex   # erzeugt main-diffv0.1-entwurf.tex
```

## Konventionen

- Ein Satz pro Zeile (bessere Diffs in Git).
- Labels: `cap:` für Kapitel, `fig:` für Abbildungen, `tab:` für Tabellen, `eq:` für Formeln.
- Dateinamen von Bildern ohne Leerzeichen und Umlaute.
