# Multi-Document AI Chatbot (RAG)

A Retrieval-Augmented Generation chatbot that lets you upload multiple PDFs and ask questions about them in plain English. Instead of the LLM hallucinating answers from its own training data, it actually retrieves relevant chunks from your documents first and grounds its response in that — which is the whole point of RAG.

Built this to get hands-on with a proper LLMOps pipeline rather than just calling an API and calling it a day: chunking, embeddings, vector search, and serving it through an actual interface.

## Features

- Upload and process multiple PDF documents at once
- Semantic search over document content using vector embeddings
- Context-aware Q&A — answers are grounded in the retrieved chunks, not just model memory
- Fast responses using Groq's LLM inference
- Efficient similarity search with FAISS
- Simple Streamlit interface to interact with

## Tech Stack

- Python
- LangChain
- Google Gemini Embeddings
- FAISS (vector store)
- Groq LLM
- FastAPI
- Streamlit

## Project Structure

```
LLMOPS_PROJECT/
├── multi_doc_chat/     # core RAG logic
├── notebook/            # experimentation notebooks
├── static/
├── templates/
├── test/
├── data/
├── main.py
├── requirements.txt
├── pyproject.toml
└── README.md
```

## Getting Started

Clone the repo:
```bash
git clone https://github.com/ritzzxyoo/llmops-multi-document-chatbot.git
cd llmops-multi-document-chatbot
```

Install dependencies:
```bash
pip install -r requirements.txt
```

Create a `.env` file in the root directory and add your API keys:
```env
GOOGLE_API_KEY=your_google_api_key
GROQ_API_KEY=your_groq_api_key
```

Run the app:
```bash
python main.py
```

## How it works

1. **Upload** — PDFs are parsed and split into smaller chunks
2. **Embed** — each chunk is converted into a vector using Google Gemini embeddings
3. **Store** — vectors are indexed in FAISS for fast similarity search
4. **Retrieve** — when you ask a question, the most relevant chunks are pulled from the index
5. **Generate** — Groq's LLM takes your question + the retrieved context and generates an answer grounded in the actual documents

## Use Cases

- Document Q&A for research papers or reports
- Internal knowledge assistant for teams
- Searching through large sets of PDFs without manually reading each one
- General-purpose PDF chatbot



GitHub: [@ritzzxyoo](https://github.com/ritzzxyoo)
