# 🔴 WAgent Chatbot — Multi-Platform AI Assistant

> An omnichannel, autonomous AI conversational agent supporting **WhatsApp** and **Facebook Messenger** with voice note processing, live web research, calendar management, and email automation.

<div align="center">

![n8n](https://img.shields.io/badge/n8n-Workflow-FF6D5A?style=flat-square&logo=n8n&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4-412991?style=flat-square&logo=openai&logoColor=white)
![Whisper](https://img.shields.io/badge/Whisper-Voice--to--Text-00A67E?style=flat-square&logo=openai&logoColor=white)
![Perplexity](https://img.shields.io/badge/Search-Perplexity%20AI-20808D?style=flat-square)
![WhatsApp](https://img.shields.io/badge/WhatsApp-Evolution%20API-25D366?style=flat-square&logo=whatsapp&logoColor=white)
![Messenger](https://img.shields.io/badge/Meta-Messenger-00B2FF?style=flat-square&logo=messenger&logoColor=white)

</div>

---

## 📷 System Screenshots

| WhatsApp + Evolution API Agent | Multi-Platform Messenger + Voice Agent |
|:------------------------------:|:--------------------------------------:|
| ![WAgent Evolution API](./WAgent_WhatsApp_Evolution_API.png) | ![MessengerBot](./WAgent_Messenger_Voice.png) |

---

## 🔄 Architectural Evolution

```
[ v1: Single-Platform Integration ]
WAgent_WhatsApp_Evolution_API.json
   ├── Primary Platform: WhatsApp via Evolution API Webhook
   ├── Memory: Buffer Window Memory (Context retention)
   ├── Core Toolset: Google Calendar, Gmail, SerpAPI, Wikipedia, HackerNews, Twitter/X, Sheets
   └── File Handling: File conversion & binary extraction nodes

               │
               ▼ Architectural Upgrade
               │

[ v2: Omnichannel & Multimodal Intelligence ]
WAgent_Messenger_Voice_Multiplatform.json
   ├── Platforms: WhatsApp + Facebook Messenger (Unified processing)
   ├── Multimodal: OpenAI Whisper Audio Transcription (Voice Notes → Text)
   ├── Deep Research: Perplexity AI Web Search with real-time citations
   └── Cognitive Enhancement: Silent "Think Tool" reasoning before synthesizing answers
```

---

## 📂 Workflows in this Directory

| File | Platform Support | Trigger Type | Nodes | Size | Description |
|------|------------------|--------------|-------|------|-------------|
| `WAgent_WhatsApp_Evolution_API.json` | WhatsApp (Evolution API) | Webhook | 58 | 36 KB | Dedicated WhatsApp AI assistant with comprehensive external integrations (Calendar, Mail, Social, Search). |
| `WAgent_Messenger_Voice_Multiplatform.json` | WhatsApp & Messenger | Webhook / Meta API | 55 | 33 KB | Multi-platform edition adding OpenAI Whisper voice-to-text processing, Perplexity search, and chain-of-thought deliberation. |

---

## 🛠️ Technology Stack & Integrations

| Service / Tool | Category | Role in Agent |
|----------------|----------|---------------|
| **OpenAI GPT-4** | Large Language Model | Core cognitive reasoning, intent classification, and conversational responses |
| **OpenAI Whisper** | Audio Processing | Transcribes incoming voice notes into text before feeding them to the agent |
| **Perplexity AI** | Advanced Search | Real-time deep web retrieval with cited academic & news sources |
| **SerpAPI (Google Search)** | Web Search | Live web scraping and localized search queries |
| **Wikipedia & HackerNews APIs** | Knowledge Bases | Instant encyclopedic lookup and tech industry updates |
| **Google Calendar** | Productivity Tool | Automated event creation, scheduling, schedule lookup, and conflict detection |
| **Gmail API** | Communication | Inbox reading, search by sender/subject, and composing/sending emails |
| **Twitter / X API** | Social Automation | Programmatic tweet posting and social broadcasts |
| **Google Sheets** | Data Storage | Structured tabular logging, survey tracking, and contact management |
| **Buffer Window Memory** | State Management | Retains multi-turn chat history per user ID across sessions |
| **Evolution API** | Messaging Gateway | High-reliability self-hosted WhatsApp API wrapper |

---

## 🌟 Key Features

- **🎙️ Voice Message Processing**: Users can send voice memos; the system automatically extracts the audio binary, passes it through OpenAI Whisper, and generates a context-aware reply.
- **🌐 Omnichannel Architecture**: Centralizes message handling for multiple social platforms without duplicating agent business logic.
- **🧠 Deliberative Reasoning (Think Tool)**: Employs a structured scratchpad allowing the agent to plan complex multi-step queries before producing a final answer.
- **📅 Full Personal Assistant Suite**: Users can check meetings, reply to emails, check weather or news, and post social updates directly from their chat app.
- **🔒 Contextual Continuity**: Retains user conversation state with persistent window memory to ensure coherent multi-turn interactions.
