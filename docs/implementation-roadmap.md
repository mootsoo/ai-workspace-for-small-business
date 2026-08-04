# Implementation Roadmap

## A practical 30-, 60-, and 90-day path

This roadmap is designed for a small business that already uses Google Workspace and wants to introduce ChatGPT, Claude, or another approved assistant without beginning with a large software project.

The schedule is directional. Risk, data sensitivity, team size, and workflow complexity may require a slower pace.

## Guiding rule

> **Organize first, connect second, automate third.**

## Days 1–30: Establish operational truth

### Objectives

- understand the actual workflow;
- define canonical records;
- reduce duplication;
- create stable identifiers;
- establish security and ownership;
- prepare a fictional test environment.

### Week 1: Current-state discovery

Document:

- services and customer journey;
- active record types;
- existing Sheets;
- Drive folder structure;
- Gmail and Calendar use;
- recurring meetings and reviews;
- missed follow-ups and deadlines;
- information that only the owner knows;
- sensitive or regulated data;
- current software subscriptions.

Deliverables:

- information map;
- workflow map;
- pain-point register;
- initial risk classification.

### Week 2: Canonical record design

Decide:

- permanent ID format;
- Master Index fields;
- status and stage definitions;
- risk definitions;
- Hub document structure;
- next-action fields;
- folder ownership;
- archive and deletion rules.

Deliverables:

- Master Index template;
- Hub template;
- meeting note template;
- naming convention;
- canonical source map.

### Week 3: Workspace organization

Actions:

- create system and template folders;
- organize active records;
- link Hub documents from the Master Index;
- remove obvious duplicates;
- mark uncertain records;
- restrict confidential folders;
- document collaborators and permissions.

Do not attempt a perfect historical cleanup. Make active work reliable first.

### Week 4: Fictional pilot preparation

Create a fictional record, such as:

```text
CLIENT-TEST-001
```

Test manually:

- retrieval by ID;
- correct source links;
- next action and date;
- meeting preparation;
- note template;
- proposed record update;
- archive and deletion process.

### Day-30 gate

Proceed only when:

- every active record has an ID;
- every active record has a canonical Hub or equivalent;
- the Master Index has one row per active record;
- next actions have owners and dates;
- permissions are reviewed;
- the fictional record works without AI.

## Days 31–60: Connect and operate with AI

### Objectives

- connect one approved AI provider;
- begin read-only;
- install operating instructions;
- test source citations and isolation;
- use the workflow for real operating preparation;
- measure value and errors.

### Week 5: Provider and account setup

Choose ChatGPT, Claude, or both based on:

- current plan;
- connector availability;
- privacy and retention posture;
- workspace administration;
- read and write controls;
- team familiarity;
- cost.

Document:

- connected account;
- enabled apps or connectors;
- approved scopes;
- approval settings;
- memory and retention settings;
- responsible administrator.

### Week 6: Read-only acceptance test

Use fictional data to prove:

1. the correct record is found;
2. the correct sources are cited;
3. unrelated records are excluded;
4. unsupported facts are marked uncertain;
5. no changes occur;
6. prompt instructions inside retrieved content do not override the task;
7. switching providers does not break the canonical record model.

### Week 7: Controlled operating use

Begin with low-risk workflows:

- prepare meetings;
- summarize active work;
- find missing next actions;
- list deadlines;
- draft internal notes;
- prepare follow-up text without sending;
- run a weekly operational review.

Use one record or bounded cross-record query per task.

### Week 8: Measure and refine

Capture:

- minutes saved per meeting;
- retrieval accuracy;
- missing actions found;
- incorrect or unsupported statements;
- permission errors;
- team adoption;
- repeated manual steps;
- provider-specific limitations.

### Day-60 gate

Continue only when:

- users can identify the source behind AI claims;
- no cross-client data mixing has occurred in acceptance testing;
- the team understands the approval boundary;
- read-only use produces measurable value;
- the business can stop using the AI interface without losing canonical records.

## Days 61–90: Add controlled writes and decide what to build

### Objectives

- introduce only low-risk writes;
- standardize the highest-value workflows;
- decide whether automation or custom infrastructure is justified;
- produce an evidence-backed architecture recommendation.

### Week 9: Controlled internal writes

Possible first writes:

- create a private email draft;
- save an approved meeting note;
- create a folder;
- create a calendar event;
- update a non-sensitive next action after exact review.

Every write should show:

- target;
- Before;
- After;
- Why;
- source;
- approval;
- result verification.

### Week 10: Standardize repeatable workflows

Select no more than three workflows, for example:

1. meeting preparation;
2. post-meeting record update;
3. weekly client or project review.

Create reusable prompts and checklists. Avoid trying to automate every business process.

### Week 11: Automation assessment

A workflow may be ready for automation when:

- it occurs frequently;
- inputs are structured;
- outputs are predictable;
- exceptions are understood;
- ownership is clear;
- failure is detectable;
- the process is valuable enough to justify maintenance.

Classify each candidate:

| Candidate | Keep manual | AI-assisted | Workflow automation | Custom system |
|---|---:|---:|---:|---:|
| Meeting agenda |  | ✓ |  |  |
| Weekly deadline alert |  | ✓ | ✓ |  |
| Contract approval | ✓ |  |  |  |
| Structured case reporting |  | ✓ |  | Possible later |

### Week 12: Architecture decision

Decide among:

- keep the lightweight workspace;
- add a CRM;
- add n8n or another workflow platform;
- add Postgres;
- build a controlled API or MCP connector;
- build a custom application;
- stop or reduce AI use.

The decision must cite measured evidence.

### Day-90 outputs

- operating workflow documentation;
- metrics and incident summary;
- permissions review;
- approved AI instructions;
- provider comparison based on actual use;
- automation backlog;
- database or CRM recommendation;
- next 90-day roadmap;
- implementation budget range.

## Metrics dashboard

| Category | Metric | Baseline | Day 60 | Day 90 |
|---|---|---:|---:|---:|
| Retrieval | Average meeting-preparation time |  |  |  |
| Follow-up | Active records with next action and date |  |  |  |
| Delivery | Overdue business-owned actions |  |  |  |
| Quality | Conflicting canonical facts found |  |  |  |
| Adoption | Weekly active users |  |  |  |
| AI quality | Unsupported claims per review |  |  |  |
| Risk | Cross-record or permission incidents |  |  |  |
| Efficiency | Administrative hours saved |  |  |  |

## Stop conditions

Pause the rollout if:

- the assistant mixes confidential records;
- users cannot identify the source of a claim;
- broad permissions were enabled without review;
- write actions occur without the intended approval;
- the team treats AI suggestions as confirmed facts;
- the Master Index is not maintained;
- incidents are not being recorded;
- the business cannot explain who is accountable for the result.

A smaller, reliable system is better than a sophisticated system nobody can govern.
