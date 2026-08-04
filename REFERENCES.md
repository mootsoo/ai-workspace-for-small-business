# Official References

**Last verified:** August 4, 2026

This repository is provider-neutral, but its capability statements must remain grounded in current official documentation. Product names, plan availability, connector behavior, OAuth scopes, action permissions, and administrative controls can change.

The implementation rule is:

> **Verify the capability in the actual account and workspace before designing a workflow around it.**

## OpenAI and ChatGPT

### Apps and connected actions

- [Apps in ChatGPT](https://help.openai.com/en/articles/11487775-connectors-in-chatgpt/)
  - Apps can search and reference connected information.
  - Some apps can take actions, depending on app capability, configuration, plan, and workspace controls.
  - App permissions may include Always ask, Any changes, Important actions, or Never ask.
  - To require approval before every write, use the most restrictive setting available for changes.

### Google app data controls

- [Google App for ChatGPT — Data Controls FAQ](https://help.openai.com/en/articles/10408842-google-app-for-chatgpt-data-controls-faq)
  - Connected Google data may be indexed and synced when the relevant feature is enabled.
  - OpenAI states that data directly retrieved from connected Google apps is not used to train generalized models, subject to the exceptions described in the official policy.
  - Google Drive actions for Docs, Sheets, and Slides are unified under the Google Drive app.
  - Available Google actions and scopes depend on enabled actions and Google Workspace authorization.

### Google Drive setup

- [Google Drive app with sync — Self-Service Setup](https://help.openai.com/en/articles/10948259)
  - Documents, Sheets, and Slides actions are available through the Google Drive app.
  - Plan and workspace administration affect availability.

### Workspace administration

- [Admin controls, security, and compliance for plugins and apps](https://help.openai.com/en/articles/11509118-admin-controls-security-and-compliance-in-apps-enterprise-edu-and-business)
  - Administrators can control user access, read and write actions, and approval settings where supported.
  - Provider OAuth approval does not automatically enable every action in ChatGPT.
  - Custom apps may use MCP in supported managed-workspace configurations.

## Anthropic and Claude

### Google Workspace connectors

- [Use Google Workspace connectors](https://support.claude.com/en/articles/10166901-use-google-workspace-connectors)
  - Claude supports Gmail, Google Calendar, and Google Drive connectors.
  - Gmail supports search, reading, organization, and draft creation; Claude does not send email on the user's behalf.
  - Calendar supports viewing and managing events according to available permissions and approval.
  - Drive supports search and retrieval, multiple file types, folder creation, upload, permissions visibility, and saving generated files when the required features are enabled.
  - Connector actions require explicit approval.
  - Drive files can be added to private Claude Projects; the Drive option is disabled for shared Projects.

### Claude Projects

- [Create and manage Projects](https://support.claude.com/en/articles/9519177-how-can-i-create-and-manage-projects)
  - Project Instructions should contain the operating rules; project names and descriptions are not sufficient as governance.

### Data and privacy

- [Is my data used for model training? — consumer products](https://privacy.claude.com/en/articles/10023580-is-my-data-used-for-model-training)
- [Is my data used for model training? — commercial products](https://privacy.claude.com/en/articles/7996868-is-my-data-used-for-model-training)

Use the current official settings and policy for the actual Claude plan. Do not assume that a consumer account and commercial account have the same defaults.

## Google Workspace

### Drive sharing

- [Share files from Google Drive](https://support.google.com/drive/answer/2494822)
  - Google Drive supports Viewer, Commenter, and Editor roles.
  - General access can be Restricted or broader, depending on the account and organization settings.
  - “Anyone with the link” can allow access without a specifically authorized account and should not be used for confidential records without a deliberate business decision.

### Shared drives

- [Store and share files with shared drives](https://support.google.com/drive/answer/7286514)
  - Shared drives can provide organization-owned storage and role-based membership for eligible Google Workspace accounts.

## Model Context Protocol

- [MCP architecture](https://modelcontextprotocol.io/docs/learn/architecture)
- [MCP specification architecture](https://modelcontextprotocol.io/specification/2025-06-18/architecture)

MCP uses a host-client-server architecture. In this framework, a future MCP server should expose narrow business tools rather than unrestricted database access.

Examples:

```text
search_clients
get_client_summary
list_overdue_actions
create_followup_draft
propose_stage_change
add_approved_meeting_note
```

## Citation and maintenance policy

When this repository states a current product capability:

1. prefer official vendor documentation;
2. record the verification date;
3. distinguish read capability from write capability;
4. distinguish product capability from plan or admin availability;
5. avoid assuming that OAuth scope approval automatically enables an action;
6. update the statement when the vendor documentation changes materially;
7. retain provider neutrality in the core architecture.

This reference list supports product capability claims only. It does not certify that an implementation is secure, compliant, or suitable for a particular regulated workflow.
