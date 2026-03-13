# Action Log

**Module:** ST422 Statistical Consulting  
**Brief:** Brief 8 — Road Safety Analysis  
**Team:** Team 1  
**Last Updated:** 12 March 2026

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
| A002 | 001     | Review and approve Management Plan against audit structure                  | ZA    | 2026-02-22 | In Progress | management_plan.md                    | [To be completed on close] |
| A003 | 001     | Establish repository structure, README, data allocation and tracking system | PA    | 2026-02-22 | In Progress | Repository link + README.md           | [To be completed on close] |
| A004 | 001     | Prepare and upload draft meeting minutes with updated action log            | CS    | 2026-02-22 | In Progress | minutes/2026-02-21.md                 | [To be completed on close] |
| A005 | 001     | Upload client questions to clarify scope and analytical direction           | YS    | 2026-02-22 | In Progress | client_questions.md                   | [To be completed on close] |
| A006 | 002     | Set up GitHub collaboration workflow (access, branches, PR template)        | YD    | 2026-03-05 | In Progress | Issue # + CONTRIBUTING.md / README.md | [To be completed on close] |
| A007 | 002     | Confirm collisions date column name + format (historic + 2025 provisional)  | PA    | 2026-03-05 | In Progress | Issue # + notebook cell / script note | [To be completed on close] |
| A008 | 002     | Build merge pipeline: Collisions + Vehicles + Casualties (1979–latest)      | CS    | 2026-03-05 | In Progress | PR # + notebooks/merge_pipeline.ipynb | [To be completed on close] |
| A009 | 002     | Clean merged data: drop <2015 rows, remove unnecessary columns              | ZA    | 2026-03-05 | Closed      | Data_Prep/ST422_DataPrep              | [To be completed on close] |
| A010 | 002     | Run Python EDA on cleaned 2015+ dataset                                     | PA    | 2026-03-05 | In Progress | Issue # + notebook cell / script note | [To be completed on close] |
| A011 | 002     | Add data dictionary + “columns to keep” list                                | PA    | 2026-03-05 | In Progress | PR # + docs/data_dictionary.md        | [To be completed on close] |
| A012 | 002     | Commit GLM last-5-years analysis artefact + short interpretation note       | AS    | 2026-03-05 | In Progress | Issue # + notebook cell / script note | [To be completed on close] |
| A013 | 003     | Combine STATS19 collisions, vehicles, and casualties datasets into one dataset | ZA | 2026-03-13 | Open        | notebooks/merge_pipeline.ipynb        | [To be completed on close] |
| A014 | 003     | Investigate issue preventing export of merged dataset to CSV                | CS    | 2026-03-13 | Open        | Issue # + merge script                | [To be completed on close] |
| A015 | 003     | Validate merged dataset and confirm readiness for cleaning pipeline         | PA    | 2026-03-14 | Open        | clean_joined.csv + validation log     | [To be completed on close] |
| A016 | 004     | Identify local authorities that have shown improvement in KSI outcomes and analyse potential contributing factors | ZA | 2026-03-18 | Open | notebooks/hotspot_analysis.ipynb | [To be completed on close] |
| A017 | 004     | Investigate policy interventions available to local authorities (e.g., speed management, traffic calming, enforcement) | AS | 2026-03-18 | Open | docs/policy_review.md | [To be completed on close] |
| A018 | 004     | Analyse factors affecting worst-performing local authorities in terms of KSI collisions | CS | 2026-03-18 | Open | notebooks/LA_factor_analysis.ipynb | [To be completed on close] |
| A019 | 004     | Conduct geographic hotspot analysis for high-KSI locations | CS | 2026-03-18 | Open | notebooks/geographic_hotspots.ipynb | [To be completed on close] |
| A020 | 004     | Perform hypothesis testing comparing Raw KSI trends vs IBRS-adjusted KSI trends using DfT guidance | CS | 2026-03-18 | Open | notebooks/ksi_adjustment_analysis.ipynb | [To be completed on close] |

---

## Blockers

| Action ID | Blocker Description | Raised By | Resolution | Resolved Date |
| --------- | ------------------- | --------- | ---------- | ------------- |
| A014 | Unable to export merged dataset to CSV after combining STATS19 tables | CS | Investigate export method and test alternative write approaches | [To be completed] |

---

## Handover and Dependency Log

This table records where one person's output is a direct input to another person's work. The receiving owner confirms readiness before proceeding.

| ID   | Output                  | Produced By         | Received By         | Dependency Description                                 | Handover Date     | Confirmed By      | Evidence (Commit / File) |
| ---- | ----------------------- | ------------------- | ------------------- | ------------------------------------------------------ | ----------------- | ----------------- | ------------------------ |
| H001 | Clean STATS19 dataset   | ZA (Data Steward)   | PA (Analysis Lead)  | Analysis cannot begin until data freeze v1 is complete | [To be completed] | [To be completed] | [To be completed]        |
| H002 | Core figures and tables | PA (Analysis Lead)  | CS (Reporting Lead) | Report drafting cannot begin until figures are locked  | [To be completed] | [To be completed] | [To be completed]        |
| H003 | Full draft report v1    | CS (Reporting Lead) | AS (QA Lead)        | QA review requires a stable draft                      | [To be completed] | [To be completed] | [To be completed]        |

---

## Status Summary

| Status      | Count |
| ----------- | ----- |
| Open        | 8     |
| In Progress | 12    |
| Complete    | 0     |
| Blocked     | 0     |
| **Total**   | **20** |
