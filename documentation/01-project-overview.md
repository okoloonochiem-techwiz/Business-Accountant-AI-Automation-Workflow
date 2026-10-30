# Project Overview

## Purpose
This n8n workflow is intended to automate invoice intake, extraction of financial details, transaction classification, and approval routing.

## Screenshot-derived workflow
Gmail Trigger → Google Drive Ingestion → PDF.co Document Parser → Format Invoice Data → Gemini Classifier → Payment/Expenditure tags → IF / ELSE Routing → Auto-Approve or Manual Approval → Central Data Ledger.

## Extracted fields
Vendor, Amount, Date, Description, and Invoice Number.

## Classification and routing
Gemini classifies each invoice as payment/income or expenditure and returns a confidence value. The discussed threshold is 95%:
- Above 95%: Auto-Approve path; set status to Draft.
- Below 95%: Manual Approval through a Slack or Microsoft Teams bot.

## Implementation note
The earlier build encountered a PDF.co input-format issue: the parser expected a PDF URL or file token, while the Drive download supplied binary data. The PDF.co Upload File step was discussed to obtain a usable file reference. A Gateway-credit warning was also encountered.

## Verification status
The current workflow JSON, exact node parameters, prompt, parser schema, final ledger destination, and end-to-end execution evidence still need review. This documentation does not claim those details are verified.
