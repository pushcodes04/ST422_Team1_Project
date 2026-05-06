# ST422 Brief 8 — Data Preparation Pipeline

This notebook (`ST422_DataPrep.ipynb`) loads the raw STATS19 DfT CSVs, filters to a configurable year window, appends the provisional year, cleans coded fields, applies label maps, builds a combined casualties + vehicles + collision-context table, and writes four CSVs to `Cleaned/`.

---

## Folder structure

Before running, ensure your project is organised as follows:

```
ST422/
├── ST422_DataPrep.ipynb        ← this notebook
├── requirements.txt            ← Python dependencies
├── README.md                   ← this file
├── Data/                       ← place all raw DfT CSVs here (see below)
└── Cleaned/                    ← output CSVs written here automatically
```

> **Note:** Do not commit the `Data/` or `Cleaned/` folders to Git — the raw and cleaned CSVs are too large. Add them to `.gitignore`.

---

## Setup

### 1. Install dependencies

In your terminal, navigate to the project root and run:

```bash
pip install -r requirements.txt
```

### 2. Download the raw data files

Place the following files inside the `Data/` folder. These are the standard DfT STATS19 filenames — do not rename them.

```
dft-road-casualty-statistics-collision-1979-latest-published-year.csv
dft-road-casualty-statistics-casualty-1979-latest-published-year.csv
dft-road-casualty-statistics-vehicle-1979-latest-published-year.csv
dft-road-casualty-statistics-collision-provisional-2025.csv
dft-road-casualty-statistics-casualty-provisional-2025.csv
dft-road-casualty-statistics-vehicle-provisional-2025.csv
local-authority-ons-district-names.csv
```

Download the historical and provisional files from:
https://www.data.gov.uk/dataset/cb7ae6f0-4be6-4935-9277-47e5ce24a11f/road-safety-data

The `local-authority-ons-district-names.csv` lookup file is already included in the repo under `Data/`.

### 3. Paths

No path editing is required. The notebook automatically detects its location using `os.getcwd()` and builds all paths relative to the project root. As long as your folder structure matches the layout above, it will work on any machine without any changes.

---

## How to run

1. Open Jupyter Notebook and navigate to the project root folder
2. Open `ST422_DataPrep.ipynb`
3. **Restart the kernel** (Kernel → Restart & Clear Output) to ensure a clean state
4. Run all cells top to bottom (Cell → Run All)

The notebook will print progress at each stage. A successful run ends with:

```
Written to: .../Cleaned
  collisions_clean.csv — x,xxx,xxx rows
  casualties_clean.csv — x,xxx,xxx rows
  vehicles_clean.csv   — x,xxx,xxx rows
  cas_full.csv         — x,xxx,xxx rows
```

---

## Changing the year window

The year filter is controlled by four variables in the **Config** cell (the first code cell):

| Variable | Default | What it does |
|---|---|---|
| `YEAR_START` | `2014` | First year included from the historical file |
| `YEAR_END` | `2024` | Last confirmed published year |
| `INCLUDE_PROVISIONAL` | `True` | Whether to append the provisional year file |
| `PROVISIONAL_YEAR` | `2025` | Which provisional file to load |

**Example — extend back to 2013:**
```python
YEAR_START = 2013
```

**Example — use confirmed years only (no provisional):**
```python
INCLUDE_PROVISIONAL = False
```

**Example — update when 2025 becomes confirmed and 2026 provisional is released:**
```python
YEAR_END         = 2025
PROVISIONAL_YEAR = 2026
```

---

## Output files

Running the notebook top to bottom creates four CSVs in the `Cleaned/` folder:

| File | Description |
|---|---|
| `collisions_clean.csv` | One row per collision |
| `casualties_clean.csv` | One row per casualty |
| `vehicles_clean.csv` | One row per vehicle |
| `cas_full.csv` | One row per casualty with vehicle and collision context joined in |

`cas_full.csv` is the main analysis file used by downstream notebooks. It is built by joining casualties to vehicles on the composite key `collision_index` + `vehicle_reference`, then merging a selected set of collision-level context columns. Pedestrians and other road users with no associated vehicle record are retained with `NaN` vehicle fields.

---

## Reproducibility notes

- Always restart the kernel before a full re-run to guarantee a clean state
- The `collision_index` column is loaded as string (`object`) dtype — any comparisons must use string literals, e.g. `'2015460259328'` not `2015460259328`
- The correct year column is `collision_year` — not `accident_year`
- Provisional data is tagged with `provisional = True` throughout. Filter with `col[~col['provisional']]` if you want confirmed years only in downstream analysis
- COVID years (2020 and 2021) are retained in the cleaned output but should be handled carefully in trend analysis — consider excluding or flagging them explicitly in analysis scripts

---

## Dependencies

All dependencies are listed in `requirements.txt`. Install with:

```bash
pip install -r requirements.txt
```

Core packages used:

```
pandas
numpy
```
