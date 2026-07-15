# Feedback Sentiment Analyzer

An AI-powered automation that reads incoming customer feedback, scores it for sentiment and urgency, stores it in a database, and alerts the team by email when something needs urgent attention.

## How it works

1. **Frontend form** — a simple HTML form collects the reviewer's name, email, and feedback message.
2. **Webhook trigger** — form submission hits an n8n webhook and kicks off the workflow.
3. **AI triage (Gemini)** — the message is sent to Google Gemini with a structured prompt that returns two fields:
   - `sentiment`: positive, negative, neutral, or spam
   - `urgency`: high, medium, or low
4. **Response parsing (Code node)** — Gemini's response is unwrapped and parsed into clean JSON, merged with the original form data.
5. **Database storage (Supabase)** — every submission is saved to a `feedback` table with sentiment, urgency, and a timestamp.
6. **Conditional email alert (Gmail)** — if urgency is `high`, an email alert is sent automatically so nothing urgent slips through.

## Tech stack

- **n8n** — workflow orchestration
- **Google Gemini** — sentiment and urgency classification
- **Supabase (Postgres)** — data storage
- **Gmail** — automated email alerts
- **HTML + Tailwind CSS** — frontend form

## Files

| File | Purpose |
|---|---|
| `index.html` | Frontend feedback form |
| `feedback-sentiment-analyzer.json` | n8n workflow export (import directly into n8n) |
| `prompt.txt` | Gemini system prompt used for classification |
| `query.sql` | Supabase table schema |

## Setup

1. Import `feedback-sentiment-analyzer.json` into n8n.
2. Connect your own Gemini, Supabase, and Gmail credentials in each node (credential fields are left blank for security).
3. Run `query.sql` in your Supabase SQL editor to create the `feedback` table.
4. Update the `WEBHOOK_URL` in `index.html` with your n8n webhook URL.
5. Activate the workflow.

## Note

Credential IDs and instance-specific identifiers have been removed from the workflow export. You'll need to reconnect your own credentials after importing.
