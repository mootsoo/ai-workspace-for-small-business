# Case Study: Small Professional-Services Firm

**This is a fictional example.**

## Business profile

A five-person advisory firm manages twenty active clients. The team uses Drive, Sheets, Gmail, and Calendar but has no consistent client operating model.

## Operating problem

- proposals and deliverables use inconsistent names;
- client status depends on the founder’s memory;
- meeting decisions remain in email or notes;
- different team members use different pipeline stages;
- weekly status preparation takes several hours;
- the firm is considering both a CRM and custom software.

## Lightweight architecture

### Master Client Index

One row per client:

```text
CLIENT-2026-001
```

The row contains:

- status;
- delivery stage;
- operational risk;
- next action;
- action owner;
- due date;
- last interaction;
- next meeting;
- Client Hub URL;
- folder URL;
- waiting-on field.

### Client Hub

The Hub contains:

- current outcome;
- latest factual position;
- current priorities;
- agreed scope;
- decisions;
- open actions;
- deadlines;
- risks;
- links to proposal, contract, notes, and deliverables.

## AI-assisted workflows

### 1. Monday operations review

```text
Read the Master Client Index.
Report overdue firm-owned actions, deadlines in the next 14 days, High-risk clients, clients with no next action, and work waiting on us.
Recommend a priority order.
Do not retrieve detailed client folders unless I approve a specific follow-up.
```

### 2. Meeting preparation

```text
Work only on CLIENT-2026-001.
Use the Client Hub, latest approved meeting note, active proposal, and current deliverable.
Prepare the meeting brief and cite each source.
Do not change anything.
```

### 3. Follow-up draft

```text
Draft a concise follow-up for CLIENT-2026-001 using only the approved meeting note and agreed actions.
Verify dates, owners, price, and commitments.
Do not create or send an email until I approve the recipient and final wording.
```

### 4. Project status

The assistant compares the current project plan, Hub, meeting decisions, and deliverables to prepare:

- completed work;
- current milestone;
- blockers;
- client decisions needed;
- next actions;
- evidence links.

## Governance

- the firm chooses one active assistant per write task;
- the Master Client Index is canonical for current operational state;
- email decisions are returned to the Hub or meeting record;
- write actions show Before, After, and Why;
- contracts, pricing, invoices, and external commitments require human approval;
- confidential folders remain restricted;
- provider-specific privacy and approval settings are documented.

## Pilot metrics

| Metric | Baseline | Review question |
|---|---:|---|
| Weekly status preparation | 3 hours | Can the team reduce this below 1 hour? |
| Active clients with complete next-action data | 60% | Can the system reach 95%? |
| Client meeting preparation | 20 minutes | Can it reach 8 minutes with equal or better quality? |
| Missed internal deadlines | 4 per month | Does visibility reduce them? |
| Duplicate client-status fields | 3 locations | Can the team establish one canonical location? |

These are fictional planning figures.

## Technology decision after 90 days

The firm reviews evidence:

- If sales reporting is the main unresolved need, adopt a CRM.
- If cross-system reminders are the main pain, add selective workflow automation.
- If structured delivery records and role-based access are the main pain, add Postgres and controlled tools.
- If the lightweight system is sufficient, keep it and avoid unnecessary software.

The pilot makes the later investment decision more informed.
