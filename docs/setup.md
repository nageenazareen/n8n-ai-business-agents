# Setup guide

This guide gets you from zero to a running template.

## 1. Get n8n

Pick one:

- n8n Cloud: sign up at n8n.io, nothing to install.
- Self-hosted with Docker:

  ```bash
  docker run -it --rm -p 5678:5678 -v n8n_data:/home/node/.n8n docker.n8n.io/n8nio/n8n
  ```

  Then open http://localhost:5678.
- Hosting platforms such as Railway or Render also offer one-click n8n deployments.

Webhooks and form triggers need a public URL. n8n Cloud and hosted platforms give you one. For a local install, use a tunnel or deploy to a server before going live.

## 2. Import a template

1. In n8n, open Workflows and choose Import from File.
2. Select the `workflow.json` from the template folder.
3. Save the workflow.

## 3. Connect your credentials

Nodes that need an account show a warning icon after import. Open each one, choose Create New Credential and follow n8n's sign-in steps. Templates in this repository can use:

| Service | Used for | Where to get it |
|---|---|---|
| Chat model (OpenAI, Gemini and others) | Understanding messages and writing replies | Your model provider's dashboard |
| Google Sheets | Logging leads and bookings | Google account, connected through n8n's OAuth |
| Gmail | Sending replies by email | Google account, connected through n8n's OAuth |
| WhatsApp Business Cloud API | Receiving and sending WhatsApp messages | Meta for Developers, business verification required |

To use a different chat model, replace the model node with the one you prefer. The prompts work with any modern chat model.

## 4. Fill in your business details

Each template ships with an example business so you can test it straight away. Replace that example with your own details: in the Business Settings node for the AI Lead Catcher, and in the AI agent's system message for the other templates. The template README says exactly where.

## 5. Test, then activate

Each template README has a short test checklist. Run it with the workflow in test mode, check the output, then switch the workflow to Active.

## Troubleshooting

- Credential errors: reconnect the account in the node and save again. Google connections in testing mode expire after about a week.
- No reply from the model: check the model node's credential and your provider's usage limits.
- Webhook not firing: make sure the workflow is active and you are using the production URL, not the test URL.
