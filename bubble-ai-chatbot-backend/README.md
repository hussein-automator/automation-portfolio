# AI Chatbot Backend for Bubble.io Applications

This repository contains a production-ready n8n workflow that serves as the "brain" for a custom chatbot built on Bubble.io. It utilizes a webhook-based architecture to handle real-time user inquiries, maintain conversational context, and synchronize AI-generated responses back to a No-Code database.

## 🚀 Business Value
* **Enhanced User Engagement:** Provides instant, context-aware support and interaction within a web application.
* **Architecture Decoupling:** Offloads complex AI logic and API processing from the front-end (Bubble) to a specialized orchestration layer (n8n), reducing app bloat and improving performance.
* **Scalable Data Sync:** Ensures every AI interaction is logged and stored in the primary CRM/Database for future analysis and personalization.

## 🛠 Tech Stack
* **Orchestration:** n8n
* **Frontend/No-Code:** Bubble.io
* **Intelligence:** OpenAI (GPT-4o)
* **API Communication:** REST API (Webhooks & HTTP Requests)

## 🧠 System Architecture
The workflow functions as a bi-directional bridge between the user interface and the LLM:

1.  **Request Ingestion (Webhook):** Receives structured data from the Bubble application, including the user's message and unique `conversation_id`.
2.  **Context Logic:** Evaluates whether the incoming request is a "New Conversation" or a continuation of an "Existing Thread" to ensure the AI has the necessary historical context.
3.  **LLM Synthesis:** Dispatches the cleaned prompt to OpenAI, utilizing optimized system instructions to align with the application's specific goals.
4.  **Database Synchronization:** Triggers a POST request back to the Bubble Data API (`save_ai_message` workflow) to store the response and update the user's view in real-time.

## 📋 Setup Instructions
1.  **Bubble API Configuration:**
    * Enable the "Workflow API" in your Bubble settings.
    * Create a backend workflow named `save_ai_message` to receive the n8n payload.
2.  **n8n Webhook:** Copy the Production Webhook URL from the n8n trigger and paste it into your Bubble API Connector or Action.
3.  **OpenAI API:** Securely add your `OPENAI_API_KEY` to the n8n credentials.
4.  **Environment Variables:**
    * `BUBBLE_API_TOKEN`: Required for secure authentication back to your app.
    * `APP_URL`: Your Bubble application's base URL.

---
*Developed by Hussein Adebayo ("Automate") — Expert in Revenue Operations and Intelligence.*
