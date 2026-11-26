# 📋 Stata-zu-Python Cheat Sheet (Work in Progress)

Diese Übersicht hilft beim schnellen Umstieg von Stata auf Python (`pandas`). Alle Beispiele gehen davon aus, dass die Bibliotheken importiert wurden und der Datensatz im DataFrame `df` gespeichert ist.

### Bibliotheken laden

| Stata | Python | Beschreibung |
| :--- | :--- | :--- |
| | `import numpy as np` <br> `import pandas as pd` <br> `import pyreadstat` | Python Bibliotheken laden |

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

### Speichern

| Stata | Python | Beschreibung |
| :--- | :--- | :--- |
| `save "daten.dta", replace` | `df.to_stata("daten.dta", write_index=False)` | Datensatz speichern |

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
| `use "daten.dta"` | `df = pd.read_stata("daten.dta")` | Datensatz einlesen |
| `save "daten.dta", replace` | `df.to_stata("daten.dta", write_index=False)` | Datensatz speichern |

**pyreadstat**

| Stata | Python | Beschreibung |
| :--- | :--- | :--- |
| `use "daten.dta"` | `df, meta = pyreadstat.read_dta("daten.dta")` | Datensatz und Metadaten einlesen (zwei Objekte) |
| `save "daten.dta", replace` | `pyreadstat.write_dta(df, "daten.dta", ...)` | Datensatz speichern |

* Das Speichern der Labels ist wie folgt möglich:

```python
df, meta = pyreadstat.read_dta("daten.dta")

# ... Datensatz bearbeiten ...

pyreadstat.write_dta(
    df, "daten.dta",
    column_labels=meta.column_names_to_labels,          # Variablenlabels
    variable_value_labels=meta.variable_value_labels,   # Value Labels
    version=14                                          # damit Stata/BE und SE die Datei öffnen können
)
```

---

⬅️ [Zurück zur Hauptseite](./README.md)
