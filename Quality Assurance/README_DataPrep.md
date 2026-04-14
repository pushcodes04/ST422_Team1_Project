# ST422 Brief 8 — Data Preparation: README

**Author:** [Your Name] | **Student ID:** u2211111  
**Notebook:** `ST422_DataPrep.ipynb`  
**Date run:** April 2026  

---

## What this notebook does

`ST422_DataPrep.ipynb` loads the six raw DfT STATS19 CSV files, cleans and joins them into a single analysis-ready dataset (`cas_full.csv`), and saves four cleaned output files to the `Cleaned` directory. All subsequent analysis notebooks depend on the outputs of this notebook.

---

## Changes made before running

The original notebook was written by a teammate with hardcoded local paths pointing to their machine:

```python
# Original (teammate's machine — will not run on any other computer)
DATA_DIR   = '/Users/zahidahmed/Documents/Stats/ST422/Data'
OUTPUT_DIR = '/Users/zahidahmed/Documents/Stats/ST422/Cleaned'
```

These were updated to point to the correct directories on this machine:

```python
# Updated (this machine)
DATA_DIR   = 'C:/Users/u2211111/ST422/Data'
OUTPUT_DIR = 'C:/Users/u2211111/ST422/Cleaned'
```

No other changes were made to the notebook. All logic, merges, and cleaning steps are identical to the original.

---

## Data files required

The following six raw CSV files must be present in `DATA_DIR` before running:

| File | Description |
|------|-------------|
| `dft-road-casualty-statistics-collision-1979-latest-published-year.csv` | Historical collisions (1979–2024) |
| `dft-road-casualty-statistics-casualty-1979-latest-published-year.csv` | Historical casualties (1979–2024) |
| `dft-road-casualty-statistics-vehicle-1979-latest-published-year.csv` | Historical vehicles (1979–2024) |
| `dft-road-casualty-statistics-collision-provisional-2025.csv` | Provisional 2025 collisions |
| `dft-road-casualty-statistics-casualty-provisional-2025.csv` | Provisional 2025 casualties |
| `dft-road-casualty-statistics-vehicle-provisional-2025.csv` | Provisional 2025 vehicles |
| `local-authority-ons-district-names.csv` | LA name lookup file |

All files downloaded from:  
https://www.gov.uk/government/statistical-data-sets/road-safety-open-data

---

## How to run

1. Download all data files listed above into your `Data` folder
2. Open `ST422_DataPrep.ipynb` in Jupyter
3. Update the two lines at the top of **Cell 1**:
   ```python
   DATA_DIR   = 'YOUR/PATH/TO/Data'
   OUTPUT_DIR = 'YOUR/PATH/TO/Cleaned'
   ```
4. Run all cells in order (**Kernel → Restart & Run All**)
5. Check the `Cleaned` folder for the four output files

---

## Expected outputs

After a successful run, the following four files should appear in `OUTPUT_DIR`:

| File | Description | Expected rows (approx.) |
|------|-------------|--------------------------|
| `cas_full.csv` | Main analysis file — one row per casualty, collision and vehicle context joined | ~2.5 million |
| `casualties_clean.csv` | Cleaned casualties table | ~2.5 million |
| `collisions_clean.csv` | Cleaned collisions table | ~2.0 million |
| `vehicles_clean.csv` | Cleaned vehicles table | ~3.5 million |

---

## Quality assurance checks performed

After running the notebook, the following checks were carried out to confirm the output was correct:

### 1. Output files exist
Confirmed all four CSV files were present in the `Cleaned` folder after the run completed.

### 2. Row counts checked
```python
import pandas as pd
cas_full = pd.read_csv('C:/Users/u2211111/ST422/Cleaned/cas_full.csv')
print(f'cas_full rows: {len(cas_full):,}')
print(f'cas_full cols: {cas_full.shape[1]}')
```
Output confirmed a plausible row count consistent with GB-wide STATS19 data.

### 3. Year range confirmed
```python
print(cas_full['collision_year'].min(), cas_full['collision_year'].max())
```
Confirmed data runs from the expected start year through to 2025 (provisional).

### 4. No duplicate rows
```python
print('Duplicates:', cas_full.duplicated().sum())
```
Result: 0 duplicates confirmed.

### 5. Key columns present and not fully missing
```python
key_cols = ['collision_year', 'casualty_severity', 
            'local_authority_ons_district', 'road_user', 'speed_limit']
for c in key_cols:
    pct = cas_full[c].isna().mean() * 100
    print(f'{c}: {pct:.1f}% missing')
```
All key columns present. Known missingness in `road_user` and deprivation fields is consistent with STATS19 documentation.

### 6. Severity codes valid
```python
print(cas_full['casualty_severity'].value_counts().sort_index())
```
Only codes 1 (Fatal), 2 (Serious), and 3 (Slight) present — no invalid codes.

### 7. Rerun test
The notebook was run a second time from **Kernel → Restart & Run All** to confirm full reproducibility. All four output files were regenerated and row counts matched the first run exactly.

---

## Known issues and caveats

- `DATA_DIR` and `OUTPUT_DIR` must be updated manually by each analyst — this is the only required edit before running.
- The raw data files are large (collision history file ~1.4GB). Allow 10–15 minutes for the full pipeline to run.
- The `local-authority-ons-district-names.csv` lookup file was shared by the team and is not available from the standard DfT download page. It is included in the repo under `data/lookups/`.

---

## Dependencies

```
pandas
numpy
jupyter
```

Install with:
```
pip install pandas numpy jupyter
```

---

*End of README*
