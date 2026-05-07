# ST422 Team 1 — Brief 8: Road Safety Analysis

Analysis of DfT STATS19 road casualty data for ST422 Statistical Consulting.
Brief 8: identifying road safety hotspots, contributory factors, and evaluating whether recent policy changes are working.

---

## Quick Start — Reproduce the Full Analysis

### Step 1: Install dependencies (once only)

From the repo root:

```bash
pip install -r requirements.txt
```

### Step 2: Download raw data

Place the following files into `Final_Workflow/Data_Prep/Data/`. Download from:
https://www.data.gov.uk/dataset/cb7ae6f0-4be6-4935-9277-47e5ce24a11f/road-safety-data

```
dft-road-casualty-statistics-collision-1979-latest-published-year.csv
dft-road-casualty-statistics-casualty-1979-latest-published-year.csv
dft-road-casualty-statistics-vehicle-1979-latest-published-year.csv
dft-road-casualty-statistics-collision-provisional-2025.csv
dft-road-casualty-statistics-casualty-provisional-2025.csv
dft-road-casualty-statistics-vehicle-provisional-2025.csv
```

Two lookup files are already in the repo and do not need downloading:
- `local-authority-ons-district-names.csv`
- `ons_la_population_2024.csv`

### Step 3: Run the data preparation pipeline

```
Final_Workflow/Data_Prep/data_cleaning.ipynb
```

Open in Jupyter, restart kernel, run all cells. Produces four cleaned CSVs in `Final_Workflow/Data_Prep/Cleaned/`.

### Step 4: Run the analysis pipeline

```
Final_Workflow/Data_Analysis/data_analysis.ipynb
```

Open in Jupyter, restart kernel, run all cells. Produces all figures, tables, traceability, and findings page in `Final_Workflow/Data_Analysis/Outputs/`.

Each notebook has its own `README.md` with full details on configurable parameters and output inventory.

---

## Repo Structure

```
ST422_Team1_Project/
├── Final_Workflow/              ← MAIN ANALYSIS — start here
│   ├── Data_Prep/               ← Step 1: data cleaning pipeline
│   │   ├── data_cleaning.ipynb
│   │   ├── README.md
│   │   ├── Data/                ← place raw DfT CSVs here (see above)
│   │   └── Cleaned/             ← generated on run, not committed
│   └── Data_Analysis/           ← Step 2: full analysis pipeline
│       ├── data_analysis.ipynb
│       ├── README.md
│       └── Outputs/             ← generated on run, not committed
├── Quality_Assurance/           ← QA evidence for data pipeline
│   ├── QA_Data_Load.ipynb       ← 32 automated checks (31/32 passed)
│   └── README.md
├── Group_Contact/               ← team coordination evidence (B6)
│   ├── Action_Log/              ← full task log with owners and evidence pointers
│   └── Meeting_Minutes/         ← meeting minutes with agreed actions
├── Management_Plan/             ← workplan, risk register, QA plan (B7)
├── Client_Resources/            ← client brief, weekly updates, reference material
├── Draft_Work/                  ← draft notebooks from Weeks 8–10 (audit trail)
├── Archive/                     ← superseded data prep notebooks
├── Akeel_Work/                  ← Akeel Shah's individual submission folder
├── Caleb_Work/                  ← Caleb Sithole's individual submission folder
├── requirements.txt             ← all Python dependencies (install once from root)
└── README.md                    ← this file
```

---

## Verifying the Data Pipeline (Optional)

After running `data_cleaning.ipynb`, you can verify the outputs by running:

```
Quality_Assurance/QA_Data_Load.ipynb
```

This runs 32 automated checks on the four cleaned CSVs. 31/32 are expected to pass. The one known fail (`collisions_clean.csv` has 2,771 duplicate rows from the raw DfT source) does not affect `cas_full.csv` which is the sole input to the analysis pipeline.

---

## Team Working Evidence

All project management evidence is in `Group_Contact/`:

- `Action_Log/` — every task logged with owner, deadline, status, and evidence pointer
- `Meeting_Minutes/` — minutes from all 6 team meetings

The management plan (risk register, QA plan, milestones) is in `Management_Plan/`.

---

## Individual Submission Folders

- `Akeel_Work/` — Akeel Shah's individual working notebooks and submission artefacts
- `Caleb_Work/` — Caleb Sithole's individual working notebooks and submission artefacts

These are not part of the reproducible pipeline. The final analysis is in `Final_Workflow/` only.

---

## Dependencies

All dependencies for the full pipeline are in `requirements.txt` at the repo root. Install once with:

```bash
pip install -r requirements.txt
```

```
pandas
numpy
matplotlib
scipy
statsmodels
geopandas
```
