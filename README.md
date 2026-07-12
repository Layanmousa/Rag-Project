# 📄 RAG PDF Question Answering System

A Retrieval-Augmented Generation (RAG) system that answers questions directly from PDF documents using semantic search and Large Language Models (LLMs).

The project extracts text from PDF files, converts the content into embeddings, stores them in a vector database, retrieves the most relevant information, and generates grounded answers based only on the retrieved context.

---

##  Features

- Load any PDF document
- Extract readable text automatically
- Split documents into semantic chunks
- Generate embeddings using Sentence Transformers
- Store embeddings in ChromaDB
- Retrieve the Top-K most relevant chunks
- Generate grounded answers using FLAN-T5
- Prevent hallucination by answering only from the retrieved context

---

##  Project Pipeline

```
PDF Document
      │
      ▼
Text Extraction
      │
      ▼
Chunking
      │
      ▼
Embeddings
      │
      ▼
ChromaDB
      │
      ▼
Semantic Retrieval
      │
      ▼
FLAN-T5
      │
      ▼
Grounded Answer
```

---

##  Technologies Used

- Python
- PyPDF
- Sentence Transformers
- ChromaDB
- Transformers
- FLAN-T5
- NumPy

---

##  Project Structure

```
RAG-PDF-Question-Answering/
│
├── data/
│   └── iso27001.pdf
│
├── chroma_db/
│
├── RAG_Project.ipynb
│
├── requirements.txt
│
├── README.md
│
└── LICENSE
```

---

##  Workflow

### 1. Load PDF

The system loads the selected PDF document.

### 2. Extract Text

Readable text is extracted from every page.

### 3. Chunking

The extracted document is divided into overlapping chunks.

- Chunk Size: 500 characters
- Chunk Overlap: 50 characters

### 4. Create Embeddings

Each chunk is converted into a semantic embedding using:

```
all-MiniLM-L6-v2
```

### 5. Store Embeddings

Embeddings are stored inside ChromaDB for efficient semantic search.

### 6. Retrieval

The user's question is converted into an embedding.

The vector database retrieves the Top-3 most relevant chunks.

### 7. Answer Generation

FLAN-T5 generates the final answer using only the retrieved context.

If the answer is unavailable, the model responds with:

> "The information is not available in the provided document."

---

##  Example

### Question

```
What is the purpose of ISO/IEC 27001?
```

### Retrieved Chunks

```
Top 3 most relevant document chunks
```

### Generated Answer

```
ISO/IEC 27001 specifies the requirements for establishing,
implementing, maintaining and continually improving an
Information Security Management System (ISMS).
```

---

##  Future Improvements

- Support multiple PDF documents
- Hybrid Search (BM25 + Vector Search)
- OCR support for scanned PDFs
- Streamlit Web Application
- Conversation Memory
- Metadata Filtering
- Support OpenAI, Gemini, and Llama models

---

##  Skills Demonstrated

- Retrieval-Augmented Generation (RAG)
- Natural Language Processing (NLP)
- Semantic Search
- Vector Databases
- Information Retrieval
- Prompt Engineering
- Large Language Models
- Python Development

---

##  Author

**Layan Mousa**


