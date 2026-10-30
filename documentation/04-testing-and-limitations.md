# Testing and Limitations

## Suggested verification tests
- Gmail receives an invoice email.
- Google Drive stores or retrieves the invoice file.
- PDF.co upload returns a parser-compatible file reference.
- PDF.co extracts invoice content.
- Formatting produces Vendor, Amount, Date, Description, and Invoice Number.
- Gemini returns a valid transaction type and confidence.
- Payment and Expenditure tags are applied correctly.
- Confidence above 95% reaches Auto-Approve and sets status to Draft.
- Confidence below 95% reaches Manual Approval.
- The final result is written to the configured ledger.

## Known issue from earlier build
The PDF.co AI Invoice Parser expected a PDF URL or file token, while the incoming Drive file was binary. The PDF.co Upload File step was discussed as the bridge. A Gateway-credit warning was also encountered; confirm the user's PDF.co credentials and account credits.

## Limitations
- Do not claim a branch is operational until it has been tested in n8n.
- Confirm the actual central ledger destination.
- Manual approval depends on a configured Slack or Microsoft Teams integration.
- AI classification should support, not replace, human financial review.
