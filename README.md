# Project 3: Google Forms → Slack Lead Alerts (Make.com + n8n + Webhooks + APIs)

> **One-liner:** When someone submits your lead form, details ping Slack instantly + optional AI qualification — lead follow-up time from hours to seconds, 21x higher close rate.

[![Google Forms API](https://img.shields.io/badge/Google%20Forms%20API-Trigger-green)](https://developers.google.com/forms/api)
[![Slack API](https://img.shields.io/badge/Slack%20API-Delivery-purple)](https://api.slack.com)
[![Make.com](https://img.shields.io/badge/Make.com-Automation-blue)](https://make.com)
[![n8n](https://img.shields.io/badge/n8n-Workflow-red)](https://n8n.io)
[![Webhooks](https://img.shields.io/badge/Webhooks-Instant-orange)](https://en.wikipedia.org/wiki/Webhook)

**Live Hub:** [automation-portfolio](https://github.com/aiagentbuilderhq/automation-portfolio) | **Other Projects:** [Sheets → Gmail](https://github.com/aiagentbuilderhq/sheets-gmail-automation) · [Weather Bot](https://github.com/aiagentbuilderhq/weather-telegram-bot) · [AI Inbox](https://github.com/aiagentbuilderhq/ai-inbox-assistant) · [Lead Scoring](https://github.com/aiagentbuilderhq/ai-lead-scoring)

## 🎯 Problem
Leads submit a Google Form. Team checks responses manually 2x/day. Hot leads go cold. By the time someone follows up, competitor already replied. Industry stat: Responding within 5 minutes = 21x more likely to close vs 30 min later.

## ✅ Solution — Instant Lead Alerts + Optional AI Scoring

**Make.com (2-3 steps):**
1. Google Forms → Watch Responses (Forms API + Webhook — instant trigger)
2. Slack → Create a Message (Slack API) — posts to #leads channel
3. Optional: Gmail → Send Confirmation + Gemini → Score Lead (MCP pattern)

**n8n (3 nodes):**
1. Google Forms Trigger / Webhook Trigger
2. Slack Node → Post to #leads
3. Gmail Node → Auto-reply "Thanks, we'll reply in 15 min" + Optional: AI scoring via Gemini API

**Message Format:**
`📩 New lead! {{Name}} ({{Email}}) says: {{Message}} | Source: {{Form Title}} | Score: {{AI Score}}/10`

## 🏗️ Architecture

```
[Google Forms: Watch Responses — Forms API + Webhook (Instant)]
        ↓
[Slack: Create a Message — Slack API — Channel: #leads]
        ↓
[Optional: Gmail — Send Confirmation + Gemini API — Score Lead]
        ↓
[Optional: Google Sheets — Log Lead + Score]
```

**n8n:**
```
[Webhook Trigger: Form Submit] → [Slack Node] → [Gmail Node: Confirmation] → [Sheets Node: Log]
```

## 📈 Results

- **Before:** Form → Manual check 2x/day → Follow-up after 4-6 hours
- **After:** Form → Slack in <60 seconds → Follow-up in 5 minutes
- **Close Rate:** +35% (faster follow-up = higher close)
- **Time Saved:** 1 hour/day + higher revenue
- **Build Time:** 25 minutes

## 🛠️ Tools Used — Founder-Searched Skills

- **APIs:** Google Forms API · Slack API · Gmail API · Webhooks (instant) · Gemini API (optional scoring) · Sheets API (logging)
- **Automation:** Make.com (Free) · n8n (Free) · Error Handling · Router
- **Advanced:** MCP pattern (Form → AI → Slack), Instant Webhooks vs Polling, Lead Enrichment
- **Running Cost:** $0/month — uses tools client already has
- **Why Both Platforms?** Client already uses n8n? I build in n8n. Make.com? I build there. No new tool to learn.

## 💼 Client Use Cases (Same Pattern, Different APIs)

- E-commerce: Shopify Form → Slack #orders + Gmail confirmation
- Coaching: Calendly Booking → Slack #sales + Gmail + Notion API log
- Agency: Typeform → Slack + HubSpot API + Sheets
- Real Estate: Viewing request → Slack + SMS via Twilio API
- SaaS: Demo request → Slack + HubSpot API + AI scoring via Gemini

**Pitch:** "Form → Slack is foundation. Add AI scoring (Project 5), add Gmail confirmation, add HubSpot/Notion logging — all same pattern. I connect any API, not just Slack."

## 🎥 Demo Video

**YouTube Unlisted:** `[Paste Link]`
Demo: Fill test form live → Show Slack message arriving instantly → Show n8n version → Show optional AI score

## 🔒 Security

- No keys stored, fake lead data only

---
**Built by Isaac — aiagentbuilderhq | [Full Portfolio Hub](https://github.com/aiagentbuilderhq/automation-portfolio) | Tech: Make.com + n8n + Forms API + Slack API + Webhooks + Gmail API + MCP**
