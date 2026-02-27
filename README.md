# 🌍 AI-Powered Climate Policy Debate Simulator

## 📌 Overview

The AI Climate Policy Debate Simulator is a multi-agent AI system that simulates a structured climate policy debate between three geopolitical entities:

- 🇺🇸 USA  
- 🇪🇺 European Union  
- 🇨🇳 China  

The system uses Retrieval-Augmented Generation (RAG) with local policy documents and runs entirely using local LLMs via Ollama, ensuring privacy, low cost, and offline capability.

---

## 🚀 Key Features

- Multi-agent AI debate orchestration
- Turn-based structured conversation
- Retrieval-Augmented Generation (RAG)
- Policy-grounded responses
- Robust stance extraction (supportive / opposed / neutral)
- AI Judge summary and winner selection
- FastAPI backend
- Interactive HTML/JavaScript frontend
- Fully local LLM execution (Ollama)
- Docker support (optional)

---

## 🏗 System Architecture

Frontend (HTML / JavaScript)
        ↓
FastAPI Backend (main.py)
        ↓
Debate Orchestrator (agents/debater.py)
        ↓
RAG Service (core/rag_service.py)
        ↓
ChromaDB Vector Store
        ↓
Policy JSON Documents
        ↓
Ollama Local LLM

---

## 🧠 How It Works

1. User enters a debate topic and number of rounds.
2. The system initializes debate state.
3. Each agent (USA → EU → China) takes turns.
4. For each turn:
   - Relevant policy chunks are retrieved using ChromaDB.
   - A structured prompt is constructed.
   - The LLM generates a persuasive response.
   - Stance is extracted and cleaned.
5. After all rounds:
   - An AI Judge analyzes the transcript.
   - A summary and winner are generated.
6. The full transcript and judge result are returned to the frontend.

---

## 🛠 Technology Stack

- Python 3.11
- FastAPI
- Ollama (Local LLM)
- ChromaDB
- Sentence Transformers
- HTML / CSS / JavaScript
- Docker (optional)

---

## 📂 Project Structure

climate-debate-simulator/
├── main.py
├── agents/
│   └── debater.py
├── core/
│   └── rag_service.py
├── data/
│   └── policies/
│       ├── usa_policy.json
│       ├── eu_policy.json
│       └── china_policy.json
├── static/
│   ├── index.html
│   └── script.js
├── tests/
│   └── test_debate.py
├── requirements.txt
├── Dockerfile
├── docker-compose.yml
└── README.md

---

## ⚙️ Setup Instructions (Local Run)

1️⃣ Install Python 3.11

Download from:
https://www.python.org/downloads/

2️⃣ Create Virtual Environment

py -3.11 -m venv venv
venv\Scripts\activate

3️⃣ Install Dependencies

pip install -r requirements.txt

4️⃣ Install Ollama

Download from:
https://ollama.com

Verify installation:

ollama --version

5️⃣ Pull Model

ollama pull tinyllama

Or for better quality:

ollama pull mistral

6️⃣ Run Application

python -m uvicorn main:app --reload

Open in browser:

http://localhost:8000

---

## 🐳 Docker Setup (Optional)

docker-compose up --build

---

## 🔌 API Endpoints

GET /health  
Returns:
{ "status": "ok" }

GET /policies/{country}  
Returns full policy JSON.

POST /debate/start  

Request:
{
  "topic": "Global carbon tax",
  "rounds": 2
}

Response:
{
  "messages": [...],
  "judge_summary": "Summary + Winner + Reason"
}

---

## 🎯 AI Judge Feature

After debate completion:
- Provides analytical summary
- Declares strongest country
- Explains reasoning

---

## 🔒 Design Principles

- Local-first AI
- Minimal cloud dependency
- Structured prompt engineering
- Controlled output format
- Clean modular architecture
- Extensible agent design

---

## 🎓 Academic Value

This project demonstrates:
- Multi-agent orchestration
- Retrieval-Augmented Generation
- Prompt engineering techniques
- LLM state management
- API design with FastAPI
- Local LLM integration
- Real-world AI system architecture

---

## 👩‍💻 Author

Patnala Kousalya

---

## 📜 License

For educational and demonstration purposes.
