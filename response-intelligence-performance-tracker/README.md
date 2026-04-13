# Real-Time Lead Response & SLA Tracking System

This repository contains a high-performance "Speed-to-Lead" monitoring system designed for service-based businesses. The automation solves the "Smart Automation Problem" of tracking team accountability and response latency across unified messaging channels, ensuring no opportunity is lost due to slow engagement.

## 🚀 Business Value
* **Revenue Leakage Prevention:** Identifies missed opportunities in real-time by flagging leads that have not been acknowledged within defined Service Level Agreements (SLAs).
* **Operational Visibility:** Transforms raw messaging metadata into a structured Airtable CRM for leadership to monitor team performance and conversion trends.
* **Instant Accountability:** Triggers immediate Slack alerts for inbound messages, creating a transparent environment for response tracking and team coordination.

## 🛠 Tech Stack
* **Orchestration:** n8n
* **Unified Messaging API:** Unipile (Tracking LinkedIn, WhatsApp, or Email)
* **CRM & Dashboard:** Airtable
* **Communication:** Slack (Real-time team notifications)
* **Logic:** Custom JavaScript for precise timestamp differential calculation

## 🧠 System Architecture
The system operates as a state-machine that monitors the "Age" of a conversation:

1.  **Inbound Detection:** A Unipile webhook triggers the workflow the moment a new message is received across any connected channel.
2.  **CRM Synchronization:** The system searches the Airtable CRM to see if the message belongs to an active thread or a new inquiry.
3.  **Response Time Calculation:** A specialized logic node captures the `inbound_timestamp` and compares it against the `acknowledgment_timestamp` from the team.
4.  **SLA Flagging:** If the delta exceeds the business-defined threshold (e.g., 5 minutes), the system applies a "Late Response" flag in Airtable and triggers a priority escalation alert in Slack.
5.  **Performance Logging:** All data points—including response time in seconds—are logged to a centralized Airtable dashboard to calculate "Average Time to Respond" and individual team member efficiency.

## 📋 Setup Instructions
1.  **Webhook Configuration:** Set up the Unipile `message.received` webhook to point to the n8n production URL.
2.  **Airtable Schema:** Ensure your Base has a table with fields for `Inbound Time`, `Reply Time`, `Response Duration`, and `SLA Status`.
3.  **Threshold Definition:** Adjust the "Switch" node or JavaScript logic to define your specific "Late" vs "On-Time" response window.
4.  **Slack Integration:** Connect your Slack Workspace and define the specific channel for real-time lead alerts and performance escalations.

---
*Developed by Hussein Adebayo ("Automate") — Systems Architect specializing in Revenue Operations and Intelligence.*
