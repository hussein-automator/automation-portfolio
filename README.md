# Automation Portfolio

A collection of production-ready automations built with n8n, organized for easy import and reuse.

---

## Automations

### Gmail Monitor & Categorizer
**File:** `gmail-monitor-and-categorizer.json`

Monitors Gmail in real-time via push notifications. Categorizes every incoming email, applies labels, marks as read, logs Upwork job posts to Google Sheets, and sends instant Telegram alerts.

**Flow:**
```
Gmail Trigger (Webhook)
  → Get Full Email
  → IF Upwork? ──► Label + Mark Read + Extract URL + Log to Sheets + Telegram Alert
                └► Switch: Newsletter / Finance / Social / Personal → Label + Mark Read
```

**Integrations:** Gmail · Google Sheets · Telegram

**Setup:**
1. Create Gmail labels: `Upwork-Jobs`, `Newsletter`, `Finance`, `Social`, `Personal`
2. Create a Google Sheet with tab `Upwork Jobs` and headers: `Date Received | Job Title | Preview | Job URL`
3. Create a Telegram bot via `@BotFather` and get your chat ID from `@userinfobot`
4. In n8n, connect credentials: Gmail OAuth2, Google Sheets OAuth2, Telegram API
5. Import `gmail-monitor-and-categorizer.json` and activate

---

## Stack
- **Automation:** n8n Cloud
- **Auth:** Google OAuth2, Telegram Bot API
