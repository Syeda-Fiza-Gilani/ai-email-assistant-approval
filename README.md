# 📧 Autonomous AI Email Assistant with Human Approval (n8n + Gemini)

An enterprise-grade **n8n workflow** that automatically processes incoming emails via Gmail, converts HTML content into clean Markdown, generates summaries and contextual draft replies using Google Gemini AI, and routes drafts through a **Human-in-the-Loop (HITL) approval link** before dispatching.

---

## 📌 Workflow Architecture

<img width="1444" height="574" alt="image" src="https://github.com/user-attachments/assets/9d73885c-4eeb-4f80-a1e0-0aa43fb01864" />

---

## 🚀 Key Features

* **Automated Email Intake:** Listens for new incoming emails in Gmail in real time.
* **Clean Text Extraction:** Converts raw HTML email bodies into clean Markdown for optimized token efficiency and precise LLM interpretation.
* **Dual-Stage Gemini AI Pipeline:**
  * **Stage 1 (Summarization):** Distills incoming message context using Google Gemini Chat Model.
  * **Stage 2 (Response Agent):** Synthesizes incoming context and memory to draft a professional response.
* **Human-in-the-Loop (HITL) Safety Guard:** Sends an approval request (email/form link) to review or tweak the draft before anything is sent.
* **Conditional Dispatch:** Only fires the final outbound Gmail response if explicit approval (`Approved == True`) is received.

---

## 🛠️ Prerequisites & Setup

1. **n8n Instance:** Version 1.0+ (Self-hosted Docker or n8n Cloud).
2. **Required Credentials:**
   * **Google Gemini API Key:** Connected to `@n8n/n8n-nodes-langchain.lmChatGoogleGemini`.
   * **Gmail OAuth2 Credential:** Connected to Gmail Trigger and Gmail Send nodes.

---

## 📥 Installation & Usage

1. Clone this repository:
   ```bash
   git clone https://github.com/Syeda-Fiza-Gilani/ai-email-assistant-approval.git
