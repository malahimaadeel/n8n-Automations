# n8n Form-to-Email Automation Workflow

Automated workflow built with n8n that collects form data, saves it to Google Sheets, and sends occupation-based custom emails — no manual work, no code.

## How it works
1. Form submission triggers the workflow
2. Data auto-saved to Google Sheets (Append/Update mode, no duplicates)
3. Filter blocks "Student" entries
4. Switch routes Doctors and Engineers to separate paths
5. Each group gets a custom welcome email
6. Paths merge, everyone gets a final common email

## Tools
- n8n Cloud
- Google Sheets API
- Gmail API

## Setup
Import `n8n_automation_workflow.json` into your n8n instance, connect your own Google Sheets + Gmail credentials, done.

## Note
Credentials, IDs, and personal data removed from this file for privacy. Replace placeholder values with your own before running.
