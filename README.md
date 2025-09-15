# Optimierung und Implementierung eines Artikel-Empfehlungssystems für die SV-Gruppe auf der Google Cloud Platform

![LaTeX](https://img.shields.io/badge/LaTeX-008080?style=for-the-badge&logo=latex&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![GCP](https://img.shields.io/badge/Google_Cloud-4285F4?style=for-the-badge&logo=google-cloud&logoColor=white)

Dieses Repository enthält den Quellcode und die schriftliche Ausarbeitung meiner Projektarbeit im Rahmen des dualen Studiums Data Science und Künstliche Intelligenz an der DHBW Ravensburg.

---

## Kurzbeschreibung

Das Kernziel dieser Arbeit war die Konzeption, Implementierung und Optimierung eines hybriden Empfehlungssystems zur Steigerung der Nutzerbindung auf einem Nachrichtenportal. Die Performance des Systems wurde anhand der Metrik `nDCG@10` auf realen Nutzerinteraktionsdaten aus Google Analytics 4 evaluiert und optimiert. Der entwickelte Prototyp wurde auf der Google Cloud Platform implementiert und validiert.

---

## Kernkonzepte & Methodik

Die Arbeit basiert auf einem hybriden Ansatz, der die Stärken von zwei komplementären Empfehlungsstrategien kombiniert:

* **Content-Based Filtering (CBF):** Nutzung von hochdimensionalen Text-Embeddings (3072D) zur Berechnung der semantischen Ähnlichkeit zwischen Artikeln.
* **Collaborative Filtering (CF):** Einsatz eines modernen **Neural Collaborative Filtering (NCF)** Modells, um nicht-lineare Muster in den historischen Nutzer-Item-Interaktionen zu lernen.
* **Hybrides System:** Eine gewichtete Summe der Scores aus dem CBF- und CF-Modell dient als finale Zielfunktion zur Erstellung der Empfehlungsliste.
* **Optimierung:** Das Framework **Optuna** wurde verwendet, um die optimalen Gewichtungsfaktoren für die Hybridisierung durch einen bayesianischen Suchprozess zu finden.
* **Technologie-Stack:** Die Systemarchitektur basiert auf einem Microservice-Ansatz auf der **Google Cloud Platform (GCP)**, insbesondere unter Nutzung von BigQuery, Vertex AI und einem FastAPI-basierten Orchestrierungs-Service.

---

## Repository-Struktur

Das Repository ist entsprechend der LaTeX-Vorlage der DHBW Ravensburg strukturiert:

```
.
├── chapter/        # .tex-Dateien für die Hauptkapitel (Einleitung, Grundlagen, etc.)
├── pages/          # .tex-Dateien für den Vorspann (Inhaltsverzeichnis, alle anderen Verzeichnisse)
├── config/         # Konfigurationsdateien für die Vorlage (Layout, Gliederung, etc.)
├── content/        # Inhalte, die in die Arbeit eingebunden werden (Abbildungen, Tabellen)
├── appendix/       # Inhalte für den Anhang
├── scripts/        # (Empfehlung) Python-Skripte für Datenverarbeitung, Modelltraining & Visualisierung
├── vorlage.tex     # Die LaTeX-Hauptdatei, die alles zusammenfügt
└── literatur.bib   # Die Bibliographie-Datei
```

---

## Ergebnisse

Die Evaluation zeigt, dass das optimierte hybride Empfehlungssystem die etablierten Baseline-Modelle (z.B. Popularität, Aktualität) in der `nDCG@10`-Metrik signifikant übertrifft. Die Optimierung identifizierte eine robuste Konfiguration, in der die kontextuelle Relevanz (CBF) den dominanten Einfluss hat, aber durch die kollaborative Komponente (CF) entscheidend verbessert wird. Dies bestätigt die Hypothese, dass ein hybrider Ansatz für die Empfehlung von Nachrichtenartikeln überlegen ist.

---

## Kompilierung

Um das PDF der Arbeit aus den LaTeX-Quellen zu erstellen, wird eine vollständige LaTeX-Distribution (z.B. TeX Live, MiKTeX) benötigt. Aufgrund der Verwendung von `biblatex` mit `biber` und den Verzeichnissen ist ein mehrstufiger Kompilierungsprozess erforderlich:

```bash
pdflatex vorlage
biber vorlage
pdflatex vorlage
pdflatex vorlage
```

---

## Autor

* **Finn Hertsch**

## Betreuer

* **DHBW Ravensburg:** [Name des Betreuers/der Betreuerin]
* **Schwäbisch Media:** [Name des Betreuers/der Betreuerin]