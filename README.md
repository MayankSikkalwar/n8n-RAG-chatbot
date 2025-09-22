# 🤖 AI Chatbot with a Custom Knowledge Base (RAG)

An advanced **[n8n.io](https://n8n.io/)** workflow that implements a **Retrieval-Augmented Generation (RAG)** pipeline to create a chatbot capable of answering questions about **specific custom documents**.

---

## 🎯 The Problem  

Standard Large Language Models (LLMs) like **ChatGPT** or **Google Gemini** have vast general knowledge, but they **cannot answer questions** about your private documents (e.g., company policies, FAQs, or internal guides).  

---

## ✨ The Solution  

This project builds an **intelligent chatbot** using a **RAG pipeline**:  

- Reads and understands your **custom PDF/document**  
- Uses this private knowledge to **answer questions accurately**  
- Provides responses **based only on your documents**, avoiding hallucinations  

This transforms a **generic AI** into a **specialist** with deep knowledge of your domain.  

---

## 🚀 The RAG Architecture  

This project consists of **two automated workflows**:  

### **Phase 1: Data Ingestion (Learning Process)**  
- Watches for new documents  
- Processes them into smaller chunks  
- Stores embeddings in a **vector database**  

### **Phase 2: Chat & Retrieval (Answering Process)**  
- Receives user queries  
- Retrieves relevant knowledge from the database  
- Generates context-aware, accurate answers  

📌 **Workflow Visualization:**  

<img width="1705" height="577" alt="image" src="https://github.com/user-attachments/assets/c0056db4-bce8-4923-bf53-41a829b6e319" />


---

## ⚙️ How It Works  

### **Phase 1: Data Ingestion & Indexing**  
1. **📁 File Trigger** → Watches Google Drive for new documents  
2. **🧩 Chunking** → Splits PDFs into smaller, searchable text chunks  
3. **🧠 Embeddings** → Converts chunks into vector embeddings via **OpenAI**  
4. **📚 Storage** → Saves embeddings + text into **Pinecone Vector DB**  

### **Phase 2: Chat & Retrieval**  
1. **💬 Query Received** → User asks a question (e.g., *“What is our warranty policy?”*)  
2. **🤖 AI Agent** → Uses **Google Gemini** for reasoning  
3. **🔍 Smart Search** → Finds relevant chunks from **Pinecone**  
4. **📝 Context-Aware Answer** → Gemini responds using retrieved context only  

✅ Result → **Accurate, document-specific answers**  

---

## 🛠️ Tech Stack  

| Category         | Technology / Service |
|------------------|-----------------------|
| Automation Core  | [n8n.io](https://n8n.io/) |
| AI & LLMs        | Google Gemini (generation), OpenAI (embeddings) |
| Vector Database  | [Pinecone](https://www.pinecone.io/) |
| Data Source      | Google Drive |
| Core Concepts    | RAG (Retrieval-Augmented Generation), Vector Embeddings |

---

## ⚡ Setup Instructions  

To replicate this project:  

1. Deploy an **n8n instance** (cloud or self-hosted).  
2. Generate API keys for:  
   - **Google Gemini** (generation)  
   - **OpenAI** (embeddings)  
   - **Pinecone** (vector DB)  
3. Import the workflow JSON file from this repository into n8n.  
4. Update credentials (Google, OpenAI, Pinecone) inside workflow nodes.  
5. Upload your custom document → Start chatting with your own knowledge base.  

---

💡 With this, you can transform **any PDF or internal document** into a **smart, private AI chatbot**.  

