# Security

## Credentials

- n8n stores credentials separately from workflows. Exported `workflow.json` files contain only credential names and IDs, never the secret values.
- Still, check every export before sharing it: API keys typed directly into an HTTP Request node or a Code node are saved inside the workflow.
- Never commit `.env` files, API keys, tokens, phone numbers or customer data to this repository.

## Customer data

- Leads and bookings contain personal information. Keep your Google Sheet private and share it only with your team.
- Tell customers that they are chatting with an automated assistant and how to reach a person.
- Delete test data before going live.

## Reporting a problem

If you find a security issue in a template, please email nageena@evoxaitech.com instead of opening a public issue.
