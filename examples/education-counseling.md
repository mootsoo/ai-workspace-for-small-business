# Case Study: Independent Education Counseling Practice

**All organizations, students, records, and data in this example are fictional.**

## Business profile

A small education counseling practice supports high-school students and families through planning, application preparation, essays, deadlines, and school decisions.

The practice already uses:

- Google Drive for student folders and documents;
- Google Sheets for student tracking;
- Gmail for family communication;
- Google Calendar for counseling sessions;
- ChatGPT and/or Claude for drafting and analysis.

## Before

The counselor experiences:

- student history spread across several documents;
- inconsistent folder names;
- deadlines stored in different places;
- session notes that do not always produce a next action;
- significant meeting-preparation time;
- privacy risk from broad file sharing;
- pressure to buy or build a CRM before the workflow is fully understood.

## Record model

Each student receives a permanent fictional Case ID:

```text
STU-DEMO-001
```

### Master Student Index

| Field | Example |
|---|---|
| Case ID | STU-DEMO-001 |
| Display name | Maya Demo |
| Status | Active |
| Stage | College or program list |
| Operational risk | Medium |
| Next action | Confirm preliminary college list |
| Action owner | Student |
| Next action date | 2026-08-18 |
| Student Hub URL | Fictional restricted Drive URL |
| Folder URL | Fictional restricted Drive URL |
| Waiting on | Preferences questionnaire |

### Student folder

```text
STU-DEMO-001 — Maya Demo/
├── 00 Student Hub
├── 01 Profile and Goals
├── 02 Counseling Plan
├── 03 Session Notes/
├── 04 Application Tracker
├── 05 Essays and Documents/
└── 06 Parent Communication Log
```

## AI operating flow

### Before a session

```text
Work only on STU-DEMO-001.
Use the Student Hub, latest approved session note, Counseling Plan, and Application Tracker.
Prepare a 45-minute session agenda.
Separate confirmed facts, decisions, suggestions, and needs confirmation.
Cite every source.
Do not change anything.
```

### After a session

The counselor dictates rough notes. The assistant formats them into the standard template without adding facts.

The counselor reviews the note, then asks the assistant to propose exact updates to:

- current stage;
- risk;
- next action;
- action owner;
- next action date;
- last session date;
- next session date;
- latest Student Hub summary.

Every proposed change shows Before, After, and Why.

### Weekly review

The assistant uses only the Master Student Index to identify:

- overdue actions;
- deadlines in the next 14 days;
- high-risk cases;
- active students with no next action;
- students with no recent session;
- items waiting on the counselor.

Detailed student folders are retrieved only when the counselor authorizes a specific case task.

## Privacy boundary

- Student folders use Restricted sharing.
- Real student records are not stored in GitHub.
- One identifiable case is handled per bounded chat or task.
- Passwords and university-portal credentials are excluded.
- The counselor approves official notes and communication.
- The AI assistant does not make admissions or counseling decisions.
- Consent, retention, and jurisdiction-specific duties are handled outside this public example.

## What the pilot measures

| Metric | Before | Pilot target |
|---|---:|---:|
| Meeting-preparation time | 30 minutes | 10 minutes |
| Active students with a dated next action | 55% | 95% |
| Overdue counselor-owned actions | Unknown | Visible weekly |
| Session notes completed within 24 hours | 60% | 90% |
| Cross-student data-mixing incidents | Not measured | 0 in acceptance testing |

The numbers are fictional examples, not claims of actual performance.

## When a custom system becomes justified

The practice considers Postgres and a controlled connector when:

- active student volume grows materially;
- several counselors require role-based access;
- cross-student reporting becomes unreliable;
- a structured audit trail is required;
- forms, billing, communication, and deadlines require transaction-safe synchronization;
- repeated manual updates create measurable cost or error.

Until then, the lightweight system provides immediate learning and operating value.
