# WhatsApp FAQ Bot

Answers the questions your customers ask every day (timings, location, services, prices) on WhatsApp, straight from your own FAQ and in the customer's language. When it is not sure, or the customer wants a person, it hands over politely and flags the chat for your team.

<!-- demo.gif goes here -->

## How it works

```text
WhatsApp Trigger (incoming message)
   -> Is Text Message? (ignores images, voice notes and status updates)
   -> Extract Message: phone, name, text
   -> AI Agent (with per-customer memory)
        - answers only from your FAQ, in short WhatsApp-style messages
        - hands over when the answer is not in the FAQ or the customer asks for a person
        - Save Lead tool: adds or updates the customer in Google Sheets
          with status info, interested or needs_human
   -> Send Reply (WhatsApp)
```

Your team filters the sheet by needs_human to see who is waiting for a reply.

## What you need

- n8n with a public URL (n8n Cloud or a hosted server)
- WhatsApp Business Cloud API access from Meta
- A chat model credential. The template uses OpenAI (gpt-4o-mini); you can swap in any chat model node.
- A Google account for Google Sheets

## Setup

1. Import `workflow.json` into n8n.
2. WhatsApp Trigger and Send Reply: connect your WhatsApp Business Cloud credential, then add the trigger's webhook URL in the Meta developer dashboard.
3. Chat Model: connect your model credential.
4. Create a Google Sheet with these columns in row 1:

   ```text
   phone | name | need | status | last_message | updated_at
   ```

5. Save Lead: connect your Google account and select the sheet.
6. Open AI Agent and replace the example business and FAQ (Bright Smile Dental Clinic) with your own.
7. Activate the workflow and send a WhatsApp message to your business number.

## Test checklist

- Ask a question that is in your FAQ. Expected: a short, correct answer.
- Ask something that is not in your FAQ. Expected: a polite handover message and status needs_human in the sheet.
- Write "I want to talk to a person". Expected: the same handover.
- Write in another language. Expected: the reply is in that language.

## Customise it

- Add an IF node after the AI Agent to email or message your team when a lead is marked needs_human.
- Add a Google Calendar tool so the agent can offer and book appointment slots.

## Need it set up?

WhatsApp Business API approval is usually the hardest part. [Evox AI Tech](https://evoxaitech.com) handles the Meta setup, your FAQ and the handover to your team.
