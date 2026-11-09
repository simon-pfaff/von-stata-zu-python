# Von Stata zu Python: Eine Einführung für Stata-Umsteiger

Willkommen im GitHub-Repository zum Guide **"Von .do zu .py - Datenanalyse mit Python"**. 

Dieses Repository enthält alle begleitenden Jupyter Notebooks (`.ipynb`) und Praxis-Codebeispiele. Es wurde speziell für Stata-Nutzer entwickelt, die sich in Python und pandas einarbeiten möchten.

## 📖 Begleitender Kurs auf Substack
Die ausführlichen methodischen Erklärungen, Stolpersteine und detaillierten Syntax-Vergleiche erscheinen kapitelweise als Newsletter.

👉 **[Hier geht es zum Substack-Kurs](HIER_SPÄTER_IHR_SUBSTACK_LINK_REIN)** (Jetzt kostenlos abonnieren!)

---

## 🗺️ Inhaltsverzeichnis & Kursstruktur

Hier finden Sie die Jupyter Notebooks zu den einzelnen Abschnitten (wird wöchentlich aktualisiert):

### Teil 1: Die Grundlagen des Umstiegs
* 📂 `kapitel_01/` **Datenstrukturen & Import**
  * Von `.dta` und `use` zu Pandas DataFrames (`pd.read_stata`, `pd.read_csv`)
* 📂 `kapitel_02/` **Daten-Inspektion & Erste Übersicht**
  * Das Python-Äquivalent zu `describe`, `summarize` und `codebook`
* 📂 `kapitel_03/` **Data Cleaning & Transformation**
  * Variablen manipulieren: `keep if`, `drop`, `replace` und `egen` in Python umsetzen

### Teil 2: Fortgeschrittene Datenmanipulation
* 📂 `kapitel_04/` **Zusammenfügen & Aggregieren**
  * Datensätze matchen: `merge 1:1` und `merge m:1` vs. `pd.merge()`
  * Daten kollabieren: Der Wechsel von `collapse (mean)` zu `.groupby().mean()`
* 📂 `kapitel_05/` **Reshaping & Paneldaten** (In Überarbeitung)
  * Daten umstrukturieren: `reshape long` und `reshape wide` mit Pandas `melt` und `pivot`

### Teil 3: Ökonometrie & Datenvisualisierung (Geplant)
* 📂 `kapitel_06/` **Regressionsanalysen & Statistische Modelle**
  * Lineare Regressionen: Von `regress y x` zu `statsmodels` und `linearmodels`
* 📂 `kapitel_07/` **Grafikerstellung**
  * `twoway scatter` adieu: Datenvisualisierung mit `matplotlib` und `seaborn`
