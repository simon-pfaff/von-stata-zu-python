# Von .do zu .py - Datenanalyse mit Python: Eine Einführung für Stata-Umsteiger

Willkommen im GitHub-Repository zum Guide **"Von .do zu .py"**. 

Dieses Repository enthält alle begleitenden Jupyter Notebooks (`.ipynb`) und Praxis-Codebeispiele. Es wurde für Stata-Nutzer entwickelt, die sich mit Python und padas beschäftigen möchten.

👉 **Direkt zum Nachschlagen:** [Stata-zu-Python Cheat Sheet (Befehlsübersicht)](./CHEATSHEET.md)

## 📖 Begleitender Kurs auf Substack
Die ausführlichen Erklärungen, Hintergrundberichte und vertiefenden Syntax-Vergleiche erscheinen kapitelweise als Newsletter.

👉 **[Hier geht es zum Substack-Kurs](HIER_SPÄTER_IHR_SUBSTACK_LINK_REIN)** (Jetzt kostenlos abonnieren!)

---

## 🗺️ Inhaltsverzeichnis & Repository-Struktur

Hier finden Sie die Jupyter Notebooks und Code-Beispiele zu den einzelnen Abschnitten (wird fortlaufend aktualisiert):

### 1. Einführung
* 📂 `01_einfuehrung/`
  * 1.1 Beispieldatensätze und Importkonventionen

### 2. Software für die Datenanalyse
* 📂 `02_software_setup/`
  * 2.1 Der Ausgangspunkt: Anaconda
    * 2.1.1 virtuelle Umgebungen
  * 2.2 Die Auswahl der Entwicklungsumgebung (IDE)
    * 2.2.1 IPython
    * 2.2.2 Spyder
    * 2.2.3 Jupyter Notebook
    * 2.2.4 Ein Blick über den Tellerrand

### 3. Erste Schritte hin zur Datenanalyse mit pandas
* 📂 `03_erste_schritte_pandas/`
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
* 📂 `04_daten_einlesen/`
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
*Hinweis: Der Quellcode und die Jupyter Notebooks werden parallel zur kapitelweisen Veröffentlichung auf Substack freigeschaltet.*
