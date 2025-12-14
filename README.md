# 🏋️ Gym AI Agent – Daily Stats & Report Automation

An automated AI-powered reporting system that fetches daily gym data, analyzes it using an LLM, and emails a concise operational report to the gym owner — fully hands-free.

Built using **n8n**, **Supabase Edge Functions**, and **Groq LLM APIs**.

---

## 🚀 What This Project Does

Every day at a scheduled time, this system automatically:

1. Fetches gym member data from a **secure Supabase Edge Function**
2. Classifies members into **high-value** and **standard** categories
3. Aggregates daily statistics
4. Uses an **LLM (via Groq)** to generate a business-focused report
5. Emails the report to the gym owner via SMTP

No dashboards.  
No manual clicks.  
Just actionable insights delivered daily.

---

## 🧠 AI Report Output

The AI-generated report includes:

- Member distribution summary
- Identification of high-value members
- One clear, actionable recommendation for the gym owner

The tone is **concise, operational, and business-focused**.

---

## 🧩 Architecture Overview

Schedule Trigger (Daily)
->
Supabase Members Edge Function
->
Data Classification (JavaScript)
->
Aggregation
->
LLM Analysis (Groq)
->
Email Delivery (SMTP)


---

## 🔧 Tech Stack

- **n8n** – Workflow orchestration
- **Supabase Edge Functions** – Secure backend APIs
- **Groq LLM API** – AI inference (OpenAI-compatible)
- **SMTP (Gmail App Password)** – Email delivery
- **JavaScript** – Data processing and logic

---

## 🔐 Supabase Members Function (External Dependency)

> ⚠️ **Important**
>
> The Supabase Edge Function used to fetch members is **NOT included in this repository**.

### Why it is excluded
- Uses **Supabase Service Role credentials**
- Contains **direct database access**
- Must remain private for security reasons

### What the function does
The external `members` Edge Function:
- Verifies admin authorization
- Fetches gym member records
- Returns normalized member data for reporting

### Expected API Response Shape

```json
{
  "success": true,
  "data": [
    {
      "id": 1,
      "name": "John Doe",
      "membership_plan": "Gold",
      "status": "active"
    }
  ]
}
```

The workflow depends on this response structure.

### Repository Contents
```
├── workflow.json        # Exported n8n workflow
├── README.md            # Project documentation
```

All credentials, API keys, and backend functions are intentionally excluded.

---
## ⚙️ Setup (High-Level)

Import workflow.json into n8n

Configure credentials inside n8n:

Supabase Members API (Service Role access)

Groq API key

SMTP email credentials

Activate the workflow

The daily report will run automatically


## 📊 Current Report Scope (v1)

Member classification (high-value vs standard)

Aggregated daily member statistics

AI-generated operational insight

Automated email delivery

## 🔮 Future Enhancements

Planned extensions for upcoming versions:

### 📈 Data Expansion

New members per day

Daily fee collection

Expense tracking

Profit calculation

### 🧠 Smarter AI Analysis

Weekly and monthly trend analysis

Churn risk detection

Retention and pricing recommendations

### 📬 Delivery Channels

WhatsApp notifications

Slack integration

Admin dashboard view

### 🔐 Scalability & Security

Role-based access

Multi-branch gym support

Per-owner report customization

## 🧪 Project Status

Version: v1
State: Stable & operational
Purpose: Learning, experimentation, and real-world automation

## 📄 License

MIT License — free to use, modify, and extend.

## 👤 Author

Shujahat Jadoon
Backend • Automation • AI Systems
GitHub: https://github.com/jadoondevs
