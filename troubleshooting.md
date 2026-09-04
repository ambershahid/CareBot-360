<div align="center">

# 🛠️ CareBot 360 - Troubleshooting Guide
### *Challenges We Faced & How We Solved Them*

<img src="https://img.shields.io/badge/Status-Solved-10B981?style=for-the-badge"/>
<img src="https://img.shields.io/badge/Lessons-Learned-F59E0B?style=for-the-badge"/>

</div>

---

## 🌸 Building CareBot 360 was not easy. 
Here are all the real challenges we faced during development and exactly how we fixed them:

---

### 1. **Running Out of API Credits** 💳
**Problem:**  
Google Gemini 2.5 Flash free credits ran out very fast during testing. We kept getting: `429 Quota Exceeded` error every few minutes.

**Solution:**  
1.  **Rate Limiting**: Added a `Wait` node in n8n. 1 request every 2 seconds
2.  **Fallback Model**: Set `gemini-1.5-flash` as a backup model

**Lesson:** Always enable billing before going to production.

---

### 2. **Too Many Requests Exceeded** 📈
**Problem:**  
The `Chat Trigger` was receiving too many requests at once. The workflow crashed with `Too Many Requests` error.

**Solution:**  
1.  **Batch Control**: Changed from processing 5 messages at once to processing 1 message at a time

**Lesson:** Even in healthcare, traffic spikes happen. Your system must be scalable.

---

### 3. **Dimension Mismatch Error** 📐
**Problem:**  
When saving patient history to `Pinecone` vector DB, we got this error:  
`Error: 768 vs 1536 dimensions do not match`

**Solution:**  
1.  **Check Model**: We were using Gemini `text-embedding-004` which has 768 dimensions
2.  **Recreate Index**: Created a new Pinecone index with `dimension: 768` and `metric: cosine`
**Lesson:** Always check the embedding model docs before creating your vector DB index.

---

### 4. **Saving Data to Google Sheets** 📊
**Problem:**  
Patient chat history was being overwritten in Google Sheets. Every new chat deleted the old row.

**Solution:**  
1.  **Use Append**: Used "Append Row" instead of "Update Row" in the Google Sheets node
2.  **Unique ID**: Generated unique ID for each patient using `{{$now}} + {{$json.email}}`
3.  **Add Timestamp**: Added date and time to every entry for tracking

**Sheet Columns:** `Time | Patient message | AI Reply`

---

### 5. **Saving Chat History to Pinecone** 🧠
**Problem:**  
Window Buffer Memory only remembers the last 10 messages. We needed long-term memory. When saving to Pinecone, metadata was getting mixed.

**Solution:**  
1.  **Create Embeddings**: Converted every user message to embeddings using Gemini
2.  **Add Metadata**: Saved this in Pinecone: `{patient meassage, time, AI reply, text}`
3.  **Smart Retrieval**: On new question, fetch top 5 similar past chats from Pinecone and add to prompt
4.  **Use Namespaces**: Created separate `namespace` for each patient so data never mixes

