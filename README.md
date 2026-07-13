# 🤖 Multi-Utility AI Chatbot

An intelligent chatbot built using **LangGraph**, **LangChain**, and **OpenAI** that combines **Retrieval-Augmented Generation (RAG)** with tool-calling capabilities. The chatbot can answer questions from uploaded PDFs, search the web, perform mathematical calculations, fetch live stock prices, and maintain persistent conversation history across multiple chat sessions.

Webapp Link: https://dhiraj-langgraph-chatbot.streamlit.app/
---

## ✨ Features

- 📄 **PDF Question Answering (RAG)**
  - Upload a PDF and ask natural language questions.
  - Uses semantic search over document embeddings for accurate responses.

- 🔍 **Web Search**
  - Retrieves up-to-date information using DuckDuckGo Search.

- 📈 **Live Stock Prices**
  - Fetches the latest stock prices using the Alpha Vantage API.

- 🧮 **Calculator Tool**
  - Performs basic arithmetic operations (addition, subtraction, multiplication, division).

- 💬 **Persistent Chat Memory**
  - Stores conversation history using LangGraph's SQLite checkpointing.
  - Resume previous conversations anytime.

- 📚 **Thread-Specific Document Retrieval**
  - Each conversation maintains its own indexed PDF.
  - Multiple chats can have different documents.

- ⚡ **Real-Time Streaming Responses**
  - Streams LLM responses for a smooth user experience.
  - Displays tool execution status while processing requests.

- 🎨 **Interactive Streamlit UI**
  - Upload documents
  - Manage conversations
  - Start new chats
  - Continue previous sessions

---

## 🏗️ Architecture

```
                    User
                      │
              Streamlit Interface
                      │
              LangGraph Chat Agent
                      │
        ┌─────────────┼──────────────┐
        │             │              │
        ▼             ▼              ▼
   PDF RAG Tool   Web Search   Calculator
        │
        ▼
   FAISS Vector Store
        │
        ▼
 OpenAI Embeddings
```

---

## 🛠️ Tech Stack

| Category | Technologies |
|----------|--------------|
| Language | Python |
| Framework | LangGraph, LangChain |
| LLM | OpenAI GPT-4o Mini |
| Embeddings | OpenAI text-embedding-3-small |
| Vector Database | FAISS |
| UI | Streamlit |
| PDF Processing | PyPDFLoader |
| Memory | SQLite Checkpointer |
| Search | DuckDuckGo Search |
| External API | Alpha Vantage |

---

## 📂 Project Structure

```
.
├── backend.py          # LangGraph workflow, tools, RAG pipeline
├── frontend.py         # Streamlit UI
├── chatbot.db          # SQLite checkpoint database
├── requirements.txt
└── README.md
```

---

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/yourusername/multi-utility-chatbot.git
cd multi-utility-chatbot
```

### 2. Create a virtual environment

```bash
python -m venv myenv
```

### Windows

```bash
myenv\Scripts\activate
```

### Linux / Mac

```bash
source myenv/bin/activate
```

---

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

---

### 4. Create a `.env` file

```env
OPENAI_API_KEY=your_openai_api_key
ALPHA_VANTAGE_API_KEY=your_alpha_vantage_api_key
```

---

### 5. Run the application

```bash
streamlit run frontend.py
```

---

## 🚀 How It Works

### Step 1

Upload a PDF from the sidebar.

### Step 2

The chatbot:

- Reads the PDF
- Splits it into chunks
- Generates embeddings
- Stores them in a FAISS vector database

### Step 3

Ask questions such as:

- "Summarize this document."
- "What are the key findings?"
- "Explain Chapter 3."

The chatbot retrieves the most relevant document chunks before generating its response.

---

## 🔧 Available Tools

### 📄 PDF Retrieval Tool

Answers questions using uploaded PDFs through semantic search.

Example:

```
What does the paper say about transformers?
```

---

### 🌐 Web Search

Searches the web when current information is required.

Example:

```
Latest AI news
```

---

### 📈 Stock Price Lookup

Example:

```
What is the current stock price of AAPL?
```

---

### 🧮 Calculator

Example:

```
Calculate 145 × 28
```

---

## 💾 Conversation Memory

The chatbot stores:

- Chat history
- Thread IDs
- Conversation checkpoints

Users can switch between previous conversations without losing context.

---

## 📷 Application Features

- Upload PDFs
- Ask questions about uploaded documents
- Live response streaming
- Automatic tool execution
- Persistent conversation history
- Multiple chat sessions
- Thread-specific document indexing

---

## 🎯 Future Improvements

- Support multiple PDFs within a single conversation
- Citation-aware document responses
- OCR support for scanned PDFs
- Hybrid retrieval (BM25 + Vector Search)
- Multi-agent workflow
- Support for additional external tools
- Cloud database for persistent storage

---

## 👨‍💻 Author

**Dhiraj Agarwal**

M.Sc. Mathematics & Computing  
Indian Institute of Technology Guwahati

---

## ⭐ If you found this project useful

Consider giving the repository a **Star** ⭐
