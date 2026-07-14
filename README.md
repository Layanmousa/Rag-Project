# RAG Question Answering System

A Retrieval-Augmented Generation (RAG) project that answers questions from PDF documents using semantic search and Large Language Models (LLMs).

The project implements a complete RAG workflow including document loading, text extraction, chunking, embedding generation, vector database indexing, semantic retrieval, and answer generation.

---

# Project Overview

This project demonstrates how Retrieval-Augmented Generation (RAG) enhances question answering by retrieving the most relevant document chunks before generating a response.

Instead of relying solely on the language model, the system retrieves relevant information from the provided document, significantly reducing hallucinations and improving answer reliability.

---

# Document Used

**ISO/IEC 27001:2022**

Information Security Management Systems (ISMS)

The document serves as the knowledge source for retrieval and question answering.

---

# Features

- PDF document loading
- Text extraction
- Text chunking
- Semantic embeddings
- ChromaDB vector database
- Semantic similarity search
- Context-aware answer generation
- Retrieval distance visualization
- Hallucination reduction

---

# Project Workflow

```
PDF Document
      │
      ▼
Text Extraction
      │
      ▼
Text Chunking
      │
      ▼
Embedding Generation
      │
      ▼
ChromaDB Vector Database
      │
      ▼
Semantic Retrieval
      │
      ▼
Context Construction
      │
      ▼
FLAN-T5
      │
      ▼
Generated Answer
```

---

# Technologies Used

- Python
- Sentence Transformers
- ChromaDB
- Transformers
- FLAN-T5
- PyTorch
- PyPDF2
- NumPy
- Pandas
- Matplotlib

---

# RAG Components

| Component | Model |
|-----------|----------------------|
| Embedding Model | all-MiniLM-L6-v2 |
| Vector Database | ChromaDB |
| Language Model | google/flan-t5-base |

---

# Chunking Strategy

The document is divided into overlapping text chunks before generating embeddings.

Current configuration:

- Chunk Size: **500 characters**
- Chunk Overlap: **16 characters**

This approach balances semantic context while improving retrieval precision.

---

# Retrieval Process

The user question is converted into an embedding vector.

The system then performs semantic similarity search inside ChromaDB to retrieve the three most relevant document chunks.

Those retrieved chunks are combined into a context prompt before being passed to the FLAN-T5 language model.

---

# Evaluation

The system was evaluated using ten different questions covering multiple scenarios.

Evaluation categories included:

- Available Information
- Detailed Questions
- Unavailable Information

The retrieval process was also evaluated using semantic distance scores for every retrieved chunk.

---

# Results

The implemented RAG pipeline successfully retrieves semantically relevant document chunks before generating responses.

The system demonstrated:

- Accurate retrieval for document-based questions.
- Context-aware answer generation.
- Reduced hallucination by grounding responses in the retrieved document.
- Ability to identify when requested information is unavailable.

The project also highlights how retrieval quality directly affects answer quality, making chunking strategy and embedding selection essential components of a successful RAG system.

---

# Skills Demonstrated

- Retrieval-Augmented Generation (RAG)
- Semantic Search
- Vector Databases
- Embedding Models
- Prompt Engineering
- Large Language Models
- Natural Language Processing
- Python Development

---

# Future Improvements

Potential enhancements include:

- Adaptive Chunking
- Semantic Chunking
- Hybrid Search (BM25 + Embeddings)
- Re-ranking Models
- OCR Integration
- Multi-document Retrieval
- Larger Open-source Language Models
- Agentic RAG

---

# Repository Structure

```text
RagProject/
│
├── RagProject.ipynb
├── README.md
├── ISO27001.pdf
├── chroma_db/
└── requirements.txt
```

---

# Author

**Layan Mousa**



GitHub:
https://github.com/Layanmousa

