# Case Study: Client Delivery Business

**This is a fictional operating-model example.** It can represent a consulting firm, creative agency, engineering practice, software studio, research service, architecture office, or another business that delivers knowledge-intensive work for clients.

## Business profile

A five-person client-delivery business manages twenty active clients and several overlapping projects. The team already uses:

- Google Drive for proposals, contracts, meeting notes, research, and deliverables;
- Google Sheets for client and project tracking;
- Gmail for client communication and approvals;
- Google Calendar for meetings, milestones, and deadlines;
- ChatGPT and/or Claude for drafting, analysis, and retrieval.

The business is considering a CRM, a project-management platform, and custom software, but it has not yet defined which system should own each fact.

## Operating problem

The business experiences:

- proposals and deliverables with inconsistent names;
- client status that depends on the founder’s memory;
- meeting decisions left inside email threads or personal notes;
- different pipeline and delivery stages used by different team members;
- active projects with no clearly dated next action;
- several versions of the same status across Sheets, Docs, and chat;
- weekly status preparation that requires manual reconstruction;
- pressure to buy software before the operating model is clear.

## Core operating flow

```text
Lead or referral
→ qualification
→ proposal
→ signed engagement
→ project delivery
→ client review and approval
→ completion
→ follow-up or renewal
```

The AI workspace does not replace this workflow. It gives every stage a clear record, owner, and evidence trail.

## Canonical record model

### Stable identifiers

Each client and project receives a permanent identifier:

```text
CLIENT-2026-001
PROJECT-2026-014
```

The identifiers appear in:

- the Master Client Index;
- the Master Project Index;
- folder names;
- Client and Project Hubs;
- meeting notes;
- approved deliverables;
- future database records.

### Master Client Index

One row per client, containing:

- Client ID;
- client display name;
- relationship status;
- account owner;
- current opportunity or engagement;
- next relationship action;
- action owner;
- action date;
- last interaction;
- next meeting;
- Client Hub URL;
- restricted folder URL;
- waiting-on field.

### Master Project Index

One row per active project, containing:

- Project ID;
- Client ID;
- project name;
- delivery stage;
- operational risk;
- current milestone;
- next action;
- action owner;
- due date;
- Project Hub URL;
- current deliverable URL;
- waiting-on field.

### Client Hub

The Client Hub contains the current relationship truth:

- relationship purpose;
- active and past engagements;
- current priorities;
- commercial status;
- key decisions;
- open relationship actions;
- important contacts;
- links to proposals, contracts, projects, and approved correspondence.

### Project Hub

The Project Hub contains the current delivery truth:

- agreed outcome and scope;
- current milestone;
- completed work;
- open decisions;
- client dependencies;
- risks and blockers;
- next actions with owners and dates;
- links to meeting notes, plans, evidence, and deliverables.

## Suggested Drive structure

```text
CLIENT-2026-001 — Example Client/
├── 00 Client Hub
├── 01 Commercial/
│   ├── Proposals/
│   └── Contract/
├── 02 Projects/
│   └── PROJECT-2026-014 — Example Engagement/
│       ├── 00 Project Hub
│       ├── 01 Plan and Scope
│       ├── 02 Meeting Notes/
│       ├── 03 Working Files/
│       ├── 04 Deliverables/
│       └── 05 Evidence and Approval/
└── 90 Archive/
```

## AI-assisted workflows

### 1. Monday operations review

```text
Read only the Master Client Index and Master Project Index.
Report:
- overdue company-owned actions;
- milestones due in the next 14 days;
- High-risk projects;
- active clients or projects with no dated next action;
- items waiting on our team;
- items waiting on clients.

Recommend a priority order and explain the evidence.
Do not retrieve detailed folders unless I approve a specific follow-up.
Do not change any record.
```

### 2. Client meeting preparation

```text
Work only on CLIENT-2026-001 and PROJECT-2026-014.
Use the Client Hub, Project Hub, latest approved meeting note,
current proposal or scope, and latest deliverable.

Prepare:
- the meeting objective;
- confirmed current state;
- unresolved decisions;
- risks and dependencies;
- questions to ask;
- proposed next actions.

Cite every source. Do not change anything.
```

### 3. Meeting-note processing

The team provides rough notes. The assistant:

- formats the notes into the standard template;
- separates facts, decisions, actions, suggestions, and needs confirmation;
- does not add unsupported commitments;
- proposes updates to the Client Hub, Project Hub, and indexes;
- presents every material change as Before, After, and Why.

A human approves the official record.

### 4. Follow-up drafting

```text
Draft a concise follow-up for PROJECT-2026-014 using only the approved meeting note and agreed actions.
Verify the recipient role, dates, owners, price references, scope, and commitments.
Mark any unsupported point as Needs confirmation.
Do not create or send an email until I approve the final wording and recipient.
```

### 5. Project-status preparation

The assistant compares the Project Hub, approved plan, recent meeting decisions, and current deliverables to prepare:

- completed work;
- current milestone;
- evidence of progress;
- blockers;
- client decisions needed;
- next actions;
- forecast risks;
- links to supporting records.

## Human-control boundaries

The AI assistant may retrieve, compare, summarize, format, and draft within an authorized scope.

It must not independently:

- approve scope, price, or contract terms;
- promise a delivery date;
- change a client or project stage without review;
- send external communication;
- mark a deliverable accepted;
- alter invoices or financial commitments;
- delete records or change access permissions;
- mix information from unrelated clients.

## Governance rules

- one canonical location owns each current fact;
- the business chooses one active assistant per write task;
- email decisions return to the Hub or approved meeting record;
- consequential updates show Before, After, and Why;
- restricted folders remain restricted;
- provider-specific privacy, retention, and approval settings are documented;
- confidential data is not copied into public repositories or unapproved tools.

## Pilot metrics

| Metric | Fictional baseline | Pilot review question |
|---|---:|---|
| Weekly portfolio-status preparation | 3 hours | Can the team reduce this below 1 hour? |
| Active projects with a dated next action | 60% | Can the system reach at least 95%? |
| Client meeting preparation | 20 minutes | Can it reach 8 minutes with equal or better quality? |
| Missed internal deadlines | 4 per month | Does visibility reduce them materially? |
| Duplicate current-status fields | 3 locations | Can the team establish one canonical location? |
| Meeting notes approved within 24 hours | 55% | Can the workflow reach at least 90%? |

The figures are fictional planning values, not performance claims.

## Technology decision after 90 days

The business reviews evidence:

- adopt a CRM when opportunity management, sales forecasting, and account activity are the main unresolved problems;
- add project-management software when task dependencies, capacity planning, and team execution require richer coordination;
- add selective workflow automation when repeated cross-system handoffs are stable and measurable;
- add PostgreSQL and controlled API or MCP tools when structured records, role-based access, reporting, and audit history exceed the safe limits of Sheets;
- retain the lightweight workspace when it remains sufficient and well governed.

The purpose of the pilot is not to avoid software. It is to make the next software decision from operating evidence.