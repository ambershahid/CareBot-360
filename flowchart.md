<div align="center">

# 🔄 CareBot 360 - Workflow Flowchart
### *Complete Patient Chat Processing Flow*

</div>

---

## 🌸 How CareBot 360 Works

This is the exact flow of how CareBot 360 handles every patient message to make sure nothing is forgotten:

1.  **Chat Trigger**  
    A patient sends a message through chat, WhatsApp, or website.

2.  **Save to Short-Term Memory**  
    The message is immediately saved to `Window Buffer Memory`. This keeps the last 10 messages for instant context.

3.  **Save to Pinecone Vector DB**  
    The same message is converted to embeddings and saved in `Pinecone`. This ensures the model never forgets the patient's previous messages, even after days.

4.  **AI Agent Generates Reply**  
    The AI Agent pulls data from both: Buffer Memory + Pinecone history + Medical Knowledge Base. Then it uses `Google Gemini 2.5 Flash` to generate a smart, personalized reply.

5.  **Save Full Chat to Google Sheets**  
    The entire conversation is appended to a Google Sheet named **`Patient Chat History`**. Columns: Time, patient Message, AI Reply

6.  **Send Response to Patient**  
    The final reply is sent back to the patient.

---
## 🎥 Demo Video

https://www.linkedin.com/posts/amber-shahid-684874350_ai-healthtech-artificialintelligence-activity-7501329305617133568-Cmw5?utm_source=share&utm_medium=member_desktop&rcm=ACoAAFexdcQB64WadUaxFz6H3bGdWAAFG0bEMLw

## 📊 Workflow Diagram

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

