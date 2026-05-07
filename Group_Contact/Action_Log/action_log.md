# Action Log

**Module:** ST422 Statistical Consulting  
**Brief:** Brief 8 — Road Safety Analysis  
**Team:** Team 1  
**Last Updated:** May 2026

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
| A004 | 001     | Prepare and upload draft meeting minutes with updated action log            | CS    | 2026-02-22 | In Progress | Group_Contact/Meeting_Minutes/2026-02-21.md                 | [To be completed on close] |
| A005 | 001     | Upload client questions to clarify scope and analytical direction           | YS    | 2026-02-22 | In Progress | client_questions.md                   | [To be completed on close] |
| A006 | 002     | Set up GitHub collaboration workflow (access, branches, PR template)        | YD    | 2026-03-05 | In Progress | Issue # + CONTRIBUTING.md / README.md | [To be completed on close] |
| A007 | 002     | Confirm collisions date column name + format (historic + 2025 provisional)  | PA    | 2026-03-05 | In Progress | Issue # + notebook cell / script note | [To be completed on close] |
| A008 | 002     | Build merge pipeline: Collisions + Vehicles + Casualties (1979–latest)      | CS    | 2026-03-05 | In Progress | PR # + notebooks/merge_pipeline.ipynb | [To be completed on close] |
| A009 | 002     | Clean merged data: drop <2015 rows, remove unnecessary columns              | ZA    | 2026-03-05 | Closed      | Final_Workflow/Data_Prep/data_cleaning.ipynb | Data preparation pipeline built and uploaded to GitHub. Four cleaned CSVs output to Final_Workflow/Data_Prep/Cleaned/. |
| A010 | 002     | Build Week 8 road safety analysis notebook covering KSI trends, road user profiles, hotspot analysis, and contributory factors | ZA | 2026-03-02 | Closed | Draft_Work/Week8_Road_Safety.ipynb | Week 8 analysis notebook completed and exported to HTML. Covers 2019–2024 window. |
| A011 | 002     | Run Python EDA on cleaned 2015+ dataset                                     | PA    | 2026-03-05 | In Progress | Issue # + notebook cell / script note | [To be completed on close] |
| A012 | 002     | Add data dictionary + "columns to keep" list                                | PA    | 2026-03-05 | In Progress | PR # + docs/data_dictionary.md        | [To be completed on close] |
| A013 | 002     | Commit GLM last-5-years analysis artefact + short interpretation note       | AS    | 2026-03-05 | In Progress | Issue # + notebook cell / script note | [To be completed on close] |
| A014 | 003     | Combine STATS19 collisions, vehicles, and casualties datasets into one dataset | ZA | 2026-03-13 | Closed | Final_Workflow/Data_Prep/data_cleaning.ipynb | Four cleaned CSVs produced: collisions_clean.csv, casualties_clean.csv, vehicles_clean.csv, and cas_full.csv covering 2014–2025. |
| A015 | 003     | Investigate issue preventing export of merged dataset to CSV                | CS    | 2026-03-13 | Open        | Issue # + merge script                | [To be completed on close] |
| A016 | 003     | Validate merged dataset and confirm readiness for cleaning pipeline         | PA    | 2026-03-14 | Open        | clean_joined.csv + validation log     | [To be completed on close] |
| A017 | 003     | Build Week 9 road safety analysis notebook covering 2014–2024 with IBRS-adjusted KSI, severity profiles, geographic hotspot analysis, contributory factors, and robustness checks | ZA | 2026-03-09 | Closed | Draft_Work/Week9_Road_Safety.ipynb | Week 9 analysis notebook completed and exported to HTML. Uploaded to Client Resources. |
| A018 | 003     | Develop IBRS-adjusted KSI series and robustness check comparing raw vs adjusted trend direction | ZA | 2026-03-09 | Closed | Draft_Work/Week9_Road_Safety.ipynb | Adjusted series shows -284.5 KSI/yr vs raw +182.6 KSI/yr. IBRS adoption identified as primary driver of apparent raw KSI rise. |
| A019 | 003     | Build 2025 provisional data seasonality check and annualised KSI estimate   | ZA    | 2026-03-09 | Closed      | Draft_Work/Week9_Road_Safety.ipynb    | H1/H2 seasonality factor computed excluding COVID years. 2025 annualised estimate produced with caveat. |
| A020 | 003     | Build hotspot sensitivity analysis comparing count-based vs rate-based LA rankings | ZA | 2026-03-09 | Closed | Draft_Work/Week9_Road_Safety.ipynb | Zero overlap between top 15 count and rate authorities confirmed. Client implication documented. |
| A021 | 003     | Fix KSI % above 100% bug in local authority chart                           | ZA    | 2026-03-09 | Closed      | Draft_Work/Week9_Road_Safety.ipynb    | Threshold raised to 500 collisions. Duplicate ONS diagnostic added. |
| A022 | 003     | Rewrite Week 10 client update to decision-led prose with evidence anchoring | ZA    | 2026-03-13 | Closed      | Client_Resources/Week10_Client_Update.pdf | Revised and finalised. Submitted as PDF to client space. |
| A023 | 004     | Identify local authorities that have shown improvement in KSI outcomes and analyse potential contributing factors | ZA | 2026-03-16 | Closed | Draft_Work/Week10_LA_Trends.ipynb | LA trend analysis completed using OLS regression. Top 5 improving and worsening authorities identified with factor breakdowns. |
| A024 | 004     | Build Week 10 improving LA analysis notebook with 3-year average comparison and robustness checks | ZA | 2026-03-16 | Closed | Draft_Work/Week10_Improving_Analysis.ipynb | Top 5 improving LAs identified with completeness filter and robustness checks across three weighting schemes. |
| A025 | 004     | Build Week 10 worsening LA analysis notebook with 3-year average comparison and robustness checks | ZA | 2026-03-16 | Closed | Draft_Work/Week10_Worsening_Analysis.ipynb | Top 5 worsening LAs identified with completeness filter and robustness checks across three weighting schemes. |
| A026 | 004     | Add boundary reorganisation completeness filter to data prep pipeline and update README | ZA | 2026-03-16 | Closed | Final_Workflow/Data_Analysis/data_analysis.ipynb §1.4 (filter logic moved from prep to analysis as a methodological gate) | Filter removes 53 LAs with incomplete data across analysis windows. README updated with reproducibility notes. |
| A027 | 004     | Build Week 10 road safety report notebook in client-facing format           | ZA    | 2026-03-16 | Closed      | Draft_Work/Week10_Road_Safety.ipynb   | Week 10 report notebook completed with findings and recommendations in plain English. |
| A028 | 004     | Investigate policy interventions available to local authorities              | AS    | 2026-03-18 | Open        | docs/policy_review.md                 | [To be completed on close] |
| A029 | 004     | Analyse factors affecting worst-performing local authorities                 | CS    | 2026-03-18 | Open        | notebooks/LA_factor_analysis.ipynb    | [To be completed on close] |
| A030 | 004     | Conduct geographic hotspot analysis for high-KSI locations                  | CS    | 2026-03-18 | Open        | notebooks/geographic_hotspots.ipynb   | [To be completed on close] |
| A031 | 004     | Perform hypothesis testing comparing Raw KSI trends vs IBRS-adjusted KSI trends | CS | 2026-03-18 | Closed | notebooks/ksi_adjustment_analysis.ipynb | Not required |
| A032 | 005     | Reproduce DataPrep notebook on local machine and verify all four output CSVs | AS   | 2026-04-14 | Closed      | Quality_Assurance/README_DataPrep.md; commit `16084c6` (Update README_DataPrep.md, 14 Apr 2026) | DataPrep notebook run successfully. All four output files confirmed present and correct. |
| A033 | 005     | Write and run QA notebook to verify DataPrep outputs                        | AS    | 2026-04-14 | Closed      | Quality_Assurance/QA_DataLoad.ipynb; commit `97bb090` (Add files via upload, 14 Apr 2026) | 31 of 32 checks passed. One known issue documented. Data confirmed ready for analysis. |
| A034 | 005     | Create Quality Assurance folder and upload QA evidence files to repo        | AS    | 2026-04-14 | Closed      | Quality_Assurance/; commit `8414b2e` (Create Quality Assurance, 14 Apr 2026) | QA folder created. QA notebook and README uploaded to repo. |
| A035 | 005     | Build supplementary analysis notebook covering analyses missing from Weeks 8–10 | AS | 2026-04-14 | Closed | Draft_work/Week11_Missing_Analysis.ipynb; commit `46b3f87` (Add files via upload, 14 Apr 2026) | Notebook built covering 7 missing analyses with 12 figures saved to outputs/. |
| A036 | 006     | Fix hardcoded paths across all notebooks to use relative paths              | AS    | 2026-04-18 | Closed      | ST422_Analysis_v2.ipynb; commit `f6b4ace` (Update Action Log.md, 18 Apr 2026) | All notebooks updated to use os.getcwd(). No hardcoded paths remain. |
| A037 | 006     | Combine weekly analysis notebooks into a single reproducible pipeline       | AS    | 2026-04-18 | Closed      | ST422_Analysis_v2.ipynb; commit `2bd4d2c` (Add files via upload, 18 Apr 2026) | Combined notebook built and tested. Runs clean top to bottom. |
| A038 | 006     | Add missing analysis sections identified from template review               | AS    | 2026-04-18 | Closed      | ST422_Analysis_v2.ipynb; commit `c862baf` (Add files via upload, 18 Apr 2026) | Junction type, factor breakdowns, 20mph evaluation, and material change threshold added. |
| A039 | 006     | Add uncertainty quantification to LA trend models                           | AS    | 2026-04-18 | Closed      | ST422_Analysis_v2.ipynb; commit `c7f6f64` (Add files via upload, 18 Apr 2026) | 95% confidence intervals added to all per-LA OLS slopes. |
| A040 | 006     | Add choropleth map to hotspot analysis                                      | AS    | 2026-04-18 | Closed      | ST422_Analysis_v2.ipynb; commit `40051eb` (Add files via upload, 18 Apr 2026) | Choropleth map added using geopandas. geopandas added to requirements.txt. |
| A041 | 006     | Update repo documentation to reflect combined notebook                      | AS    | 2026-04-18 | Closed      | README.md; commit `1c79b57` (Update README.md, 14 Apr 2026) | README and DataPrep README updated. All new figures and tables listed. |
| A042 | 007     | Add AIC/BIC model comparison to analysis notebook                           | AS    | 2026-04-20 | Closed      | ST422_Analysis_v2.ipynb section 10; commit `d8a14a` (Update Action Log.md, 20 Apr 2026) | AIC/BIC comparison run for null, linear OLS, and quadratic models. Linear OLS confirmed as preferred model. |
| A043 | 007     | Add time-series decomposition to analysis notebook                          | AS    | 2026-04-20 | Closed      | ST422_Analysis_v2.ipynb section 10; commit `7dd17e8` (Add files via upload, 20 Apr 2026) | Additive STL decomposition fitted to monthly KSI series 2014–2024. Trend, seasonal, and residual components extracted. statsmodels added to requirements.txt. |
| A044 | 007     | Add MLE vs OLS comparison to justify estimation procedure                   | AS    | 2026-04-20 | Closed      | ST422_Analysis_v2.ipynb section 10; commit `e8cb49d` (Delete Final_Notebook/ST422_Analysis_v2 (1).ipynb, 20 Apr 2026) | MLE fitted via numerical optimisation. Confirmed identical point estimates to OLS for normal linear model. OLS retained on grounds of interpretability. |
| A045 | 007     | Add bootstrap confidence intervals as non-parametric uncertainty check      | AS    | 2026-04-20 | Closed      | ST422_Analysis_v2.ipynb section 10; commit `d3cd723` (Delete Final_Notebook/ST422_Analysis_v2.ipynb, 20 Apr 2026) | 1000-iteration bootstrap run for raw and adjusted KSI slopes. Bootstrap CIs match analytical OLS CIs confirming assumptions are reasonable. |
| A046 | 007     | Add threats to validity, alternatives considered, and traceability sections | AS    | 2026-04-20 | Closed      | ST422_Analysis_v2.ipynb; commit `496fb50` (Delete Final_Notebook/ST422_Analysis_v2 (2).ipynb, 22 Apr 2026) | External validity, construct validity, failure modes, and alternative approaches documented. Traceability table added mapping all client claims to output files. |
| A047 | 006     | Make analysis pipeline year-over-year reproducible: anchored windows with auto-shift fallback, schema assertion at load, no hardcoded LA names or year literals, all parameters editable from §0 config | ZA | 2026-05-06 | Closed | Final_Workflow/Data_Analysis/data_analysis.ipynb §0–§1 | Pipeline self-adapts to new STATS19 releases. Status prints make window resolution loud on every run. README documents all configurable parameters. |
| A048 | 006     | Build auto-generated findings page surfacing every LA flagged by any analytical criterion (C1–C7) with criterion definitions, sorted by evidence strength | ZA | 2026-05-06 | Closed | Final_Workflow/Data_Analysis/data_analysis.ipynb §13; Outputs/findings.html | Self-contained HTML page surfaces evidence; priority decision left to client analyst. Generalises across years without code changes. |
| A049 | 006     | Build master analysis notebook integrating Week 8/9/10 analytical core with team methodological extensions (Caleb stepwise GLM, choropleth, three-way exposure, per-LA bootstrap; Akeel diagnostics, traceability, policy framework); resolve parameter defaults; auto-generate traceability table and run metadata | ZA | 2026-05-06 | Closed | Final_Workflow/Data_Analysis/data_analysis.ipynb | 13 sections, 33 code cells, 20 figures, 12+ tables. Outputs traceability.csv + run_metadata.json on every run. |
| A050 | 006     | Restructure repo into Final_Workflow/Data_Prep + Data_Analysis with Cleaned/ as the contract between them; archive draft notebooks to Draft_Work/ | ZA + PA | 2026-05-06 | Closed | Repo structure | Master deliverable self-contained in two folders. |
| A051 | 006     | Author analysis notebook README documenting run order, configurable parameters, output inventory, and troubleshooting | ZA | 2026-05-06 | Closed | Final_Workflow/Data_Analysis/README.md | Single source of truth for re-running the analysis on future STATS19 releases. |
| A052 | 006     | Restructure repo: rename folders for consistency, move Action_Log and Meeting_Minutes into Group_Contact/, move Data_Prep to Archive/, rename Client Resources and Quality Assurance to use underscores | ZA | 2026-05-07 | Closed | Repo structure; commits `cf17a9b`, `dee2820` | Repo structure consistent and audit-ready. Group_Contact/ consolidates all B6 evidence. |
| A053 | 006     | Update Data_Prep README to reflect correct notebook name (data_cleaning.ipynb), folder structure, run instructions, lookup file notes, and downstream run order | ZA | 2026-05-07 | Closed | Final_Workflow/Data_Prep/README.md; commit `c987918` | README accurate and submission-ready. |
| A054 | 006     | Author Data_Analysis README documenting run order, configurable parameters, full section inventory, output file list, and reproducibility notes | ZA | 2026-05-07 | Closed | Final_Workflow/Data_Analysis/README.md | Covers all 13 sections, config parameters, and output inventory. |
| A055 | 006     | Fix QA notebook hardcoded path to relative path; add missing column checks for ksi, fatal, la_name, provisional | ZA | 2026-05-07 | Closed | Quality_Assurance/QA_Data_Load.ipynb | QA notebook now runs on any machine without path editing. Column checks aligned with data_analysis.ipynb schema. |
| A056 | 006     | Update QA README to reflect correct notebook name, workflow position, actual check results (31/32), and root requirements.txt dependency | ZA | 2026-05-07 | Closed | Quality_Assurance/README.md | QA README accurate and consistent with current repo structure. |
| A057 | 006     | Update Management Plan: correct delivery approach, close all milestones and risks with evidence, populate reproducibility record, and fill evidence of plan use section | ZA | 2026-05-07 | Closed | Management_Plan/Team1_Management_Plan_ST422.md; commit `2e6ad71` | Management plan reflects actual project delivery. All ZA milestones closed with evidence pointers. |
| A058 | 006     | Create meeting minutes for 2026-05-05 covering final pipeline ownership, CS/AS integration decision, and repo restructure plan | ZA | 2026-05-07 | Closed | Group_Contact/Meeting_Minutes/minutes_2026-05-05.md | Meeting 006 documented. ZA and PA ownership of final deliverables confirmed. |
| A059 | 006     | Create root-level requirements.txt covering all dependencies across data_cleaning.ipynb, data_analysis.ipynb, and QA_Data_Load.ipynb | ZA | 2026-05-07 | Closed | requirements.txt | Single install covers full pipeline: pandas, numpy, matplotlib, scipy, statsmodels, geopandas. |
| A060 | 006 | Create root requirements.txt covering all pipeline dependencies and update root README | ZA | 2026-05-07 | Closed | requirements.txt; README.md | Single pip install covers full pipeline. Root README guides marker through full reproducible run. |
---

## Blockers

| Action ID | Blocker Description | Raised By | Resolution | Resolved Date |
| --------- | ------------------- | --------- | ---------- | ------------- |
| A015 | Unable to export merged dataset to CSV after combining STATS19 tables | CS | Investigate export method and test alternative write approaches | [To be completed] |

---

## Handover and Dependency Log

| ID   | Output                  | Produced By         | Received By         | Dependency Description                                 | Handover Date     | Confirmed By      | Evidence (Commit / File) |
| ---- | ----------------------- | ------------------- | ------------------- | ------------------------------------------------------ | ----------------- | ----------------- | ------------------------ |
| H001 | Clean STATS19 dataset   | ZA (Data Steward)   | PA (Analysis Lead)  | Analysis cannot begin until data freeze v1 is complete | 2026-03-13        | ZA | Final_Workflow/Data_Prep/data_cleaning.ipynb |
| H002 | Core figures and tables | PA (Analysis Lead)  | CS (Reporting Lead) | Report drafting cannot begin until figures are locked  | [To be completed] | [To be completed] | [To be completed]        |
| H003 | Full draft report v1    | CS (Reporting Lead) | AS (QA Lead)        | QA review requires a stable draft                      | [To be completed] | [To be completed] | [To be completed]        |
| H004 | QA_DataLoad.ipynb + README_DataPrep.md | AS (QA Lead) | All team members | QA sign-off confirms data is ready for analysis. | 2026-04-14 | AS | Quality_Assurance/QA_DataLoad.ipynb; commit `8414b2e` |
| H005 | ST422_Analysis_v2.ipynb | AS (QA Lead)        | All team members    | Combined notebook replaces individual weekly notebooks for submission. | 2026-04-20 | AS | ST422_Analysis_v2.ipynb; commit `e8cb49d` |

---

## Status Summary

| Status      | Count |
| ----------- | ----- |
| Open        | 5     |
| In Progress | 6     |
| Closed      | 51    |
| Blocked     | 0     |
| **Total**   | **61** |
