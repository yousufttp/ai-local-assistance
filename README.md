# 🧠 Local AI Support Assistant (RAG-based Chatbot)

## Overview
This project is a **fully local AI chatbot** designed to assist with **IT support and troubleshooting** by answering questions based on internal documents (SOPs, KBs, runbooks).

The chatbot runs **entirely on a local machine** using open-source tools — no cloud APIs, no data leaving the system — making it suitable for **enterprise, privacy-sensitive environments**.
<img width="950" height="472" alt="image" src="https://github.com/user-attachments/assets/e906962c-0fc6-405d-8eb3-543ba939ac1a" />


---

## Problem Statement
In enterprise IT support environments:
- Knowledge is scattered across PDFs, documents, and KBs  
- Support agents waste time searching for correct procedures  
- Cloud AI tools raise **data privacy and compliance concerns**  

As a result:
- Incident resolution time increases  
- Knowledge reuse is poor  
- Support quality becomes inconsistent  

---

## Solution
A **local Retrieval-Augmented Generation (RAG) chatbot** that:
- Runs completely offline  
- Uses internal documents as a knowledge source  
- Provides grounded, context-aware answers  
- Can be extended into an AI agent for automation  

---

## Key Features
- ✅ 100% local execution (no external APIs)  
- ✅ Browser-based chat UI  
- ✅ Document-based Q&A using RAG  
- ✅ Lightweight models suitable for CPU-only systems  
- ✅ Modular and extensible architecture  

---

## Architecture
```
User (Browser)
   |
   v
Open WebUI (Chat Interface)
   |
   v
Ollama (LLM Runtime)
   |
   v
RAG Pipeline
   ├── Document Chunking
   ├── Embedding Generation
   └── Vector Search (Local Storage)
```

---

## Technology Stack
- **LLM Runtime:** Ollama  
- **Models:**  
  - `qwen2.5:0.5b` (primary – CPU friendly)  
  - `llama3.2` (optional – higher quality, slower)  
- **UI:** Open WebUI (Docker)  
- **RAG:** Open WebUI Knowledge Base  
- **OS:** Windows 11  
- **Deployment:** Local machine (Docker + Ollama)  

---

## Why This Matters
Most AI demos assume:
- Cloud access  
- GPUs  
- External APIs  

This project demonstrates:
- Practical AI under real-world constraints  
- Cost-aware and privacy-first design  
- Applicability to enterprise IT/Ops environments  

---

## Setup Instructions (Local)
### Prerequisites
- Windows 11  
- Docker Desktop  
- Ollama installed  

### Run Open WebUI
```bash
docker run -d -p 3000:8080   -e OLLAMA_BASE_URL=http://host.docker.internal:11434   -v open-webui:/app/backend/data   --name open-webui --restart always   ghcr.io/open-webui/open-webui:main
```

Open:
```
http://localhost:3000
```

---

## How RAG Works in This Project
1. Documents are uploaded into a Knowledge Base  
2. Documents are chunked and embedded locally  
3. User queries retrieve relevant chunks  
4. The LLM generates answers grounded in retrieved content  

Example queries:
- “What is the SLA for P1 incidents?”  
- “Summarize the troubleshooting steps for login failures”  

---

## Demo
*(Add screenshots here)*
- Chat interface  
- Knowledge base upload  
- Example Q&A response  

---

## What I Learned
- Trade-offs between model size and CPU performance  
- Importance of chunking strategy in RAG  
- How local-first AI can still deliver real value  
- Practical constraints of running LLMs without GPUs  

---

## Limitations
- Slower responses on CPU-only systems  
- Smaller models may produce less fluent answers  
- No automated feedback loop yet  

---

## Future Enhancements
- Integrate Qdrant as an external vector database  
- Add incident classification and clustering  
- Convert chatbot into an AI agent with tools  
- Connect with ServiceNow/Jira (mock or real APIs)  

---

## Intended Audience
- IT Support Engineers  
- AI Engineers exploring local-first systems  
- Enterprises with strict data privacy requirements  

---

## Status
🚧 **Active learning project** — continuously improving based on experiments and real-world constraints.
