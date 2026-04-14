# Action Log

**Module:** ST422 Statistical Consulting  
**Brief:** Brief 8 — Road Safety Analysis  
**Team:** Team 1  
**Last Updated:** April 2026

This is the single master record of all actions across the entire project. Every action must have a named owner, a deadline, a status, and a verifiable evidence reference (PR number, commit hash, issue ID, or file path). This document is updated continuously as actions are opened, progressed, and closed.

---

## Status Key

| Status      | Meaning                                             |
| ----------- | --------------------------------------------------- |
| Open        | Not yet started                                     |
| In Progress | Work underway                                       |
| Complete    | Delivered and verified                              |
| Blocked     | Cannot proceed — blocker recorded in Blockers table |

---

## Master Actions Table

| ID   | Meeting | Action                                                                      | Owner | Deadline   | Status      | Evidence (PR / Commit / Issue / File) | Outcome                    |
| ---- | ------- | --------------------------------------------------------------------------- | ----- | ---------- | ----------- | ------------------------------------- | -------------------------- |
| A001 | 001     | Finalise and upload Client Brief 8 selection in SELECTION.md                | AS    | 2026-02-22 | In Progress | SELECTION.md                          | [To be completed on close] |
| A002 | 001     | Review and approve Management Plan against audit structure                  | ZA    | 2026-02-22 | Closed      | management_plan.md                    | Management plan reviewed and approved against audit structure. |
| A003 | 001     | Establish repository structure, README, data allocation and tracking system | PA    | 2026-02-22 | In Progress | Repository link + README.md           | [To be completed on close] |
| A004 | 001     | Prepare and upload draft meeting minutes with updated action log            | CS    | 2026-02-22 | In Progress | minutes/2026-02-21.md                 | [To be completed on close] |
| A005 | 001     | Upload client questions to clarify scope and analytical direction           | YS    | 2026-02-22 | In Progress | client_questions.md                   | [To be completed on close] |
| A006 | 002     | Set up GitHub collaboration workflow (access, branches, PR template)        | YD    | 2026-03-05 | In Progress | Issue # + CONTRIBUTING.md / README.md | [To be completed on close] |
| A007 | 002     | Confirm collisions date column name + format (historic + 2025 provisional)  | PA    | 2026-03-05 | In Progress | Issue # + notebook cell / script note | [To be completed on close] |
| A008 | 002     | Build merge pipeline: Collisions + Vehicles + Casualties (1979–latest)      | CS    | 2026-03-05 | In Progress | PR # + notebooks/merge_pipeline.ipynb | [To be completed on close] |
| A009 | 002     | Clean merged data: drop <2015 rows, remove unnecessary columns              | ZA    | 2026-03-05 | Closed      | Data_Prep/ST422_DataPrep              | Data preparation pipeline built and uploaded to GitHub. Four cleaned CSVs output to Cleaned Data/. |
| A010 | 002     | Build Week 8 road safety analysis notebook covering KSI trends, road user profiles, hotspot analysis, and contributory factors | ZA | 2026-03-02 | Closed | Draft_work/Week8_Road_Safety.ipynb | Week 8 analysis notebook completed and exported to HTML. Covers 2019–2024 window. |
| A011 | 002     | Run Python EDA on cleaned 2015+ dataset                                     | PA    | 2026-03-05 | In Progress | Issue # + notebook cell / script note | [To be completed on close] |
| A012 | 002     | Add data dictionary + "columns to keep" list                                | PA    | 2026-03-05 | In Progress | PR # + docs/data_dictionary.md        | [To be completed on close] |
| A013 | 002     | Commit GLM last-5-years analysis artefact + short interpretation note       | AS    | 2026-03-05 | In Progress | Issue # + notebook cell / script note | [To be completed on close] |
| A014 | 003     | Combine STATS19 collisions, vehicles, and casualties datasets into one dataset | ZA | 2026-03-13 | Closed | Data_Prep/ST422_DataPrep | Four cleaned CSVs produced: collisions_clean.csv, casualties_clean.csv, vehicles_clean.csv, and cas_full.csv covering 2014–2025. |
| A015 | 003     | Investigate issue preventing export of merged dataset to CSV                | CS    | 2026-03-13 | Open        | Issue # + merge script                | [To be completed on close] |
| A016 | 003     | Validate merged dataset and confirm readiness for cleaning pipeline         | PA    | 2026-03-14 | Open        | clean_joined.csv + validation log     | [To be completed on close] |
| A017 | 003     | Build Week 9 road safety analysis notebook covering 2014–2024 with IBRS-adjusted KSI, severity profiles, geographic hotspot analysis, contributory factors, and robustness checks | ZA | 2026-03-09 | Closed | Draft_work/Week9_Road_Safety.ipynb | Week 9 analysis notebook completed and exported to HTML. Uploaded to Client Resources. |
| A018 | 003     | Develop IBRS-adjusted KSI series and robustness check comparing raw vs adjusted trend direction | ZA | 2026-03-09 | Closed | Draft_work/Week9_Road_Safety.ipynb | Adjusted series shows -284.5 KSI/yr vs raw +182.6 KSI/yr. IBRS adoption identified as primary driver of apparent raw KSI rise. |
| A019 | 003     | Build 2025 provisional data seasonality check and annualised KSI estimate   | ZA    | 2026-03-09 | Closed      | Draft_work/Week9_Road_Safety.ipynb    | H1/H2 seasonality factor computed excluding COVID years. 2025 annualised estimate produced with caveat. |
| A020 | 003     | Build hotspot sensitivity analysis comparing count-based vs rate-based LA rankings | ZA | 2026-03-09 | Closed | Draft_work/Week9_Road_Safety.ipynb | Zero overlap between top 15 count and rate authorities confirmed. Client implication documented. |
| A021 | 003     | Fix KSI % above 100% bug in local authority chart                           | ZA    | 2026-03-09 | Closed      | Draft_work/Week9_Road_Safety.ipynb    | Threshold raised to 500 collisions. Duplicate ONS diagnostic added. |
| A022 | 003     | Rewrite Week 10 client update to decision-led prose with evidence anchoring | ZA    | 2026-03-13 | Closed      | Client_Resources/Week10_Client_Update.pdf | Revised and finalised. Submitted as PDF to client space. |
| A023 | 004     | Identify local authorities that have shown improvement in KSI outcomes and analyse potential contributing factors | ZA | 2026-03-16 | Closed | Draft_work/Week10_LA_Trends.ipynb | LA trend analysis completed using OLS regression. Top 5 improving and worsening authorities identified with factor breakdowns. |
| A024 | 004     | Build Week 10 improving LA analysis notebook with 3-year average comparison and robustness checks | ZA | 2026-03-16 | Closed | Draft_work/Week10_Improving_Analysis.ipynb | Top 5 improving LAs identified with completeness filter and robustness checks across three weighting schemes. |
| A025 | 004     | Build Week 10 worsening LA analysis notebook with 3-year average comparison and robustness checks | ZA | 2026-03-16 | Closed | Draft_work/Week10_Worsening_Analysis.ipynb | Top 5 worsening LAs identified with completeness filter and robustness checks across three weighting schemes. |
| A026 | 004     | Add boundary reorganisation completeness filter to data prep pipeline and update README | ZA | 2026-03-16 | Closed | Data_Prep/ST422_DataPrep.ipynb | Filter removes 53 LAs with incomplete data across analysis windows. README updated with reproducibility notes. |
| A027 | 004     | Build Week 10 road safety report notebook in client-facing format           | ZA    | 2026-03-16 | Closed      | Draft_work/Week10_Road_Safety.ipynb   | Week 10 report notebook completed with findings and recommendations in plain English. |
| A028 | 004     | Investigate policy interventions available to local authorities (e.g., speed management, traffic calming, enforcement) | AS | 2026-03-18 | Open | docs/policy_review.md | [To be completed on close] |
| A029 | 004     | Analyse factors affecting worst-performing local authorities in terms of KSI collisions | CS | 2026-03-18 | Open | notebooks/LA_factor_analysis.ipynb | [To be completed on close] |
| A030 | 004     | Conduct geographic hotspot analysis for high-KSI locations                  | CS    | 2026-03-18 | Open        | notebooks/geographic_hotspots.ipynb   | [To be completed on close] |
| A031 | 004     | Perform hypothesis testing comparing Raw KSI trends vs IBRS-adjusted KSI trends using DfT guidance | CS | 2026-03-18 | Closed | notebooks/ksi_adjustment_analysis.ipynb | Not required |
| A032 | 005     | Reproduce DataPrep notebook on local machine — update hardcoded paths to local directory and verify all four output CSVs generated correctly | AS | 2026-04-14 | Closed | Quality_Assurance/README_DataPrep.md | DataPrep notebook run successfully after updating DATA_DIR and OUTPUT_DIR to C:/Users/u2211111/ST422. All four output files confirmed present: cas_full.csv (682.2 MB), casualties_clean.csv (199.7 MB), collisions_clean.csv (409.7 MB), vehicles_clean.csv (297.6 MB). |
| A033 | 005     | Write and run QA notebook to verify DataPrep outputs are correct, complete, and ready for analysis | AS | 2026-04-14 | Closed | Quality_Assurance/QA_DataLoad.ipynb | QA notebook run. 31 of 32 checks passed. One known issue: collisions_clean.csv contains 2,771 duplicate rows — confirmed as a known STATS19 raw data issue, does not affect cas_full.csv which passed all checks. Data confirmed ready for analysis. |
| A034 | 005     | Create Quality Assurance folder in repo and upload QA evidence files        | AS    | 2026-04-14 | Closed      | Quality_Assurance/                    | Quality Assurance folder created in repo. QA_DataLoad.ipynb and README_DataPrep.md uploaded. README.md added to repo root for visibility. |
| A035 | 005     | Build supplementary analysis notebook covering analyses identified as missing from Weeks 8–10: time patterns, road user priority ranking, fatalities by LA, geographic choropleth map, material change threshold, 20mph policy evaluation, and top 3 LA prioritisation | AS | 2026-04-14 | Closed | Draft_work/Week11_Missing_Analysis.ipynb | Notebook built covering all 7 missing analyses with 12 figures. Figures saved as PNGs to outputs/figures/. Full references included. |

---

## Blockers

| Action ID | Blocker Description | Raised By | Resolution | Resolved Date |
| --------- | ------------------- | --------- | ---------- | ------------- |
| A015 | Unable to export merged dataset to CSV after combining STATS19 tables | CS | Investigate export method and test alternative write approaches | [To be completed] |

---

## Handover and Dependency Log

| ID   | Output                  | Produced By         | Received By         | Dependency Description                                 | Handover Date     | Confirmed By      | Evidence (Commit / File) |
| ---- | ----------------------- | ------------------- | ------------------- | ------------------------------------------------------ | ----------------- | ----------------- | ------------------------ |
| H001 | Clean STATS19 dataset   | ZA (Data Steward)   | PA (Analysis Lead)  | Analysis cannot begin until data freeze v1 is complete | 2026-03-13        | [To be completed] | Data_Prep/ST422_DataPrep.ipynb |
| H002 | Core figures and tables | PA (Analysis Lead)  | CS (Reporting Lead) | Report drafting cannot begin until figures are locked  | [To be completed] | [To be completed] | [To be completed]        |
| H003 | Full draft report v1    | CS (Reporting Lead) | AS (QA Lead)        | QA review requires a stable draft                      | [To be completed] | [To be completed] | [To be completed]        |
| H004 | QA_DataLoad.ipynb + README_DataPrep.md | AS (QA Lead) | All team members | QA sign-off confirms data is ready for analysis. All analysis notebooks must use cas_full.csv from Cleaned/ directory. | 2026-04-14 | AS | Quality_Assurance/QA_DataLoad.ipynb |

---

## Status Summary

| Status      | Count |
| ----------- | ----- |
| Open        | 5     |
| In Progress | 7     |
| Closed      | 23    |
| Blocked     | 0     |
| **Total**   | **35** |
