# 📧 Gmail Automation based on CrewAI

An intelligent Gmail automation system powered by CrewAI agents.
Automatically categorize, prioritize, organize, respond to, and clean your inbox — safely and intelligently.

---

## 🚀 Overview

CrewAI Gmail Automation connects securely to your Gmail account using IMAP and deploys AI agents to:

* Analyze unread emails
* Assign strict priority levels
* Apply labels and stars
* Generate draft responses
* Send Slack notifications (optional)
* Clean up low-value emails safely
* Protect important content like YouTube communications

This system helps you maintain a clean, actionable inbox without manual sorting.

---

## ✨ Features

### 📋 Smart Email Categorization

Automatically classifies emails into:

* Personal
* Promotions
* Newsletters
* Receipts
* YouTube-related
* System notifications

---

### 🔔 Priority Assignment

Each email is strictly labeled as:

* **HIGH** – Requires immediate attention
* **MEDIUM** – Important but not urgent
* **LOW** – Can be archived or deleted

---

### 🏷 Smart Organization

* Applies Gmail labels
* Adds stars to high-priority emails
* Preserves structured inbox organization

---

### ✍ Automated Draft Responses

* Generates contextual reply drafts
* Saves drafts directly in Gmail
* You remain in full control before sending

---

### 🔔 Slack Notifications (Optional)

High-priority emails trigger Slack notifications so you never miss critical messages.

---

### 🧹 Intelligent Cleanup

Built-in deletion rules:

* Promotions older than 2 days → deleted
* Newsletters older than 7 days → deleted (unless HIGH priority)
* Certain low-value emails → auto-removed
* Receipts and important documents → archived safely

---

### 🎬 YouTube Email Protection

All YouTube-related emails are:

* Preserved
* Marked READ_ONLY
* Never deleted

---

### 🧵 Thread Awareness

Understands email threads and maintains context across conversations.

---

## 🏗 How It Works

1. Establishes a secure SSL connection to `imap.gmail.com`
2. Authenticates using your Gmail App Password
3. Fetches unread emails
4. Runs AI agents for classification & decision-making
5. Applies actions (labels, drafts, deletions)
6. Closes connection securely

No emails are stored externally.
All operations occur directly on Gmail servers via IMAP.

---

## 🛠 Installation

```bash
# Clone the repository
git clone https://github.com/your-username/crewai-gmail-automation.git
cd crewai-gmail-automation

# Create virtual environment
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate

# Install dependencies
crewai install
```

---

## ⚙️ Configuration

Create a `.env` file in the project root:

```
# LLM Provider (choose one)

# OpenAI (Recommended)
MODEL=openai/gpt-4o-mini
OPENAI_API_KEY=your_openai_api_key

# Gemini
# MODEL=gemini/gemini-2.0-flash
# GEMINI_API_KEY=your_gemini_api_key

# Ollama (tool-enabled models only)
# MODEL=ollama/llama3-groq-tool-use

# Gmail Credentials
EMAIL_ADDRESS=your_email@gmail.com
APP_PASSWORD=your_gmail_app_password

# Optional: Slack Notifications
SLACK_WEBHOOK_URL=your_slack_webhook_url
```

---

## 🔐 Create a Gmail App Password

1. Go to your Google Account → Security
2. Enable **2-Step Verification**
3. Navigate to **App Passwords**
4. Select:

   * App: Mail
   * Device: Other (Custom name)
5. Name it: `CrewAI Gmail`
6. Copy the generated 16-character password
7. Paste into `.env` as `APP_PASSWORD`

⚠ App passwords require 2FA enabled.

---

## 🔗 Optional: Slack Webhook Setup

1. Visit [https://api.slack.com/apps](https://api.slack.com/apps)
2. Create a new app
3. Enable **Incoming Webhooks**
4. Add webhook to your workspace
5. Copy the webhook URL
6. Add it to `.env`

---

## ▶ Usage

Run the automation:

```bash
crewai run
```

You will be prompted to enter the number of unread emails to process.

The system will then:

1. Fetch unread emails
2. Categorize and prioritize
3. Apply labels & stars
4. Generate drafts if needed
5. Send Slack alerts (if enabled)
6. Clean up low-priority clutter

---

## 🧠 LLM Compatibility

Supported providers:

* OpenAI (recommended)
* Gemini
* Ollama (tool-capable models only)

Ensure selected models support tool/function calling.

---

## 🔒 Security & Privacy

* Uses secure IMAP over SSL
* Requires App Password (not your real Google password)
* Credentials stored locally in `.env`
* No third-party email storage
* No external email logging

Your data remains under your control.

---

## 📦 Project Structure

```
.
├── agents/
├── tasks/
├── tools/
├── config/
├── .env
├── main.py
└── README.md
```

---

## 🤝 Contributing

Contributions are welcome.

1. Fork the repository
2. Create a feature branch
3. Submit a Pull Request

---

## 📄 License

MIT License

