# Automated 30-Day SMS Nurture Sequence

This repository contains a robust SMS outreach system designed to convert new and warm leads through a strategic, multi-day touchpoint sequence. Unlike reactive one-time triggers, this workflow manages the entire lead lifecycle over a 30-day period using consistent, high-converting message templates.

## 🚀 Business Value
* **Consistent Follow-up:** Automates the "Fortune is in the Follow-up" philosophy by ensuring every lead receives exactly 6 touchpoints over a month.
* **Predictable Outreach:** Uses proven message templates to maintain brand voice and compliance, removing the variability of AI-generated content.
* **Warm Lead Retention:** Specifically tuned for leads that have already shown interest, keeping your service top-of-mind during their decision-making window.

## 🗓 The Sequence Logic
The system is programmed to deliver value-driven messages at strategic intervals to maximize engagement without being intrusive:
* **Day 1:** Immediate acknowledgment and initial value offer.
* **Day 4:** First follow-up / "Check-in" message.
* **Day 9:** Case study or social proof snippet.
* **Day 14:** Addressing common objections or FAQs.
* **Day 20:** "Soft" re-engagement nudge.
* **Day 30:** Final "Break-up" or long-term resource offer.

## 🛠 Tech Stack
* **Orchestration:** n8n
* **Communication:** Twilio (SMS Gateway)
* **Source of Truth:** Google Sheets (Lead tracking and sequence state)
* **Logic:** Wait nodes and conditional routing for multi-day delays.

## 🧠 System Architecture
1.  **Lead Injection:** New leads are pulled from Google Sheets.
2.  **Sequence Management:** The workflow uses a combination of `Wait` nodes or scheduled triggers to track which "Day" a lead is currently on.
3.  **Template Engine:** Based on the sequence day, the system selects a specific pre-written template to ensure professional and compliant communication.
4.  **Twilio Dispatch:** Messages are sent via Twilio, with the status synced back to Google Sheets to provide a full audit trail of the conversation.

## 📋 Setup Instructions
1.  **Sheet Setup:** Your Google Sheet must include columns for `Lead Name`, `Phone`, `Signup Date`, and `Current Step` (1-6).
2.  **Twilio Config:** Connect your Twilio SID/Token and ensure your "From" number is SMS-enabled.
3.  **Template Customization:** Update the "Set" or "Template" nodes in n8n with your specific outreach copy for each of the 6 stages.

---
*Developed by Hussein Adebayo ("Automate") — Expert in Revenue Operations and Lead Nurturing Systems.*
