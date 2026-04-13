# AI Video Production & Publishing Pipeline

This repository contains a dual-workflow automation engine that transforms raw text documents into professional AI-avatar videos and handles automated distribution to YouTube. It replicates a high-touch manual production process using a 100% automated agentic architecture.

## 🚀 Business Value
* **Scalable Content Production:** Converts static `.txt` or `.md` notes into fully produced video assets without manual editing.
* **Consistency at Scale:** Ensures every video maintains the same tone, visual dimension, and professional "pose" through strict API parameter control.
* **Human-in-the-Loop Publishing:** Automates the technical heavy lifting of YouTube uploads while keeping videos "Unlisted" for a final human quality check before going live.

## 🛠 Tech Stack
* **Orchestration:** n8n
* **AI Video Synthesis:** HeyGen API
* **Content Intelligence:** Claude API (Anthropic)
* **Storage & Triggers:** Google Drive / Google Docs
* **Distribution:** YouTube API
* **Data Tracking:** Google Sheets

## 🧠 System Architecture

### Phase 1: The Creator Workflow (`Heygen_avatar_video`)
This workflow handles the "Creative" heavy lifting:
1.  **File Ingestion:** Monitors Google Drive for new `.txt` or `.md` files.
2.  **Script Synthesis:** Extracts raw text and utilizes the Claude API to transform unstructured notes into a professional, timed narration script.
3.  **Avatar Generation:** Dispatches the script to HeyGen with specific configurations (Orientation: Portrait, Avatar ID, and Pose).
4.  **Status Polling:** Implements a recursive check (polling) to monitor video rendering progress, ensuring the workflow only proceeds once the asset is ready for download.

### Phase 2: The Publisher Workflow (`Post-2-Youtube`)
This workflow handles the "Technical" distribution:
1.  **Asset Retrieval:** Triggers via Webhook once the video is rendered, downloading the high-quality file via HTTP Request.
2.  **Metadata Cleanup:** Uses custom logic to clean file titles and prepare SEO-friendly descriptions.
3.  **Secure Upload:** Integrates with the YouTube API to upload the video as "Unlisted," allowing for final review.
4.  **Audit Trail:** Updates a central Google Sheet with the live video URL and processing status.

## 📋 Setup Instructions
1.  **n8n Environment:** Ensure you have the YouTube, Google Drive, and Google Sheets nodes configured.
2.  **API Credentials:**
    * `HEYGEN_API_KEY`: For video agent generation.
    * `CLAUDE_API_KEY`: For script transformation.
    * `YOUTUBE_OAUTH2`: For secure channel uploads.
3.  **Polling Configuration:** The system is set to wait for 5-minute intervals during the HeyGen render phase to optimize API call efficiency.

---
*Developed by Hussein Adebayo ("Automate") — Expert in Revenue Operations and Intelligence.*
