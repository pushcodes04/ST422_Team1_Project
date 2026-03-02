# Management Plan

**Module:** ST422 Statistical Consulting  
**Brief:** Brief 8 — Road Safety Analysis  
**Team:** Team 1  
**Date:** 23 February 2026  
**Last Updated:** 23 February 2026

This plan sets out how Team 1 will organise and deliver the consultancy. Roles are provisional and will be confirmed at the first team meeting. The document is live and will be updated as work progresses.

---

## 1. Workplan and Milestones

### 1.1 Delivery Approach

At the macro level, we are using a waterfall structure, with phases running broadly in sequence and defined handover points between them. Within each phase, work is organised in weekly sprints reviewed every Sunday evening. This approach provides overall structure while keeping individual weeks flexible.

The project runs from Week 6 (16 February) with a target internal completion date of 20 April. This provides a one-week buffer before the formal deadline of 27 April. As exams begin around that time, we aim to avoid relying on the final week.

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
| QA and Finalisation | Peer review of claims and figures. Full reproducibility run from a fresh clone. Resolve issues. Prepare submission. | Final report, reproducibility record, QA log. | Fresh run reproduces all outputs. All compliance requirements satisfied. | 20 Apr 2026 |

---

### 1.3 Milestones

Internal deadlines are scheduled at least one week before they become critical, allowing time for revision if necessary.

| Milestone | Milestone Definition | Rationale | Date | Owner | Status |
|---|---|---|---|---|---|
| Scope agreed | Decision question confirmed. Out-of-scope list documented. SELECTION.md submitted. | Prevents scope creep from the outset. | 23 Feb | All | Open |
| Repository and workspace live | GitHub repository created. Folder structure agreed. Notion workspace operational. | Establishes shared governance and a single working environment. | 23 Feb draft; 28 Feb v1 | All | Open |
| Data freeze v1 | Clean STATS19 dataset produced via code. Version tagged. Data dictionary completed. | Prevents dataset drift during analysis. | 13 Mar | All | Open |
| First figures completed | Core plots and tables drafted, including initial versions. | Enables early narrative drafting and identifies data issues. | 23 Mar | All | Open |
| Draft recommendations prepared | Recommendation and supporting rationale drafted. | Ensures the report remains decision-led rather than descriptive. | 6 Apr | All | Open |
| First full reproducible build | Report renders from repository root without manual edits. | Identifies reproducibility issues while time remains to address them. | 13 Apr | All | Open |
| Peer review completed | Sections reviewed by non-authors and comments addressed. | Improves clarity and reduces avoidable errors. | 17 Apr | All | Open |
| Final submission | Portfolio submitted to Moodle. | Hard deadline. | 27 Apr 1pm | All | Open |

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

---

## 2. Risk Register

The following risks have been identified as most likely to affect delivery or validity. The register will be reviewed weekly and updated accordingly.

| Risk | Likelihood | Impact | Trigger | Mitigation | Owner | Status |
|---|---|---|---|---|---|---|
| Scope creep | Medium | High | Tasks introduced that are not linked to the decision question | Freeze scope at Week 7. Maintain an out-of-scope record. Require full team agreement for additions. | Project Lead | Open |
| STATS19 data quality issues | Medium | High | High missingness or inconsistent coding across years | Assess data quality during triage. Document exclusions. Run sensitivity analyses where required. | Data Steward | Open |
| Uneven contribution | Low | High | Agreed tasks not completed on schedule | Assign each task to a named owner. Review weekly progress. Escalate concerns early. | Project Lead | Open |
| Reproducibility failure | Medium | High | Code dependent on local paths or missing dependencies | Use relative paths from outset. Maintain renv.lock. Conduct early clean-run test. | QA Lead | Open |
| Writing compressed into final weeks | Medium | High | No draft narrative by early April | Begin executive summary skeleton early. Lock figures before final writing stage. | Reporting Lead | Open |
| Exam period impact | High | Medium | Reduced team availability in late April | Target internal completion by 20 April. Avoid planning substantial work in final week. | All | Open |

---

## 3. Quality Assurance Plan

### 3.1 Data Quality Checks

These checks are performed each time the dataset is updated. Results are recorded.

| Check | Method | Acceptance Threshold | Timing | Owner | Status |
|---|---|---|---|---|---|
| Missingness assessment | Scripted summary of percentage missing by variable | Flag if greater than 10 percent in variables used in primary claims | Each data update | Data Steward | Open |
| Duplicate detection | Check accident reference identifiers and full-row duplication | No duplicates in accident_index | Each data update | Data Steward | Open |
| Range and validity checks | Rule-based constraints for severity codes, dates, casualty counts | Values must fall within documented valid ranges | Each data update | Data Steward | Open |
| Year consistency review | Confirm consistent coding definitions across years | Any material change flagged and documented | At data freeze | Data Steward | Open |

---

### 3.2 Robustness Checks

Each robustness check is directly linked to a principal claim. Material change thresholds are defined in advance.

| Check | Rationale | Adjustment | Threshold for Reassessment | Owner | Status |
|---|---|---|---|---|---|
| Alternative severity filter | Severity classification changed in 2016 | Restrict analysis to post-2016 data and compare results | If direction or magnitude of trend changes materially | Analysis Lead | Open |
| Alternative hotspot definition | Geographic unit choice may affect priorities | Compare police force area with local authority geography | If priority areas change substantially | Analysis Lead | Open |
| Alternative factor grouping | Grouping decisions influence factor prominence | Re-run analysis with alternative grouping schemes | If ranking of top factors changes materially | Analysis Lead | Open |
| Excluding COVID years | 2020 and 2021 had atypical collision volumes | Re-run trends excluding those years | If overall trend direction changes | Analysis Lead | Open |

---

### 3.3 Scheduled Review Process

Review is scheduled as a formal milestone rather than a final-stage activity.

| Review Type | Scope | Method | Scheduled Date | Responsible | Status |
|---|---|---|---|---|---|
| Narrative review | Claims, executive summary, recommendations | Non-author review with comments recorded | 17 Apr 2026 | All | Open |
| Figure validation | Labels, units, comparators, clarity | Checklist review against associated claim | 17 Apr 2026 | All | Open |
| Code verification | Full analytical pipeline and dependency restoration | Fresh clone build following README | 13 Apr 2026 | QA Lead | Open |

---

### 3.4 Reproducibility Verification Record

A full clean build will be completed by 13 April. This section is updated when the clean run is executed.

| Field | Detail |
|---|---|
| Date of clean run | To be completed |
| Executed by | To be completed |
| Operating system | To be completed |
| R version | To be completed |
| Dependency restoration method | renv.lock |
| Outcome (Pass / Fail) | To be completed |
| Issues identified | To be completed |
| Issues resolved (with PR/commit reference) | To be completed |

**Procedure**

1. Clone repository from project root
2. Restore dependencies via renv.lock
3. Render report from project root using README run sequence
4. Compare regenerated outputs against those in the submitted report

**Outputs to Verify**

| Output | File Path | Match (Yes / No) |
|---|---|---|
| [Placeholder — Figure 1] | outputs/fig/ | To be completed |
| [Placeholder — Figure 2] | outputs/fig/ | To be completed |
| [Placeholder — Table 1] | outputs/tab/ | To be completed |
| [Placeholder — Table 2] | outputs/tab/ | To be completed |

---

## 4. Evidence of Plan Use

This section is updated throughout the project to record that the management plan was actively used to guide delivery, not just completed at the outset.

| Date | Update Type | Detail | Recorded By |
|---|---|---|---|
| 23 Feb 2026 | Plan created | Initial version drafted and agreed at kickoff meeting. | Project Lead |
| [Placeholder] | Risk status update | [e.g., Reproducibility failure — Closed after clean run on DD Mon] | QA Lead |
| [Placeholder] | Milestone closed | [e.g., Data freeze v1 — completed DD Mon, commit reference] | Data Steward |
| [Placeholder] | QA sign-off | [e.g., Figure validation completed — issues logged in PR #X] | All |
| [Placeholder] | Risk escalated | [e.g., Scope creep flagged in weekly review — resolved by agreement] | Project Lead |