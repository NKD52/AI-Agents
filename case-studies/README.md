# Automation case studies

## Agency client lifecycle

An n8n workflow for managing client work across lead intake, onboarding, invoicing, and project completion.

1. An incoming webhook event is validated before the client record is updated in Airtable.
2. A new lead triggers a follow-up task. An accepted proposal triggers an onboarding checklist.
3. Invoice events update payment state. Project completion triggers a feedback request.

The workflow uses Airtable to record client and lifecycle data, with email and Slack for notifications.

## Client churn risk scoring

Two n8n workflows help an account team review clients who may need attention.

1. A scheduled Airtable workflow collects recent activity, last response, payment status, and missed sessions.
2. The collection workflow combines those signals into one record per client.
3. A separate scoring workflow reads the collected records, assesses risk with an OpenRouter model, and writes the results back to Airtable for human review.

A risk assessment is a prompt for review. Missing signals and outdated account records can affect the assessment.

## Dormant lead reactivation

Two paths in an n8n workflow manage re-engagement and incoming replies.

1. The outreach path reads leads from Google Sheets, drafts a message with a language model, and sends it through Gmail.
2. A Gmail trigger handles replies. The reply path looks up the lead, handles the response, and updates the record in Sheets.

For a demo, use synthetic lead records and a test mailbox. Route drafts to yourself before enabling a live trigger.

These write-ups describe the workflow behavior. The original workflow exports, account identifiers, and contact records are kept outside this public repository.
