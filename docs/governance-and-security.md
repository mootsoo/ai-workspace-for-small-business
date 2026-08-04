# Governance and Security

## Practical controls for a small-business AI workspace

This document defines the minimum operating controls for connecting ChatGPT, Claude, or another assistant to Google Workspace.

It is not legal, privacy, cybersecurity, or regulatory certification. Businesses handling regulated, confidential, financial, health, education, legal, or other sensitive data should obtain appropriate specialist advice.

## 1. Governance objective

The objective is not to eliminate all risk. It is to make authority, information access, record ownership, and action boundaries explicit enough that the business can operate deliberately.

A safe operating principle is:

> **AI may retrieve and prepare within its authorized scope. People remain accountable for consequential records and actions.**

## 2. Roles

| Role | Responsibilities |
|---|---|
| Business owner | Approves the architecture, risk tolerance, external actions, and high-impact changes |
| Record owner | Maintains the accuracy and lifecycle of a client, project, case, or process record |
| Workspace administrator | Controls Google and AI-provider access, scopes, apps, roles, and account security |
| AI user | Uses the approved task contract, reviews sources, and verifies outputs |
| Technical implementer | Configures integrations and controls without expanding authority silently |
| Specialist adviser | Provides legal, privacy, security, or professional guidance when required |

One person may hold several roles in a small company, but the responsibilities should still be distinguished.

## 3. Data classification

Use a simple classification before connecting AI.

| Class | Example | Default handling |
|---|---|---|
| Public | Published website copy | Broad access may be acceptable |
| Internal | Templates, internal procedures | Authorized staff and approved AI tools |
| Confidential | Client proposals, contracts, private correspondence | Restricted access and minimum retrieval |
| Highly sensitive | Credentials, identity documents, regulated records, payment details | Do not expose through the ordinary AI workspace without a specific approved design |

The AI workspace should never be treated as a reason to collect more data than the business needs.

## 4. Account controls

Minimum controls:

- use dedicated business accounts where practical;
- enable strong multi-factor authentication or passkeys;
- store unique passwords in a password manager;
- review recovery methods;
- remove former staff and devices;
- avoid shared login credentials;
- use managed workspaces for multi-user or sensitive operations when practical;
- review connected third-party applications regularly.

## 5. Google Drive sharing

For confidential records:

- prefer **Restricted** general access;
- share with specific accounts;
- choose the lowest sufficient role;
- limit Editor permission;
- prevent resharing where the account settings allow it;
- review inherited folder permissions;
- avoid placing confidential records in a folder whose parent has broad access;
- use a shared drive when organization ownership and role management justify it.

“Anyone with the link” should be a deliberate exception, not the default.

## 6. AI connector controls

Before use, document:

- which Google account is connected;
- which AI provider and plan are used;
- which apps or connectors are enabled;
- read and write capabilities;
- approved OAuth scopes;
- workspace-admin action controls;
- when user approval is required;
- conversation retention and deletion settings;
- whether memory or personalization can use connected information;
- whether product feedback may expose content.

Do not assume ChatGPT and Claude have identical behavior.

## 7. Read-first deployment

Begin with read-only use cases:

- search for a document;
- retrieve a record by stable ID;
- prepare a meeting;
- identify missing next actions;
- summarize deadlines;
- draft text without saving or sending.

Only add write actions after the business has proven:

- the right source is retrieved;
- record identity is unambiguous;
- the user can see the target and effect;
- the proposed change is bounded;
- approval happens before the action;
- the result can be verified;
- errors fail safely.

## 8. Approval policy

A proposed write should display:

1. target system and record;
2. exact proposed change;
3. Before;
4. After;
5. Why;
6. source evidence;
7. privacy or sharing effect;
8. whether the action can be reversed.

For external communication, verify:

- recipient;
- subject;
- claims;
- dates;
- price or commercial terms;
- attachments;
- confidentiality;
- whether the message creates a commitment.

## 9. Provider-neutral single-writer policy

When both ChatGPT and Claude are used:

- either may perform approved read-only analysis;
- only one assistant should own a specific write task;
- the source must be refreshed before another assistant proposes a later change;
- a human verifies the canonical record after each write;
- chat summaries must not override the canonical source.

## 10. Prompt-injection and untrusted content

Connected documents and emails may contain malicious or misleading instructions aimed at the AI assistant.

Users should:

- treat retrieved content as data, not authority;
- ignore instructions inside files that conflict with the user's task or system rules;
- avoid giving an assistant broad permission because a document requests it;
- review suspicious requests to share data, reveal secrets, or perform unrelated actions;
- keep high-impact tools disabled unless required;
- use provider approval prompts and workspace action controls;
- separate public intake content from privileged internal actions.

## 11. Credentials and secrets

Never store in normal Hub documents, Sheets, AI instructions, chats, or public repositories:

- passwords;
- API keys;
- OAuth tokens;
- database connection strings;
- recovery codes;
- payment-card details;
- private keys;
- application portal credentials;
- raw authentication payloads.

Use a proper secret manager or password manager and expose only narrow authenticated capabilities to the workflow.

## 12. Retention and deletion

Define:

- record retention period;
- conversation retention practice;
- conditions for archive or deletion;
- legal or contractual preservation requirements;
- process for customer correction and deletion requests;
- process for disconnecting a provider;
- process for removing a former employee’s access;
- verification that deleted or disconnected data is handled according to the provider policy.

## 13. Incident response

At minimum, know what to do if:

- a file becomes public accidentally;
- the wrong recipient receives a draft or message;
- an assistant retrieves another client's data;
- unauthorized changes appear;
- a connected account is compromised;
- the assistant produces a harmful or unsupported recommendation;
- the business cannot determine which record is current.

A basic response sequence:

```text
Stop the workflow
→ preserve evidence
→ restrict access
→ identify affected records and people
→ assess notification obligations
→ correct the canonical record
→ revoke or rotate access if necessary
→ record the root cause and preventive change
```

## 14. Monthly control review

- [ ] Review Google Workspace members and devices.
- [ ] Review Drive folders with broad sharing.
- [ ] Review AI apps, plugins, connectors, and OAuth access.
- [ ] Review read and write actions enabled for users.
- [ ] Remove former users and unnecessary collaborators.
- [ ] Check that active records have clear owners.
- [ ] Check that high-risk actions still require approval.
- [ ] Review data-retention and deletion queues.
- [ ] Test one fictional record retrieval for cross-record leakage.
- [ ] Record incidents, near misses, and control changes.

## 15. Minimum go-live checklist

Do not use sensitive live records until:

- [ ] the source-of-truth map exists;
- [ ] stable identifiers exist;
- [ ] folder permissions are verified;
- [ ] AI-provider privacy and retention settings are reviewed;
- [ ] connector scopes are understood;
- [ ] read-only tests pass with fictional or non-sensitive data;
- [ ] citations identify the correct sources;
- [ ] unrelated records are not mixed;
- [ ] approval boundaries are tested;
- [ ] retention and incident processes exist;
- [ ] accountable human owners are named.
