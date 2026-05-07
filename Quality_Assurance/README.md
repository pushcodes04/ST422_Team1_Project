# ST422 Brief 8 — Data Preparation: README

**Author:** Akeel Shah | **Student ID:** u2211111  
**Notebook:** `ST422_DataPrep.ipynb`  
**Date run:** April 2026  

---

## What this notebook does

`ST422_DataPrep.ipynb` loads the six raw DfT STATS19 CSV files, cleans and joins them into a single analysis-ready dataset (`cas_full.csv`), and saves four cleaned output files to the `Cleaned` directory. All subsequent analysis notebooks depend on the outputs of this notebook.

---

## Changes made before running

The original notebook was written with hardcoded local paths. These have been updated to use relative paths via `os.getcwd()` so the notebook runs on any machine without editing:

```python
# Updated — no path editing required
import os
DATA_DIR   = os.path.join(os.getcwd(), 'Data')
OUTPUT_DIR = os.path.join(os.getcwd(), 'Cleaned')
```

No other changes were made to the notebook. All logic, merges, and cleaning steps are identical to the original.

---

## Data files required

The following files must be present in the `Data/` folder before running:

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

1. Download all data files listed above into the `Data/` folder
2. Install dependencies: `pip install -r requirements.txt`
3. Open `ST422_DataPrep.ipynb` in Jupyter
4. No path editing required — paths are set automatically relative to the project root using `os.getcwd()`
5. Run all cells in order (**Kernel → Restart & Run All**)
6. Check the `Cleaned/` folder for the four output files

---

## Expected outputs

After a successful run, the following four files should appear in `Cleaned/`:

| File | Description | Expected rows (approx.) |
|------|-------------|--------------------------|
| `cas_full.csv` | Main analysis file — one row per casualty, collision and vehicle context joined | ~2.5 million |
| `casualties_clean.csv` | Cleaned casualties table | ~2.5 million |
| `collisions_clean.csv` | Cleaned collisions table | ~2.0 million |
| `vehicles_clean.csv` | Cleaned vehicles table | ~3.5 million |

---

## Quality assurance checks performed

After running the notebook, the following checks were carried out via `QA_DataLoad.ipynb` to confirm the output was correct. 31 of 32 checks passed.

### 1. Output files exist
Confirmed all four CSV files were present in the `Cleaned/` folder after the run completed.

### 2. Row counts checked
Output confirmed a plausible row count consistent with GB-wide STATS19 data. `cas_full` row count matches `casualties_clean` exactly — confirming the join did not create duplicates.

### 3. Year range confirmed
Data runs from 2014 through to 2025 (provisional Jan–Jun). No unexpected year gaps.

### 4. Duplicate rows
`cas_full.csv` — 0 duplicates confirmed. `collisions_clean.csv` — 2,771 duplicate rows found. This is a known issue in the raw DfT STATS19 collision file and does not affect `cas_full.csv`. All analysis notebooks use `cas_full` directly and are unaffected.

### 5. Key columns present and not fully missing
All key columns present. Known missingness in deprivation fields is consistent with STATS19 documentation.

### 6. Severity codes valid
Only codes 1 (Fatal), 2 (Serious), and 3 (Slight) present — no invalid codes.

### 7. Join integrity confirmed
All expected collision-level columns (`speed_limit`, `road_type`, `latitude`, `longitude`, `urban_or_rural_area`) present in `cas_full` — join completed successfully.

### 8. Geographic coverage
393 unique local authorities present. All valid coordinates fall within the GB bounding box (49.5–61.0N, -8.0–2.0E).

### 9. Rerun test
The notebook was run a second time from **Kernel → Restart & Run All** to confirm full reproducibility. All four output files were regenerated and row counts matched the first run exactly.

---

## Known issues and caveats

- The raw data files are large (collision history file ~1.4GB). Allow 10–15 minutes for the full pipeline to run.
- The `local-authority-ons-district-names.csv` lookup file is included in the repo under `Data/`.
- `collisions_clean.csv` contains 2,771 duplicate rows originating from the raw DfT source file. This does not affect `cas_full.csv` which has zero duplicates and is the sole input to all analysis notebooks.

---

## Dependencies

All dependencies are listed in `requirements.txt`. Install with:

```bash
pip install -r requirements.txt
```

Core packages: `pandas`, `numpy`, `matplotlib`, `scipy`, `geopandas`

