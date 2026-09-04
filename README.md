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

## ✨ Key Features

| Feature | Description |
| --- | --- |
| **🤖 24/7 Support** | Answers patient queries anytime with accurate, empathetic responses |
| **📅 Appointment Helper** | Reminds and schedules appointments automatically |
| **🩹 Symptom Checker** | Provides initial guidance based on symptoms |
| **💊 Medication Reminders** | Never miss a dose with smart reminders |
| **🧠 Memory** | Remembers past conversations for personalized care |
| **🌍 Multilingual** | Speaks in multiple languages for wider accessibility |

---

## 🔄 How It Works

```mermaid
flowchart TD
    A[👤 Patient Message] --> B[1. Chat Trigger]
    B --> C[2. Memory Buffer<br/>Load Past Conversations]
    C --> D[3. AI Agent<br/>+ Medical Knowledge Base]
    D --> E[4. Google Gemini 2.5 Flash]
    E --> F[5. CareBot Response]
    F --> G[6. Save to Memory]
    G --> A

    style A fill:#E0F2FE,stroke:#0284C7,color:#0C4A6E
    style B fill:#FEE2E2,stroke:#EF4444,color:#7F1D1D
    style C fill:#DCFCE7,stroke:#22C55E,color:#14532D
    style D fill:#FEF9C3,stroke:#EAB308,color:#713F12
    style E fill:#EDE9FE,stroke:#8B5CF6,color:#4C1D95
    style F fill:#FFE4E6,stroke:#F43F5E,color:#881337
    style G fill:#E0E7FF,stroke:#6366F1,color:#312E81