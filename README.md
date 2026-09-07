# 🧠 RAG-based Smart Learning Assistant

> An AI-powered learning assistant that uses **Retrieval-Augmented Generation (RAG)** to help students understand and interact with their study material.

[![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)](https://www.python.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-Backend-009688?logo=fastapi)](https://fastapi.tiangolo.com/)
[![Streamlit](https://img.shields.io/badge/Streamlit-Frontend-FF4B4B?logo=streamlit)](https://streamlit.io/)
[![LangChain](https://img.shields.io/badge/LangChain-RAG-green)](https://www.langchain.com/)
[![Hugging%20Face](https://img.shields.io/badge/Hugging%20Face-Models-yellow?logo=huggingface)](https://huggingface.co/)

---

## 📌 Overview

The **RAG-based Smart Learning Assistant** is an AI application designed to make studying from educational material more interactive and efficient.

The system combines **Retrieval-Augmented Generation (RAG)** with a large language model to retrieve relevant information from learning material and use that context to generate answers.

It also provides an **AI-powered mind map generation feature**, allowing students to convert their study material into a structured visual representation of important concepts.

### Key capabilities

* 💬 Ask questions about study material using a RAG-powered chatbot
* 📄 Process educational documents
* 🔎 Retrieve relevant information from documents
* 🤖 Generate context-aware answers using an LLM
* 🗺️ Generate interactive mind maps from learning material
* 🎨 Access the application through a Streamlit interface
* ⚡ FastAPI-based backend for serving the AI functionality

---

## ✨ Features

### 💬 RAG-based Chatbot

The chatbot allows users to ask questions about their learning material.

Instead of simply asking the LLM to answer a question, the system first retrieves relevant information and then provides that information as context to the language model.

```text
User Question
      ↓
Query Processing
      ↓
Relevant Information Retrieval
      ↓
Context
      ↓
LLM
      ↓
Generated Answer
```

---

### 🗺️ AI Mind Map Generator

The application can transform educational content into an interactive mind map.

```text
Document
   ↓
Text Extraction
   ↓
Concept Identification
   ↓
Hierarchical Structure
   ↓
Graph Generation
   ↓
Interactive Mind Map
```

This can help students quickly understand the relationships between different topics and concepts.

---

### 📄 Document Processing

The project includes document-processing capabilities for extracting information from learning material.

Technologies used include:

* PyMuPDF
* PyPDF
* Tesseract OCR
* Pillow

---

## 🏗️ System Architecture

```text
                    ┌─────────────────────┐
                    │      Streamlit      │
                    │      Frontend       │
                    └──────────┬──────────┘
                               │
                               │ HTTP
                               ▼
                    ┌─────────────────────┐
                    │       FastAPI       │
                    │       Backend       │
                    └──────────┬──────────┘
                               │
                ┌──────────────┴──────────────┐
                │                             │
                ▼                             ▼
       ┌─────────────────┐          ┌─────────────────┐
       │   RAG Chatbot   │          │  Mind Map       │
       │                 │          │  Generator      │
       └────────┬────────┘          └────────┬────────┘
                │                            │
                ▼                            ▼
       ┌─────────────────┐          ┌─────────────────┐
       │ Document        │          │ Text Extraction │
       │ Retrieval       │          │ & Processing    │
       └────────┬────────┘          └────────┬────────┘
                │                            │
                ▼                            ▼
       ┌─────────────────┐          ┌─────────────────┐
       │ Vector Search   │          │ Concept         │
       │ / Embeddings    │          │ Hierarchy       │
       └────────┬────────┘          └────────┬────────┘
                │                            │
                ▼                            ▼
       ┌─────────────────┐          ┌─────────────────┐
       │   Gemma 3 4B    │          │ Interactive     │
       │    Instruct     │          │ Mind Map        │
       └─────────────────┘          └─────────────────┘
```

---

## 🛠️ Tech Stack

| Category              | Technology                 |
| --------------------- | -------------------------- |
| Language              | Python                     |
| Frontend              | Streamlit                  |
| Backend               | FastAPI                    |
| Server                | Uvicorn                    |
| LLM                   | Google Gemma 3 4B Instruct |
| Model Platform        | Hugging Face               |
| RAG Framework         | LangChain                  |
| Vector Search         | FAISS                      |
| Vector Database       | ChromaDB                   |
| Graph Visualization   | PyVis                      |
| PDF Processing        | PyMuPDF, PyPDF             |
| OCR                   | Tesseract                  |
| Image Processing      | Pillow                     |
| HTTP Client           | Requests                   |
| Workflow              | LangGraph                  |
| Environment Variables | python-dotenv              |

---

## 📁 Project Structure

```text
RAG-based-Smart-learning-assistant/
│
├── combined_backend.py
├── frontend_combined.py
├── config.py
├── demo.py
├── graph_builder.py
├── tree_generator.py
├── requirements.txt
│
├── EduThinkAI/
│   └── ...
│
├── extractor/
│   └── ...
│
├── uploads/
│   └── ...
│
└── outputs/
    └── ...
```

### Important Files

| File                   | Description                                          |
| ---------------------- | ---------------------------------------------------- |
| `combined_backend.py`  | FastAPI backend containing chatbot and mind-map APIs |
| `frontend_combined.py` | Streamlit frontend                                   |
| `config.py`            | Model and RAG configuration                          |
| `tree_generator.py`    | Generates the hierarchical structure for mind maps   |
| `graph_builder.py`     | Builds the interactive graph                         |
| `demo.py`              | Demo/testing script                                  |
| `requirements.txt`     | Project dependencies                                 |

---

## 🚀 Installation

### 1. Clone the repository

```bash
git clone https://github.com/nipunmodi/RAG-based-Smart-learning-assistant.git

cd RAG-based-Smart-learning-assistant
```

### 2. Create a virtual environment

```bash
python -m venv venv
```

Activate it:

#### Windows

```bash
venv\Scripts\activate
```

#### Linux / macOS

```bash
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

---

## 🔑 Environment Variables

Create a `.env` file in the project root:

```env
HF_TOKEN=your_huggingface_token
```

The Hugging Face token is used to access the configured language model.

> ⚠️ Never commit your `.env` file or API keys to GitHub.

Add this to `.gitignore`:

```gitignore
.env
venv/
__pycache__/
*.pyc
```

---

## ▶️ Running the Application

### Start the FastAPI Backend

```bash
uvicorn combined_backend:app --reload
```

The backend will be available at:

```text
http://localhost:8000
```

You can check the API using:

```text
http://localhost:8000/
```

Health check:

```text
http://localhost:8000/health
```

---

### Start the Streamlit Frontend

Open another terminal and run:

```bash
streamlit run frontend_combined.py
```

Streamlit will provide a local URL in the terminal.

---

## 🔌 API Endpoints

### Root

```http
GET /
```

Checks whether the API is running.

---

### Health Check

```http
GET /health
```

Returns the current backend status.

---

### Chatbot

```http
POST /chatbot/chat
```

Accepts:

* User query
* Optional image

Example:

```text
What is deadlock in operating systems?
```

The system retrieves relevant information and generates an answer using the configured LLM.

---

### Mind Map Generation

```http
POST /mindmap/generate
```

Accepts an uploaded document and generates an interactive mind map.

---

## 🧠 RAG Pipeline

The core chatbot workflow is:

```text
                User Query
                    │
                    ▼
             Query Processing
                    │
                    ▼
          Document / Vector Search
                    │
                    ▼
          Relevant Context Chunks
                    │
                    ▼
             Prompt + Context
                    │
                    ▼
             Gemma 3 4B
                    │
                    ▼
              Final Answer
```

The configured RAG parameters include:

```text
Model:          google/gemma-3-4b-it
Chunk Size:     4000
Chunk Overlap:  200
Max Chunks:     15
```

---

## 🗺️ Mind Map Generation

The mind-map workflow is:

```text
             Learning Material
                    │
                    ▼
              Text Extraction
                    │
                    ▼
           Concept Identification
                    │
                    ▼
          Hierarchical Tree
                    │
                    ▼
             Graph Builder
                    │
                    ▼
          Interactive Mind Map
```

For example, learning material about Operating Systems could be organized as:

```text
Operating Systems
│
├── Process Management
│   ├── Process States
│   ├── Scheduling
│   └── Context Switching
│
├── Memory Management
│   ├── Paging
│   ├── Segmentation
│   └── Virtual Memory
│
└── Deadlocks
    ├── Mutual Exclusion
    ├── Hold and Wait
    ├── No Preemption
    └── Circular Wait
```

---

## 🎯 Why RAG?

A traditional LLM application can be represented as:

```text
Question → LLM → Answer
```

A RAG-based application instead follows:

```text
Question
   ↓
Retrieve Relevant Information
   ↓
Provide Retrieved Context
   ↓
LLM
   ↓
Context-Aware Answer
```

This allows the application to ground its responses in the user's learning material rather than relying solely on the model's pre-trained knowledge.

---

## 💡 Example Use Case

A student uploads their **Operating Systems notes** and asks:

```text
What are the four necessary conditions for deadlock?
```

The system:

1. Processes the learning material.
2. Searches for relevant content.
3. Retrieves the appropriate context.
4. Passes the context to the LLM.
5. Generates an answer based on the retrieved material.

The student can then generate a mind map to visually revise the same material.

---

## 🔐 Security

Sensitive credentials should always be stored in environment variables.

For example:

```env
HF_TOKEN=your_token_here
```

Do not hard-code API keys or authentication tokens in Python files.

For production deployment, CORS should also be restricted to trusted frontend domains instead of allowing all origins.

---

## 🚧 Future Improvements

* [ ] Persistent user-specific knowledge bases
* [ ] Conversation history
* [ ] Source and page-level citations
* [ ] Support for additional document formats
* [ ] Improved OCR
* [ ] Streaming responses
* [ ] User authentication
* [ ] Personalized learning
* [ ] Quiz generation
* [ ] Flashcard generation
* [ ] Learning progress tracking
* [ ] Voice-based interaction
* [ ] Docker support
* [ ] Production-grade deployment

---

## 👨‍💻 Author

**Nipun Modi**

GitHub:
https://github.com/nipunmodi

Repository:
https://github.com/nipunmodi/RAG-based-Smart-learning-assistant

---

## ⭐ Support

If you find this project useful, consider giving the repository a ⭐.

**Built with Python, RAG, FastAPI, Streamlit, and Generative AI. 🚀**

