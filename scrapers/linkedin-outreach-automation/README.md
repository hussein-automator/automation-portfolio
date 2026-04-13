# LinkedIn Job Application & Outreach Engine

This automation system is designed to streamline professional networking and job application follow-ups. By combining web scraping, LLM-based personalization, and unified messaging APIs, the workflow ensures consistent engagement with hiring managers at scale.

## 🚀 Business Value
* **Automated Lead Discovery:** Leverages high-performance scraping to identify targets without manual searching.
* **Speed-to-Lead:** Drastically reduces the time between a job application and the initial outreach message—a critical factor in competitive hiring.
* **Intelligent Personalization:** Uses OpenAI to tailor messages based on scraped data, ensuring outreach doesn't feel "robotic."

## 🛠 Tech Stack
* **Orchestration:** n8n
* **Messaging API:** Unipile (LinkedIn Integration)
* **Data Extraction:** Apify
* **Database:** Google Sheets
* **Intelligence:** OpenAI (GPT-4o/mini)
* **Communication:** Gmail (for secondary follow-ups/notifications)

## 🧠 System Architecture
The workflow follows a structured path from data extraction to final communication:

1.  **Data Ingestion (Apify):** Triggers scraping tasks to extract LinkedIn profile data, job descriptions, or company insights.
2.  **Centralized Database (Google Sheets):** Acts as the "Source of Truth" for lead tracking, storing contact info and outreach status.
3.  **AI Personalization (OpenAI):** Analyzes the scraped data to generate highly relevant, professional outreach copy.
4.  **Multi-Channel Dispatch:** * **Primary:** Sends LinkedIn messages via **Unipile** to maintain high response rates.
    * **Secondary:** Triggers **Gmail** notifications or emails where necessary for the workflow.
5.  **Status Sync:** Updates Google Sheets with timestamps and "Sent" confirmations to prevent duplicate outreach.

## 📋 Setup Instructions
1.  **Google Sheets:** Set up a sheet with headers for `Name`, `LinkedIn URL`, `Status`, and `Custom Message`.
2.  **Apify Integration:** Connect your Apify API key to trigger specific LinkedIn or Web scrapers.
3.  **Unipile Setup:** Authenticate your LinkedIn account via Unipile and add the `DSN` and `Access Token` to the n8n nodes.
4.  **OpenAI Config:** Provide an API key and define the system prompt for your professional "voice."

---
*Developed by Hussein Adebayo ("Automate") — Expert in Revenue Operations and Intelligence.*
