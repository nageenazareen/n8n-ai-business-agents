<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:04080f,45:0055cc,75:0088ff,100:00bbff&height=200&section=header&text=n8n%20AI%20Business%20Agents&fontSize=44&fontColor=ffffff&fontAlignY=38&desc=Free%2C%20ready-to-import%20AI%20workflows%20for%20real%20businesses&descAlignY=60&descSize=17" alt="n8n AI Business Agents" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/n8n-templates-0088ff?style=flat-square&logo=n8n&logoColor=white&labelColor=04080f" alt="n8n templates" />
  <img src="https://img.shields.io/badge/license-MIT-00bbff?style=flat-square&labelColor=04080f" alt="MIT license" />
  <img src="https://img.shields.io/badge/languages-English_%7C_Arabic-0055cc?style=flat-square&labelColor=04080f" alt="English and Arabic" />
  <img src="https://img.shields.io/github/stars/nageenazareen/n8n-ai-business-agents?style=flat-square&color=0088ff&labelColor=04080f" alt="GitHub stars" />
</p>

<p align="center">
  Import a workflow, add your own credentials, and have an AI agent answering leads and customers in under 15 minutes.
</p>

<br/>

## Why this exists

Small businesses lose customers every day because nobody replies fast enough: a lead fills in a form at 11 PM, a guest wants a table on Friday, a customer asks the same question for the hundredth time. These templates handle that first reply automatically, so the team only steps in when it matters.

Every template in this repository:

- runs on n8n (self-hosted or n8n Cloud)
- uses nodes that ship with n8n, so there are no custom plugins to install
- works with any chat model supported by n8n (OpenAI, Gemini and others)
- contains no credentials: you connect your own accounts after import
- comes with a step-by-step setup guide and a test checklist

<br/>

## Templates

| Template | What it does | Best for |
|---|---|---|
| [AI Lead Catcher](templates/ai-lead-catcher) | Reads every form lead, scores it Hot, Warm or Cold, sends a personal reply in the lead's language and logs it to Google Sheets | Agencies, real estate, clinics, any business with a contact form |
| [Restaurant Reservation Agent](templates/restaurant-reservation-agent) | Website chat in Arabic or English that answers menu questions, takes table bookings, confirms them with the guest and saves them to Google Sheets | Restaurants and cafes |
| [WhatsApp FAQ Bot](templates/whatsapp-faq-bot) | Answers customer questions on WhatsApp from your own FAQ and flags the chat for your team when it is unsure | Clinics, salons, shops, service businesses |

More templates are added regularly. Watch or star the repository to get notified.

<br/>

## Quick start

1. Open n8n and go to Workflows, then Import from File.
2. Choose the `workflow.json` file from the template folder.
3. Open each node that shows a warning and connect your own credentials.
4. Replace the example business details (name, services, hours, menu or FAQ) as described in the template's README.
5. Run the test described in the template's README, then activate the workflow.

New to n8n? Read the [setup guide](docs/setup.md) first.

<br/>

## Repository structure

```text
templates/
  ai-lead-catcher/                README, workflow.json, screenshots
  restaurant-reservation-agent/   README, workflow.json, screenshots
  whatsapp-faq-bot/               README, workflow.json, screenshots
docs/
  setup.md                        installing n8n and connecting credentials
  security.md                     keeping keys and customer data safe
```

<br/>

## Need it built for your business?

These templates are a solid starting point. Running them for real customers usually needs a bit more: WhatsApp Business API approval, your own services and prices, Arabic and English tuning, booking or CRM integrations, hosting and monitoring.

[Evox AI Tech](https://evoxaitech.com) sets this up for clinics, restaurants, hotels and service businesses, usually within a few days.

<p align="center">
  <a href="https://evoxaitech.com"><img src="https://img.shields.io/badge/Visit-evoxaitech.com-0088ff?style=for-the-badge&labelColor=04080f" alt="Visit Evox AI Tech" /></a>
  <a href="mailto:nageena@evoxaitech.com"><img src="https://img.shields.io/badge/Get_it_set_up-Email_us-00bbff?style=for-the-badge&labelColor=04080f" alt="Email Evox AI Tech" /></a>
</p>

<br/>

## Contributing

Found a bug or have an idea for a new template? Open an issue. Pull requests that improve a template or its documentation are welcome. Please never include real credentials, phone numbers or customer data.

## License

MIT. Use these templates in personal and commercial projects.

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:00bbff,30:0088ff,60:0055cc,100:04080f&height=100&section=footer" alt="" />
</p>
