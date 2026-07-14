# AI Restaurant Reservation Confirmation (n8n + Gemini)

An automation that generates and sends personalized restaurant reservation confirmation emails using AI, built with n8n and Google Gemini.

## What it does

1. Guest fills a form (name, email, reservation details) on a simple web frontend
2. Data is sent to an n8n webhook
3. Google Gemini writes a warm, professional confirmation email
4. A Code node parses the AI response into subject and body
5. Gmail node sends the email automatically
6. Frontend shows a success message

## Tech stack

- **n8n** — workflow automation engine (Webhook, Code, Gmail nodes)
- **Google Gemini** (`gemini-flash-lite-latest`) — email generation
- **HTML + Tailwind CSS** — frontend form
- **JavaScript** — response parsing logic

## Credit

Built by customizing the base workflow structure taught in an n8n automation course teacher, adapted with a new use case (restaurant reservations) and migrated from OpenAI to Google Gemini.
