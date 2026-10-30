# Invoice Processing Workflow

## Purpose
Receive invoice emails, process invoice PDFs, extract structured financial details, classify transactions, and route results for automated or human review.

## Screenshot-derived sequence
Gmail Trigger → Google Drive Ingestion → PDF.co Document Parser → Format Invoice Data → Gemini Classifier → Payment / Expenditure tags → IF / ELSE Routing → Auto-Approve or Manual Approval → Central Data Ledger.

## Fields
Vendor, Amount, Date, Description, Invoice Number.

## Confidence routing
The discussed threshold is 95%. Above 95%, the Auto-Approve path sets status to Draft. Below 95%, the item is routed for manual approval through Slack or Microsoft Teams.

## Export and evidence
- Put the n8n workflow JSON export in `workflow-export/`.
- Put sanitized screenshots in `screenshots/`.
- Remove credentials, secrets, and real invoice/customer data before committing.
- Update this documentation after checking the exported node parameters and test executions.
