# LangGraph Streamlit RAG Chatbot & Agent

A modern, containerized, conversational AI agent built with **LangGraph**, **LangChain**, and **Streamlit**. It supports conversational memory, message streaming, multiple concurrent chat threads, persistent SQLite storage, and a dynamic Retrieval-Augmented Generation (RAG) pipeline for PDF document querying.

---

## 🚀 Features

- **📂 Dynamic PDF RAG**: Upload any PDF directly in the sidebar. The application will chunk the document, generate embeddings (`all-MiniLM-L6-v2`), store them in a local **FAISS** vector database, and call a retrieval tool dynamically to answer context-specific questions.
- **🔧 Agentic Tool Orchestration**: Powered by LangGraph's state machine, the LLM can call external tools on the fly:
  - `rag_tool`: Query context from the uploaded PDF document.
  - `DuckDuckGo Search`: Access live web information.
  - `calculator`: Perform basic math operations (`add`, `sub`, `mul`, `div`).
  - `get_stock_price`: Look up real-time stock quotes.
- **💾 Conversational Memory & Persistence**: Uses a SQLite checkpointer database (`chatbot.db`) to preserve state, allowing users to switch between past conversations without losing context.
- **💬 Streamlit UI with Token Streaming**: High-fidelity user interface featuring real-time assistant responses, sidebar thread navigation, and automatic conversation title generation based on the first user messages.
- **🐳 Docker Ready**: Configured for simple containerized execution and deployment.

---

## 📂 Project Structure

- **`streamlit_rag_frontend.py`**: The Streamlit interface featuring thread switching, PDF upload/indexing status, and assistant token streaming.
- **`langraph_rag_backend.py`**: LangGraph compilation defining state schemas, tool integrations, and SQLite persistence.
- **`Dockerfile`**: Docker configuration optimized for local container runs or cloud platforms (e.g., Hugging Face Spaces).
- **`requirements.txt`**: Complete Python package requirements frozen to match the working environment.
- **`chatbot.db`**: Local SQLite database storing conversation checkpoints.

---

## 🔧 Local Installation & Setup

### 1. Clone the Repository
```bash
git clone https://github.com/Akshat-124/chatbot.git
cd chatbot
