# Master Client Index Template

Use one row per client, case, project, or engagement. Adapt the nouns to the business, but preserve stable identity, ownership, and dates.

## Recommended columns

| Column | Field | Purpose |
|---:|---|---|
| A | Record ID | Permanent identifier such as `CLIENT-2026-001` |
| B | Display name | Operational name used by the team |
| C | Record type | Lead, client, project, case, engagement, or another controlled value |
| D | Status | Current lifecycle status |
| E | Stage | Current business-process stage |
| F | Risk | Low, Medium, or High operational risk |
| G | Next action | One clear next action |
| H | Action owner | Person or role responsible |
| I | Next action date | Absolute date |
| J | Last interaction date | Absolute date |
| K | Next meeting date | Absolute date or blank |
| L | Hub URL | Stable URL of the current Hub document |
| M | Folder URL | Stable URL of the Drive folder |
| N | Waiting on | Person, role, input, or external event |
| O | Brief note | Short non-sensitive operating note |

## Setup rules

- Freeze the header row.
- Enable filters.
- Use ISO-style dates: `YYYY-MM-DD`.
- Use dropdowns for Record type, Status, Stage, Risk, and Action owner when practical.
- Keep one row per record.
- Do not store passwords, tokens, payment credentials, or unnecessary sensitive details.
- Link to the canonical document rather than copying large notes into the Sheet.
- Archive rather than reuse an old Record ID.

## Generic statuses

| Status | Meaning |
|---|---|
| Prospective | Not yet an active engagement |
| Active | Receiving deliberate work |
| Waiting | Progress depends mainly on another party or event |
| Paused | Intentionally paused with a restart condition |
| Completed | Agreed outcome or stopping point reached |
| Archived | Retained for history, no longer active |

## Generic operational risk

Risk describes delivery or follow-through risk, not the quality or character of a client.

| Risk | Meaning |
|---|---|
| Low | Work is on track and no critical dependency is overdue |
| Medium | A delayed action, missing input, or approaching deadline needs attention |
| High | A critical commitment, deadline, decision, or dependency is likely to fail without immediate action |

## AI review prompt

```text
Read the Master Client Index and produce an operations review as of [DATE].

Report:
1. overdue actions;
2. deadlines in the next 14 days;
3. High-risk records;
4. Active records with no next action;
5. records with no interaction in the last 21 days;
6. work waiting on our business;
7. recommended priority order.

Use only the Index unless I explicitly authorize detailed record retrieval.
Cite the relevant rows or source.
Do not change anything.
```

## Data dictionary section

Add a second Sheet tab named `Definitions` containing:

- field name;
- type;
- allowed values;
- owner;
- update trigger;
- example;
- sensitivity class.

This makes later database migration and AI use more reliable.
