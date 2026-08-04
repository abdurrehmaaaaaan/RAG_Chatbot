# RAG Chatbot

A simple Retrieval-Augmented Generation (RAG) chatbot built in a Jupyter notebook. It takes a knowledge base, chunks and embeds it, stores it in a vector database, and answers questions using only the retrieved context.

## How it works

1. Knowledge base text is written to a PDF, then extracted back as text.
2. Text is split into overlapping chunks.
3. Chunks are embedded using `sentence-transformers` (`all-MiniLM-L6-v2`).
4. Embeddings are stored in a Chroma vector database.
5. On a query, the top matching chunks are retrieved and passed as context to a Groq LLM to generate the answer.

## Requirements

- `sentence-transformers`
- `chromadb`
- `pypdf`
- `fpdf2`
- `groq`

Install with:
```bash
pip install sentence-transformers chromadb pypdf fpdf2 groq
```

## Setup

Add your Groq API key in the notebook:
```python
os.environ["GROQ_API_KEY"] = "your key here"
```

## Usage

Run all cells in order, then query the chatbot:
```python
print(rag_answer("your question here"))
```
