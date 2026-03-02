# ST422 Team Shared Folder (Audit and Delivery)

## Purpose

This folder is the **shared team workspace** for ST422. It is **only visible to
team members** and is used to maintain an auditable record of progress,
attendance, and agreed decisions.

This folder is also used to provide **ongoing assurance to the client** (who
has access) that the project is active, organised, and progressing.

## Required contents

### 1) Attendance record

You must record attendance for the Monday weekly sessions.

- File: `TEAMx_ATTENDANCE.xlxs` (where `x` denotes the team number)
- Update: **every Monday** during the 0900 to 1200 session
- Minimum fields per week:
  - Date
  - Attendees present
  - Apologies
  - Notes (optional)

Note, this record will be checked against class attendance records.

### 2) Client brief selection

You must record which client brief your team is following.

- File: `SELECTION.md`
- Must include:
  - Selected brief title
  - Link to dataset/source
  - One-paragraph summary of the client decision context
  - Date agreed
- Update whenever the brief/data changes (include a change log entry).

### 3) Minutes of meetings

You must add the minutes of **all** meetings to this folder for audit purposes.
This includes:

- **Draft minutes** (same day as meeting where possible)
- **Approved minutes** (after agreement by the team)

Required structure:
- Create a folder: `minutes/`
- Naming convention:
  - Draft: `minutes/YYYY-MM-DD_meeting-title_DRAFT.md`
  - Approved: `minutes/YYYY-MM-DD_meeting-title_APPROVED.md`
- Minimum content in each set of minutes:
  - Date, attendees, agenda
  - Decisions made
  - Action log (action, owner, deadline, status, evidence pointer)

Update requirement:

- Minutes must be uploaded **at least weekly** so the client can be reassured
  of progress. But you must include all meeting minutes.

### 4) Management plan submission

Your completed management plan must be added **by the Moodle deadline** in
three formats:

- `management_plan.md`
- `management_plan.html`
- `management_plan.pdf`

Minimum expectation:

- The content should match the agreed template (workplan/milestones, risk
  register, QA plan).
- The Markdown version should be the "source of truth".
- The HTML/PDF should be rendered from the Markdown/RMarkdown source to avoid
  version drift.

## Recommended folder structure

- `README.md` (this file)
- `SELECTION.md`
- `ATTENDANCE.md`
- `management_plan.md`
- `management_plan.html`
- `management_plan.pdf`
- `minutes/`
  - `YYYY-MM-DD_weekly-sync_DRAFT.md`
  - `YYYY-MM-DD_weekly-sync_APPROVED.md`
  - `...`
- `evidence/` (optional)
  - screenshots, exports, supporting artefacts referenced in minutes

## Operating expectations

- Keep records **current** and **action-led**.
- Every action should have an owner, deadline, and an evidence pointer (e.g.,
  PR number, commit hash, file name, or link).
- Use consistent naming so an external reviewer can audit the project quickly.

## Quick checklist (minimum weekly compliance)

- [ ] Attendance updated for Monday session (`ATTENDANCE.md`)
- [ ] Weekly minutes uploaded (draft and/or approved in `minutes/`)
- [ ] Action log statuses updated in the latest minutes
- [ ] Any changes to the client brief recorded (`SELECTION.md`)