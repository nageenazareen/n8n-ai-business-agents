# AI Lead Catcher

Every lead from your website form gets read, scored and answered within a minute, day or night. Your team opens one Google Sheet in the morning and sees exactly who to call first.

<!-- demo.gif goes here -->

## How it works

```text
Lead Form (n8n form, or your own website form)
   -> Business Settings: your business name, services and signature
   -> AI Lead Scorer: scores the lead Hot, Warm or Cold, picks the matching service
      and writes a short personal reply in the lead's language (English or Arabic)
   -> Reply to Lead: sends the reply by Gmail
   -> Save Lead: adds a row to Google Sheets
```

The AI never quotes prices or promises results. It offers a free 15-minute call to warm leads and replies briefly to cold ones.

## What you need

- n8n (Cloud or self-hosted)
- A chat model credential. The template uses OpenAI (gpt-4o-mini); you can swap in any chat model node.
- A Google account for Gmail and Google Sheets

## Setup

1. Import `workflow.json` into n8n.
2. Open Business Settings and fill in: business_name, sender_name, contact_email, services, hot_budget and timezone.
3. Create a Google Sheet with these columns in row 1:

   ```text
   Received At | Name | Email | Company | Need | Budget | Score | Service | Summary | Reply Sent
   ```

4. Save Lead: connect your Google account and select the sheet.
5. Reply to Lead: connect your Gmail account.
6. Chat Model: connect your model credential.
7. Activate the workflow and open the form URL from the Lead Form node.

## Test checklist

- Submit an English lead with a clear need and a budget of $1,000 or more. Expected: score Hot and an English reply offering a call.
- Submit a lead written in Arabic. Expected: the whole reply is in Arabic.
- Submit a vague one-line message with "Not sure yet" as the budget. Expected: Cold or Warm, and a short polite reply.
- Check that each test created a row in the sheet and an email arrived.

## Customise it

- Change the scoring rules in the AI Lead Scorer system message to match your sales process.
- Change the form fields in Lead Form, and update the prompt and sheet columns to match.
- Add an IF node after the scorer to alert your team on Slack or Telegram for Hot leads only.

## Need it set up?

[Evox AI Tech](https://evoxaitech.com) can connect this to your website, CRM and WhatsApp, and tune the replies for your business.
