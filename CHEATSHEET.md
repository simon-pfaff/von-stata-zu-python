# 📋 Stata-zu-Python Cheat Sheet (Work in Progress)

Diese Übersicht hilft beim schnellen Umstieg von Stata auf Python (`pandas`). Alle Beispiele gehen davon aus, dass `pandas` bereits importiert wurde (`import pandas as pd`) und der Datensatz im DataFrame `df` gespeichert ist.

| Stata | Python (Pandas) | Beschreibung |
| :--- | :--- | :--- |
| `use "daten.dta"` | `df = pd.read_stata("daten.dta")` | Datensatz einlesen |
| `describe` | `print(df.info())` | Datensatz beschreiben |
| `list 1/5` | `print(df.head())` | Erste 5 Zeilen anzeigen |
| `list in -5/l` | `print(df.tail())` | Letzte 5 Zeilen anzeigen |
| `count` | `len(df)` <br> `df.shape[0]` | Zahl der Beobachtungen |
| *(Dimensionen)* | `df.shape` | Zahl der Beobachtungen & Variablen |
| `keep if alter == 18` | `df = df[df['alter'] == 18].copy()` | Auswahl (Filtern) |
| `drop if alter == 18` | `df = df[df['alter'] != 18].copy()` | Inverse Auswahl |
| `save "daten.dta", replace` | `df.to_stata(r"daten.dta", write_index=False)` | Datensatz speichern |
| `drop Einkommen` | `df = df.drop(columns="Einkommen")` <br> `del df["Einkommen"]` | Spalte löschen |
| `drop if index == 1` | `df = df.drop(index=1)` | Zeile löschen |
| `summarize var1 var2, detail` | `df[['var1', 'var2']].describe()` | Zusammenfassende Statistiken |
| `tab UMOD` | `df['UMOD'].value_counts()` | Häufigkeitsverteilung |
| `tabulate v7, missing` | `df['v7'].value_counts(dropna=False).sort_index()` | Häufigkeitsverteilung (inkl. Missings) |
| `tab var1 var2` | `pd.crosstab(df["var1"], df["var2"])` | Kreuztabelle |
| `sum VB` | `df['VB'].mean()` | Mittelwert |

---

⬅️ [Zurück zur Hauptseite](./README.md)
 
