# 🟠 Alpha Finance — AI Financial Intelligence System

> An AI-powered financial data processing system built on **independent REST API workflows**.  
> Each endpoint handles a specific financial task: receipt OCR, transaction analysis, AI assistant, notifications, and OTP verification.

![n8n](https://img.shields.io/badge/n8n-REST%20API-FF6D5A?style=flat-square&logo=n8n&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4%20Vision-412991?style=flat-square&logo=openai&logoColor=white)
![Webhook](https://img.shields.io/badge/Trigger-Webhook-f59e0b?style=flat-square)
![Gmail](https://img.shields.io/badge/Gmail-OTP-EA4335?style=flat-square&logo=gmail&logoColor=white)

---

---

## 📷 System Screenshots

| Chat Bot | Financial Analyst |
|----------|-----------------|
| ![Chat Bot](./Alpha_Chat_Bot.png) | ![Financial Analyst](./Alpha_Financial_Analyst.png) |

| Notifications | Send OTP Email |
|--------------|----------------|
| ![Notifications](./Alpha_Notifications.png) | ![Send OTP Email](./Alpha_Send_OTP_Email.png) |

---

## 🏗️ System Architecture

```
Client Application
        │
        ├── POST /receipt      ──▶  Alpha_Transaction_Extraction.json
        │                              └── [GPT-4 Vision → OCR → Structured JSON]
        │
        ├── POST /analyze      ──▶  Alpha_Analyze.json
        │                              └── [GPT-4 → Financial Report]
        │
        ├── POST /assist       ──▶  Alpha_Assist.json
        │                              └── [AI Agent + Conversation Memory]
        │
        ├── POST /notification ──▶  Alpha_Notifications.json
        │                              └── [Push Notification Sender]
        │
        └── POST /otp          ──▶  Alpha-OTP.json
                                       └── [Gmail OTP Verification]
```

---

## 📂 Workflows

| File | Endpoint | Purpose | Nodes | Size |
|------|----------|---------|-------|------|
| `Alpha_Transaction_Extraction.json` | `POST /receipt` | Extracts transactions from receipt images and bank statements using GPT-4 Vision OCR | 19 | 33 KB |
| `Alpha_Analyze.json` | `POST /analyze` | Analyzes financial data and generates a structured report | 9 | 29 KB |
| `Alpha_Assist.json` | `POST /assist` | Conversational AI financial assistant with memory | 8 | 33 KB |
| `Alpha_Notifications.json` | `POST /notification` | Sends push notifications to users | 7 | 4.6 KB |
| `Alpha-OTP.json` | `POST /otp` | One-Time Password verification system via Gmail | 5 | 3.3 KB |

---

## 🛠️ Tech Stack

| Technology | Role |
|-----------|------|
| **OpenAI GPT-4 Vision** | Analyzes receipt images and extracts transaction data |
| **OpenAI GPT-4** | Financial text analysis and Q&A responses |
| **Structured Output Parser** | Returns clean, machine-readable JSON responses |
| **Webhook REST API** | Independent HTTP entry point for each workflow |
| **Gmail API** | Sends OTP codes for user identity verification |

---

## ✅ Why This Design?

| Principle | How It’s Applied |
|-----------|------------------|
| **Independence** | Each workflow runs and scales independently — no shared state |
| **Speed** | Each endpoint handles a single, focused task — minimal latency |
| **Testability** | Call any workflow directly without running a full system |
| **Single Responsibility** | One file, one purpose — clear ownership and easy debugging |
