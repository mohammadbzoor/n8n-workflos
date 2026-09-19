# 🔵 WF CV System — Full CV Development Platform

> A complete, production-ready **AI-powered CV development platform** built on a **Microservices architecture** using n8n.  
> Users interact via a **Telegram Bot**, and all CV data is stored in **MySQL**.

![n8n](https://img.shields.io/badge/n8n-Microservices-FF6D5A?style=flat-square&logo=n8n&logoColor=white)
![Telegram](https://img.shields.io/badge/Telegram-Bot-26A5E4?style=flat-square&logo=telegram&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4-412991?style=flat-square&logo=openai&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-Database-4479A1?style=flat-square&logo=mysql&logoColor=white)

---

## 🏗️ System Architecture

![WF CV System Architecture](./architecture.jpg)

---

## 🔄 Workflow Flow

```
📱 Telegram User
        │
        ▼
┌─────────────────────────────┐
│  WF_00 — Channel Gateway    │  ← Receives all Telegram messages & classifies them
└─────────────────────────────┘
        │
        ▼
┌─────────────────────────────┐
│  WF_01 — Orchestrator       │  ← Routes requests to the correct sub-workflow
└─────────────────────────────┘
        │
   ┌────┴────┬──────────┬──────────┬──────────┐
   ▼         ▼          ▼          ▼          ▼
WF_10     WF_11      WF_12      WF_14      WF_20
Create    Analyze   Gen PDF    Match Job  File Proc
        │
        ▼
┌─────────────────────────────┐
│  WF_31 — CV Structurer      │  ← Structures CV data before storing in MySQL
└─────────────────────────────┘
        │
        ▼
┌─────────────────────────────┐
│  WF_90 — Response Dispatcher│  ← Sends the final reply back to the user
└─────────────────────────────┘
        │
        ▼
📱 Telegram User
```

---

## 📂 Workflows

| File | Purpose | Nodes | Size |
|------|---------|-------|------|
| `WF_00_Channel_Gateway.json` | **Main Gateway** — Receives all Telegram messages, classifies intent, and routes to the orchestrator | 29 | 31 KB |
| `WF_01_Assistant_Orchestrator.json` | **Orchestrator** — Analyzes user requests and dispatches to the correct sub-workflow | 7 | 12 KB |
| `WF_10_Create_CV.json` | **CV Creator** — Generates a complete, structured resume from user input using GPT-4 | 18 | 42 KB |
| `WF_11_Analyze_CV.json` | **CV Analyzer** — Evaluates an existing CV, provides feedback and improvement suggestions | 17 | 89 KB |
| `WF_12_Generate_Optimized_CV_PDF.json` | **PDF Generator** ⭐ — Generates a professionally formatted, ATS-optimized CV as a PDF | 27 | 175 KB |
| `WF_13_Generate_Cover_Letter_PDF.json` | **Cover Letter** — Generates a tailored cover letter PDF *(in development)* | 2 | 2 KB |
| `WF_14_Match_CV_With_Job.json` | **Job Matcher** — Compares a CV against a job description and scores the fit | 23 | 57 KB |
| `WF_20_File_Processor.json` | **File Processor** — Extracts and parses text from uploaded PDF and DOCX files | 29 | 30 KB |
| `WF_31_CV_Structurer.json` | **Data Structurer** — Normalizes and structures CV data before saving to MySQL | 7 | 13 KB |
| `WF_90_Response_Dispatcher.json` | **Response Dispatcher** — Formats and sends the final reply to the user via Telegram | 5 | 6.5 KB |

> ⭐ **WF_12** is the largest file (175 KB) and produces the user-facing PDF output.  
> ⚠️ **WF_13** is currently under development (skeleton only — 2 nodes).

---

## 🛠️ Tech Stack

| Technology | Role |
|-----------|------|
| **OpenAI GPT-4** | CV content generation, analysis, job matching |
| **MySQL** | Persistent storage for user profiles and CV data |
| **Telegram Bot API** | Primary user communication channel |
| **HTTP API** | Calls external PDF generation service |
| **n8n Sub-Workflows** | Microservices architecture — each feature is isolated |

---

## ✅ Design Strengths

| Strength | Description |
|----------|-------------|
| **Microservices Architecture** | Each function lives in its own sub-workflow — easier to develop, test, and maintain independently |
| **Separation of Concerns** | The gateway (WF_00) is fully decoupled from business logic (WF_01+) and from response delivery (WF_90) |
| **Scalable Design** | New capabilities can be added as new sub-workflows without touching any existing ones |
| **Modular Processing** | File processing, CV structuring, and response dispatching each run independently |

---

## 📝 Developer Notes

- This is the **most mature and feature-complete** project in this repository.
- The previous single-agent version is in [`02_CvDevloper/`](../02_CvDevloper/README.md).
- `WF_13` (Cover Letter PDF) is a **work in progress** — it exists as a scaffold only.
- Import workflows in order: `WF_00` first, then `WF_01`, then the feature workflows, then `WF_90`.
