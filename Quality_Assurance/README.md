# ST422 Brief 8 — Quality Assurance: Data Load Check

**Author:** Akeel Shah  
**Notebook:** `QA_Data_Load.ipynb`  
**Date run:** 2026-04-14  

---

## What this notebook does

Verifies that `Final_Workflow/Data_Prep/data_cleaning.ipynb` produced correct, complete, and consistent output files. Runs 32 automated checks against the four cleaned CSVs. Does not rerun the data preparation pipeline.

---

## Where it fits in the workflow

```
Final_Workflow/Data_Prep/data_cleaning.ipynb
        ↓
Quality_Assurance/QA_Data_Load.ipynb   ← run this to verify outputs
        ↓
Final_Workflow/Data_Analysis/data_analysis.ipynb
```

---

## How to run

1. Ensure `data_cleaning.ipynb` has been run and four CSVs exist in `Final_Workflow/Data_Prep/Cleaned/`
2. Navigate to `Quality_Assurance/`
3. Open `QA_Data_Load.ipynb`
4. Restart kernel and run all cells

No path editing required — paths are set relative to `os.getcwd()`.

---

## Expected outputs

This notebook does not write any files. The four files it validates are:

| File | Expected rows |
|---|---|
| `cas_full.csv` | ~1.75 million |
| `casualties_clean.csv` | ~1.75 million |
| `collisions_clean.csv` | ~1.35 million |
| `vehicles_clean.csv` | ~2.47 million |

---

## QA checks

32 checks across 8 categories. 31 of 32 passed.

| # | Check | Result |
|---|---|---|
| 1 | All four CSVs present in `Cleaned/` | PASS |
| 2 | `cas_full` row count matches `casualties_clean` | PASS |
| 3 | Year range covers 2014–2025, no gaps | PASS |
| 4 | Zero duplicates in `cas_full`, `casualties_clean`, `vehicles_clean` | PASS |
| 4 | `collisions_clean` duplicates | FAIL — see known issues |
| 5 | All required columns present: `ksi`, `fatal`, `la_name`, `provisional` etc. | PASS |
| 6 | Severity codes 1, 2, 3 only; KSI % = 17.0% | PASS |
| 7 | All collision-level columns present in `cas_full` after join | PASS |
| 8 | 393 unique LAs; 100% coordinates within GB bounding box | PASS |

---

## Known issues

`collisions_clean.csv` contains 2,771 duplicate rows from the raw DfT STATS19 source file. This does not affect `cas_full.csv` which has zero duplicates and is the sole input to all analysis notebooks. No action required.

---

## Dependencies

See root `requirements.txt`. Install with:

```bash
pip install -r requirements.txt
```
