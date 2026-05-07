# ST422 Brief 8 — Data Analysis Pipeline

This notebook (`data_analysis.ipynb`) reads the cleaned STATS19 data produced by `Data_Prep/data_cleaning.ipynb` and produces all figures, tables, a traceability table, run metadata, and a self-contained findings page.

**Run order:** `Data_Prep/data_cleaning.ipynb` first, then this notebook.

---

## Folder structure

```
Final_Workflow/
├── Data_Prep/
│   ├── data_cleaning.ipynb     ← run this first
│   └── Cleaned/                ← outputs consumed by this notebook
│       ├── collisions_clean.csv
│       ├── casualties_clean.csv
│       ├── vehicles_clean.csv
│       └── cas_full.csv
└── Data_Analysis/
    ├── data_analysis.ipynb     ← this notebook
    ├── README.md               ← this file
    └── Outputs/                ← generated on run
        ├── figures/            ← fig01–fig17 PNGs
        ├── tables/             ← tab_*.csv files
        ├── findings.html       ← self-contained findings page
        ├── traceability.csv    ← maps every claim to an output file
        └── run_metadata.json   ← records windows, parameters, timestamp
```

> **Note:** The `Outputs/` folder is generated when the notebook runs and is not committed to the repo.

---

## Setup

### 1. Install dependencies

In your terminal, navigate to `Final_Workflow/Data_Analysis/` and run:

```bash
pip install -r requirements.txt
```

### 2. Prerequisites

`Data_Prep/data_cleaning.ipynb` must have been run first and the four cleaned CSVs must exist in `Data_Prep/Cleaned/`. The notebook will error at load if they are missing.

---

## How to run

1. Open Jupyter Notebook and navigate to `Final_Workflow/Data_Analysis/`
2. Open `data_analysis.ipynb`
3. **Restart the kernel** (Kernel → Restart & Clear Output) to ensure a clean state
4. Run all cells top to bottom (Cell → Run All)

The notebook prints progress at each section. A successful run ends with:

```
Run complete.
Outputs written to: .../Final_Workflow/Data_Analysis/Outputs/
```

---

## Configurable parameters

All parameters are set in **§0 Config** (the first code cell). No other cell needs editing.

| Parameter | Default | What it does |
|---|---|---|
| `BASE_WINDOW_ANCHOR` | `(2015, 2017)` | Pre-COVID base comparison window |
| `RECENT_WINDOW_ANCHOR` | `(2022, 2024)` | Recent comparison window |
| `RECENT_N` | `3` | Window size if anchors are set to `None` |
| `MIN_KSI_BASE` | `30` | Minimum mean KSI for LA to be included in OLS trend |
| `MIN_YEARS` | `6` | Minimum years of data required per LA for OLS |
| `LOW_R2` | `0.5` | R² threshold below which trend is flagged as non-linear |
| `TOP_N_WORSENING` | `5` | Top N worsening LAs shown |
| `TOP_N_IMPROVING` | `5` | Top N improving LAs shown |
| `HOTSPOT_N` | `3` | Number of most recent confirmed years used for hotspot analysis |
| `HOTSPOT_TOP_N` | `15` | Top N LAs in hotspot rankings |
| `MIN_COLLISIONS` | `500` | Minimum collisions for LA to appear in rate-based ranking |
| `MATERIAL_CHANGE_PCT` | `15` | % KSI change threshold for material change flag |
| `N_BOOTSTRAP` | `1000` | Bootstrap iterations for CI robustness check |
| `COVID_YEARS` | `[2020, 2021]` | Years excluded from trend fitting |

**Window anchoring:** When the cleaned data extends past the anchor's end year, both windows shift forward by the same offset to preserve the COVID gap. Set anchors to `None` for fully auto-derived windows.

---

## Analysis sections

| Section | Description | Outputs |
|---|---|---|
| §0 | Config and path setup | — |
| §1 | Load cleaned data, schema assertion, window resolution, completeness filter | — |
| §2 | Data quality — missingness and IBRS adoption | Fig 1, tab_null_rates_by_year.csv, tab_ibrs_adoption.csv |
| §3 | KSI trends — seasonality, national trend, raw vs IBRS-adjusted | Figs 2–4, tab_ksi_trend_national.csv, tab_ksi_raw_vs_adjusted.csv |
| §4 | Road user severity profile | Fig 5, tab_road_user_severity.csv |
| §5 | Geographic hotspots — count, rate, choropleth, rank comparison, road user | Figs 6, 6b, 6c, 6d, tab_la_hotspots_*.csv |
| §6 | Contributory factors — urban/rural, speed/road type, day/hour, junction | Figs 7–9, tab_ksi_by_*.csv |
| §7 | LA trend analysis — OLS per LA, worsening/improving, factor breakdown | Figs 10–11, tab_la_ols_results.csv, tab_la_worsening.csv, tab_la_improving.csv |
| §8 | Robustness checks | Fig 12, tab_la_robustness_stability.csv |
| §9 | Diagnostics and modelling — OLS diagnostics, bootstrap, stepwise GLM, AIC/BIC | Figs 13–14, tab_residual_diagnostics.csv, tab_bootstrap_ci_comparison.csv |
| §10 | Policy evaluation | — |
| §11 | Material change threshold | Fig 17, tab_material_change_flagged.csv |
| §12 | Traceability and run metadata | traceability.csv, run_metadata.json |
| §13 | Findings page | findings.html |

---

## Output files

| File | Description |
|---|---|
| `Outputs/figures/fig01–fig17_*.png` | All analysis figures |
| `Outputs/tables/tab_*.csv` | All key tables |
| `Outputs/findings.html` | Self-contained HTML findings page — every LA flagged by any criterion (C1–C7) sorted by evidence strength |
| `Outputs/traceability.csv` | Maps every client-facing claim to its output file and notebook section |
| `Outputs/run_metadata.json` | Records analysis windows, parameter values, and run timestamp |

---

## Reproducibility notes

- Always restart the kernel before a full re-run to guarantee a clean state
- All paths are relative — no editing required on any machine
- The year axis, LA list, and ranked candidates are all derived from the data at runtime — nothing is hardcoded except the configurable constants in §0
- The choropleth (Fig 6b) fetches ONS LAD boundary GeoJSON from a public ArcGIS endpoint — requires an internet connection
- Population data (`ons_la_population_2024.csv`) is optional — if present in `Data_Prep/Data/`, it is used for the three-way exposure robustness check; if absent, that check is skipped gracefully

---

## Dependencies

```
pandas
numpy
matplotlib
scipy
statsmodels
geopandas
```

Install with:

```bash
pip install -r requirements.txt
```
