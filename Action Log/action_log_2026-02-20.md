# Action Log

**Module:** ST422 Statistical Consulting  
**Brief:** Brief 8 — Road Safety Analysis  
**Team:** Team 1  
**Last Updated:** 22 February 2026

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

---

## Blockers

| Action ID        | Blocker Description | Raised By | Resolution | Resolved Date |
| ---------------- | ------------------- | --------- | ---------- | ------------- |
| [None currently] | —                   | —         | —          | —             |

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
| Open        | 0     |
| In Progress | 5     |
| Complete    | 0     |
| Blocked     | 0     |
| **Total**   | **5** |
