# Action Log

**Module:** ST422 Statistical Consulting  
**Brief:** Brief 8 — Road Safety Analysis  
**Team:** Team 1  
**Last Updated:** 16 March 2026

This is the single master record of all actions across the entire project. Every action must have a named owner, a deadline, a status, and a verifiable evidence reference (PR number, commit hash, issue ID, or file path). This document is updated continuously as actions are opened, progressed, and closed.

---

# Status Key

| Status | Meaning |
|------|------|
| Open | Not yet started |
| In Progress | Work underway |
| Complete | Delivered and verified |
| Blocked | Cannot proceed — blocker recorded in Blockers table |

---

# Master Actions Table

| ID | Meeting | Action | Owner | Deadline | Status | Evidence | Outcome |
|----|----|----|----|----|----|----|----|
| A001 | 001 | Finalise and upload Client Brief 8 selection in SELECTION.md | AS | 2026-02-22 | In Progress | Team1_Management_Plan_ST422.md | [To be completed on close] |
| A002 | 001 | Review and approve Management Plan against audit structure | ZA | 2026-02-22 | Closed | Management_Plan.html | Management plan reviewed and approved against audit structure. |
| A003 | 001 | Establish repository structure, README, data allocation and tracking system | PA | 2026-02-22 | In Progress | test.txt | [To be completed on close] |
| A004 | 001 | Prepare and upload draft meeting minutes with updated action log | CS | 2026-02-22 | In Progress | Week7_Client_meeting.md | [To be completed on close] |
| A005 | 001 | Upload client questions to clarify scope and analytical direction | YS | 2026-02-22 | In Progress | Clientquestions.docx | [To be completed on close] |
| A006 | 002 | Set up GitHub collaboration workflow (access, branches, PR template) | YD | 2026-03-05 | In Progress | test.txt | [To be completed on close] |
| A007 | 002 | Confirm collisions date column name + format (historic + 2025 provisional) | PA | 2026-03-05 | In Progress | Dataset merge and missing value inspect.ipynb | [To be completed on close] |
| A008 | 002 | Build merge pipeline: Collisions + Vehicles + Casualties (1979–latest) | CS | 2026-03-05 | In Progress | Dataset merge and missing value inspect.ipynb | [To be completed on close] |
| A009 | 002 | Clean merged data: drop <2015 rows, remove unnecessary columns | ZA | 2026-03-05 | Closed | Dataset Work.ipynb | Data preparation pipeline built and uploaded to GitHub. |
| A010 | 002 | Build Week 8 road safety analysis notebook covering KSI trends, road user profiles, hotspot analysis, and contributory factors | ZA | 2026-03-02 | Closed | Week8_Road_Safety.ipynb | Week 8 analysis notebook completed and exported to HTML. |
| A011 | 002 | Run Python EDA on cleaned 2015+ dataset | PA | 2026-03-05 | In Progress | Dataanalysis.ipynb | [To be completed on close] |
| A012 | 002 | Add data dictionary + "columns to keep" list | PA | 2026-03-05 | In Progress | Current Dataset Work.Rmd | [To be completed on close] |
| A013 | 002 | Commit GLM last-5-years analysis artefact + short interpretation note | AS | 2026-03-05 | In Progress | GLM_Road_Casualties.pdf | [To be completed on close] |
| A014 | 003 | Combine STATS19 collisions, vehicles, and casualties datasets into one dataset | ZA | 2026-03-13 | Closed | Dataset merge and missing value inspect.ipynb | Four cleaned CSVs produced covering 2014–2025. |
| A015 | 003 | Build Week 9 road safety analysis notebook covering 2014–2024 with IBRS-adjusted KSI, severity profiles, geographic hotspot analysis, contributory factors, and robustness checks | ZA | 2026-03-09 | Closed | Week9_Road_Safety.ipynb | Week 9 analysis notebook completed and exported to HTML. |
| A016 | 003 | Develop IBRS-adjusted KSI series and robustness check comparing raw vs adjusted trend direction | ZA | 2026-03-09 | Closed | Week9_Road_Safety.ipynb | Adjusted trend analysis completed. |
| A017 | 003 | Build 2025 provisional data seasonality check and annualised KSI estimate | ZA | 2026-03-09 | Closed | Week9_Road_Safety.ipynb | Annualised estimate produced with caveat. |
| A018 | 003 | Build hotspot sensitivity analysis comparing count-based vs rate-based LA rankings | ZA | 2026-03-09 | Closed | Week9_Road_Safety.ipynb | Zero overlap between top 15 count and rate authorities confirmed. |
| A019 | 003 | Fix KSI % above 100% bug in local authority chart | ZA | 2026-03-09 | Closed | Week9_Road_Safety.ipynb | Duplicate ONS diagnostic added. |
| A020 | 003 | Rewrite Week 10 client update to decision-led prose with evidence anchoring | ZA | 2026-03-13 | Closed | Week10_Client_Update.pdf | Final client update submitted. |
| A021 | 003 | Investigate issue preventing export of merged dataset to CSV | CS | 2026-03-13 | Open | Dataset merge and missing value inspect.ipynb | [To be completed on close] |
| A022 | 003 | Validate merged dataset and confirm readiness for cleaning pipeline | PA | 2026-03-14 | Open | Dataset Work.ipynb | [To be completed on close] |
| A023 | 004 | Identify local authorities that have shown improvement in KSI outcomes and analyse potential contributing factors | ZA | 2026-03-18 | Closed | Week10_Improving_Analysis.ipynb | LA trend analysis completed. |
| A024 | 004 | Build Week 10 improving LA analysis notebook with robustness checks | ZA | 2026-03-16 | Closed | Week10_Improving_Analysis.ipynb | Top improving authorities identified. |
| A025 | 004 | Build Week 10 worsening LA analysis notebook with robustness checks | ZA | 2026-03-16 | Closed | Week10_Worsening_Analysis.ipynb | Top worsening authorities identified. |
| A026 | 004 | Add boundary reorganisation completeness filter to data prep pipeline and update README | ZA | 2026-03-16 | Closed | Dataset Work.ipynb | Completeness filter implemented. |
| A027 | 004 | Build Week 10 LA trend analysis notebook using OLS regression | ZA | 2026-03-16 | Closed | Week10_Road_Safety.ipynb | OLS trend model fitted across 2014–2024. |
| A028 | 004 | Investigate policy interventions available to local authorities | AS | 2026-03-18 | Open | Week7_Team1_question_response.pdf | [To be completed on close] |
| A029 | 004 | Analyse factors affecting worst-performing local authorities in terms of KSI collisions | CS | 2026-03-18 | Open | Week10_Worsening_Analysis.ipynb | [To be completed on close] |
| A030 | 004 | Conduct geographic hotspot analysis for high-KSI locations | CS | 2026-03-18 | Open | Week10_Road_Safety.ipynb | [To be completed on close] |
| A031 | 004 | Perform hypothesis testing comparing Raw KSI trends vs IBRS-adjusted KSI trends | CS | 2026-03-18 | Closed | Week9_Road_Safety.ipynb | Not required |

---

# Blockers

| Action ID | Blocker Description | Raised By | Resolution | Resolved Date |
|-----------|--------------------|-----------|-----------|--------------|
| A021 | Unable to export merged dataset to CSV after combining STATS19 tables | CS | Investigate export method and test alternative write approaches | [To be completed] |

---

# Handover and Dependency Log

| ID | Output | Produced By | Received By | Dependency Description | Handover Date | Confirmed By | Evidence |
|----|----|----|----|----|----|----|----|
| H001 | Clean STATS19 dataset | ZA | PA | Analysis cannot begin until data freeze v1 is complete | 2026-03-13 | [To be completed] | Dataset Work.ipynb |
| H002 | Core figures and tables | PA | CS | Report drafting cannot begin until figures are locked | [To be completed] | [To be completed] | Week9_Road_Safety.html |
| H003 | Full draft report v1 | CS | AS | QA review requires a stable draft | [To be completed] | [To be completed] | Week10_Client_Update.pdf |

---

# Status Summary

| Status | Count |
|-------|------|
| Open | 6 |
| In Progress | 7 |
| Closed | 18 |
| Blocked | 0 |
| **Total** | **31** |
