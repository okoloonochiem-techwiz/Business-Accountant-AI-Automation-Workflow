# System Architecture

1. Gmail Trigger receives the incoming invoice email.
2. Google Drive Ingestion stores or retrieves the invoice document.
3. PDF.co Document Parser processes the PDF.
4. Format Invoice Data prepares Vendor, Amount, Date, Description, and Invoice Number.
5. Gemini Classifier identifies payment/income versus expenditure and returns confidence.
6. The workflow applies the Payment or Expenditure tag.
7. IF / ELSE Routing checks the confidence threshold.
8. Above 95%, Auto-Approve sets the status to Draft.
9. Below 95%, Manual Approval routes the item to Slack or Microsoft Teams.
10. The result is intended for a Central Data Ledger (Airtable, Xero, or Google Sheets; confirm the actual configured destination).

## PDF.co file handling
The earlier troubleshooting established that the AI Invoice Parser expected a PDF URL or file token, not the raw binary payload. The PDF.co Upload File step was discussed to upload the binary and provide a parser-compatible file reference.

Exact connections and mappings must be checked against the current n8n export.
