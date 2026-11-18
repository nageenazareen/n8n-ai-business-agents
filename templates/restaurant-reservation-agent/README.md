# Restaurant Reservation Agent

A website chat assistant for restaurants. It answers menu questions in Arabic or English, collects booking details, reads the booking back to the guest for confirmation and saves it to Google Sheets.

<!-- demo.gif goes here -->

## How it works

```text
Website Chat (n8n chat widget)
   -> AI Receptionist (agent with conversation memory)
        - answers questions from your restaurant info and menu only
        - collects name, phone, date, time, guests and special requests
        - checks opening hours and that the date is not in the past
        - repeats the booking and waits for the guest to confirm
   -> Save Reservation (Google Sheets tool, called only after confirmation)
```

If saving fails, the agent does not pretend the booking is confirmed. It apologises and tells the guest the team will call them.

## What you need

- n8n (Cloud or self-hosted)
- A chat model credential. The template uses OpenAI (gpt-4o-mini); you can swap in any chat model node.
- A Google account for Google Sheets

## Setup

1. Import `workflow.json` into n8n.
2. Open AI Receptionist and replace the example restaurant (Al Noor Grill) with your own: name, opening hours, location, party size limit and menu.
3. If you are not in the UAE, change `Asia/Dubai` in the system message and in Save Reservation to your timezone.
4. Create a Google Sheet with a tab named Reservations and these columns in row 1:

   ```text
   Booked At | Name | Phone | Date | Time | Guests | Special Request | Language
   ```

5. Save Reservation: connect your Google account and select the sheet and tab.
6. Chat Model: connect your model credential.
7. Update the welcome message and title in Website Chat, then activate the workflow and open the chat URL.

## Test checklist

- Ask about a dish on the menu and one that is not. Expected: correct price for the first, "not available" for the second.
- Book a table with all details in one message. Expected: the agent repeats the booking and asks you to confirm.
- Confirm. Expected: a new row in the sheet.
- Ask for a time after the last booking slot. Expected: the agent suggests another time.
- Write in Arabic. Expected: the whole reply is in Arabic.

## Need it set up?

[Evox AI Tech](https://evoxaitech.com) can put this on WhatsApp and Instagram, connect it to your booking system and tune it to your menu.
