# Garmin Sleep Analysis

Exploratory analysis of 2+ years of personal sleep data exported from a Garmin watch via Garmin Connect.

The goal is to identify patterns in sleep quality, duration, and stage composition over time using data I collected through my Garmin watch.

---

## Data

Data was exported directly from [Garmin Connect](https://www.garmin.com/en-US/account/datamanagement/exportdata) as JSON files. The raw exports cover **December 2023 through February 2026** and contain nightly records with sleep stage breakdowns, Garmin's proprietary sleep scores, respiration rates, stress levels, and qualitative feedback labels.

> **Note:** Raw data files are not included in this repository as they contain personal health information. If you want to replicate this project with your own data, you can export your sleep history from Garmin Connect under **Account > Data Management > Export Your Data**.

---

## Pipeline

The project will be structured as a sequential three-notebook pipeline:

| Notebook | Status | Purpose |
|---|---|---|
| `01_sleep_concat.ipynb` | ✅ Complete | Load and combine raw JSON files |
| `02_sleep_clean.ipynb` | 🔜 Coming soon | Clean and transform the combined data |
| `03_sleep_analysis.ipynb` | 🔜 Coming soon | Exploratory analysis and visualizations |

---

## 01_sleep_concat.ipynb

Loads all 9 raw sleep JSON files and combines them into a single table of 800 nightly records.

The only transformation applied at this stage is flattening Garmin's nested `sleepScores` sub-object into individual columns. Everything else — the raw field names, original units, empty rows, and all columns — is preserved exactly as exported. All cleaning decisions are deferred to the next notebook.

**Output:** `sleep_concat.csv` — 800 rows, 31 columns

---

## Stack

- Python 3
- pandas
- Jupyter Notebook

---

## Status

Active — notebooks 2 and 3 in progress.
