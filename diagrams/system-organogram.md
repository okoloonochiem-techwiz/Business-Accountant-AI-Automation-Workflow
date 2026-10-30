# Business Accountant AI Automation — System Organogram

```mermaid
flowchart TD
    A([GMAIL TRIGGER<br/>Incoming Invoice]) --> B[GOOGLE DRIVE INGESTION]
    B --> C[PDF.CO DOCUMENT PARSER]
    C --> D[FORMAT INVOICE DATA<br/>Vendor · Amount · Date<br/>Description · Invoice Number]
    D --> E[GEMINI CLASSIFIER<br/>Income vs Spending + Confidence]
    E --> F{Transaction Type}
    F -->|Payment / Income| G[Tag as Payment]
    F -->|Expenditure| H[Tag as Expenditure]
    G --> I{IF / ELSE ROUTING<br/>Check AI Confidence}
    H --> I
    I -->|Above 95%| J[AUTO-APPROVE<br/>Set Status: Draft]
    I -->|Below 95%| K[MANUAL APPROVAL<br/>Slack / Microsoft Teams Bot]
    J --> L[(CENTRAL DATA LEDGER<br/>Airtable / Xero / Google Sheets)]
    K --> L
```

## Notes
- The 95% threshold and Draft status are taken from the earlier workflow discussion.
- The central ledger options were described as Airtable, Xero, or Google Sheets; confirm which one is actually connected in the current n8n workflow.
- Verify exact node connections and execution status against the current workflow export before treating the diagram as final.
