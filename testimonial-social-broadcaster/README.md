# Automated Testimonial-to-Social Distribution Engine

This repository contains a high-efficiency automation pipeline that converts customer testimonials into multi-platform social media posts. By integrating a CRM-driven trigger with a unified social posting API, the system ensures that positive social proof is amplified across the web the moment it is received.

## 🚀 Business Value
* **Social Proof Amplification:** Automatically broadcasts client success stories to five platforms, increasing brand authority and trust without manual intervention.
* **Reputation-Marketing Loop:** Closes the gap between receiving a testimonial and publishing it, ensuring marketing content is always fresh and relevant.
* **Operational Efficiency:** Saves hours of manual copy-pasting and scheduling by handling the formatting and distribution through a single orchestration layer.

## 🛠 Tech Stack
* **Orchestration:** n8n
* **CRM / Trigger:** GoHighLevel (GHL)
* **Social Distribution:** Socialbu (Facebook, Instagram, LinkedIn, X, Google Business Profile)
* **Logic:** Custom JavaScript for content parsing and URL normalization

## 🧠 System Architecture
The workflow follows a "Capture-Publish-Sync" lifecycle:

1.  **Lead Capture (GoHighLevel):** Triggers via webhook the moment a client submits a testimonial through a GHL form or reputation management module.
2.  **Content Transformation:** Extracts the testimonial text and customer details, formatting them into platform-optimized snippets.
3.  **Omnichannel Publishing (Socialbu):** Simultaneously dispatches the content to:
    * Facebook (Page/Group)
    * Instagram (Business)
    * LinkedIn (Profile/Company)
    * X (formerly Twitter)
    * Google Business Profile (GBP)
4.  **Status Polling & Verification:** Implements short delays (e.g., 20 seconds) to verify successful publication on each platform.
5.  **CRM Feedback Loop:** Retrieves the live post URLs and pushes them back into the GoHighLevel contact or opportunity record, providing a complete audit trail of the marketing activity.

## 📋 Setup Instructions
1.  **GHL Webhook:** Create a "Workflow" in GoHighLevel that triggers on "Testimonial Submitted" and sends a POST request to the n8n webhook URL.
2.  **Socialbu API:** Connect your Socialbu account and retrieve your API Key. Ensure your social accounts are already linked within the Socialbu dashboard.
3.  **Variable Mapping:** Ensure the `customData` fields in the GHL webhook match the logic in the n8n "Set" nodes.
4.  **Verification:** The workflow includes `Wait` nodes (20s) to allow the Socialbu API to return the unique post IDs for each platform.

---
*Developed by Hussein Adebayo ("Automate") — Systems Architect specializing in Revenue Operations and Intelligence.*
