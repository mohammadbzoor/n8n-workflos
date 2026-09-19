# 🤖 n8n AI Workflows Portfolio

<div align="center">

**A curated collection of production-ready n8n AI automation workflows**  
covering CV processing, financial intelligence, conversational agents, smart recruitment, and personal productivity.

![n8n](https://img.shields.io/badge/n8n-Workflows-FF6D5A?style=for-the-badge&logo=n8n&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4-412991?style=for-the-badge&logo=openai&logoColor=white)
![Status](https://img.shields.io/badge/Status-Active-22c55e?style=for-the-badge)
![Projects](https://img.shields.io/badge/Projects-7-3b82f6?style=for-the-badge)
![Workflows](https://img.shields.io/badge/Workflows-22-f59e0b?style=for-the-badge)

</div>

---

## 📁 Repository Structure

```
n8n-workflos/
├── 01_WF_CV_System/      🔵  Full CV Platform — Microservices Architecture    [10 workflows]
├── 02_CvDevloper/        🟢  AI CV Assistant — Single Agent                   [ 1 workflow ]
├── 03_Alpha_Finance/     🟠  Financial Intelligence System — REST API          [ 5 workflows]
├── 04_WAgent_Chatbot/    🔴  Multi-Platform AI Chatbot — WhatsApp + Messenger  [ 2 workflows]
├── 05_CV_Matching_RAG/   🟡  Smart Recruitment — RAG + Vector Search           [ 1 workflow ]
├── 06_Secretary_MCP/     🟣  AI Secretary — MCP Protocol + Telegram            [ 1 workflow ]
├── teckNetworks/         🤖  AI Recruitment Ecosystem — ATS + Engine           [ 2 workflows]
└── README.md             📄  This file
```

---

## 🚀 Projects Overview

### 🔵 [01 — WF CV System](./01_WF_CV_System/README.md)
> **Full-stack CV development platform with Microservices architecture**

The most advanced project in this repo. Each feature runs as a dedicated sub-workflow (WF_00 → WF_90), triggered through a Telegram Bot and persisting data in MySQL.

`Telegram Bot` · `OpenAI GPT-4` · `MySQL` · `n8n Sub-Workflows` · `PDF Generation`

---

### 🟢 [02 — CV Developer](./02_CvDevloper/README.md)
> **Conversational AI assistant for building and improving resumes**

A single AI Agent node that guides users through creating or optimizing their CV via an interactive chat interface — the prototype that evolved into the full CV System.

`OpenAI GPT-4` · `n8n AI Agent` · `n8n Chat UI`

---

### 🟠 [03 — Alpha Finance](./03_Alpha_Finance/README.md)
> **AI-powered financial data extraction and analysis system**

Five independent REST API endpoints for financial intelligence: receipt OCR via Vision AI, transaction analysis, an AI financial assistant with memory, push notifications, and OTP email verification.

`OpenAI GPT-4 Vision` · `Webhook REST API` · `Gmail API` · `Structured Output`

---

### 🔴 [04 — WAgent Chatbot](./04_WAgent_Chatbot/README.md)
> **Feature-rich AI agent for WhatsApp and Facebook Messenger**

A multi-platform conversational agent with 12+ integrated tools: real-time web search, calendar management, email, Twitter/X posting, Google Sheets, voice message transcription, and more.

`WhatsApp` · `Messenger` · `Evolution API` · `OpenAI Whisper` · `Perplexity AI` · `Google Calendar`

---

### 🟡 [05 — CV Matching RAG](./05_CV_Matching_RAG/README.md)
> **Semantic candidate-to-job matching using Vector Search and RAG**

Matches resumes with job descriptions using a two-stage approach: fast semantic search via Pinecone, followed by precision reranking with Cohere, then GPT-4 generates detailed match reports.

`Pinecone Vector DB` · `OpenAI Embeddings` · `Cohere Reranker` · `RAG Pipeline`

---

### 🟣 [06 — Secretary MCP](./06_Secretary_MCP/README.md)
> **Intelligent Telegram secretary powered by MCP Protocol**

An AI agent on Telegram that orchestrates external tools via the Model Context Protocol — creating calendar events, reading emails, running web searches, and answering questions in natural language.

`MCP Protocol` · `OpenAI GPT-4` · `Google Calendar` · `Gmail` · `Telegram Bot`

---

### 🤖 [teckNetworks — AI Recruitment Ecosystem](./teckNetworks/README.md)
> **End-to-end hiring automation: ATS analyzer + semantic recruiter engine**

A two-sided recruitment system. Candidates upload their CV and receive an ATS compatibility score with improvement tips. Recruiters search for candidates using natural language, and the system returns ranked matches with AI-generated explanations.

`Pinecone` · `OpenAI GPT-4o` · `Cohere Reranking` · `ATS Scoring Engine` · `PDF Extraction`

---

## 📈 Development Timeline

```
Phase 1 — CV Assistant Prototype
   └── 02_CvDevloper          ← Simple single-agent version

Phase 2 — Full CV Platform (Microservices Rebuild)
   └── 01_WF_CV_System        ← 10 sub-workflows: WF_00 → WF_90

Phase 3 — Semantic Search & RAG
   └── 05_CV_Matching_RAG     ← Pinecone + Cohere Reranker

Phase 4 — Multi-Platform Conversational Agent
   └── 04_WAgent_Chatbot      ← WhatsApp + Messenger + Voice

Phase 5 — Financial Intelligence
   └── 03_Alpha_Finance       ← Receipt OCR + Financial AI

Phase 6 — MCP Protocol Integration
   └── 06_Secretary_MCP       ← MCP-powered Telegram Secretary

Phase 7 — Full Recruitment Ecosystem
   └── teckNetworks           ← ATS Analyzer + Recruitment Engine
```

---

## 🛠️ Tech Stack at a Glance

| Technology | Role | Used In |
|-----------|------|---------|
| **OpenAI GPT-4 / GPT-4o** | Primary reasoning LLM | All projects |
| **OpenAI GPT-4 Vision** | Image & receipt analysis | 03 |
| **OpenAI Embeddings** | Text-to-vector for semantic search | 05, teckNetworks |
| **OpenAI Whisper** | Voice message transcription | 04 |
| **Pinecone Vector DB** | Semantic storage and fast search | 05, teckNetworks |
| **Cohere Reranker** | Second-pass relevance ranking | 05, teckNetworks |
| **MCP Protocol** | Model Context Protocol tool orchestration | 06 |
| **Telegram Bot API** | Primary user communication channel | 01, 06 |
| **Evolution API** | Flexible WhatsApp API layer | 04 |
| **MySQL** | Relational CV data storage | 01 |
| **Gmail API** | Email reading, sending, OTP | 03, 06 |
| **Google Calendar API** | Calendar event management | 04, 06 |
| **Webhook REST API** | HTTP trigger for each workflow | 03 |
| **SerpAPI / Perplexity** | Real-time web search | 04, 06 |

---

## 📊 Repository Stats

| Metric | Value |
|--------|-------|
| Total JSON Workflows | **22 files** |
| Total Workflow Images | **14 screenshots** |
| Total Projects | **7 projects** |
| Largest Workflow | `WF_12_Generate_Optimized_CV_PDF.json` — 175 KB |
| Most Complex Project | `01_WF_CV_System` — 10 interconnected sub-workflows |
| Most Advanced Tech | `teckNetworks` — ATS + Vector DB + Reranking |

---

## ⚡ Quick Start

1. Install [n8n](https://n8n.io/) (self-hosted or cloud)
2. Open any project folder and read its `README.md`
3. In n8n: **Workflows → Import from file** → select the `.json` file
4. Configure the required credentials (API keys, tokens, DB connections)
5. Activate the workflow and test

> **Note:** Each project folder contains a dedicated `README.md` with full setup instructions and workflow descriptions.

---

*Last updated: September 2026*
