# Advanced Hybrid RAG Pipeline (PostgreSQL + Vector Search)

This project implements an advanced Retrieval-Augmented Generation (RAG) pipeline using PostgreSQL, vector embeddings, hybrid search, and reranking. The system combines keyword-based search and semantic vector search to retrieve highly relevant documents and improve AI-generated responses.

The pipeline also integrates reranking using Cohere, allowing the system to reorder search results based on contextual relevance.

---

## Key Features

- Hybrid Search System combining keyword search and semantic vector search
- Vector database using PostgreSQL with pgvector
- OpenAI embeddings for semantic similarity search
- PostgreSQL full-text search for keyword-based retrieval
- Cohere reranking to improve result relevance
- High-performance search using GIN indexing

---

## Tech Stack

- Python  
- PostgreSQL  
- pgvector  
- OpenAI Embeddings  
- Cohere Rerank API  
- Docker  
- Pandas  

---

## System Architecture

The retrieval pipeline works in the following steps:

1. Documents are converted into vector embeddings using OpenAI.
2. Embeddings are stored in PostgreSQL using pgvector.
3. User queries are processed using:
   - Keyword Search
   - Semantic Vector Search
4. Results from both searches are combined.
5. Cohere reranking reorders results based on relevance.
6. The most relevant documents are returned.

---

## Setup

### Install dependencies

```bash
pip install -r requirements.txt
```

### Start database

```bash
docker compose up -d
```

### Insert document embeddings

```bash
python insert_vectors.py
```

### Run search

```bash
python search.py
```

---

## Dataset

This project uses the CNN/DailyMail dataset for testing the retrieval pipeline.

---

## Use Cases

- AI chatbots with document knowledge
- Semantic search engines
- Knowledge base retrieval systems
- Document question-answering systems
