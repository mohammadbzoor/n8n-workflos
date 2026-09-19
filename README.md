# 📁 n8n Workflows Portfolio — مجموعة مشاريع الذكاء الاصطناعي

> مجموعة منظّمة من **n8n Workflows** تغطي مجالات: السيرة الذاتية، الذكاء المالي،  
> وكلاء المحادثة، التوظيف الذكي، والإنتاجية الشخصية.

---

## هيكل المجلدات

```
n8n-workflos/
├── 01_WF_CV_System/        🔵  منصة CV كاملة (Microservices)   [10 ملف JSON]
├── 02_CvDevloper/          🟢  مساعد CV ذكي (AI Agent)         [ 1 ملف JSON]
├── 03_Alpha_Finance/       🟠  نظام الذكاء المالي              [ 5 ملفات JSON]
├── 04_WAgent_Chatbot/      🔴  وكيل WhatsApp/Messenger AI      [ 2 ملف JSON]
├── 05_CV_Matching_RAG/     🟡  نظام التوظيف الذكي (RAG)        [ 1 ملف JSON]
├── 06_Secretary_MCP/       🟠  سكرتير ذكي بـ MCP Protocol     [ 1 ملف JSON]
├── teckNetworks/           🗂️  أرشيف ملفات تجريبية             [ 2 ملف JSON]
└── README.md               📄  هذا الملف
```

---

## وصف المشاريع

### 🔵 [01_WF_CV_System](./01_WF_CV_System/README.md) — المشروع الأكبر والأكثر تطوراً
منصة متكاملة لتطوير السيرة الذاتية بمعمارية **Microservices**.  
كل وظيفة في sub-workflow مستقل (WF_00 → WF_90).  
**القناة:** Telegram | **قاعدة البيانات:** MySQL | **AI:** OpenAI GPT-4

---

### 🟢 [02_CvDevloper](./02_CvDevloper/README.md) — مساعد CV ذكي
وكيل AI يساعد في إنشاء وتحسين السيرة الذاتية عبر Chat UI.  
**التقنيات:** OpenAI GPT-4 + n8n AI Agent

---

### 🟠 [03_Alpha_Finance](./03_Alpha_Finance/README.md) — نظام الذكاء المالي
نظام AI لاستخراج وتحليل المعاملات المالية من صور ونصوص.  
**النمط:** كل workflow مستقل عبر Webhook | **AI:** OpenAI Vision + GPT-4

---

### 🔴 [04_WAgent_Chatbot](./04_WAgent_Chatbot/README.md) — وكيل المحادثة المتطور
وكيل AI متعدد المنصات (WhatsApp + Messenger) مع 12+ أداة متكاملة.  
**المميزات:** بحث + تقويم + بريد + صوت + ذاكرة محادثة

---

### 🟡 [05_CV_Matching_RAG](./05_CV_Matching_RAG/README.md) — نظام التوظيف الذكي
يطابق السير الذاتية مع الوظائف باستخدام **Vector Search** و**RAG**.  
**التقنيات:** Pinecone + OpenAI Embeddings + Cohere Reranker

---

### 🟠 [06_Secretary_MCP](./06_Secretary_MCP/README.md) — السكرتير الذكي
وكيل Telegram يستخدم **MCP Protocol** لإدارة التقويم والبريد والمهام.  
**التقنيات:** MCP + OpenAI GPT-4 + Google Calendar + Gmail

---

### 🗂️ [teckNetworks](./teckNetworks/README.md) — أرشيف تجريبي
ملفات تجريبية قديمة محتفَظ بها كمرجع تطوري.

---

## خريطة التطور الزمني

```
المرحلة 1: بداية مشروع CV
   └── 02_CvDevloper  ← النسخة الأولى البسيطة

المرحلة 2: إعادة هيكلة كاملة
   └── 01_WF_CV_System ← Microservices (WF_00 → WF_90)

المرحلة 3: توسيع — RAG & Vector Search
   └── 05_CV_Matching_RAG ← Pinecone + Cohere

المرحلة 4: وكلاء المحادثة
   └── 04_WAgent_Chatbot ← WhatsApp + Messenger

المرحلة 5: الذكاء المالي
   └── 03_Alpha_Finance ← Financial AI System

المرحلة 6: MCP Protocol
   └── 06_Secretary_MCP ← MCP-powered Secretary
```

---

## التقنيات الأكثر استخداماً

| التقنية | الاستخدام |
|---------|----------|
| **OpenAI GPT-4** | في جميع المشاريع — LLM رئيسي |
| **Telegram Bot API** | 01, 06 — قناة التواصل |
| **MySQL** | 01 — تخزين بيانات CVs |
| **Pinecone Vector DB** | 05 — البحث الدلالي |
| **OpenAI Embeddings** | 05 — تحويل نصوص لمتجهات |
| **Cohere Reranker** | 05 — إعادة ترتيب النتائج |
| **MCP Protocol** | 06 — بروتوكول أدوات الوكيل |
| **Webhook REST API** | 03 — نقطة دخول كل workflow |
| **OpenAI Whisper** | 04 — تحويل صوت لنص |
| **Evolution API** | 04 — WhatsApp API مرن |

---

## إحصائيات المستودع

| الإحصائية | القيمة |
|-----------|--------|
| إجمالي ملفات JSON | **22 ملف** |
| إجمالي الصور | **11 صورة** |
| عدد المشاريع | **6 مشاريع + أرشيف** |
| أضخم ملف | `WF_12_Generate_Optimized_CV_PDF.json` (175 KB) |

---

*آخر تحديث: سبتمبر 2026*
