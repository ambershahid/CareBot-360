<div align="center">

# 🩺 CareBot 360
### *Your AI-Powered Healthcare Assistant*

<img src="https://img.shields.io/badge/n8n-Workflow-FF6B9D?style=for-the-badge&logo=n8n&logoColor=white"/>
<img src="https://img.shields.io/badge/Google-Gemini_2.5_Flash-8B5CF6?style=for-the-badge&logo=google&logoColor=white"/>
<img src="https://img.shields.io/badge/Status-Active-10B981?style=for-the-badge"/>

</div>

---

## 🌸 Overview
**CareBot 360** is an intelligent AI healthcare assistant built with **n8n** and **Google Gemini 2.5 Flash**. 
It helps patients, clinics, and caregivers with 24/7 support, appointment reminders, symptom checking, and medical guidance — all in a calm, human-like conversation.

> *"Healthcare made simple, accessible, and compassionate."*

---
## 🎥 Demo Video

https://www.linkedin.com/posts/amber-shahid-684874350_ai-healthtech-artificialintelligence-activity-7501329305617133568-Cmw5?utm_source=share&utm_medium=member_desktop&rcm=ACoAAFexdcQB64WadUaxFz6H3bGdWAAFG0bEMLw

## ✨ Key Features

| Feature | Description |
| --- | --- |
| **🤖 24/7 Support** | Answers patient queries anytime with accurate, empathetic responses |
| **📅 Appointment Helper** | Reminds and schedules appointments automatically |
| **🩹 Symptom Checker** | Provides initial guidance based on symptoms |
| **🧠 Memory** | Remembers past conversations for personalized care |


---

## 🔄 How It Works

```mermaid
flowchart TD
    A[👤 Patient Sends Message] 
    --> B[1. Chat Trigger]
    --> C[2. Save to Window Buffer Memory]
    --> D[3. Save to Pinecone<br/>Vector Database]
    --> E[4. AI Agent + Gemini 2.5 Flash<br/>Generates Reply]
    --> F[5. Save to Google Sheet<br/>'Patient Chat History']
    --> G[6. Send Response to Patient]
    --> A

    style A fill:#E0F2FE,stroke:#0284C7,stroke-width:2px,color:#0C4A6E
    style B fill:#E0F2FE,stroke:#0284C7,stroke-width:2px,color:#0C4A6E
    style C fill:#E0F2FE,stroke:#0284C7,stroke-width:2px,color:#0C4A6E
    style D fill:#E0F2FE,stroke:#0284C7,stroke-width:2px,color:#0C4A6E
    style E fill:#DCFCE7,stroke:#16A34A,stroke-width:2px,color:#14532D
    style F fill:#DCFCE7,stroke:#16A34A,stroke-width:2px,color:#14532D
    style G fill:#DCFCE7,stroke:#16A34A,stroke-width:2px,color:#14532D