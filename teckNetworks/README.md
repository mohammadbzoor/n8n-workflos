# 🤖 AI Recruitment Ecosystem — Dual-Sided Talent Intelligence Platform

> A comprehensive, dual-sided AI recruitment platform built on **n8n** that bridges candidates and talent acquisition teams through deterministic ATS resume evaluation, semantic vector matching, and cross-encoder re-ranking.

<div align="center">

![n8n](https://img.shields.io/badge/n8n-Dual%20Workflows-FF6D5A?style=flat-square&logo=n8n&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4o%20%7C%20Embeddings-412991?style=flat-square&logo=openai&logoColor=white)
![Pinecone](https://img.shields.io/badge/Pinecone-Vector%20Store-000000?style=flat-square&logo=pinecone&logoColor=white)
![Cohere](https://img.shields.io/badge/Cohere-Cross--Encoder%20Rerank-39594C?style=flat-square)
![Architecture](https://img.shields.io/badge/System-Candidate%20%2B%20Recruiter-22c55e?style=flat-square)

</div>

---

## 📷 System Architectural Overviews

| 👤 ATS Resume Analyzer (Candidate Side) | 🏢 AI Recruitment Engine (Recruiter Side) |
|:--------------------------------------:|:-----------------------------------------:|
| ![ATS Architecture](./ATS_Architecture.jpg) | ![Recruitment Engine Architecture](./Recruitment_Engine_Architecture.jpg) |

---

## 🌐 Platform Architecture Overview

The ecosystem operates as two complementary, decoupled workflows that synchronize talent data:

| Dimension | Workflow File | Role & Capabilities | Nodes | Size |
|-----------|---------------|---------------------|-------|------|
| 👤 **Candidate Side** | `ATS_Resume_Analyzer.json` | PDF text parsing, deterministic ATS scoring, keyword gap analysis, and interactive AI CV re-writing | 26 | 82 KB |
| 🏢 **Recruiter Side** | `AI_Recruitment_Engine.json` | Semantic talent search, dense vector generation, Pinecone index lookup, and Cohere precision re-ranking | 21 | 23 KB |

---

## 👤 Subsystem 1: ATS Resume Analyzer (Candidate Side)

### Architectural Flow

```
📄 Candidate PDF Upload
        │
        ▼
┌─────────────────────────────────────────┐
│     PDF Extraction & MIME Validation    │
└─────────────────────────────────────────┘
        │
        ▼
┌─────────────────────────────────────────┐
│     Resume Cleaning & Normalization     │
└─────────────────────────────────────────┘
        │
        ▼
┌─────────────────────────────────────────┐
│     CV Hashing & Token Preprocessing    │
└─────────────────────────────────────────┘
        │
    ┌───┴───────────────────────────────┐
    ▼                                   ▼
┌─────────────────────────┐   ┌───────────────────────────────┐
│   Deterministic ATS     │   │   AI CV Assistant (GPT-4o)    │
│   Scoring Engine        │   │                               │
│   ───────────────────── │   │   • Resume Rewriting          │
│   • Quantitative Score  │   │   • Gap Fill Recommendations  │
│   • ATS Fit Classification│ │   • Contextual Q&A            │
│   • Strengths & Weaknesses│ │   • Section-by-Section Polish │
│   • Missing Keywords    │   │   • Formatting Advice         │
└─────────────────────────┘   └───────────────────────────────┘
    │                                   │
    └─────────────────┬─────────────────┘
                      ▼
┌─────────────────────────────────────────┐
│      Structured JSON Response Body      │
└─────────────────────────────────────────┘
```

### Key Capabilities
- **Deterministic ATS Scoring**: Evaluates candidate resumes against standardized criteria producing repeatable, objective metrics.
- **Missing Keyword Detection**: Identifies critical technical proficiencies and domain keywords missing from the applicant's profile.
- **Conversational Resume Optimization**: Provides real-time guidance, section rewrite suggestions, and actionable tips to boost interview callback rates.
- **Robust Ingestion Pipeline**: Validates binary PDF uploads, strips formatting artifacts, and sanitizes input data.

### Sample ATS Analysis Output

```json
{
  "success": true,
  "userId": 139,
  "cvId": 35,
  "atsScore": 78,
  "atsLevel": "Good",
  "summary": "Backend Software Developer with 2 years of experience building scalable server-side systems.",
  "strengths": [
    "Strong technical skills across multiple programming languages",
    "Proven experience with AI workflow automation and microservices"
  ],
  "weaknesses": [
    "Lack of measurable business outcomes and quantifiable metrics in experience section",
    "Project descriptions focus on tasks rather than impact"
  ],
  "recommendations": [
    "Incorporate concrete metrics (e.g., 'reduced latency by 35%', 'handled 10k daily requests').",
    "Explicitly detail architectural decisions and technical stack per project."
  ],
  "missingKeywords": ["Docker", "CI/CD", "PostgreSQL", "Unit Testing"],
  "isAnalyzed": true
}
```

---

## 🏢 Subsystem 2: AI Recruitment Engine (Recruiter Side)

### Architectural Flow

```
🏢 Recruiter Natural Language Query (e.g., "Senior Go engineer with high-throughput Kafka experience")
        │
        ▼
┌─────────────────────────────────────────┐
│     Query Preprocessing & Intent Parse  │
└─────────────────────────────────────────┘
        │
        ▼
┌─────────────────────────────────────────┐
│     OpenAI Dense Text Embeddings        │  ──▶ Converts query into high-dimensional vector
└─────────────────────────────────────────┘
        │
    ┌───┴─────────────────────────┐
    ▼ (Candidate Indexing)        ▼ (Real-Time Search)
┌───────────────────────┐   ┌─────────────────────────────────┐
│  Pinecone Vector Store│   │  Semantic Vector Query (Top-K)  │
│  (Indexed Candidate   │   └─────────────────────────────────┘
│   Profiles)           │                 │
└───────────────────────┘                 ▼
                            ┌─────────────────────────────────┐
                            │  Cohere Cross-Encoder Reranker  │  ──▶ High-precision relevance score
                            └─────────────────────────────────┘
                                          │
                                          ▼
                            ┌─────────────────────────────────┐
                            │  GPT-4 Recruitment Intelligence │  ──▶ Candidate comparison & synthesis
                            └─────────────────────────────────┘
                                          │
                                          ▼
                            📊 Ranked Candidate Matches (JSON)
```

### Key Capabilities
- **Semantic Talent Discovery**: Recruiters search using plain English requirements; the engine matches conceptual competencies even without exact keyword overlap.
- **Two-Stage Search Pipeline**: Merges Pinecone's sub-second vector search (Stage 1) with Cohere's deep cross-encoder re-ranking (Stage 2) for maximum candidate relevance.
- **AI-Powered Synthesis**: Summarizes candidate fit against role requirements, citing specific projects and career milestones.

### Sample Recruiter Query & Output

**Recruiter Query:**
```text
Need a frontend developer skilled in React, real-time dashboards, and AI automation workflows
```

**Ranked System Response:**
```json
{
  "success": true,
  "query": "Need a frontend developer skilled in React, real-time dashboards, and AI automation workflows",
  "matches": [
    {
      "candidateId": 21,
      "name": "Candidate Profile #21",
      "matchScore": 0.94,
      "matchedSkills": ["React.js", "WebSockets", "n8n Workflow Automation", "REST APIs"],
      "reason": "Candidate demonstrates 3+ years in enterprise React development, built operational monitoring dashboards, and integrated custom AI automation nodes."
    }
  ]
}
```

---

## 🛠️ Complete Technology Stack

| Layer | Component | Purpose |
|-------|-----------|---------|
| **Orchestration** | **n8n** | Multi-node workflow automation engine connecting all APIs, parsing logic, and databases |
| **Generative AI** | **OpenAI GPT-4o / GPT-4o-mini** | In-depth resume critique, conversational editing assistance, and recruiter rationale generation |
| **Embeddings** | **OpenAI text-embedding-3-small** | Generates high-fidelity semantic vector embeddings from candidate profiles |
| **Vector Index** | **Pinecone Vector Database** | Managed vector database delivering sub-second similarity search across candidate pools |
| **Re-Ranking** | **Cohere Rerank API** | Cross-encoder model providing state-of-the-art candidate-to-query alignment |
| **Document Processing** | **PDF Extraction Nodes** | Native binary extraction, cleaning, and normalization of resume files |
| **Interface** | **REST Webhooks & JSON APIs** | Clean API interfaces designed for effortless integration with frontend dashboards |

---

## 🔄 End-to-End System Synchronization

```
[ Candidate Submits Resume ]                [ Recruiter Searches Talent Pool ]
              │                                             │
              ▼                                             ▼
     ATS_Resume_Analyzer                           AI_Recruitment_Engine
              │                                             │
              ├──▶ [ATS Score & AI Feedback]                │
              └──▶ [Generates Embedding] ──▶ [Pinecone DB] ◀── [Semantic Query]
                                                    │
                                                    ▼
                                     [Ranked Shortlist with Rationales]
```

---

## 💡 Engineering Highlights

- **Separation of Concerns**: Candidate evaluation runs independently from recruiter queries, allowing separate scaling and isolated security controls.
- **Deterministic + Non-Deterministic Blend**: Uses deterministic rules for standardized ATS metrics and generative LLMs for natural language explanations.
- **Production-Ready JSON Schemas**: Every endpoint returns predictable, strongly typed JSON designed for seamless frontend rendering.
