# When Google Workspace Is No Longer Enough

A lightweight AI workspace is a starting architecture, not a promise that spreadsheets can run every business forever.

The goal is to learn where complexity is justified.

## 1. Keep the lightweight system when

- the team is small;
- active records are manageable;
- one row per client or case is sufficient;
- reporting is simple;
- write concurrency is low;
- permissions are not highly granular;
- the workflow is still evolving;
- manual approval remains practical;
- Google Workspace remains the natural document environment;
- the business is still proving value.

## 2. Consider a CRM when

- the primary problem is sales pipeline management;
- stages and conversion reporting are stable;
- several salespeople collaborate;
- activities, contacts, and opportunities require standard reporting;
- email and marketing integrations are central;
- the business will consistently maintain the CRM;
- a mature commercial product meets the need better than custom software.

A CRM should replace duplicated tracking, not create another copy.

## 3. Consider workflow automation when

- a process repeats frequently;
- trigger and outcome are well defined;
- exceptions are understood;
- failure is visible;
- the workflow crosses several systems;
- manual routing consumes material time;
- the automation does not need to own canonical business judgment.

Examples for n8n, Make, Zapier, or custom automation:

```text
New website inquiry
→ validate required fields
→ create proposed lead record
→ notify owner
```

```text
Meeting completed
→ remind record owner to approve notes
```

```text
Deadline approaching
→ create internal alert
→ prepare draft follow-up
→ wait for human approval
```

Do not place core record truth or high-impact decision logic only inside a visual workflow.

## 4. Consider PostgreSQL when

- several users edit records concurrently;
- relationships between clients, projects, actions, and documents become complex;
- structured reporting exceeds practical Sheet formulas;
- duplicate or conflicting data becomes common;
- state transitions require validation;
- role-based access is required;
- audit history matters;
- integrations need transaction-safe writes;
- record volume or operational importance justifies engineering and maintenance;
- the business needs an API or customer-facing application.

## 5. Consider a controlled API or MCP connector when

The business wants ChatGPT, Claude, or another assistant to retrieve and update structured records reliably.

A good tool layer exposes business operations rather than database primitives.

### Good

```text
get_client_summary(client_id)
list_overdue_actions(owner_id, as_of_date)
propose_stage_change(client_id, new_stage, reason)
add_approved_meeting_note(client_id, note, approval_id)
```

### Bad

```text
run_sql(query)
delete_any_record(table, id)
execute_shell(command)
```

The narrow interface can enforce:

- authentication;
- authorization;
- required fields;
- allowed states;
- date and identifier validation;
- tenant boundaries;
- idempotency;
- audit history;
- approval requirements;
- redaction and safe errors.

## 6. Consider a custom application when

- non-technical users need a dedicated interface;
- the workflow is a product differentiator;
- customers need direct access;
- role-based dashboards are required;
- mobile or field use matters;
- integrations must be invisible to users;
- the business model can support product maintenance;
- a commercial product cannot meet the requirement economically.

## 7. Decision matrix

| Signal | Workspace only | CRM | Automation | Postgres + tools | Custom app |
|---|---:|---:|---:|---:|---:|
| Small team, evolving workflow | ✓ |  |  |  |  |
| Stable sales pipeline |  | ✓ | Possible | Possible |  |
| Cross-system repetitive routing |  |  | ✓ | Possible |  |
| Complex relational records |  |  |  | ✓ | Possible |
| Strict audit and permissions |  | Possible |  | ✓ | Possible |
| Customer-facing workflow |  | Possible |  | ✓ | ✓ |
| High transaction volume |  | Possible | Possible | ✓ | ✓ |
| Unique proprietary process |  |  | Possible | ✓ | ✓ |

## 8. Evidence required before building

Do not approve custom development using only statements such as:

- “It would be nice.”
- “AI should automate this.”
- “Spreadsheets are not professional.”
- “Competitors have a CRM.”

Collect:

- record count and growth;
- active users;
- error frequency;
- duplicate-entry effort;
- hours spent reconciling data;
- reporting requirements;
- permission requirements;
- incident history;
- revenue or cost affected;
- customer or employee adoption evidence;
- commercial software alternatives;
- estimated build and operating cost.

## 9. Migration-ready pilot design

The lightweight system should make migration easier by preserving:

- permanent IDs;
- consistent status and stage values;
- explicit owners;
- normalized dates;
- stable Drive file IDs or URLs;
- one canonical row per record;
- reusable templates;
- documented field definitions;
- archive rules;
- provider-neutral AI instructions.

A future database row might include:

```json
{
  "client_id": "CLIENT-2026-001",
  "status": "active",
  "stage": "delivery",
  "risk": "medium",
  "next_action": "Review draft proposal",
  "action_owner": "Tsolmon",
  "next_action_date": "2026-08-18",
  "hub_url": "https://docs.google.com/...",
  "folder_url": "https://drive.google.com/..."
}
```

The documents stay in Drive while structured truth moves into Postgres.

## 10. Final decision rule

> **Build the custom system when repeated operational pain, risk, volume, or business value justifies its lifecycle cost.**

Software has a continuing cost: security, hosting, support, upgrades, backups, monitoring, documentation, user training, and governance. The decision should include those costs, not only initial development.
