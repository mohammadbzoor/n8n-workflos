# 🟣 Secretary MCP — Autonomous Executive Assistant via MCP Protocol

> An intelligent executive personal assistant accessible via **Telegram**, built upon Anthropic's open **Model Context Protocol (MCP)** standard to handle scheduling, email triage, and web research through decoupled, modular tooling.

<div align="center">

![n8n](https://img.shields.io/badge/n8n-Workflow-FF6D5A?style=flat-square&logo=n8n&logoColor=white)
![Protocol](https://img.shields.io/badge/Protocol-MCP%20Standard-6366f1?style=flat-square)
![Telegram](https://img.shields.io/badge/Telegram-Bot%20API-26A5E4?style=flat-square&logo=telegram&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4-412991?style=flat-square&logo=openai&logoColor=white)
![Google](https://img.shields.io/badge/Google-Calendar%20%26%20Gmail-4285F4?style=flat-square&logo=google&logoColor=white)

</div>

---

## 📷 System Overview

![Secretary MCP Overview](./Secretary_MCP_Overview.png)

---

## 🏗️ Architectural Flow

```
📱 Telegram Client (Incoming User Message)
        │
        ▼
┌────────────────────────────────────────────────────────┐
│   n8n Executive Assistant Core                         │
│   ┌────────────────────────────────────────────────┐   │
│   │   OpenAI GPT-4 Agent Node                      │   │
│   │   + Buffer Window Memory (Multi-turn Context)  │   │
│   └────────────────────────────────────────────────┘   │
│                           │                            │
│                 MCP Client Interface                   │
│                           │                            │
│   ┌───────────────────────┴────────────────────────┐   │
│   │              Modular MCP Tools                 │   │
│   │  ├── Google Calendar (4 tools: CRUD operations)│   │
│   │  ├── Gmail Service   (5 tools: Inbox & Send)   │   │
│   │  ├── SerpAPI         (Live Google Search)      │   │
│   │  ├── Wikipedia       (Knowledge Base)          │   │
│   │  └── HackerNews      (Tech Industry Feed)      │   │
│   └────────────────────────────────────────────────┘   │
└────────────────────────────────────────────────────────┘
        │
        ▼
📱 Telegram Client (Structured Response & Confirmation)
```

---

## 📂 Workflow Specifications

| Workflow File | Platform | Primary Purpose | Nodes | File Size |
|---------------|----------|-----------------|-------|-----------|
| `Secretary_MCP_Telegram.json` | Telegram Bot | Autonomous executive assistant operating via MCP protocol with calendar, email, and live research capabilities | 55 | 25 KB |

---

## 🛠️ Integrated Toolset & Technologies

| Component | Category | Details & Actions |
|-----------|----------|-------------------|
| **Model Context Protocol (MCP)** | Architecture | Standardized protocol separating tool definitions and execution from the model context |
| **OpenAI GPT-4** | Intelligence Engine | Reasons over user intent, selects appropriate MCP tool calls, and crafts natural replies |
| **Buffer Window Memory** | Memory Management | Preserves conversation context across multiple turns and topics |
| **Google Calendar Tools** | Scheduling | Create events, query agenda, update time slots, and cancel appointments |
| **Gmail Tools** | Email Management | Search threads by query, read unread messages, draft responses, and send emails |
| **SerpAPI** | Live Web Intelligence | Real-time Google search for current events, local businesses, and flight/hotel data |
| **Wikipedia & HackerNews** | Reference Data | General encyclopedic information and top tech news digest |
| **Telegram Bot API** | User Interface | Low-friction, mobile-first messaging interface with inline markdown formatting |

---

## 💡 Why the Model Context Protocol (MCP)?

```
[ Traditional Agent Architecture ]
AI Model ──▶ Hardcoded Tools inside Workflow (Rigid, tightly coupled, hard to maintain)

[ MCP Modular Architecture ]
AI Model ──▶ MCP Client ──▶ MCP Protocol Standard ──▶ Pluggable Tool Servers (Flexible, extensible, secure)
```

### Key Architectural Benefits:
1. **Separation of Concerns**: Tools run as independent service interfaces without polluting prompt templates.
2. **Effortless Extensibility**: New tools (e.g., Notion, Jira, Slack) can be connected without altering existing prompt logic.
3. **Enterprise Compliance**: Centralized control over API keys, permissions, and tool execution boundaries.

---

## 💬 Example Natural Language Interactions

| User Prompt | Executed MCP Action | Agent Response |
|-------------|---------------------|----------------|
| *"Schedule a team sync tomorrow at 3 PM for 45 minutes"* | `calendar_create_event(summary, time, duration)` | Confirms date, time, and sends a direct invite link |
| *"Do I have any unread emails from Sarah regarding the contract?"* | `gmail_search_messages("from:Sarah contract")` | Summarizes the email content and asks if a reply should be drafted |
| *"What are the top tech discussions trending today?"* | `hackernews_get_top_stories(limit=5)` | Provides a bulleted brief with article titles, scores, and links |
| *"Find top Italian restaurants in Amman that take reservations"* | `serpapi_search("Amman Italian restaurants")` | Returns top-rated options with addresses and phone numbers |
