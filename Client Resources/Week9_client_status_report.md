---
output:
  pdf_document: default
  html_document: default
---

# Client project status report

## EXECUTIVE OVERVIEW AND PROGRESS

**Project name:** STATS19 Road Safety Analysis  
**Team:** Team 1  
**Reporting period:** 23 Feb – 5 Mar 2026  
**Date produced:** 05 March 2026  

### Executive summary

**Overall status:** 🟢 Green – On Track  

- The project scope, governance structure, and repository were established, and the full STATS19 dataset (1979–2024; 1.9M collisions) was downloaded, filtered to 2015–2024, and analysed to produce the first client-ready figures.
- Early results suggest fatal collisions remain relatively stable (~1,500–1,700 annually), while serious collisions have increased since 2020; however, this trend must be interpreted cautiously due to the 2016 change in injury severity classification.
- Next period will focus on completing the data cleaning pipeline, hotspot analysis, and reproducible analysis workflow. No client support is currently required to maintain progress.

---

### Key milestones achieved

- Project scope agreed and `SELECTION.md` submitted (23 Feb 2026)
- Repository and project workspace established (23 Feb 2026)
- Management plan and governance documents finalised (23 Feb 2026)
- Full STATS19 dataset downloaded and explored (28 Feb 2026)
- Initial severity and road user analysis figures produced (05 Mar 2026)

---

### Top 3 risks/issues

**1) Data join limitation – full STATS19 collision file incomplete**

- **Why it matters:** The full 1979–present collision file contains only ~21% of expected records, preventing reliable joins across collision, vehicle, and casualty tables for the entire time period.
- **Current mitigation and owner:** Analysis scope split by dataset quality.  
  - 5-year collision dataset (2020–2024) used for geographic hotspot analysis.  
  - 10-year casualty dataset used for trend analysis.  
  Owner: PA
- **Next update date:** 12 March 2026

---

**2) Severity reclassification bias (post-2016)**

- **Why it matters:** A 2016 change to injury-based reporting increased the number of recorded serious injuries, which could inflate trend estimates if raw severity categories are used.
- **Current mitigation and owner:** Adjusted severity variables confirmed complete for 2015 onwards; all analysis uses adjusted severity measures.  
  Owner: PA
- **Next update date:** 12 March 2026

---

**3) Exam period compressing final reporting weeks**

- **Why it matters:** Team availability will reduce during late April due to exams, creating a risk of compressed writing and QA timelines.
- **Current mitigation and owner:** Internal completion target set for 20 April, providing a one-week buffer before final deadlines. Executive summary drafting begins week of 16 March.  
  Owner: All
- **Next update date:** 20 April 2026

---

## DETAILED PERFORMANCE AND NEXT STEPS

### Work accomplished

- **Local authority reference dataset integrated** to support geographic aggregation of collisions (Evidence: `local-authority-ons-district-names.csv`).
- **Data integration strategy defined** after assessing join compatibility across collision, vehicle, and casualty tables (Evidence: `data_join_notes.md`, `join_validation_summary.csv`).
- **Project governance established**, including GitHub repository, management plan, and risk register (Evidence: `management_plan.md`, `action_log.md`).
- **Full STATS19 dataset explored** across all three tables (1.9M collisions, 3.7M vehicles, 6.9M casualties) with missingness assessed (Evidence: `missingness_summary.csv`).
- **Filtered dataset to 2015–2024** and validated completeness of geographic coordinates and adjusted severity variables (Evidence: `filter_summary.csv`).
- **Initial trend and severity analysis completed**, showing stable fatalities but rising serious casualties (Evidence: `fig1_yearly_trend.png`, `fig2_severity_breakdown.png`, `fig4_casualty_type.png`).
- **COVID robustness check performed**, confirming that excluding 2020–2021 does not change overall trend direction (Evidence: `fig3_covid_robustness.png`, `table3_covid_robustness.csv`).
- **Generalized Linear Model (Poisson) implemented** to test the effect of the March 2020 lockdown, identifying a statistically significant reduction in casualties (Evidence: `glm_results_table.csv`, `glm_lockdown_model.png`, `glm_time_series_plot.png`).

---

### Planned work

| Planned item / work package | Owner | Target date | Output expected |
|-----------------------------|-------|-------------|-----------------|
| Full data cleaning pipeline (recoding, deduplication, validation) | ZA | 13 Mar 2026 | `clean_joined.csv`, `exclusions_log.csv` |
| Hotspot analysis – geographic severity mapping by local authority | PA | 23 Mar 2026 | `fig_hotspot_map.png`, `table_hotspot.csv` |
| Contributory factor analysis (speed limit, road type, junction, light conditions) | PA | 23 Mar 2026 | `fig_factors.png`, `table_factors.csv` |
| Robustness check using post-2016 severity definitions only | PA | 23 Mar 2026 | `table_robustness_severity.csv` |
| Executive summary skeleton drafted | CS | 16 Mar 2026 | `report/executive_summary_v0.md` |
| Full reproducibility test from repository root | AS | 13 Mar 2026 | QA log entry, `reproducibility_record.md` |

---

### Decisions required

- **Decision/request 1:** Confirm analysis time window (2015–2024 casualty trends vs. 2020–2024 full three-table analysis).  
  **By:** 10 March 2026  
  **Why it matters:** Determines whether the project prioritises longer-term trends or higher-quality recent data joins. Delay risks duplicated analysis work.

- **Decision/request 2:** Confirm preferred geographic resolution for hotspot analysis (local authority vs. police force area).  
  **By:** 10 March 2026  
  **Why it matters:** Defines hotspot methodology and determines how geographic risk will be reported.

- **Decision/request 3:** Confirm whether the contributory factors data request has been submitted to the Department for Transport (DfT).  
  **By:** 12 March 2026  
  **Why it matters:** Without approval, factor analysis will be limited to non-sensitive variables.

---

**Output format:** PDF
