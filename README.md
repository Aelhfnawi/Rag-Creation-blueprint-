🧠 RAG Backend Blueprint — FastAPI + LangChain + FAISS

This repository is a blueprint for building Retrieval-Augmented Generation (RAG) systems with ease.
It’s not just another AI backend — it’s a plug-and-play foundation showing exactly how to connect PDFs, embeddings, and chat logic into a clean, modular FastAPI architecture.

If you’ve ever wanted to create your own custom knowledge-aware chatbot that actually remembers context and talks from your data, this is your roadmap.

🚀 Highlights
🧩 Modular Design — Each layer (config, services, routes, schemas) is cleanly separated
📚 RAG Workflow Ready — Upload → Embed → Retrieve → Chat
⚙️ Built with Best Practices — Pydantic settings, service layers, structured logging
🧠 LLM-Powered Conversations — Uses Groq API with memory-aware context
💾 PDF to Vector Pipeline — Automatic embedding via FAISS and Ollama

⚙️ Setup Guide
1️⃣ Clone and Navigate
git clone https://github.com/YourUsername/rag-backend-blueprint.git
cd rag-backend/backend

2️⃣ Create a Virtual Environment
python -m venv venv
source venv/bin/activate   # Mac/Linux
venv\Scripts\activate      # Windows

3️⃣ Install Dependencies
pip install -r requirements.txt

4️⃣ Configure Environment
Create a .env file in the backend/ folder:
GROQ_API_KEY=your_groq_key
HF_TOKEN=your_huggingface_token
OLLAMA_BASE_URL=http://localhost:11434
EMBEDDING_MODEL=all-minilm
LLM_MODEL=llama3-70b

▶️ Run the Server
uvicorn main:app --reload

Access API docs here:
👉 http://127.0.0.1:8000/docs

🔍 API Overview
Endpoint	Method	Description
/health	GET	Check server, embeddings, and model status
/upload	POST	Upload a PDF and create its vectorstore
/chat	POST	Send a message and get an AI response
/sessions	GET	List all active sessions
/sessions/{id}/info	GET	Get session metadata
/sessions/{id}	DELETE	Delete a session
/sessions/{id}/clear-history	POST	Clear chat history but keep vectors

🧩 Under the Hood
Upload PDFs → split text → embed → store vectors
Ask Questions → retrieve context → send to Groq LLM
Generate Responses → contextual answers with source references
Maintain Sessions → each chat remembers its own history
This repo is built to be understandable first, powerful second.
You can extend it to multiple document types, new models, or databases with minimal refactoring.

🧠 Tech Stack

Framework: FastAPI
Language: Python 3.10+
Vector DB: FAISS
LLM API: Groq
Embeddings: Ollama
Core Tools: LangChain, Pydantic, python-dotenv

🚧 Future Add-Ons
Multi-document retrieval
Redis for caching and session memory
Streamlit / React front-end
User authentication and role management

👨‍💻 Author
Ahmed Elhfnawi
AI / ML Engineer
