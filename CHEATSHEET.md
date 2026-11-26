
markdown

# Von .do zu .py - Datenanalyse mit Python: Eine Einführung für Stata-Umsteiger

Willkommen im GitHub-Repository zum Guide **"Von .do zu .py"**. 

Dieses Repository enthält alle begleitenden Jupyter Notebooks (`.ipynb`) und Praxis-Codebeispiele. Es wurde für Stata-Nutzer entwickelt, die sich mit Python und pandas beschäftigen möchten.

👉 **Direkt zum Nachschlagen:** [Stata-zu-Python Cheat Sheet (Befehlsübersicht)](./CHEATSHEET.md)

## 📖 Begleitender Kurs auf Substack
Die ausführlichen Erklärungen, Hintergrundberichte und vertiefenden Syntax-Vergleiche erscheinen kapitelweise als Newsletter auf Substack (Start in Kürze).

<!-- 👉 **[Hier geht es zum Substack-Kurs](HIER_SPÄTER_IHR_SUBSTACK_LINK_REIN)** (Jetzt kostenlos abonnieren!) -->

---

## 🗺️ Inhaltsverzeichnis & Repository-Struktur

Hier finden Sie die Jupyter Notebooks und Code-Beispiele zu den einzelnen Abschnitten (wird fortlaufend aktualisiert):

### 1. Einführung
* 📂 `01_einfuehrung/` *(folgt)*
  * 1.1 Beispieldatensätze und Importkonventionen

### 2. Software für die Datenanalyse
* 📂 `02_software_setup/` *(folgt)*
  * 2.1 Der Ausgangspunkt: Anaconda
    * 2.1.1 virtuelle Umgebungen
  * 2.2 Die Auswahl der Entwicklungsumgebung (IDE)
    * 2.2.1 IPython
    * 2.2.2 Spyder
    * 2.2.3 Jupyter Notebook
    * 2.2.4 Ein Blick über den Tellerrand

### 3. Erste Schritte hin zur Datenanalyse mit pandas
* 📂 `03_erste_schritte_pandas/` *(folgt)*
  * 3.1 Eindimensionales Datenarray: Series
    * 3.1.1 Series als Python Dictionary
    * 3.1.2 Slicing in Python
    * 3.1.3 Anwendungsbeispiel 1
  * 3.2 Zweidimensionales Datenarray: DataFrame
    * 3.2.1 Einträge ergänzen und löschen
    * 3.2.2 Auswahl von Daten
    * 3.2.3 Sortieren von Daten
    * 3.2.4 Erste deskriptive Statistiken berechnen I
    * 3.2.5 Erste deskriptive Statistiken berechnen II

### 4. Daten einlesen
* 📂 `04_daten_einlesen/` *(folgt)*
  * 4.1 Einfache Wege: Manuelle Eingabe und CSV-Dateien
  * 4.2 Daten im Stata-Format einlesen mit `pd.read_stata()`
    * 4.2.1 Ein erster Check der Daten
    * 4.2.2 Häufigkeitstabelle und Durchschnittswert
    * 4.2.3 Teildatensatz auswählen und speichern
  * 4.3 Daten im Stata-Format einlesen mit der Bibliothek `pyreadstat`
    * 4.3.1 Installation von pyreadstat
    * 4.3.2 Einlesen der Daten
  * 4.4 `pd.read_stata()` versus `pyreadstat`

---

## 📊 Daten
Die Beispiele verwenden das Politbarometer 2024 (GESIS, Studiennummer ZA8974). Die Daten selbst sind nicht in diesem Repository enthalten, sie sind über das GESIS-Datenarchiv erhältlich. Die Notebooks enthalten nur den Code ohne Ausgaben. Die Ergebnisse lassen sich mit den Originaldaten reproduzieren.

## 🧰 Verwendete Bibliotheken

| Bibliothek | Beschreibung |
| :--- | :--- |
| `pandas` | pandas ist die zentrale Python-Bibliothek für die Datenaufbereitung und -analyse. Sie stellt mit Series und DataFrame tabellarische Datenstrukturen bereit, die einem Stata-Datensatz ähneln, und ermöglicht das Einlesen, Filtern, Sortieren, Umformen und Zusammenfügen von Daten sowie die Berechnung deskriptiver Statistiken. Zudem lassen sich Daten in gängige Formate wie CSV, Excel oder .dta importieren und exportieren. |
| `numpy` | NumPy ist die grundlegende Python-Bibliothek für numerische Berechnungen. Sie stellt leistungsfähige mehrdimensionale Arrays sowie mathematische Funktionen für Vektor- und Matrixoperationen, Zufallszahlen und statistische Kennwerte bereit. pandas baut technisch auf NumPy auf; in der Datenanalyse wird NumPy vor allem für Berechnungen und das Erzeugen neuer Variablen genutzt, etwa mit `np.where()` als Gegenstück zu Statas `cond()`. |
| `pyreadstat` | pyreadstat ist eine Python-Bibliothek zum Lesen und Schreiben von Datendateien aus Statistikprogrammen wie Stata (.dta), SPSS (.sav) und SAS. Anders als `pd.read_stata()` liefert sie neben dem Datensatz ein separates Metadaten-Objekt mit Variablenlabels und Value Labels und behält dabei die ursprünglichen Zahlencodes. Damit eignet sie sich besonders für sozialwissenschaftliche Umfragedaten, bei denen Labels wichtig sind. |
| `matplotlib` | Matplotlib ist eine weit verbreitete Python-Bibliothek zur Datenvisualisierung. Sie ermöglicht die Erstellung statischer, animierter und interaktiver Diagramme (wie Balken-, Linien- oder Streudiagramme) sowie die detaillierte Anpassung von Beschriftungen, Farben, Achsen und Layouts für den Export in gängige Bild- und Dokumentformate. |
| `openpyxl` | OpenPyXL ist eine Python-Bibliothek zum Lesen, Schreiben und Bearbeiten von modernen Excel-Dateien (.xlsx, .xlsm). Im Rahmen der Datenanalyse dient sie der Datenaufbereitungs-Bibliothek pandas als technische Schnittstelle (Engine), um Tabellendaten direkt aus Excel-Arbeitsmappen zu importieren oder darin zu speichern. Ein eigener Import ist dafür nicht nötig, die Bibliothek muss nur installiert sein. |

---
*Hinweis: Der Quellcode und die Jupyter Notebooks werden parallel zur kapitelweisen Veröffentlichung auf Substack freigeschaltet.*

nice, danke. jetzt bitte nochmal das cheat sheep inkl. der kurzbeschreibungen der bibliotheken als md, bitte
markdown

# 📋 Stata-zu-Python Cheat Sheet (Work in Progress)

Diese Übersicht hilft beim schnellen Umstieg von Stata auf Python (`pandas`). Alle Beispiele gehen davon aus, dass die Bibliotheken importiert wurden und der Datensatz im DataFrame `df` gespeichert ist.

### Bibliotheken laden

| Stata | Python | Beschreibung |
| :--- | :--- | :--- |
| | `import numpy as np` <br> `import pandas as pd` <br> `import pyreadstat` <br> `import matplotlib.pyplot as plt` | Python Bibliotheken laden |

| Bibliothek | Zweck |
| :--- | :--- |
| `pandas` | Datensätze (DataFrames) aufbereiten und analysieren |
| `numpy` | Numerische Berechnungen, z. B. `np.where()` |
| `pyreadstat` | .dta/.sav einlesen und speichern, inkl. Labels |
| `matplotlib` | Grafiken erstellen |
| `openpyxl` | Excel-Dateien lesen und schreiben (wird von pandas im Hintergrund genutzt, kein Import nötig) |

### Datensatz einlesen I

| Stata | Python | Beschreibung |
| :--- | :--- | :--- |
| `use "daten.dta"` | `df = pd.read_stata("daten.dta")` | Datensatz einlesen |

### Datensatz einlesen II, Labels anzeigen

| Stata | Python | Beschreibung |
| :--- | :--- | :--- |
| | `df, meta = pyreadstat.read_dta("daten.dta")` | Datensatz und Metadaten einlesen (zwei Objekte) |
| `describe <variablenname>` | `meta.column_names_to_labels.get('<variablenname>')` | Variablenlabel anzeigen |
| - | `meta.variable_value_labels.get('<variablenname>')` | Value Labels einer Variablen anzeigen |
| `describe <variablenname>` | `meta.variable_to_label.get('<variablenname>')` | Labelname der Variablen anzeigen |
| `label list <labelname>` | `meta.value_labels['<labelname>']` | Value Labels nach Labelname |

### Datensatzbetrachtung

| Stata | Python | Beschreibung |
| :--- | :--- | :--- |
| `describe` | `df.info()` | Datensatz beschreiben |
| `list in 1/5` | `df.head()` | erste 5 Zeilen anzeigen |
| `list in -5/L` | `df.tail()` | letzte 5 Zeilen anzeigen |
| `count` | `len(df)` <br> `df.shape[0]` | Zahl der Beobachtungen |
| `describe, short` | `df.shape` | Zahl der Beobachtungen & Variablen |

### Auswahl

| Stata | Python | Beschreibung |
| :--- | :--- | :--- |
| `keep if alter == 18` | `df = df[df['alter'] == 18].copy()` | Auswahl |
| `drop if alter == 18` | `df = df[df['alter'] != 18].copy()` | Inverse Auswahl |

### Spalten und Zeilen löschen

| Stata | Python | Beschreibung |
| :--- | :--- | :--- |
| `drop Einkommen` | `df = df.drop(columns="Einkommen")` <br> `del df["Einkommen"]` | Spalte löschen |
| `drop if index == 1` | `df = df[df['index'] != 1].copy()` | Zeilen löschen, in denen die Variable `index` den Wert 1 hat |
| `drop if _n == 2` | `df = df.drop(index=1)` | Zeile mit dem Indexlabel 1 löschen (= 2. Zeile) |
| `drop in 1` | `df = df.drop(df.index[0])` | Erste Zeile löschen |

### Deskriptive Statistiken

| Stata | Python | Beschreibung |
| :--- | :--- | :--- |
| `summarize var1 var2, detail` | `df[['var1', 'var2']].describe()` | Zusammenfassende Statistiken |
| `tab UMOD` | `df['UMOD'].value_counts().sort_index()` | Häufigkeitsverteilung |
| `tabulate v7, missing` | `df['v7'].value_counts(dropna=False).sort_index()` | Häufigkeitsverteilung, absolut |
| `tabulate v7, missing` | `df['v7'].value_counts(dropna=False, normalize=True).sort_index()` | Häufigkeitsverteilung, Prozent |
| `tab var1 var2` | `pd.crosstab(df["var1"], df["var2"])` | Kreuztabelle |
| `summarize VB` | `df['VB'].mean()` | Mittelwert |

---

## Erläuterungen

* `pd.read_stata` und `pyreadstat` verhalten sich bei Labels unterschiedlich. `pd.read_stata` macht aus Variablen mit Value Labels standardmäßig Kategorien mit den Labeltexten (`convert_categoricals=True`). Die Zahlencodes sind dann nicht enthalten. Mit `pd.read_stata("daten.dta", convert_categoricals=False)` behält auch pandas die Zahlencodes. `pyreadstat.read_dta` behält die Zahlencodes.

### Speichern der Datensätze

**pandas**

| Stata | Python | Beschreibung |
| :--- | :--- | :--- |
| `use "daten.dta"` | `df =


Claude ist eine KI und kann Fehler machen.
Claude antwortet
