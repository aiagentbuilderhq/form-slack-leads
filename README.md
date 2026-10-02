# Project 3: Google Forms → Slack Lead Alerts

> **One-liner:** When someone submits your lead form, details ping Slack instantly — lead follow-up time from hours to seconds.

[![Google Forms](https://img.shields.io/badge/Google%20Forms-Trigger-green)](https://forms.google.com)
[![Slack](https://img.shields.io/badge/Slack-Delivery-purple)](https://slack.com)
[![Make.com](https://img.shields.io/badge/Make.com-Automation-blue)](https://make.com)

## 🎯 Problem
Leads submit a Google Form. Team checks responses manually once or twice a day. Hot leads go cold. By the time someone follows up, competitor already replied.

**Industry stat:** Responding within 5 minutes makes you 21x more likely to close vs 30 minutes later.

## ✅ Solution
2-step Make.com scenario:
1. **Google Forms → Watch Responses** — triggers instantly on new submission
2. **Slack → Create a Message** — posts formatted lead details to #general or #leads channel

**Message Format:**
`📩 New lead! {{Name}} ({{Email}}) says: {{Message}} | Source: {{Form Title}}`

## 🏗️ Architecture

```
[Google Forms: Watch Responses]
        ↓
[Slack: Create a Message - Channel: #leads]
        ↓
[Optional: Gmail - Send Confirmation to Lead]
```

## 📸 Screenshots (Add Yours)

- `form.png` — Google Form with 3 fields (Name, Email, Message)
- `scenario.png` — Forms + Slack modules connected
- `slack-message.png` — Slack channel showing lead alert

## 📈 Results

- **Before:** Form → Manual check 2x/day → Follow-up after 4-6 hours
- **After:** Form → Slack in < 60 seconds → Follow-up in 5 minutes
- **Time Saved:** 1 hour/day + higher close rate
- **Build Time:** 25 minutes

## 🛠️ Tools Used

- Google Forms (Free)
- Slack Workspace (Free tier — perfect for this)
- Make.com (Free tier)
- **Running Cost:** $0/month — uses tools client already has

## 🎥 Demo Video

**YouTube Unlisted Link:** `[Paste Link Here]`

**Demo Script (35 sec):**
- 0-5s: "Form → Slack — Never Miss a Lead"
- 5-15s: Fill test form live (Name: Test Client, Email: test@client.com, Message: Need automation help)
- 15-25s: Show Slack message arriving instantly
- 25-35s: Result + closer "From hours to seconds — Built with Make.com + Slack"

## 🚀 How To Replicate

1. forms.google.com → Blank Form → Title: Lead Capture → Add: Name (Short answer), Email (Short answer), Message (Paragraph) → Copy form link
2. slack.com → Create Workspace Free → Name: My Automation Lab → Channel #leads
3. Make.com → New Scenario → Google Forms → Watch Responses → Add Connection → Authorize Google → Select your form
4. Add Slack → Create a Message → Add Connection → Authorize Workspace → Select #leads → Message: template above → Map fields from Forms
5. Run Once → Test: Submit form yourself → Check Slack (should arrive in 1-2 min)
6. Turn ON → Schedule: Immediately (or every 15 min on free tier)
7. Screenshot everything for portfolio

## 💼 Client Use Cases

- E-commerce: New order form → Slack #orders
- Coaching: Discovery call form → Slack #sales + Calendar invite
- Agency: Contact form → Slack + Gmail confirmation
- Real Estate: Viewing request → Slack + SMS via Twilio (future upgrade)

## 🔒 Security

- No keys stored
- Use fake lead data in screenshots
- Real Slack workspace names redacted if client work

## 📄 Case Study

See `case-study.md`

---
**Built by Isaac — aiagentbuilderhq | [Full Portfolio](https://github.com/aiagentbuilderhq/automation-portfolio)**
