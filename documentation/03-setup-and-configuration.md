# Setup and Configuration

## Services shown or discussed
- n8n
- Gmail
- Google Drive
- PDF.co
- Google Gemini
- Slack or Microsoft Teams for manual review, if enabled
- Airtable, Xero, or Google Sheets as the ledger destination; verify which is configured

## Configuration checklist
1. Configure Gmail credentials and the incoming invoice trigger.
2. Configure Google Drive access.
3. Configure PDF.co credentials and upload/parser steps.
4. Pass the PDF URL or file token expected by the parser.
5. Map Vendor, Amount, Date, Description, and Invoice Number.
6. Configure Gemini to return transaction type and confidence.
7. Apply Payment or Expenditure tagging.
8. Configure the IF / ELSE threshold at 95%.
9. Set the high-confidence path status to Draft.
10. Configure Slack or Microsoft Teams for manual review if that branch is active.
11. Map the result to the actual central ledger.

Do not commit credentials, OAuth tokens, webhook secrets, real invoices, or personal/financial information.

## Details to confirm from the workflow export
Exact credential names, node parameter values, Gemini prompt, output schema, destination ledger, and Slack/Teams action configuration.
