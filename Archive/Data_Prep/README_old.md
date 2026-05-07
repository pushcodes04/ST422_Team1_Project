# ST422 Brief 8 — Data Preparation Pipeline

This notebook (`ST422_DataPrep.ipynb`) loads the raw STATS19 DfT CSVs, filters to a configurable year window, appends the provisional year, cleans coded fields, applies label maps, builds a combined casualties + vehicles + collision-context table, and writes four CSVs to `Cleaned Data/`.

---

## Setup

### 1. Data files

The notebook expects the following files in your data directory. These are the standard DfT STATS19 download filenames — do not rename them.

```
dft-road-casualty-statistics-collision-1979-latest-published-year.csv
dft-road-casualty-statistics-casualty-1979-latest-published-year.csv
dft-road-casualty-statistics-vehicle-1979-latest-published-year.csv
dft-road-casualty-statistics-collision-provisional-2025.csv
dft-road-casualty-statistics-casualty-provisional-2025.csv
dft-road-casualty-statistics-vehicle-provisional-2025.csv
local-authority-ons-district-names.csv
```

Download the historical and provisional files from: https://www.data.gov.uk/dataset/cb7ae6f0-4be6-4935-9277-47e5ce24a11f/road-safety-data

The `local-authority-ons-district-names.csv` is a manual lookup — it should already be in the repo under `Data/`.

### 2. Set your paths

Open `ST422_DataPrep.ipynb` and edit the **Config** cell at the top (the first code cell). You need to set two variables:

```python
DATA_DIR   = '/path/to/your/Data/folder'
OUTPUT_DIR = '/path/to/your/Data Prep/Cleaned Data'
```

Everything else in the notebook reads from these two variables — you do not need to change any other paths.

> **GitHub users:** Do not commit your local paths. Before pushing, reset `DATA_DIR` and `OUTPUT_DIR` to placeholder strings (e.g. `'../Data'`) or add a local config file to `.gitignore`.

---

## Changing the year window

The year filter is controlled by four variables in the **Config** cell:

| Variable | Default | What it does |
|---|---|---|
| `YEAR_START` | `2014` | First year included from the historical file |
| `YEAR_END` | `2024` | Last confirmed published year |
| `INCLUDE_PROVISIONAL` | `True` | Whether to append the provisional year file |
| `PROVISIONAL_YEAR` | `2025` | Which provisional file to load (update when DfT releases a new one) |

**Example — extend back to 2013:**
```python
YEAR_START = 2013
```

**Example — use confirmed years only (no provisional):**
```python
INCLUDE_PROVISIONAL = False
```

**Example — update for when 2025 becomes confirmed and 2026 provisional is released:**
```python
YEAR_END            = 2025
PROVISIONAL_YEAR    = 2026
```

---

## Output

Running the notebook top to bottom creates a `Cleaned Data/` folder (at `OUTPUT_DIR`) containing:

```
Cleaned Data/
  collisions_clean.csv   — one row per collision
  casualties_clean.csv   — one row per casualty
  vehicles_clean.csv     — one row per vehicle
  cas_full.csv           — one row per casualty, with vehicle and collision context joined in
```

`cas_full.csv` is built by joining casualties to vehicles on the composite key `collision_index` + `vehicle_reference`, then merging a selected set of collision-level context columns from `collisions_clean`. Use it when you need casualty, vehicle, and collision fields in a single table. Pedestrians and other road users with no associated vehicle record are retained with `NaN` vehicle fields.

These are the files used by all downstream analysis notebooks. Do not commit them to Git — add `Cleaned Data/` to `.gitignore`.

---

## Dependencies

```
pandas
numpy
```

Install with:
```bash
pip install pandas numpy
```

---

## Reproducibility notes

- Run cells top to bottom. Restart the kernel before a full re-run to guarantee a clean state.
- The `collision_index` column loads as `object` (string) dtype. Any comparisons against it must use string literals, e.g. `'2015460259328'` not `2015460259328`.
- The correct year column is `collision_year` — not `accident_year`.
- Provisional data is tagged with `provisional = True` throughout. Filter with `col[~col['provisional']]` if you want confirmed years only in downstream analysis.
- COVID years (2020, 2021) are retained in the cleaned output but should be handled carefully in trend analysis — consider excluding or flagging them explicitly.
