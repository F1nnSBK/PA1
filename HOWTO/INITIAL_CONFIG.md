# Initiale Konfiguration
In der Datei: ```config/config.tex``` muss folgender Bereich mit deinen persönlichen Angaben ausgefüllt werden:
```TeX
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%% Konfiguration %%

\def\myType{0}
%% 0=Projektarbeit   %%
%% 1=Bachelorarbeit  %%
%% 2=Projektdokumentation %%

\def\myTopic{Titel}
\def\mySubTopic{Subtitel}
\def\myStudyProgram{}               % Studiengang

\def\myAutor{}
\def\myProf{}
\def\myCompany{}
\def\myCompanion{}                  % Begleitperson des dualen Partners
\def\myEndDate{}
\def\myDeliveryLocation{}           % Abgabort

%% Projektarbeit %%
\def\myProjNumber{1}                % [1|2]
\def\myPraxPhase{1}                 % [1|2|3|4|5|6]

%% Bachelorarbeit %%
\def\myTypeOfBachelor{}             % [Arts|Science]

%% Konfiguration KI-Verzeichnis und Selbständigkeitserklärung und Sperrvermerk %%
\def\myLanguage{0}                 
%% 0=kein KI-Verzeichnis   %%
%% 1=Deutsch    %%
%% 2=Englisch   %%

\def\myDecOfIndependence{0}
%% 0=keine Selbständigkeitserklärung   %%
%% 1=Selbständigkeitserklärung    %%

\def\myBlockingNote{0}
%% 0=kein Sperrvermerk   %%
%% 1=Sperrvermerk    %%

%Ort und Datum der Unterschrift auf KI-Verzeichnis Selbständigkeitserklärung und Sperrvermerk
\def\myDate{}
\def\myPlace{}
```
#### Die Befehle im Einzelnen
```
\def\myType{1}
```
Gibt an welche Art von Projekt geschrieben wird. Dadurch wird das entsprechende Titelblatt mit den nachfolgenden Informationen befüllt.
Folgende Werte können verwendet werden:
- {0} [Projektarbeit](#Projektarbeit)
- {1} [Bachelorarbeit](#Bachelorarbeit)
- {2} [Projektdokumentation](#Projektdokumentation)

##### Allgemeine Informationen

| Befehl                          | variable              | Erläuterung                                           |
| ------------------------------- |:---------------------:| ----------------------------------------------------- |
| `\def\myType{1}`                | **_1_**               | Art der Arbeit                                        |
| `\def\myTopic{Titel}`           | **_Titel_**           | Der Titel der Arbeit                                  |
| `\def\mySubTopic{Untertitel}`   | **_Untertitel_**      | Der Unteritel der Arbeit (falls vorhanden)            |
| `\def\myAutor{Vorname Nachname}`| **_Vorname Nachname_**| Vorname und Nachname des Autors                       |
| `\def\myProf{Betruer Name}`     | **_Betreuer Name_**   | Titel Vorname und Nachname des Betreuenden Lehrkörpers|
| `\def\myEndDate{Abgabe Datum}`  | **_Abgabe Datum_**    | Abgabedatum der Arbeit                                |

##### <a name="Seminararbeit"></a>Seminararbeit
Spezielle befehle für eine Seminararbeit:

| Befehl                              | variable              | Erläuterung                                           |
| ----------------------------------- |:---------------------:| ----------------------------------------------------- |
| `\def\myType{0}`                    | **_0_**               | Option **0** ist Seminararbeit                        |
| `\def\myVorlesung{Vorlesungstitel}` | **_Vorlesungstitel_** | Titel der Vorlesung                                   |

##### <a name="Projektarbeit"></a>Projektarbeit

| Befehl                              | variable              | Erläuterung                                           |
| ----------------------------------- |:---------------------:| ----------------------------------------------------- |
| `\def\myType{1}`                    | **_1_**               | Option **1** ist Projektarbeit                        |
| `\def\myCompany{Unternehmensname}` | **_Unternehmensname_** | Name des betreuenden Unternehmens                                  |
| `\def\myCompanyAddressStreet{Unternehmen Anschrift}` | **_Unternehmen Anschrift_** | Straße Hausnummer Unternehmenssitzes                                 |
| `\def\myCompanyAddressCity{Stadt des Unternehmenssitzes}` | **_Stadt des Unternehmenssitzes_** | PLZ Stadt Unternehmenssitzes                                   |

##### <a name="Bachelorarbeit"></a>Bachelorarbeit

| Befehl                              | variable              | Erläuterung                                           |
| ----------------------------------- |:---------------------:| ----------------------------------------------------- |
| `\def\myType{2}`                    | **_2_**               | Option **2** ist Bachelorarbeit                        |
| `\def\myCompany{Unternehmensname}` | **_Unternehmensname_** | Name des betreuenden Unternehmens                                  |
| `\def\myCompanyAddressStreet{Unternehmen Anschrift}` | **_Unternehmen Anschrift_** | Straße Hausnummer Unternehmenssitzes                                 |
| `\def\myCompanyAddressCity{Stadt des Unternehmenssitzes}` | **_Stadt des Unternehmenssitzes_** | PLZ Stadt Unternehmenssitzes                                   |

##### <a name="Projektdokumentation"></a>Projektdokumentation
Bei Projektdokumentationen gibt es die Besonderheit, dass es mehrere Autoren geben kann.
Daher wird das Feld: `\myAutor` anders belegt.

| Befehl                              | variable              | Erläuterung                                           |
| ----------------------------------- |:---------------------:| ----------------------------------------------------- |
| `\def\myType{3}`                    | **_3_**               | Option **3** ist Projektdokumentation                 |
| `\def\myAutor{Autorenliste}`        | **_Autorenliste_**    | Eine kommagetrennte Liste der Autoren, Name Nachname Martrikelnummer |

Beispiel:

```TeX
\def\myAutor{
	 Klaus Mustermann 2312354,
	 John Doe 6386782,
	 Herbert Hirnriss 50082145,
	 Peter Silie 6102134,
	 Peter Pan 3421540
	}
```
