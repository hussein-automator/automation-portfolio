# AI-Driven RSS Newsletter Pipeline

This repository contains a sophisticated content automation engine that monitors global industry trends via RSS and utilizes Large Language Models (LLMs) to synthesize, draft, and distribute professional newsletters. This pipeline bridges the gap between raw information and ready-to-publish content.

## 🚀 Business Value
* **Automated Content Curation:** Eliminates hours of manual research by automatically scanning RSS feeds for relevant industry news.
* **Intelligent Summarization:** Uses OpenAI to filter out noise and extract high-value insights, ensuring the newsletter is concise and impactful.
* **Omnichannel Distribution:** Creates a permanent record in Google Docs for archival/editing while simultaneously pushing the final version to Telegram for immediate consumption.

## 🛠 Tech Stack
* **Orchestration:** n8n
* **Intelligence:** OpenAI (GPT-4o)
* **Ingestion:** RSS Feed Parser
* **Document Management:** Google Docs API
* **Communication:** Telegram Bot API

## 🧠 System Architecture
The pipeline follows a seamless "Ingest-Synthesize-Deploy" logic:

1.  **Trigger (RSS):** Continuously monitors a curated list of RSS feeds for new articles or updates.
2.  **Content Extraction:** Pulls raw text and metadata from the identified sources.
3.  **AI Synthesis (OpenAI):** Analyzes the raw content to generate headlines, bulleted summaries, and a cohesive narrative in a specified newsletter format.
4.  **Document Archival (Google Docs):** Automatically creates a formatted document containing the full draft, allowing for further manual polish or long-term storage.
5.  **Instant Delivery (Telegram):** Sends the final, ready-to-read newsletter to a Telegram channel, providing an instant feedback loop for the creator or subscribers.

## 📋 Setup Instructions
1.  **RSS Configuration:** Add your target feed URLs into the RSS trigger node.
2.  **OpenAI API:** Configure your API key and set the system prompt to define the "voice" and "tone" of your newsletter.
3.  **Google Workspace Setup:** Authenticate via OAuth2 to allow n8n to create and write to Google Docs.
4.  **Telegram Bot:** Initialize a bot via BotFather and provide the `CHAT_ID` and `BOT_TOKEN` to receive the final outputs.

---
*Developed by Hussein Adebayo ("Automate") — Expert in Revenue Operations and Intelligence.*
