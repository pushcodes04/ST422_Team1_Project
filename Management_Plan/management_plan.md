# Management Plan

**Module:** ST422 Statistical Consulting  
**Brief:** Brief 8 — Road Safety Analysis  
**Team:** Team 1  
**Date:** 23 February 2026  
**Last Updated:** 07 May 2026

This plan sets out how Team 1 will organise and deliver the consultancy. Roles are provisional and will be confirmed at the first team meeting. The document is live and will be updated as work progresses.

---

## 1. Workplan and Milestones

### 1.1 Delivery Approach

At the macro level, the project follows a waterfall structure, with phases running broadly in sequence and defined handover points between them. Within each phase, coordination was managed through meeting minutes, a live action log, and ad-hoc team meetings rather than fixed weekly cadences. This approach provided overall structure while remaining responsive to how work actually progressed.

The project runs from Week 6 (16 February) with a target internal completion date of 20 April. This provides a one-week buffer before the formal deadline of 27 April. As exams begin around that time, we aimed to avoid relying on the final week.

---

### 1.2 Phases of Work

Each phase concludes with a defined deliverable and clear completion criteria.

| Phase | Key Activities | Deliverable | Completion Criteria | Target Date |
|---|---|---|---|---|
| Triage and Scope | Read Brief 8. Agree the decision question, scope boundaries, and exclusions. Set up Notion workspace and GitHub repository. | Agreed scope note (SELECTION.md). Repository and workspace established. | All team members have read the brief. Scope documented and agreed. | 23 Feb 2026 |
| Data Readiness | Download STATS19 datasets (accidents, vehicles, casualties). Join tables, clean, assess missingness, document exclusions. | Clean joined dataset and concise data dictionary. | Cleaning script runs from repository root. No manual intervention required. | 13 Mar 2026 |
| Analysis | Severity and trend analysis. Hotspot identification. Contributory factor analysis. At least two robustness checks. | Core figures and tables saved to outputs directory. Results notes drafted. | All principal claims supported by a figure or table. | 30 Mar 2026 |
| Interpretation | Translate findings into decision-relevant insights. Draft limitations and uncertainty framing. Agree recommendations. | Draft findings section with recommendations and rationale. | Recommendations follow directly from evidence. Limitations framed as decision risks. | 6 Apr 2026 |
| Reporting | Write executive summary, client report, technical report, and traceability table. | Full draft report (Version 1). | Narrative aligns with evidence. Each claim has an anchored figure or table. Traceability table complete. | 13 Apr 2026 |
| QA and Finalisation | Peer review of claims and figures. Full reproducibility run from a fresh clone. Resolve issues. Prepare submission. | Final report, reproducibility record, QA log. | Fresh run reproduces all outputs. All compliance requirements satisfied. | 05 May 2026 |

---

### 1.3 Milestones

Internal deadlines are scheduled at least one week before they become critical, allowing time for revision if necessary.

| Milestone | Milestone Definition | Rationale | Date | Owner | Status |
|---|---|---|---|---|---|
| Scope agreed | Decision question confirmed. Out-of-scope list documented. SELECTION.md submitted. | Prevents scope creep from the outset. | 23 Feb | All | Closed |
| Repository and workspace live | GitHub repository created. Folder structure agreed. Notion workspace operational. | Establishes shared governance and a single working environment. | 23 Feb draft; 28 Feb v1 | All | Closed |
| Data freeze v1 | Clean STATS19 dataset produced via code. Version tagged. Data dictionary completed. | Prevents dataset drift during analysis. | 13 Mar | ZA | Closed — four cleaned CSVs produced (A014). Evidence: Data_Prep/ST422_DataPrep.ipynb |
| First figures completed | Core plots and tables drafted, including initial versions. | Enables early narrative drafting and identifies data issues. | 02 Mar | ZA | Closed — Week 8 analysis notebook completed with KSI trends, severity profiles, hotspot analysis (A010). Evidence: Draft_work/Week8_Road_Safety.ipynb |
| Draft recommendations prepared | Recommendation and supporting rationale drafted. | Ensures the report remains decision-led rather than descriptive. | 16 Mar | ZA | Closed — Week 10 client-facing report notebook completed with findings and recommendations (A027). Evidence: Draft_work/Week10_Road_Safety.ipynb |
| First full reproducible build | Report renders from repository root without manual edits. | Identifies reproducibility issues while time remains to address them. | 14 Apr | AS | Closed — DataPrep notebook reproduced on clean machine. 31 of 32 checks passed (A032). Evidence: Quality_Assurance/README_DataPrep.md; commit 16084c6 |
| Peer review completed | Sections reviewed by non-authors and comments addressed. | Improves clarity and reduces avoidable errors. | 14 Apr | AS | Closed — QA notebook and README uploaded (A033, A034). Evidence: Quality_Assurance/; commit 8414b2e |
| Final submission | Portfolio submitted to Moodle. | Hard deadline. | - | All | Open |

---

### 1.4 Roles and Responsibilities

Roles are assigned to establish accountability and maintain momentum. Leading a role means owning the process, not completing all associated tasks alone.

| Role | Responsibilities | Outputs | Assigned To |
|---|---|---|---|
| Project Lead | Maintains schedule, chairs weekly reviews, records actions, escalates risks where necessary. | Meeting notes, action log, status updates. | Yadavan Surabaskaran |
| Data Steward | Oversees data acquisition, cleaning, documentation, and version tagging. | Clean dataset, data dictionary, cleaning script. | Zahid Ahmed |
| Analysis Lead | Coordinates modelling, trend analysis, hotspot analysis, and robustness testing. | Figures, tables, results documentation. | Pushkal Ahluwalia |
| Reporting Lead | Leads drafting of executive summary, client report, technical report, and traceability table. | Draft and final reports. | Caleb Sithole |
| QA Lead | Conducts reproducibility checks, reviews code and figures, maintains QA log. | Reproducibility record, QA log, validation notes. | Akeel Shah |

**Note on role boundaries:** Roles above reflect initial assignments at project kickoff. As the project progressed, ZA, PA, and CS all contributed across data preparation and analysis beyond their initial role definitions. The action log (Group_Contact/Action_Log/Action Log.md) contains the full attributable record of tasks completed by each team member, with evidence pointers to notebooks, commits, and outputs.

---

## 2. Risk Register

The following risks have been identified as most likely to affect delivery or validity. The register will be reviewed weekly and updated accordingly.

| Risk | Likelihood | Impact | Trigger | Mitigation | Owner | Status |
|---|---|---|---|---|---|---|
| Scope creep | Medium | High | Tasks introduced that are not linked to the decision question | Freeze scope at Week 7. Maintain an out-of-scope record. Require full team agreement for additions. | Project Lead | Closed — scope held to Brief 8 throughout. No material additions outside brief. |
| STATS19 data quality issues | Medium | High | High missingness or inconsistent coding across years | Assess data quality during triage. Document exclusions. Run sensitivity analyses where required. | Data Steward | Closed — missingness assessed and documented in Week 8 notebook. IBRS recording artefact identified and addressed via adjusted series (A018). Evidence: Draft_work/Week8_Road_Safety.ipynb |
| Uneven contribution | Low | High | Agreed tasks not completed on schedule | Assign each task to a named owner. Review weekly progress. Escalate concerns early. | Project Lead | Open — task ownership tracked via action log throughout. |
| Reproducibility failure | Medium | High | Code dependent on local paths or missing dependencies | Use relative paths from outset. Maintain requirements.txt. Conduct early clean-run test. | QA Lead | Closed — hardcoded paths removed (A036). Clean run completed 14 Apr, 31/32 checks passed (A032). Evidence: commit f6b4ace; Quality_Assurance/README_DataPrep.md |
| Writing compressed into final weeks | Medium | High | No draft narrative by early April | Begin executive summary skeleton early. Lock figures before final writing stage. | Reporting Lead | Open |
| Exam period impact | High | Medium | Reduced team availability in late April | Target internal completion by 20 April. Avoid planning substantial work in final week. | All | Closed — final analysis pipeline and repo completed by 06 May (A047–A051). Evidence: Final_Workflow/Data_Analysis/data_analysis.ipynb |

---

## 3. Quality Assurance Plan

### 3.1 Data Quality Checks

These checks are performed each time the dataset is updated. Results are recorded.

| Check | Method | Acceptance Threshold | Timing | Owner | Status |
|---|---|---|---|---|---|
| Missingness assessment | Scripted summary of percentage missing by variable | Flag if greater than 10 percent in variables used in primary claims | Each data update | Data Steward | Closed — 0.0% missing on all key fields confirmed. Evidence: Quality_Assurance/QA_Data_Load.ipynb Check 5. |
| Duplicate detection | Check accident reference identifiers and full-row duplication | No duplicates in accident_index | Each data update | Data Steward | Closed — 0 duplicates in cas_full.csv confirmed. Known issue in collisions_clean.csv documented. Evidence: Quality_Assurance/QA_Data_Load.ipynb Check 4. |
| Range and validity checks | Rule-based constraints for severity codes, dates, casualty counts | Values must fall within documented valid ranges | Each data update | Data Steward | Closed — severity codes 1, 2, 3 only confirmed. KSI % = 17.0%. Evidence: Quality_Assurance/QA_Data_Load.ipynb Check 6. |
| Year consistency review | Confirm consistent coding definitions across years | Any material change flagged and documented | At data freeze | Data Steward | Closed — year range 2014–2025 confirmed, no gaps. IBRS transition documented. Evidence: Quality_Assurance/QA_Data_Load.ipynb Check 3; Draft_Work/Week8_Road_Safety.ipynb. |

---

### 3.2 Robustness Checks

Each robustness check is directly linked to a principal claim. Material change thresholds are defined in advance.

| Check | Rationale | Adjustment | Threshold for Reassessment | Owner | Status |
|---|---|---|---|---|---|
| Alternative severity filter | Severity classification changed in 2016 | Restrict analysis to post-2016 data and compare results | If direction or magnitude of trend changes materially | Analysis Lead | Closed — IBRS-adjusted vs raw KSI comparison run. Adjusted: -284.5 KSI/yr vs raw +182.6 KSI/yr. Evidence: Final_Workflow/Data_Analysis/data_analysis.ipynb §3c (A018). |
| Alternative hotspot definition | Geographic unit choice may affect priorities | Compare police force area with local authority geography | If priority areas change substantially | Analysis Lead | Closed — count vs rate hotspot rankings compared. Zero overlap in top 15 confirmed. Evidence: Final_Workflow/Data_Analysis/data_analysis.ipynb §5 (A020). |
| Alternative factor grouping | Grouping decisions influence factor prominence | Re-run analysis with alternative grouping schemes | If ranking of top factors changes materially | Analysis Lead | Closed — three-way exposure robustness check run across count, rate, and population-adjusted rankings. Evidence: Final_Workflow/Data_Analysis/data_analysis.ipynb §5d. |
| Excluding COVID years | 2020 and 2021 had atypical collision volumes | Re-run trends excluding those years | If overall trend direction changes | Analysis Lead | Closed — COVID years excluded from trend fitting. Robustness check confirms direction unchanged. Evidence: Final_Workflow/Data_Analysis/data_analysis.ipynb §8 (A010). |

---

### 3.3 Scheduled Review Process

Review is scheduled as a formal milestone rather than a final-stage activity.

| Review Type | Scope | Method | Scheduled Date | Responsible | Status |
|---|---|---|---|---|---|
| Narrative review | Claims, executive summary, recommendations | Non-author review with comments recorded | 17 Apr 2026 | All | Closed — QA sign-off completed Apr 2026. Evidence: Quality_Assurance/QA_Data_Load.ipynb; commit 8414b2e. |
| Figure validation | Labels, units, comparators, clarity | Checklist review against associated claim | 17 Apr 2026 | All | Closed — all figures verified via QA notebook. Evidence: Quality_Assurance/QA_Data_Load.ipynb. |
| Code verification | Full analytical pipeline and dependency restoration | Fresh clone build following README | 13 Apr 2026 | QA Lead | Closed — clean run completed 14 Apr 2026 (AS) and 07 May 2026 (ZA). 31/32 checks passed both runs. Evidence: Quality_Assurance/QA_Data_Load.ipynb. |

---

### 3.4 Reproducibility Verification Record

A full clean build will be completed by 13 April. This section is updated when the clean run is executed.

| Field | Detail |
|---|---|
| Date of clean run | 2026-04-14 |
| Executed by | Akeel Shah |
| Operating system | ChromeOS |
| Python version | Python 3 |
| Dependency restoration method | requirements.txt |
| Outcome (Pass / Fail) | Pass — 31 of 32 checks passed. One known issue documented. |
| Issues identified | One check failed — documented in QA notebook. |
| Issues resolved (with PR/commit reference) | Documented in Quality_Assurance/QA_Data_Load.ipynb; commit 97bb090 |

**Second clean run — ZA (07 May 2026)**

| Field | Detail |
|---|---|
| Date of clean run | 2026-05-07 |
| Executed by | Zahid Ahmed |
| Operating system | macOS |
| Python version | Python 3.11 |
| Dependency restoration method | requirements.txt |
| Outcome (Pass / Fail) | Pass — 31 of 32 checks passed. One known issue documented. |
| Issues identified | collisions_clean.csv — 2,771 duplicate rows (known DfT source issue, does not affect cas_full.csv). |
| Issues resolved (with PR/commit reference) | No new issues. Documented in Quality_Assurance/QA_Data_Load.ipynb. |

**Procedure**

1. Clone repository from project root
2. Install dependencies via requirements.txt (pip install -r requirements.txt)
3. Render report from project root using README run sequence
4. Compare regenerated outputs against those in the submitted report

**Outputs to Verify**

| Output | File Path | Match (Yes / No) |
|---|---|---|
| fig01_missingness_ibrs.png | Final_Workflow/Data_Analysis/Outputs/figures/ | Yes |
| fig03_national_ksi_trend.png | Final_Workflow/Data_Analysis/Outputs/figures/ | Yes |
| fig04_raw_vs_adjusted.png | Final_Workflow/Data_Analysis/Outputs/figures/ | Yes |
| fig06_hotspots_count_rate.png | Final_Workflow/Data_Analysis/Outputs/figures/ | Yes |
| tab_ksi_raw_vs_adjusted.csv | Final_Workflow/Data_Analysis/Outputs/tables/ | Yes |
| tab_la_hotspots_count.csv | Final_Workflow/Data_Analysis/Outputs/tables/ | Yes |
| traceability.csv | Final_Workflow/Data_Analysis/Outputs/ | Yes |
| findings.html | Final_Workflow/Data_Analysis/Outputs/ | Yes |

---

## 4. Evidence of Plan Use

This section is updated throughout the project to record that the management plan was actively used to guide delivery, not just completed at the outset.

| Date | Update Type | Detail | Recorded By |
|---|---|---|---|
| 23 Feb 2026 | Plan created | Initial version drafted and agreed at kickoff meeting. | Project Lead |
| 13 Mar 2026 | Milestone closed | Data freeze v1 completed. Four cleaned CSVs produced via code. Evidence: Final_Workflow/Data_Prep/data_cleaning.ipynb (A014). | ZA |
| 02 Mar 2026 | Milestone closed | First figures completed. Week 8 analysis notebook delivered covering KSI trends, severity profiles, hotspot and temporal analysis. Evidence: Draft_Work/Week8_Road_Safety.ipynb (A010). | ZA |
| 09 Mar 2026 | Milestone closed | Week 9 analysis completed. IBRS-adjusted KSI series, hotspot sensitivity analysis, and seasonality check delivered. Evidence: Draft_Work/Week9_Road_Safety.ipynb (A017–A021). | ZA |
| 16 Mar 2026 | Milestone closed | Draft recommendations prepared. Week 10 client-facing report notebook completed with findings and recommendations. Evidence: Draft_Work/Week10_Road_Safety.ipynb (A027). | ZA |
| 18 Apr 2026 | Risk closed | Reproducibility failure risk closed. Hardcoded paths removed across all notebooks. Evidence: commit f6b4ace (A036). | AS |
| 14 Apr 2026 | Milestone closed | First full reproducible build completed. 31 of 32 checks passed on clean machine. Evidence: Quality_Assurance/README_DataPrep.md; commit 16084c6 (A032). | AS |
| 06 May 2026 | Milestone closed | Final analysis pipeline completed. Master notebook integrating full analytical core built and tested. Repo restructured. Evidence: Final_Workflow/Data_Analysis/data_analysis.ipynb (A047–A051). | ZA |
| 07 May 2026 | QA sign-off | Second clean run completed on macOS. QA notebook run top to bottom. 31/32 checks passed. Path fix applied and column checks added. Evidence: Quality_Assurance/QA_Data_Load.ipynb (A055). | ZA |
| 07 May 2026 | Repo finalised | Root README updated, root requirements.txt created, all folder names standardised, READMEs updated for Data_Prep, Data_Analysis, and Quality_Assurance. Evidence: commits dee2820, c987918 (A052–A060). | ZA |
