# 💼 Automated Job Search & Cover Letter Generator with Match Scoring (n8n + Gemini)

## 📌 Overview

This project automates the job search and application process using **n8n** for orchestration and **Google Gemini AI** for scoring and writing cover letters.

It:
- Fetches job listings from LinkedIN
- Scores each listing based on your skills
- Generates personalized cover letters
- Logs everything in Google Sheets
- Sends a daily email with the best matches

---

## ✨ Features

- ⏰ **Daily Automation** — Runs every day at a set time (e.g., 10:00 AM IST)
- 🔎 **Job Fetching** — Using Rss.app and HTTP Request.
- 🧠 **AI Match Scoring** — Compares your resume with job descriptions and gives a match score on 5.
- 📝 **Custom Cover Letters** — Generated using Google Gemini tailored to each job
- 📊 **Google Sheets Logging** — Stores job details, scores, and cover letters.
- 📧 **Email Summary** — Sends daily summary email with top matches

---

## ⚙️ Tech Stack

| Component      | Technology                                      |
|----------------|--------------------------------------------------|
| Orchestration  | n8n                                              |
| Job Search     | RSS.app (LinkedIn), HTTP Request Node            |
| AI Integration | Google Gemini ChatModel                          |
| Storage        | Google Sheets                                    |
| Notification   | Gmail (via n8n)                                  |
| Resume Parsing | Gemini JSON Output                               |

---

## 🚀 Getting Started


### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/job-auto-generator.git
cd job-auto-generator
```

### 2. Prepare Your Environment

- Set up environment variables (if using backend service)
- Ensure Google Sheet API access is configured in n8n
- Have access to:
  - Google Gemini API key
  - RSS.app feed for job listings
  - Gmail SMTP credentials (or use Gmail node in n8n)

### 3. Import the n8n Workflow

- Go to [n8n.io](https://n8n.io) or your self-hosted instance
- Import `n8n_job_auto.json`
- Configure each node:
  - RSS Feed URL from RSS.app
  - HTTP Request for scraping full job descriptions
  - Gemini API (via HTTP Node or custom function)
  - Google Sheets Node (select spreadsheet and sheet)
  - Gmail Node (set up with your credentials)

## 🔄 Workflow Diagram

```text
[Schedule Trigger]
     ↓
[RSS Feed Node] — fetch LinkedIn job posts
     ↓
[HTTP Request] — scrape full job descriptions
     ↓
[Loop Over Jobs]
     ↓
[Gemini ChatModel - Extract JSON Info]
     ↓
[Gemini ChatModel - Match Score (out of 5)]
     ↓
[Gemini ChatModel - Cover Letter Generator]
     ↓
[Code Node - Clean/Format Response]
     ↓
[Google Sheets - Append Row]
     ↓
[Gmail Node - Email Top Matches]
```



## 📸 Screenshots

### 🧾 Google Sheet Output

![Google Sheet](assets/sheet_sample.png)

---


### 📬 Daily Summary Email

![Email Summary](assets/email_sample.png)

---

### 🔁 n8n Workflow View

![Workflow Screenshot](assets/workflow_screenshot.png)

---




