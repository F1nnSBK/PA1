# Vorlage für Wissenschaftliche Arbeiten der DHBW Ravensburg an der Fakultät Wirtschaft
Diese LaTeX Vorlage dient als Grundlage für wissenschaftliche Arbeiten an der DHBW Ravensburg in der Fakultät für Wirtschaft.

Die Vorlage orientiert sich an den Gestaltungsrichtlinien der DHBW RV.

### Enthaltene Titelblätter:                                                   
 - Projektarbeit
 - Bachelorarbeit
 - Projektdokumentation

## Benutzung
Es gibt zwei Möglichkeiten, diese Vorlage zu benutzen:

### Mit git
Um die Versionierung der Vorlage zu nutzen, empfiehlt es sich, das Repository auf Github auszuchecken. Alle Einstellungen (Parameter, Gliederung) kannst du im Ordner /config vornehmen. Dieser wird vom Repository nicht beeinflusst. Alle Konfigurationen, die du vornehmen musst, findest du im Ordner /config/example. Für ein korrektes Funktionieren der Vorlage benötigst du alle drei Dateien.
Dateien, die du zum Ordner /chapter hinzufügst, werden ebenfalls ignoriert, Änderungen an den Beispieldateien werden jedoch von der Versionsverwaltung verfolgt.

### Ohne git
Um die Vorlage zu benutzen, kannst du sie einfach [hier](https://github.com/julianbei/vorlage-dhbw-rv-wi/archive/master.zip) Downloaden.
Das .zip entpacken und den Inhalt in dein gewünschtes Arbeitsverzeichnis kopieren. (siehe: [Versionierung und Backup]( #Versionierung-und-Backup))

## Installation
Es empfiehlt sich Wissenschaftliche Arbeiten mit TexStudio zu bearbeiten.

### Installation MacOS
TBD
short:
- download and install [MacTex](https://tug.org/mactex/)
- download and install [TexStudio](http://www.texstudio.org/)
- be happy

### Installation Linux
TBD
short:
- download and install [TexLive](https://www.tug.org/texlive/)
- download and install [TexStudio](http://www.texstudio.org/)
- be happy

#### Debian Based (bspw. Ubuntu):

```
sudo apt-get install texlive-full
```

### Installation Windows
TBD (wer benutzt schon freiwillig windows)
- download and install [MikTex](http://miktex.org/)
- download and install [TexStudio](http://www.texstudio.org/)
- switch to Linux or MacOs
- think about how much the last step impacted your live in terms of happiness!

## Konfiguration von TexStudio
Konfiguration für TeXstudio: <br>
Unter: Preferences/erzeugen/Benutzerbefehle:
einen neuen Befehl mit folgendem Inhalt anlegen:
```bash
txs:///bibtex | txs:///makeindex "%.idx" -t "%.ilg" -o "%.ind" | txs:///makeindex -g -s "styles/stichwortverzeichnis.ist" % | txs:///makeindex "%.nlo" -s nomencl.ist -o "%.nls" | txs:///makeindex  -s "%.ist" -t "%.glg" -o "%.gls" "%.glo"
```
Anschließend mit Tools/benutzer/key kompilieren.									  

## Wichtige Befehle
Falls du unerfahren in LaTeX bist,
[hier](HOWTO/CHEAT_SHEET.md) gibt es eine übersicht der wichtigsten Befehle die du im Zusammenhang mit dieser Vorlage brauchst:

[Cheet Sheet](HOWTO/CHEAT_SHEET.md)

## Allgemeine Informationen zum Gebrauch
Keine Änderungen an den Dateien im Verzeichnis ```./pages/``` vornehmen. Für die Arbeit beziehen sich alle Änderungen auf diese Datei und die Dateien im Verzeichnis ```./chapter/```.

### Verzeichnisstruktur
Die Verzeichnisstruktur sieht folgendermaßen aus:
```
.
├── appendix                    # In diesem Ordner können die Anänge verwaltet werden.
│   ├── artefact.pdf            # Beispiel-Pdf die in den Anhang eingefügt wurde
│   └── index.tex               # Beispielhafter Anhang
├── chapter                     # Dein Arbeitsverzeichnis
│   ├── 10_einleitung.tex       # Beispiel Datei mit beispielen
│   ├── 20_kapitel.tex          # Beispiel Kapitel
│   ├── 80_fazit.tex            # Beispiel Fazit
│   ├──  abkuerzungsverzeichnis.tex # Datei in der du deine Abkürzungen definierst.
│   └── KiVerzeichnis.tex       # Datei in der alle Einträge in das KI-Verzeichnis vorgenommen werden.
├── config                      # Verzeichnis für die Konfigurationen deines Projektes.
│   ├── config.tex              # hier werden alle Konfigurationen vorgenommen
│   ├── gliederung.tex          # hier können alle erstellten Dateien aus dem Verzeichnis chapter in eure Arbeit eingefügt werden.
│   └── metaseiten.tex          # hier werden Funktionen wie Verzeichnisse eingefügt. Hier sollte nichts verändert werden.
├── HOWTO                       # Verzeichnis mit Anleitungen zur Benutzung
│   ├── CHEAT_SHEET.tex         # Cheat sheet
│   └── INITIAL_CONFIG.md       # Datei in der du deine Konfiguratonen (Name, Titel, ...) vornimmst. 
├── images
│   └── Seeigel_wuhuu.jpg       # Beispiel Bild
├── pages                       # Vorlagen Verzeichnis! Nichts Ändern!
│   ├── 10_titel_bachelor.tex
│   ├── 10_titel_projekt.tex
│   ├── 10_titel_projekt_doku.tex
│   ├── 10_titel_seminar.tex
│   ├── 11_sperrvermerk.tex
│   ├── 12_inhaltsverzeichnis.tex
│   ├── 13_abkuerzungsverzeichnis.tex
│   ├── 14_glossar.tex
│   ├── 15_abbildungsverzeichnis.tex
│   ├── 16_tabellenverzeichnis.tex
│   ├── 17_listingsverzeichnis.tex
│   ├── 18_literaturverzeichnis.tex
│   ├── 19_index.tex
│   └── 20_erklaerung.tex
├── literatur.bib               # Deine Literatursammlung
├── README.md                   # Die Datei die du gerade liest
└── vorlage.tex                # Hauptdatei <- Öffnen zum bearbeiten z.B. um Packages hinzuzufügen
```
### Initiale Konfiguration
siehe [INITIAL_CONFIG](HOWTO/INITIAL_CONFIG.md)

### Strukturierung der Arbeit
Es empfiehlt sich pro Kapitel eine neue Datei anzulegen.

### Literaturarbeit
Für die Erstellung des Literaturverzeichnises empfiehlt sich die Verwendung von:
- JabRef (http://jabref.sourceforge.net).
- Mendeley (https://www.mendeley.com/).

Die Datei ist unter ```./literatur/literatur.bib``` zu speichern.                                        


## <a name="Versionierung-und-Backup"></a>Versionierung und Backup
Es empfielt sich für das Schreiben von wissenschaftlichen Arbeiten eine Versionierung wie git zu verwenden.
Falls dies nicht möglich ist (bspw. weil man nicht bereit is für private repositories zu bezahlen), dann sollte man zumindest eine andere form des automatischen Backups verwenden.
Dazu empfehlen sich folgende lösungen:
  - Dropbox (2GB Kostenlos):
    https://www.dropbox.com/
  - Google Drive (15 GB Kostenlos):
    https://www.google.com/drive/
  - Microsoft OneDrive (Kostenpflichtig):
    https://onedrive.live.com/about/en-us/

Um einen dieser Clouddienste zu benutzen, muss sich das Projektverzeichnis in dem Verzeichnis des jeweiligen Anbieters befinden.

## Versionierung
Version 1.0: Markus Schutz - (WI06) 
Version 2.0: Julian Amelung - 2016
Version 3.0: Felix Keller (unterstütz von Sebastian Geimer) - 2024

## [License](LICESE.md)
The MIT License (MIT)
Copyright (c) 2024 Felix Keller

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.