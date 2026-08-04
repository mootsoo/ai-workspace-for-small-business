# Case Study: Field Service Contractor

**This is a fictional operating-model example.** It can represent a maintenance company, equipment installer, repair business, construction subcontractor, interior-fit-out team, inspection service, or another small business that coordinates office staff and field crews.

## Business profile

A twelve-person field-service contractor manages customer inquiries, site inspections, quotations, jobs, crews, materials, photos, completion evidence, invoices, and follow-up. The business already uses:

- Google Drive for quotations, contracts, drawings, site photos, and completion documents;
- Google Sheets for inquiries, jobs, materials, and payment follow-up;
- Gmail for customer and supplier communication;
- Google Calendar for inspections, crew schedules, and deadlines;
- ChatGPT and/or Claude for retrieval, drafting, summarization, and review.

The company is considering a field-service platform but first needs to understand which operational records and handoffs are actually failing.

## Operating problem

The business experiences:

- inquiries that are not converted into clearly owned next actions;
- site-visit notes stored in personal phones, notebooks, or chat threads;
- quotations with inconsistent names and unclear approval status;
- crews arriving without the latest scope, drawing, or access instructions;
- site photos that are difficult to match to the correct job and date;
- material shortages discovered after the crew is scheduled;
- completion evidence that is not returned to the office promptly;
- customer promises and change requests hidden inside email or messaging history;
- invoices delayed because completion status is uncertain;
- too much operational knowledge concentrated in the owner or dispatcher.

## Core operating flow

```text
Customer inquiry
→ qualification
→ site inspection
→ quotation
→ customer approval
→ job planning
→ crew and material assignment
→ field execution
→ quality check and completion evidence
→ invoice
→ warranty or follow-up
```

The AI workspace supports this flow by making each handoff visible. It does not authorize technical work, safety decisions, commercial changes, or field completion.

## Canonical record model

### Stable identifiers

Each customer, site, quotation, and job receives a permanent identifier:

```text
CUSTOMER-2026-018
SITE-2026-011
QUOTE-2026-043
JOB-2026-027
```

The Job ID appears in:

- the Master Job Index;
- calendar events;
- job folders;
- quotation and scope documents;
- site-visit notes;
- material lists;
- field-photo folders;
- completion records;
- invoice references;
- future database records.

### Master Job Index

One row per job, containing:

- Job ID;
- Customer ID;
- Site ID;
- job title;
- status;
- current stage;
- operational risk;
- assigned coordinator;
- crew lead;
- scheduled start;
- target completion;
- next action;
- action owner;
- action date;
- quotation status;
- material readiness;
- site-access readiness;
- Job Hub URL;
- restricted folder URL;
- waiting-on field.

### Job Hub

The Job Hub contains the current operational truth:

- customer and site details;
- agreed scope;
- approved quotation and exclusions;
- technical contact;
- access instructions;
- safety or permit dependencies;
- current stage;
- assigned team;
- material status;
- planned dates;
- approved changes;
- risks and blockers;
- next actions;
- links to drawings, notes, photos, and completion evidence.

### Site-visit record

Each inspection or visit records:

- Job or Opportunity ID;
- date and attendees;
- observed conditions;
- measurements and evidence;
- customer requests;
- technical questions;
- assumptions;
- risks;
- required follow-up;
- photos and files;
- items needing confirmation.

## Suggested Drive structure

```text
JOB-2026-027 — Example Installation/
├── 00 Job Hub
├── 01 Inquiry and Site Visit/
│   ├── Site Visit Note
│   └── Photos/
├── 02 Commercial/
│   ├── Quotation
│   ├── Approved Scope
│   └── Change Requests/
├── 03 Planning/
│   ├── Drawings and Specifications/
│   ├── Material List
│   └── Crew Brief
├── 04 Field Execution/
│   ├── Daily Notes/
│   └── Progress Photos/
├── 05 Completion/
│   ├── Quality Checklist
│   ├── Completion Photos/
│   └── Customer Sign-off
└── 90 Archive/
```

## AI-assisted workflows

### 1. Inquiry and quotation review

```text
Read only the New Inquiry Index and the approved inquiry documents.
Identify:
- inquiries with no owner;
- site visits not yet scheduled;
- quotations overdue for preparation;
- quotations awaiting customer response;
- records with missing site or contact details.

Separate confirmed facts from missing information.
Do not create prices, technical scope, or commitments.
Do not change any record.
```

### 2. Pre-job readiness check

```text
Work only on JOB-2026-027.
Use the Job Hub, approved quotation, latest site-visit note,
material list, drawings, and scheduled Calendar event.

Prepare a readiness report covering:
- confirmed scope;
- crew assignment;
- material readiness;
- site access;
- permits or safety dependencies;
- customer decisions still required;
- conflicting dates or instructions;
- items that must be confirmed before dispatch.

Cite every source. Do not mark the job Ready.
```

### 3. Crew brief preparation

The assistant prepares a draft field brief from approved sources:

- Job ID and site;
- scope and exclusions;
- latest drawings or specifications;
- customer contact and access instructions;
- planned sequence;
- required materials and tools;
- known hazards or dependencies;
- evidence required before leaving the site;
- escalation contact.

The coordinator and crew lead review and approve the brief. The assistant must not invent technical instructions.

### 4. Field-note processing

The crew or coordinator provides rough notes and uploaded evidence. The assistant:

- organizes notes by date and Job ID;
- separates observations, customer requests, completed work, defects, and proposed changes;
- identifies missing photos or sign-off evidence;
- proposes updates to the Job Hub and Master Job Index;
- presents material status or date changes as Before, After, and Why.

A human verifies the actual work and approves the official record.

### 5. Completion-package preparation

```text
Work only on JOB-2026-027.
Use the approved scope, daily notes, quality checklist,
completion photos, and customer sign-off record.

Prepare a completion-package index showing:
- agreed work;
- documented completion evidence;
- open defects or exceptions;
- customer approvals received;
- missing evidence;
- invoice-readiness questions.

Do not declare the job complete, accepted, safe, compliant, or invoice-ready.
```

### 6. Weekly operations review

Using only the Master Job Index, the assistant reports:

- overdue company-owned actions;
- jobs starting in the next seven days with incomplete readiness;
- jobs blocked by materials, access, customer decisions, or permits;
- jobs with no next action;
- jobs awaiting completion evidence;
- completed work awaiting invoicing review;
- high-risk jobs requiring management attention.

## Human-control boundaries

The AI assistant may retrieve, compare, organize, summarize, and draft within an authorized job scope.

It must not independently:

- determine that work is technically correct or safe;
- approve a quotation, discount, change order, or refund;
- modify the agreed scope;
- dispatch or reassign a crew;
- mark materials as physically received;
- certify regulatory or permit compliance;
- declare a job complete or customer-accepted;
- approve an invoice;
- send customer communication;
- alter site access or file permissions;
- combine records from unrelated jobs.

## Governance rules

- Job ID is required on operational files and Calendar events;
- only approved scope and drawings are used for crew briefs;
- field evidence returns to the restricted job folder;
- change requests remain proposed until commercially and technically approved;
- consequential updates show Before, After, and Why;
- safety and technical judgment remain with qualified humans;
- one assistant owns each write task;
- customer, employee, and site data remain restricted;
- public repositories contain templates only, never live job records.

## Pilot metrics

| Metric | Fictional baseline | Pilot review question |
|---|---:|---|
| New inquiries with a dated next action | 65% | Can the system reach at least 95%? |
| Jobs starting with a complete approved crew brief | 50% | Can it reach at least 90%? |
| Time to prepare a crew brief | 25 minutes | Can it fall below 10 minutes? |
| Jobs delayed by missing information | 5 per month | Does readiness review reduce the number? |
| Completion evidence returned within 24 hours | 55% | Can the process reach at least 90%? |
| Completed jobs awaiting invoice review | 8 | Can the queue remain visible and below 3? |

The figures are fictional planning values, not performance claims.

## Technology decision after 90 days

The company reviews evidence:

- adopt a field-service management platform when dispatch, technician mobile workflows, routing, work orders, and customer notifications require real-time coordination;
- add inventory or ERP capability when stock, purchasing, costing, and fulfillment must be transactional;
- add selective workflow automation when stable events need reminders, folder creation, or cross-system updates;
- add PostgreSQL and controlled tools when job records, role-based access, audit history, and reporting exceed the safe limits of Sheets;
- retain Google Workspace for documents and evidence even after a specialized operational system is introduced.

The pilot clarifies what the future system must solve instead of purchasing a large platform around an undocumented workflow.