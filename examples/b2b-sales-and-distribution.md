# Case Study: B2B Sales and Distribution Business

**This is a fictional operating-model example.** It can represent an equipment supplier, building-materials distributor, industrial-products company, office-products wholesaler, importer, or another small business that coordinates customers, suppliers, quotations, orders, delivery, and payment.

## Business profile

A fifteen-person B2B sales and distribution business manages customer inquiries, product selection, quotations, negotiation, supplier coordination, confirmed orders, delivery, and payment follow-up. The business already uses:

- Google Drive for product documents, price lists, quotations, contracts, supplier files, and delivery evidence;
- Google Sheets for leads, opportunities, quotations, orders, and receivables follow-up;
- Gmail for customer and supplier communication;
- Google Calendar for follow-ups, delivery dates, and account reviews;
- ChatGPT and/or Claude for retrieval, comparison, drafting, and review.

The company is considering CRM, inventory software, ERP, and automation. Its immediate problem is that sales and fulfillment information is fragmented and the same commercial fact appears in several places.

## Operating problem

The business experiences:

- customer inquiries buried in individual inboxes;
- opportunities with no owner or dated next action;
- outdated price lists used during quotation preparation;
- different versions of quotations shared internally and externally;
- product specifications difficult to retrieve during customer conversations;
- verbal discounts or delivery promises not reflected in the official record;
- supplier availability and customer commitments that do not match;
- confirmed orders manually copied across several Sheets;
- delivery status dependent on phone calls and personal memory;
- overdue payment follow-up that starts too late;
- uncertainty about whether CRM, inventory software, or ERP should be implemented first.

## Core operating flow

```text
Lead or customer inquiry
→ qualification
→ product and requirement clarification
→ quotation
→ negotiation and approval
→ confirmed order
→ supplier or stock coordination
→ delivery
→ invoice and payment follow-up
→ account review and repeat business
```

The AI workspace improves retrieval and coordination around this flow. It does not become the inventory ledger, accounting system, pricing authority, or order-approval authority.

## Canonical record model

### Stable identifiers

Each customer, opportunity, quotation, and order receives a permanent identifier:

```text
CUSTOMER-2026-042
OPPORTUNITY-2026-031
QUOTE-2026-088
ORDER-2026-054
```

The identifiers connect:

- the Master Customer Index;
- the Opportunity and Order Indexes;
- Drive folders and documents;
- approved quotations;
- customer and supplier correspondence;
- delivery evidence;
- payment follow-up;
- future CRM, ERP, or database records.

### Master Customer Index

One row per customer, containing:

- Customer ID;
- customer name;
- account status;
- account owner;
- industry or segment;
- current open opportunities;
- current open orders;
- next relationship action;
- action owner;
- action date;
- last interaction;
- Customer Hub URL;
- restricted folder URL;
- credit or commercial note classification;
- waiting-on field.

Sensitive financial details should remain in the authorized financial system rather than a broadly accessible Sheet.

### Opportunity Index

One row per opportunity, containing:

- Opportunity ID;
- Customer ID;
- requirement summary;
- opportunity stage;
- estimated value;
- quotation status;
- probability or confidence classification;
- expected decision date;
- next action;
- action owner;
- action date;
- Opportunity Hub URL;
- current approved quotation URL;
- waiting-on field.

### Order Index

One row per confirmed order, containing:

- Order ID;
- Customer ID;
- source Opportunity ID;
- approved quotation reference;
- order status;
- fulfillment risk;
- supplier or stock status;
- promised delivery date;
- internal target date;
- delivery owner;
- next action;
- action owner;
- action date;
- Order Hub URL;
- delivery evidence URL;
- invoice reference;
- waiting-on field.

### Customer Hub

The Customer Hub contains:

- relationship summary;
- authorized contacts;
- current opportunities and orders;
- agreed commercial rules;
- approved product and service context;
- important decisions;
- open actions;
- links to official quotations, orders, correspondence, and delivery records.

### Opportunity Hub

The Opportunity Hub contains:

- confirmed customer requirement;
- product or solution options;
- questions and assumptions;
- approved pricing source;
- quotation history;
- decision process;
- competitors or alternatives when confirmed;
- next actions;
- risks;
- links to specifications and correspondence.

### Order Hub

The Order Hub contains:

- approved order scope;
- quantities and product references;
- approved commercial terms;
- supplier or stock dependencies;
- promised and internal dates;
- delivery instructions;
- changes and approvals;
- fulfillment risks;
- next actions;
- links to purchase, delivery, invoice, and acceptance evidence.

## Suggested Drive structure

```text
CUSTOMER-2026-042 — Example Customer/
├── 00 Customer Hub
├── 01 Account Documents/
├── 02 Opportunities/
│   └── OPPORTUNITY-2026-031 — Example Requirement/
│       ├── 00 Opportunity Hub
│       ├── Requirements/
│       ├── Product Information/
│       ├── Quotations/
│       └── Correspondence/
├── 03 Orders/
│   └── ORDER-2026-054 — Example Order/
│       ├── 00 Order Hub
│       ├── Approved Documents/
│       ├── Supplier and Stock Evidence/
│       ├── Delivery/
│       └── Invoice and Acceptance/
└── 90 Archive/
```

## AI-assisted workflows

### 1. Sales pipeline review

```text
Read only the Opportunity Index.
Report:
- opportunities with no owner or dated next action;
- quotations awaiting internal approval;
- quotations sent with no follow-up date;
- expected decisions in the next 14 days;
- stalled opportunities;
- high-value opportunities with incomplete requirements;
- work waiting on our team;
- work waiting on customers.

Use the index values as operational facts.
Mark recommendations as suggestions.
Do not change any record or probability.
```

### 2. Inquiry preparation

```text
Work only on CUSTOMER-2026-042 and OPPORTUNITY-2026-031.
Use the Customer Hub, Opportunity Hub, current official product documents,
and approved price source.

Prepare:
- confirmed customer requirement;
- missing technical or commercial information;
- relevant product options supported by sources;
- questions for the customer;
- internal decisions required;
- proposed next action.

Cite every source. Do not select a product, set a price, or promise availability.
```

### 3. Quotation-quality review

Before a human approves a quotation, the assistant checks the draft against authorized sources:

- Customer and Opportunity IDs;
- product codes and descriptions;
- approved price-list version;
- quantities;
- discount authorization evidence;
- tax and currency presentation;
- delivery assumptions;
- validity period;
- exclusions;
- payment terms;
- referenced specifications;
- unresolved inconsistencies.

The assistant reports discrepancies but does not approve, calculate authoritative tax, or send the quotation.

### 4. Follow-up drafting

```text
Draft a follow-up for OPPORTUNITY-2026-031 using only the approved quotation,
latest customer correspondence, and confirmed next action.
Verify quotation reference, validity date, quantities, and commitments.
Do not introduce a discount, delivery promise, or new term.
Do not create or send an email until I approve the recipient and wording.
```

### 5. Order-readiness review

```text
Work only on ORDER-2026-054.
Use the approved customer order, approved quotation, Order Hub,
supplier or stock evidence, and current delivery plan.

Report:
- confirmed order scope;
- stock or supplier status supported by evidence;
- date conflicts;
- missing approvals or documents;
- customer and supplier dependencies;
- fulfillment risks;
- next actions and owners.

Do not mark stock as available, commit a delivery date,
or release an order for fulfillment.
```

### 6. Delivery and payment follow-up

Using only the Order Index and authorized financial-status fields, the assistant identifies:

- deliveries due in the next seven days;
- orders at risk of missing the promised date;
- completed deliveries lacking acceptance evidence;
- invoices awaiting issuance review;
- receivables requiring authorized follow-up;
- records with inconsistent order, delivery, or invoice references.

Detailed financial data remains inside the authorized accounting or ERP system.

## Human-control boundaries

The AI assistant may retrieve, compare, summarize, identify inconsistencies, and prepare drafts within an authorized scope.

It must not independently:

- set or change prices;
- approve discounts or credit terms;
- select a product as technically suitable;
- confirm physical stock;
- place supplier purchase orders;
- release customer orders;
- promise a delivery date;
- modify quantities or commercial terms;
- approve invoices, refunds, or write-offs;
- send customer or supplier communication;
- treat estimated probability as a confirmed fact;
- access unrelated customer records.

## Governance rules

- only approved price and product sources may support quotations;
- every quotation and order uses stable IDs and version status;
- customer commitments return to the canonical Hub or approved order record;
- estimated values and probabilities are clearly labeled;
- consequential changes show Before, After, and Why;
- one assistant owns each write task;
- commercial, customer, supplier, and financial records remain restricted;
- accounting and inventory systems remain authoritative for transactions when present;
- public repositories contain templates and fictional examples only.

## Pilot metrics

| Metric | Fictional baseline | Pilot review question |
|---|---:|---|
| Open opportunities with a dated next action | 58% | Can the process reach at least 95%? |
| Time to prepare a standard quotation draft | 35 minutes | Can retrieval and checking reduce it below 15 minutes? |
| Quotations using the current approved price source | 75% | Can the process reach 100%? |
| Sent quotations with scheduled follow-up | 50% | Can it reach at least 95%? |
| Orders with visible fulfillment risk and owner | 60% | Can it reach at least 95%? |
| Delivery records missing acceptance evidence | 10 per month | Does the workflow reduce the backlog materially? |

The figures are fictional planning values, not performance claims.

## Technology decision after 90 days

The business reviews evidence:

- adopt a CRM when lead capture, opportunity history, account activity, forecasting, and sales-team coordination are the dominant unresolved needs;
- adopt inventory or ERP capability when stock, purchasing, costing, order fulfillment, invoicing, and financial controls must be transactional and integrated;
- add selective workflow automation when stable events need reminders, document creation, or controlled cross-system handoffs;
- add PostgreSQL and controlled API or MCP tools when custom structured workflows, role-based access, reporting, and audit history are required beyond standard platforms;
- retain Google Workspace as the document and knowledge layer even after CRM or ERP adoption.

The framework helps the business distinguish a sales-information problem from an inventory, fulfillment, or accounting problem before buying software.