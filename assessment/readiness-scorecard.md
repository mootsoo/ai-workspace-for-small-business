# AI Workspace Readiness Scorecard

Score each statement:

- **0** — not true
- **1** — partly true or inconsistent
- **2** — consistently true and verified

Maximum score: **100**

## A. Operational clarity — 20 points

| Statement | Score 0–2 |
|---|---:|
| We can describe our client or service workflow clearly |  |
| We know which records are required at each stage |  |
| Status and stage values have defined meanings |  |
| Every active record has one owner |  |
| Every active record has one next action |  |
| Every time-sensitive action has an absolute date |  |
| We can identify work waiting on our business |  |
| We can identify work waiting on the client |  |
| We have a weekly operating-review rhythm |  |
| We measure at least one operating outcome |  |

**Section score:** `/20`

## B. Information architecture — 20 points

| Statement | Score 0–2 |
|---|---:|
| Every active record has a stable ID |  |
| One Master Index exists |  |
| Every active record has a stable Hub or equivalent |  |
| Each important fact has a canonical location |  |
| Current truth is separated from detailed history |  |
| Folder and file naming is consistent |  |
| Canonical documents are linked rather than duplicated |  |
| A data dictionary defines important fields |  |
| Archive rules exist |  |
| The business can operate without relying on chat history |  |

**Section score:** `/20`

## C. Security and governance — 20 points

| Statement | Score 0–2 |
|---|---:|
| Dedicated business accounts are used |  |
| Multi-factor authentication or passkeys are enabled |  |
| Confidential folders use Restricted access |  |
| Users have the lowest sufficient permission |  |
| Shared logins are prohibited |  |
| Sensitive data is classified |  |
| Credentials are excluded from normal records and AI chats |  |
| Retention and deletion rules exist |  |
| AI-provider privacy and retention settings are reviewed |  |
| Incident response and accountability are defined |  |

**Section score:** `/20`

## D. AI operating readiness — 20 points

| Statement | Score 0–2 |
|---|---:|
| We have selected one to three bounded first use cases |  |
| The required connector capabilities were verified in the actual account |  |
| Read and write capabilities are distinguished |  |
| AI outputs cite their business-controlled sources |  |
| Facts, decisions, actions, suggestions, and uncertainty are separated |  |
| Read-only tests were completed with fictional or non-sensitive data |  |
| Unrelated records were excluded during testing |  |
| Approval rules are explicit |  |
| One assistant owns each write task |  |
| The business remains usable if the AI provider is disconnected |  |

**Section score:** `/20`

## E. Measurement and evolution — 20 points

| Statement | Score 0–2 |
|---|---:|
| We know the current time spent on the pilot workflow |  |
| We can count missed or overdue actions |  |
| We review unsupported AI claims and errors |  |
| We record permission or data-mixing incidents |  |
| We measure user adoption |  |
| We know the cost of current tools |  |
| We know which manual steps repeat frequently |  |
| We have criteria for adding automation |  |
| We have criteria for adding a CRM or database |  |
| Technology decisions are tied to measured evidence |  |

**Section score:** `/20`

# Total score

```text
Operational clarity:       /20
Information architecture:  /20
Security and governance:   /20
AI operating readiness:    /20
Measurement and evolution: /20

TOTAL:                      /100
```

## Interpretation

| Score | Interpretation | Recommended next step |
|---:|---|---|
| 0–24 | Foundations are missing | Do not connect sensitive business data. Map the workflow and organize records first. |
| 25–44 | Early structure exists | Build the Master Index, stable IDs, Hubs, and permission model. |
| 45–64 | Ready for a bounded read-only pilot | Connect one provider and test with fictional or non-sensitive data. |
| 65–79 | Ready for controlled operating use | Use meeting preparation, reviews, and draft workflows; measure results. |
| 80–89 | Ready for selective write actions and automation assessment | Add low-risk writes and evaluate repeatable cross-system workflows. |
| 90–100 | Strong foundation for advanced architecture decisions | Evaluate CRM, automation, Postgres, MCP, or custom apps based on business evidence. |

## Critical overrides

Regardless of score, do not proceed with sensitive live data if any is true:

- confidential folders are broadly shared;
- shared passwords are used;
- connector scopes are unknown;
- approval settings are not understood;
- the assistant mixed records during testing;
- users cannot identify source evidence;
- credentials are stored in normal documents or chats;
- accountability for official records is unclear;
- legal or professional duties have not been assessed where required.

## Lead conversation

A score identifies the maturity level, not the solution.

The next discussion should ask:

1. Which missing control creates the largest business risk?
2. Which workflow creates the largest operating cost?
3. Which improvement can be proven in 30 days?
4. What should remain human-controlled?
5. What evidence would justify the next technology investment?
